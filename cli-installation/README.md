# Lab: Installing the CLI

## Prerequisites

If you are working on this lab as part of the Cloudify official training course, you will be receiving
the following from the instructor:

* Public and private IP's of the VM on which the CLI is going to be installed
* Private key to use in order to access that VM

Copy the private key, provided by the instructor, to the file system on the machine you're going to use
to connect to the various VM's (most likely, that would be your own machine).

**NOTE**: if you are accessing the VM's from Linux, make sure that the private key file has restrictive enough
permissions on it, to avoid being rejected by SSH (`0400` or `0600` would do):

```bash
chmod 0400 <pem_file>
```

## Process

### Install the CLI RPM package

Run the following commands to download the CLI RPM package and install it:

```bash
curl -J -O http://cloudify-release-eu.s3.amazonaws.com/cloudify/4.5.0/ga-release/cloudify-cli-4.5.0~ga.el6.x86_64.rpm
sudo yum install -y cloudify-cli-4.5.0~ga.el6.x86_64.rpm
```

### Check Cloudify's version

```bash
cfy --version
```

The output should be similar to the following:

```
Cloudify CLI 4.5.0
```

### Look at profiles

```bash
cfy profiles list
```

As this is a fresh CLI installation, there are no profiles defined. You should get the following message:

```
No profiles found. You can create a new profile by using an existing manager via the `cfy profiles use` command
```
