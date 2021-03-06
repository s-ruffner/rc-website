+++
title="UVA Anywhere VPN on Linux"
description = ""
date = "2020-01-22T11:16:27-05:00"
author = "Staff"
categories = [
  "userinfo",
]
images=[""]
tags = [
  "login",
  "security",
]
draft = false

+++

<p class=lead>ITS does not support the UVA Anywhere VPN client on Linux.  These instructions may work but they are provided for user information only.  UVA RC does <em>not</em> support usage of the VPN on any platform.</p>

- - -

# Setting up the VPN

1. Install Software Prerequisites

    You must install some software using `yum`,`dnf`, or `apt-get`.  Note the slight difference in naming convention between distributions.

    - Centos/RedHat/Fedora

        These distributions need the following packages:

        - openssl
        - openconnect
        - NetworkManager-openconnect
        - NetworkManager-openconnect-gnome  

    - Ubuntu

        The packages are the same but the names are different.  Ubuntu 18.04 and up requires an additional package.

        - openssl
        - openconnect
        - network-manager-openconnect
        - network-manager-gnome
        - network-manager-openconnect-gnome

    It will be necessary for Network Manager to be able to manage the connection.

2. Obtain a Certificate

    Go to this unpublicized Web location to obtain a certificate for an [unknown device](https://cloud.securew2.com/public/82116/limited/?device=Unknown).  Fill out the form.  
<img src="/images/linux/cert-unknown-os.png" alt="personal-cert" style="max-width:30%; float:right; margin-left:2rem; margin-bottom:2rem;" />

    Your passphrase need not be related to your Netbadge password, and it _must_ be 15 characters or fewer.  The MAC address of your system is optional for UVA Anywhere.
    You will receive a file ending in `.p12`.  In this example we will assume it is named `mst3k.p12`.

    Download the Usher [certificate](https://download.its.virginia.edu/local-auth/universal/usher.cer).  This is the CA (Certificate Authority) certificate.

3. Extract Key and Certificate

    NetWork Manager may not recognize the `.p12` format.  Extract the key and certificate with the following commands:
```
openssl pkcs12 -in mst3k.p12 -nocerts -nodes -out mst3k.key
openssl pkcs12 -in mst3k.p12 -clcerts -nokeys -out mst3k.crt
```

4. Convert the CA certificate

    The `.cer` certificate is a Microsoft version of an "X509" certificate.  NetworkManager may not recognize this, but you can convert it to the standard format with
```
openssl x509 -inform DER -in usher.cer -out usher.crt
```
    This will not remove your original `usher.cer`.

5. Configure with Network Manager

    Click the network app in your tray, or go to Settings->Network.  Choose VPN and click the + to add a VPN.

    Select the Cisco Anyconnect compatible VPN option.
<img src="/images/linux/network-manager-linux.png" alt="network-manager" style="max-width:30%; float:right; margin-left:2rem; margin-bottom:2rem;" />

    Fill in the blanks for a new VPN.

<img src="/images/linux/vpn-setup-linux.png" alt="vpn-setup" style="max-width:30%; float:right; margin-left:2rem; margin-bottom:2rem;" />

Off-Grounds Rivanna users should use the ITS more-secure network. The gateway for that VPN is *moresecure-vpn-1.itc.virginia.edu*.  The UVA-Anywhere gateway can be used by students for other purposes.

Click "Add."

In the Details tab, make sure that "Make available to all users" is *not* checked.  This should be the default.

# Connecting to the VPN

<img src="/images/linux/running-uva-anywhere.png" alt="personal-cert" style="max-width:30%; float:right; margin-left:2rem; margin-bottom:2rem;" />

Start the VPN through the Network Manager, either through the applet in the tray (Ubuntu) or in the Notifications section of the taskbar (Centos/Fedora).  The state can be controlled through the right arrow.
