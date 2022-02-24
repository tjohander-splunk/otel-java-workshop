## Pre-Requisites (Or Pre-Work)

### 1. Virtual Machine Setup

The exercise and instructions below were created using an Ubuntu VM (18.04), but any compatible Ubuntu (debian) distro should work.

If you are planning to run this exercise locally, in a lab format, we recommend Multipass ([https://multipass.run/](https://multipass.run/)) or VirtualBox ([https://www.virtualbox.org/](https://www.virtualbox.org/)). While we do not cover VM creation here, there are plenty of resources available with detailed instructions on a number of websites. A VM with 2GB, 1vCPU and 15gb HD should be able to handle it.

The VM needs to have access to the the internet for both downloading installers as well as sending the telemetry to the Splunk endpoints

### 2. Splunk Observability Cloud Account

Another pre-requisite is access to the Splunk Observability Cloud. You should check with your team members and account admins in order to get credentials. In case you don't have an account and want to run a trial, you can create your account here: [https://www.splunk.com/en_us/observability/o11y-cloud-free-trial.html](https://www.splunk.com/en_us/observability/o11y-cloud-free-trial.html)

### 3. Basic Console (Shell) Knowledge
Lastly, this exercise requires basic knowledge and familiarity with using a shell console, running commands and editing configuration files (we are use vi here, you can use whatever editor you prefer). If you never tried that out, we recommend reading a bit around linux shell and commands/editors.

## Getting Started

### Virtual Machine Login
First step is to log in to your VM. In the steps here, we will use the commands for Multipass.

    multipass start my-o11y-vm
    multipass shell my-o11y-vm

Or you can ssh to the VM using your terminal app

    ssh ubuntu@<your-vm-ip>

Or if using VirtualBox with a Desktop Environment (Unity for Gnome, for example) just start the VM and open the `Terminal` app


### Install Required Packaages in the Virtual Machine

We will now run a few commands to download & install the required components:

    sudo apt update
    sudo apt install curl git maven openjdk-11-jdk


It might take a few minutes depending on your VM specs and network speed. The commands above will install components necessary for the exercise

### Login to Splunk Observability Cloud
Meanwhile, you can go ahead and login to your Splunk Observability Account.

- `https://app.signalfx.com` (us0 realm)
- `https://app.us1.signalfx.com` (us1 realm)
- `https://app.us2.signalfx.com` (us2 realm)
- `https://app.eu0.signalfx.com` (eu0 realm)

![enter image description here](https://github.com/asomensari-splunk/spring-petclinic/blob/main/src/main/resources/static/resources/images/loginpage.png?raw=true)

If you are not sure what in what realm your account resides, please contact your administrator or check your email for a login link.

After login, you should land in a page like this:

![enter image description here](https://github.com/asomensari-splunk/spring-petclinic/blob/main/src/main/resources/static/resources/images/o11y-landingpage.png?raw=true)
