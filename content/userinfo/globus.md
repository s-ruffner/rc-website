+++
description = ""
title = "Globus Data Transfer"
draft = false
date = "2020-01-21T15:45:12-05:00"
tags = ["data-transfer","rivanna","storage","ivy","globus","dtn","infrastructure"]
categories = ["userinfo"]
images = [""]
author = "Staff"

+++

# Globus Data Transfer</h4>

<p class="lead">Globus is a simple, reliable, and <em>fast</em> way to access and move your research data between systems. </p>

<img align="right" alt="Globus DTN" src="/images/globus-logo.png" style="max-width:35%;" />
Globus allows you to transfer data to and from systems such as:

- Laptops
- HPC clusters (Rivanna)
- Lab / departmental storage
- Tape archives
- Cloud storage
- Off-campus resources (XSEDE, National Labs)

Globus can help you share research data with colleagues and co-investigators, or to move data back and forth between a lab workstation and Rivanna or your personal computer.</p>
<p>Are your data stored at a different institution? At a supercomputing facility? All you need is your campus login.</p>

# Getting Started

{{% callout %}}
A Globus "collection" (also called an "endpoint") is any computer running the Globus Connect software. A collection can be:

<ul>
<li> Your local workstation </li>
<li> A departmental server </li>
<li> A "DTN" (Data Transfer Node) connected to Rivanna or elsewhere on the UVA campus, or </li>
<li> A server operated by another university or by a national computing center.</li>
</ul>

You must have an account on any remote server in order to connect directly to its endpoint.
{{% /callout %}}

Globus transfers data between two "collections" (or "endpoints").  You must log in to the Globus website to initiate any transfers.

1. Open a browser window to [**https://www.globus.org/**](https://www.globus.org/) and click on **Log In**.
2. Select “University of Virginia” from the drop-down list of organizations.  You may also type the name into the textbox next to the down arrow.  Click Continue.
  <img src="/images/globus-login-page.png" width="700" height="550">

3. Next to you will be directed to sign in using **UVA NetBadge**. Once logged in you will see the Transfer management page:
  <img src="/images/globus-transfer-page.png" width="700" height="450">

4. If you are transferring from an external source such as a national computing center, you may skip the creation of a personal endpoint and go to Transferring Files below.  If you wish to transfer to or from your local computer (lab or personal) you must create a collection for it.  

# Transferring Sensitive or Secure Data to Ivy

Globus is the **only** permitted data-transfer protocol for sensitive or secure data.  To transfer data to Ivy Central Storage, please see the special instructions [here](/userinfo/ivy/overview#data-transfer-in-out-of-ivy).

# Create a Personal Collection

{{% callout %}}
In order to transfer data to or from a lab or personal computer, you must 
install and configure the Globus Personal Collection application.
{{% /callout %}}

1. From the Globus home page, from the "I Want To" menu, select "Enable Globus on my system." If you are at the file manager page you can click the Globus logo in the upper left to return to the main `globus.org` page.
1a. Users can have personal Globus accounts as well as a UVA account.  If you have another Globus account you may link them.  You can also go back and do this later.
2. Click the "Get Globus Connect Personal" link.  Select your operating system in the "Install Globus Connect Personal" box on the right at this link.
  <img src="/images/globus-personal-endpoint-start.png" width="700" height="550">
3. Click the link to create a Globus Connect Personal endpoint.  Accept the terms and click Continue.
4. Decide on a name for your local endpoint. We recommend using something very descriptive, such as `mstk3-laptop` or `smith-genlab-workstation`.  Type it into the Endpoint Display Name textbox.
5. Click the "Generate Setup Key" button. A unique key for your collection will be created. Copy this key to your clipboard once it has been displayed.  Do not copy anything else to your clipboard until you have completed setting up your collection. 
  <img src="/images/globus-generate-key.png" width="700" height="550">
5. Download the [Globus Connect Personal application](https://www.globus.org/globus-connect-personal) for your laptop or workstation. 
6. Run the installer as directed.  Start the application.  When instructed to do so, paste the key from Step 5 into the indicated textbox and click "OK".
  <img src="/images/globus-paste-key.png" width="700" height="550">

On Windows and Mac OSX, the agent will run in the background on your laptop or workstation and will restart when the machine is booted. Click on the agent icon (in the tray for Windows users, in the toolbar for MacOS users) to change your preferences or to see the web console.  On Linux you must start the agent manually upon rebooting.

Your local computer is now able to serve as a Globus Collection.

# Transferring Files

{{% callout %}}
You can search for the collections to use for your transfer from the File Manager at the Globus website, then use their Web interface to initiate and monitor your transfers.
{{% /callout %}}

The official UVA managed collections are:

* `uva#main-DTN` - generally available; maps to Rivanna home directories, scratch, etc.
* `uva#ivy-DTN` - available to Ivy secure platform users, for moving files into secure storage.
** See special instructions for using the Ivy collection** [here](/userinfo/ivy/overview#data-transfer-in-out-of-ivy)

You can transfer files to or from your personal endpoint to a managed endpoint, one run either by UVA or by another institution.  You can transfer files between two managed endpoints.  You cannot transfer files from one personal endpoint to another personal endpoint.  If you wish to do this, contact Research Computing to convert at least one personal endpoint to a Globus Plus endpoint.

From the File Manager page, select an endpoint by clicking on the "Collection" link near the top of the screen ("start here, select a collection").  Start typing the name of the collection to see the options containing the string as you type.
<img src="/images/globus-collection-search.png" alt="collection-search" height="550" width="700">

Once the collection is found, click on its link.  Wait while it finds your folders.  When complete, click on "Transfer or sync to..." on the right sidebar.  If you do not remember the exact name of the second endpoint, click the magnifying glass to search.  If your second endpoint is one you have registered with Globus, you may also click Your Collections.  This will open a second pane.  Either may be the source or destination.

To transfer a file:

1. select a file or folder from your "source" pane, then
2. select the `Start > ` or ` < Start ` button at the bottom of the pane to begin the transfer into the "destination" pane.
<img src="/images/globus-transfer-start.png" alt="second-collection" height="550" width="700">

After you initiate a transfer, it will be assigned a `Task ID` that you can use to reference that specific transfer. This is a useful way of identifying transfers when checking on the status of a job or viewing your past Globus activity.

Your transfer may take several minutes or hours to complete depending upon the size of the data. Globus transfers are persistent, which means that if there is a network interruption, or one collection is turned off, the transfer will resume whenever the connection is restored.  The transfer takes place in the background, so once it is assigned an ID and you receive the notification that it has begun, you can log out from the Globus page.

The Globus Personal Connection application will show only a limited default set of paths on your computer.  If you need to use another folder, such as one on an external hard drive, as the source or destination, you will have to add it.  With the Globus Personal Collection running, click on the `g` logo in your taskbar or tray.  Mac: go to `Preferences/Access`.  Click the `+` button to add a path.  Windows: `Options/Access`, click `+` to add the path to the drive.  Navigate as usual to the location you wish to add.

<img src="/images/globus-add-path.png" alt="add-path" width="354" height="508">

## Monitoring Transfer Activity

You can check on the status of your transfer using the Task ID.

From the lefthand navigation bar of the Globus Connect manager, click on "Activity". Or visit https://app.globus.org/activity

<img alt="activity" width="354" height="508" src="/images/globus-activity-page.png">

Here you will see a list of your current and past transfer jobs.  Click on a job and you will get details and status.
<img alt="check-activity" width="354" height="508" src="https://globus-check-activity-page.png">

## Notifications

Users are notified via email for both successful and failed transfers. The email looks something like this, and provides a URL for more information:

    TASK DETAILS
    Task ID: 4460c25c-72d1-11e7-aa08-22000bf2d287
    Task Type: TRANSFER
    Status: SUCCEEDED
    Source: mst3k Lab MacBook (39e0bf8a-3037-11e7-bcae-22000b9a448b)
    Destination: uva#portable-DTN (67b9cb38-301c-11e7-bcac-22000b9a448b)
    Label: n/a
    
    https://www.globus.org/app/activity/4460c25c-72d1-11e7-aa08-22000bf2d287

# Sharing Folders

{{% callout %}}
You can share folders to either specific individuals, or to groups that you create and manage within Globus. A group must be populated with at least one user.  A shared folder must be created on a managed endpoint or on a Globus Plus endpoint; personal endpoints can receive shared folders but cannot create shares.
{{% /callout %}}

1. Open the [Globus web interface](https://www.globus.org/) and log in using UVA Netbadge.
2. From the Transfer Files interface, log in to the UVA Main-DTN endpoint as described above.  
3. Navigate in the folder structure of that collection until you find the folder you want to share. Highlight it. 
4. Next, select the Share link near the top of the files window.
  <img src="/images/globus-shared-endpoint.png" width="700" height="443" alt="create-share">
6. Globus regards shared folders as collections/endpoints, so you must create a new endpoint to share the folder.  Clicking on Share allows you to "Add a Shared Endopint." You can only create and manage shared collections for directories or files that you own and can access. Provide a Display Share Name (required) and a description (optional).
7. Click CREATE. Your new share will be created.
  <img src="/images/globus-create-share.png" alt="create-share" width="700" height="536">
8. Now click Add Permissions in the upper right. You _must_ go through this even if you do not change permissions from the default.
    - **Path** - Leave this set to `/` since it refers to the path relative to the directory you are sharing from.
    - **Share With** - Decide whether you want to share with individual users or with a group. **Please do not** set this to "All Users" or "Public". If you share with an individual user, follow the instructions below. If you choose to share with a group, you will first need to create that and add users to it by using the GROUPS tab at the top of the page.
    - **Identity/E-mail** - You can look up other Globus users by searching for a part of their name or institution. If you cannot find the individual, you should contact them to make sure they have signed into Globus at least once. Generally, users at other colleges and universities can be identified with the simple form of their email address, like `mst3k@virginia.edu` or `jdoe@mit.edu`, etc. Users who are unaffiliated with a university can still sign into Globus using Google (identified as `username@gmail.com`) or by creating a username and password in Globus (identified as `userid@globusid.org`)  
    --If you enter your collaborator's email address, it _must_ exactly match the one associated with the recipient's Globus ID. 
    - **Permissions** - You can specify whether this user has access to read or write to your share.  Keep in mind that permission to write to the folder also grants the recipient the ability to delete files within in.
9. Add a message if you wish, then click "Add Permission" whether you made any changes or not.
  <img src="/images/globus-add-permissions.png" alt="manage-permissions" height="322" width="700">
10. Since a share is a Globus collection/endpoint, to manage it see the Managing Endpoints section below.  You may delete the share to remove access, once your recipient has obtained the folder.

# Managing Endpoints

{{% callout %}}
The Globus interface makes it easy to manage and delete your endpoints.
{{% /callout %}}

You can view your collections, including your shared collections or other collections that have been shared with you, by clicking on the [Endpoints submenu](https://www.globus.org/app/endpoints) at the File Manager page.
<img src="/images/globus-endpoints-page.png" alt="endpoints" width="700" height="319">

From this page you can see endpoints

- That are shared with you
- That are shareable by you
- That are administered by you

Clicking on the name of each collection will allow you to review or modify settings.  You can modify only collections that are administered by you.  To modify or delete a collection, click the Administered By You tab, then click the endpoint you wish to manage.  You can edit its properties, open it, or delete it.
<img src="/images/globus-manage-endpoint.png" alt="manage-endpoints" width="700" height="319">

# Security

{{% callout %}}
UVA permits faculty and researchers to manage data transfer and sharing with colleagues and collaborators themselves. However, with this ability comes the responsibility to share wisely and carefully. Therefore, we ask that you follow a few basic principles when you share data using Globus:
{{% /callout %}}

1. **Grant the least permissions necessary, not the most**. If a colleague needs only to retrieve your data files, then grant read-only permissions.
2. **Grant access to specific individuals only, not to "all users" or to the public**. These settings risk your information going to people and places that you have not designated, or being used in ways you do not control.
3. **Remove shared collections as soon as they are no longer needed **. It is a good practice to revisit your endpoints page periodically to clean up and to cull unused resources.
4. **Finally, monitor and track your large file transfers**. When someone is transferring large data sets to you, or you to them, monitor their progress and keep in touch with the person or group on the other end. This helps identify any unusual behavior.

# For Advanced Users

* Globus has a [command-line interface](https://docs.globus.org/cli/).
* Globus also has an [API](https://docs.globus.org/api/transfer/) and [Python SDK](http://globus-sdk-python.readthedocs.io/en/latest/).
* For other technical details, see [**Globus Documentation**](https://docs.globus.org/how-to/).
