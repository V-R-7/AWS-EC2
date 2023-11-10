# EC2 User Data

User data scripts are often used to automate tasks that need to be performed when an instance is launched for the first time.

In other words,User data in the context of Amazon EC2 refers to scripts or metadata that can be passed to an EC2 instance when it is launched initially. 

EC2 User Data is used to automate boot tasks such as :
* Customization: Modifying the instance to specific application or business requirements.
* Config Management like -  Installing software, updating packages, or configuring settings during instance launch.

## Execution 

It is an ==One-Time Execution== , i.e., User data scripts run only once during the instance's first boot.

## Meta Data access

Within the user data script, you can access instance metadata, such as the instance ID, availability zone, or region.

## Security Considerations

Avoid including sensitive information directly in user data, as it is visible to anyone with access to the AWS Management Console or API calls.


## Windows Instances
For Windows instances, user data scripts are typically written in PowerShell.

##  Cloud-Init

Cloud-init is the industry standard multi-distribution method for cross-platform cloud instance initialisation.

For more, kindly refer documentation : https://cloudinit.readthedocs.io/en/latest/ 

For Linux instances, you can pass two types of user data to Amazon EC2: shell scripts and cloud-init directives.
AWS supports Cloud-Init for Linux instances.

You can also pass this data into the launch wizard as plain text, as a file (this is useful for launching instances using the command line tools), or as base64-encoded text (for API calls).

Use cloud-init to configure:
* Setting a default locale
* Setting the hostname Generating
* Setting up SSH private keys

Cloud Init can be instrumented in two ways: a shell script or a YAML formatted cloud-config file. Both approaches are pretty straightforward:

```
#!/bin/sh
​sudo yum --assumeyes --security update-minimal
```

### Logs - Cloud Init
Occasionally, you may want to dig deeper into Cloud Init. 
* Maybe your user data isn’t executing how you expect or possibly taking longer than expected.
* Fortunately, Cloud Init tracks a lot of details for debugging.

The main logs are:

```
/var/log/cloud-init.log
/var/log/cloud-init-output.log
```

