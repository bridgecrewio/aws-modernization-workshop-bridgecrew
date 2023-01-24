---
title: "Hack the Bank! Pt 3: ATTACK!"
chapter: false
weight: 14
pre: "<b>4 </b>"
---

In the last task, there was a custom generated JNDI/LDAP variable designed to be logged by log4j and we know that if we log in to our Bank with incorrect credentials, they will be logged.

## Step 1
What do you think the next action is?

If you get it right you'll see activity in both of your consoles.

The LDAP server will activate, offering the Exploit class via the web server and the netcat, which is silently waiting. You should see it spring to life!

Ask your proctors for a hint if you get stuck!

## Step 2
If you succeeded then your netcat has achieved what is called a "reverse shell". This is when, rather than using something like ssh to login to a remote server, something running on the remote server reaches out to a waiting utility (like netcat) and serves up a shell for our diabolical use.

If you've succeeded, try running a few based linux commands in the reverse shell to see what happens, you should find you are inside a command line shell of the banking application!

{{% notice warning %}}
Reverse shells are fragile. Do not hit ctrl-c or commands that can be interpreted by the real shell and pop you out of your reverse shell. Keep it simple, you also dont want to try tools that create a UI in the shell, such as tmux, vim or emacs. Remember this is a shell within a shell.
{{% /notice %}}


## Your Challenge
This pod may be ephemeral, lets gain more permenant access to the banks data while we are here. There is most likley a database..... Find the `POSTGRES_PASSWORD` to move onto the next step!
