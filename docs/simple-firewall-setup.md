
# Introduction: 

## Requirement: 

How to Configure a Basic Firewall Rule to allow HTTP traffic (port 80) and block all other traffic on a local machine running Ubuntu.

## UFW and its Importance in Network Security

UFW stands for **“Uncomplicated Firewall”** and is the default firewall configuration tool for **Ubuntu (Operating system)**. It provides a very quick and user-friendly method to install a firewall for **Linux** systems thereby controlling the incoming and outgoing network traffic. It allows or denies network traffic on the basis of pre-defined rules hence playing a vital role in network security by protecting the network from unauthorized access.

## Prerequisites

Ensure that the following requirements are met before configuring a Firewall Rule:

 - Ubuntu 20.04 or later
 - Terminal access with sudo privileges

## How to Setup a Simple Firewall Rule

Follow the below step-by-step guide to configure a Basic Firewall Rule to allow HTTP traffic (port 80) and block all other traffic on a local machine running Ubuntu:

### Step 1. Install UFW

1. Check if the UFW is already installed for which you can use the following command:

        ufw -- help

In most of the cases the firewall is pre-installed. The output of the above command shows the various commands associated with UFW if it’s already installed.

 ![Picture1](/images/Picture1.jpg)

2. If the firewall isn't pre-installed, you can install it using the following commands and give sudo password when prompted:

        sudo apt-get update
        
        sudo apt-get install ufw

 ![Picture2](/images/Picture2.jpg)

### Step 2. Enable UFW

The second step after the installation of the Firewall is to enable it via the following command:

        sudo ufw enable

 ![Picture3](/images)

### Step 3. Create a new inbound rule

1. To allow the incoming HTTP traffic on port 80, you will typically need to create a new rule that allows incoming TCP traffic using the following command:

        sudo ufw allow http 
    
 ![Picture4](/images/Picture3.jpg)

2. Alternatively, you can specify the port number directly via the command:

        sudo ufw allow 80/tcp

### Step 4. Deny all incoming traffic

To deny all other incoming traffic, use the following command: 

        sudo ufw default deny incoming

### Step 5. Verify the configuration

You can verify the UFW rules that are currently in place and display the status of UFW with the following command:

        sudo ufw status verbose

 ![Picture5](/images/Picture5.jpg)

## Conclusion

This basic configuration helps secure your system by only allowing the traffic you need and blocking any potential threats. With UFW, managing firewall rules is straightforward, even for those with minimal technical experience, making it a practical tool for enhancing system security.
