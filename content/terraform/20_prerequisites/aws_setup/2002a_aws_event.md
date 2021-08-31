---
title: "At an AWS Event"
chapter: false
weight: 7
pre: "<b>3.2.1 </b>"
---

# Using AWS Event engine

To complete this workshop, you are provided with an AWS account via the AWS Event Engine service. A 12-digit hash will be provided to you by event staff - this is your unique access code. eg:

## `e8476example`

### Create AWS Account

1. Connect to the portal by clicking the button or browsing to [https://dashboard.eventengine.run/](https://dashboard.eventengine.run/). The following screen shows up. Enter the provided hash in the text box. The button on the bottom right corner changes to **Accept Terms & Login**. Click on that button to continue.

![Event Engine](/images/event-engine-initial-screen.png)

2. Choose **AWS Console**, then **Open AWS Console**.
This account will expire at the end of the workshop and the all the resources created will be automatically deprovisioned. You will not be able to access this account after today.

![Event Engine Dashboard](/images/event-engine-dashboard.png)

3. Use a single region for the duration of this workshop. This workshop supports the following regions:

* us-west-2 (US West - Oregon)

Please select **US West (Oregon)** in the top right corner.

![Event Engine Region](/images/event-engine-region.png)

4. Install the AWS CLI

If you haven't already, install the AWS CLI following the directions here: https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html

5. Add the Credentials / CLI Snippets to your terminal or wherever you have your AWS CLI installed. For example, in Linux or MacOS:

```bash
export AWS_DEFAULT_REGION=us-west-2
export AWS_ACCESS_KEY_ID=ASIAYNGA6HGCPEXAMPLE
export AWS_SECRET_ACCESS_KEY=W7ZFRLHBbe61i1VDzjopoQoWR0QPGh3nvexample
export AWS_SESSION_TOKEN=EXAMPLEpZ2luX2VjEIz//////////wEaCXVzLWVhc3QtMSJGMEQCIFbnVWSc6OAivQNSWlfgud2UcvjXprUkRVy7JFr4sLvfAiAN1p08n2FhBSD2WlCVLnHdYAHkRNjBJAvAQHIIQx0tVCqgAgjF//////////8BEAAaDDU3ODA3NzczNTMwMCIM/QhZMGhfh6+ZsKJdKvQBCJ+7axtIjet9jrFUddi/Qa3wlqCx9tb+nCMxnoq5mNYmdp+dDV4Sfa3ucikQeuRQKQH0XKhxCAvEYngdCc2oJnDUpPf5rQ2WbwoUZwq6cR8JBlCIzyqZetHkt04Vgr5nOd+ZHmVm2aJJBJITzfw2qXUcokigcjyION4MHn7r0BTB5N2vKPcemevmGEO+BFpz23u1Pn4HHv61ezY1+8br2/YLQ2rS3/HOSPKMYtsG0FiqnRs0HBCbF5cq06OPuPO8uN6WTebdgXnE3pHhGqJzzrBYlPzzT4x1dNFKkdBF9hLgfZ+b2VcDsbidlSqkV89IhQejLzDA7bSJBjqeAdMdyt/HGxpG+2aS9GXdOZNg8kuAGzb/JQmNEagJWH+0TPBKlUGCvlFPEt6UXEB2wdbVMKjMOT53W8muycP5Nj5x5/NlEcJbjrs0ON1f2vq6WyiiAslqLbh3w5ggtCEnxwPYgS6v41rChcEwJnmIbCEAn3+Aqq+V/qq+ix5kR+Jvc0CqBbKks2tY8pU8DC32FUvnx+6NIP5HaNexample
```