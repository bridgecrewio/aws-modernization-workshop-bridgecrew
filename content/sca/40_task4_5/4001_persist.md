---
title: "Hack the Bank! Pt 4: PERSISTANCE!"
chapter: false
weight: 15
pre: "<b>4.1 </b>"
---

Well done on finding credentials for the log database. There is no doubt a gold mine of information in the database however, our time is running out. We need to ensure that our hacking presence can endure a reboot, detection or anything the SOC might throw at us and time is a factor.

## The Challenge - Part 4
There are many ways to ensure you can continue our hacking ways but one in particular involves first determining if our reverse shell is a server running the Java application, or is it a container running in a Kubernetes cluster. Our approach will be very different for each scenario.

### Step 1 - Am I Contained?
While there are some rather nice utilities in the open source world like amicontained, we're going to go with a much simpler route.

If we are contained then the `/proc` directory will reveal the evidence we need!

`/proc` contains a directory for every running process. If we assume that process 1 is our entrypoint for the container (the first thing run) then investigating the cgroups (part of the core anatomy of a linux container) should reveal essential clues.

Ready?

In *Terminal 1* try this out and see what you find?

`cat /proc/1/cgroup`
Do you think we are contained?

We could have made this a target but we have bigger flags to capture! This is more hacker education.

In this file and depending on the host OS and runtime, you could find evidence of a container runtime. Words like

```
docker
kubelet
containerd
cri-o
```

Are there indicators that we are in fact within a container?

### Step 2 - Am I Privileged?

One of the easiest ways to find out how much privilege or capability a container has is to see what access it has to devices. This is as straight-forward looking in the `/dev` directory.

A least privilege container will have a minimal offering. Most of the host devices will be hidden (for security reasons) from the container. Let's take a look:

`ls /dev`

Holy schnikies, that a long list isn't it?! So many devices and so little time.

### Step 3 - Access the host filesystem!

If we can access the host nodes filesystem, then we have access to all containers running on that host AND if we're smart, we can add a root SSH key for ourselves such that we can SSH directly back into that host without using our Log4shell hacking trickery. That way if they (or we later) patch the vulnerability, we will still have our backdoor in place.

First we need to see if we have access to the host filesystem. There area a few sneaky ways to determine which file in the `/dev` directory represents this device.

Try the following:

`cat /proc/cmdline`

Example output

```
BOOT_IMAGE=/boot/vmlinuz-5.4.0-1086-gcp root=UUID=bunch-of-unique-characters ro console=ttyS0
```

This might look like a bunch of gobbly goop but there is some critical details there and that is the UUID or PARTUUID of the host image! Both are important to us!

Now we can use the linux utility findfs (if you've never heard of this utility don't feel bad as it's kind of an obscure one)

Try this and see what the output is:

```
findfs UUID=bunch-of-unique-characters
```
or
```
findfs PARTUUID=shorter-bunch-of-unique-characters
```

### Step 4 - Access the Kubernetes host!

From here you're on your own!

You know the device for the host filesystem. We want you to mount the host filesystem and find the note we've buried in an SSH key in the filesystem. Think what user you'd want to log in as in future for the most powerful system access...