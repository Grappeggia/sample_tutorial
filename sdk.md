# Quickstart: Getting started with Cloud SDK #

This quickstart guides you through installing and initializing Cloud SDK
as well as running a few core `gcloud` commands to get you started.



## Installing the latest Cloud SDK version (321.0.0) ##

**Note: Googlers on gLinux machines should use the [Google-internal instructions](https://g3doc.corp.google.com/cloud/sdk/g3doc/index.md#installing-and-using-the-cloud-sdk)
instead of these instructions.**

Note: If you are behind a proxy/firewall, see the
[proxy settings](/sdk/docs/proxy-settings) page for more information on installation.

## Windows ##
1. Download the [Cloud SDK installer](https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe)

Alternatively, open a PowerShell terminal and run the following PowerShell commands.

        (New-Object Net.WebClient).DownloadFile("https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe", "$env:Temp\GoogleCloudSDKInstaller.exe")

        &  $env:Temp\GoogleCloudSDKInstaller.exe

##  ##
2. Launch the installer and follow the prompts. The installer is signed by Google LLC.

If you'd like to enable screen reader mode, select the **Turn on screen reader mode** option for a more streamlined screen reader experience. To read more about the Cloud SDK screen reader experience, refer to the [Accessibility features guide](https://cloud.google.com/sdk/docs/enabling-accessibility-features).

![image](https://cloud.google.com/sdk/docs/images/screen-reader-mode.png)

## ##
3. Cloud SDK requires Python; supported versions are 
- Python 3 (preferred, 3.5 to 3.8
- Python 2 (2.7.9 or higher)



The installer will install all necessary dependencies, including the needed Python version. 

While Cloud SDK currently uses Python 3 by default, you can use an existing Python installation if necessary by **unchecking** the option to 'Install Bundled Python'.

##  ##
4. After installation has completed, the installer presents several options:
![image](https://cloud.google.com/sdk/images/windows-installer-prompt.png)

Select:
- **Start Google Cloud SDK Shell**
- **Run 'gcloud init'**

The installer starts a terminal window and runs the [gcloud init](https://cloud.google.com/sdk/gcloud/reference/init) command.

## ##
5. The default installation does not include the App Engine extensions required to deploy an application using gcloud commands. 

These components can be installed using the [Cloud SDK component manager](https://cloud.google.com/sdk/docs/managing-components).

## Troubleshooting ##
* If the Cloud SDK fails to run after installing version 274.0.0, please refer to this [tracking bug](https://issuetracker.google.com/issues/146458519) for the latest workarounds.

* If installation is unsuccessful due to the **find** command not being recognized, ensure your `PATH` environment variable is set to include the folder containing find. Usually, this is **C:\WINDOWS\system32;**.

* If you have just uninstalled Cloud SDK, you will need to reboot your system before installing Cloud SDK again.

## Optional: Install the latest Google Cloud Client Libraries ##

You can download [Cloud Client Libraries](https://cloud.google.com/sdk/cloud-client-libraries) for supported languages.

## Initializing the Cloud SDK ##

Use the [`gcloud init`](https://cloud.google.com/sdk/gcloud/reference/init) command to perform several common Cloud SDK setup tasks. 

These include authorizing the Cloud SDK tools to access Google Cloud using your user account credentials and setting up the default configuration.

To initialize the Cloud SDK:

1.  Run the following at a command prompt:

        gcloud init

## ##
**Troubleshooting tip**: 
If you encounter an error related to the `gcloud` command not being found, run `./google-cloud-sdk/install.sh` to use the install script; it adds Cloud SDK tools to your `PATH`. 

Restart your terminal for the changes to take effect.

        Note: To prevent the command from launching a web browser, use `gcloud init --console-only` instead. 

To authorize without a web browser and non-interactively, create a service account with the appropriate scopes using the [Google Cloud Console](https://console.cloud.google.com) and use `gcloud auth activate-service-account` with the corresponding JSON key file.

## ##
2.  Accept the option to log in using your Google user account:

        To continue, you must log in. Would you like to log in (Y/n)? Y
    
3.  In your browser, log in to your Google user account when prompted and click **Allow** to grant permission to access Google Cloud resources.

## ##
4.  At the command prompt, select a Google Cloud project from the list of
those where you have **Owner**, **Editor** or **Viewer** permissions:

        Pick cloud project to use:
        [1] [my-project-1]
        [2] [my-project-2]
     
        Please enter your numeric choice:
    
## ##
If you only have one project, `gcloud init` selects it for you.

If you have access to more than 200 projects, you will be prompted to enter a project id, create a new project, or list projects.

    This account has a lot of projects! Listing them all can take a while.
     [1] Enter a project ID
     [2] Create a new project
     [3] List projects
    Please enter your numeric choice:
    

## ##
5.  If you have the Google Compute Engine API enabled, `gcloud init`
allows you to choose a default Compute Engine zone:

        Which compute zone would you like to use as project default?
        [1] [asia-east1-a]
        [2] [asia-east1-b]
        .........
        [14] Do not use default zone
        Please enter your numeric choice:
    

gcloud init` confirms that you have complete the setup steps successfully:

    gcloud has now been configured!
    You can use [gcloud config] to change more gcloud settings.

    Your active configuration is: [default]
    
## ##
6. (Optional) If you'd like a more streamlined screen reader experience, the gcloud command-line tool comes with an `accessibility/screen_reader`
property.

To enable this property, run:

   ```
   gcloud config set accessibility/screen_reader true
   ```

For more details about the accessibility features that come with the gcloud command-line tool, refer to the [Enabling accessibility features](https://cloud.google.com/sdk/docs/enabling-accessibility-features) guide.

## Running core commands ##

Run these `gcloud` commands to view information about your Cloud SDK installation:

1. To list accounts whose credentials are stored on the local system:

        gcloud auth list

`gcloud` displays a list of credentialed accounts:

        Credentialed Accounts
        ACTIVE             ACCOUNT
        *&#42;                             example-user-1@gmail.com
        example-user-2@gmail.com
    
## ##
2. To list the properties in your active Cloud SDK configuration:

        gcloud config list

`gcloud` displays the list of properties:

        [core]
        account = example-user-1@gmail.com
        disable_usage_reporting = False
        project = example-project
    
3. To view information about your Cloud SDK installation and the active
configuration:

        gcloud info

`gcloud` displays a summary of information about your Cloud SDK
installation. 
This includes information about your system, the installed components, the active user account and current project, and the properties in the active configuration.

## ##
4. To view information about `gcloud` commands and other topics from the command line:

        gcloud help

For example, to view the help for `gcloud compute instances create`:

        gcloud help compute instances create

`gcloud` displays a help topic that contains a description of the command,
a list of command flags and arguments,and examples of how to use it.

## What's next ##

* Read the [`gcloud` tool guide](https://cloud.google.com/sdk/gcloud) for an overview of the gcloud`command-line tool, intro to key concepts, command conventions, and helpful tips.
* Read the [`gcloud` reference guide](https://cloud.google.com/sdk/gcloud/reference) for detailed pages on each `gcloud` command, including descriptions, flags, and examples, that you can use to perform a variety of tasks on Google Cloud.
* Refer to the [gcloud command-line tool cheat sheet](https://cloud.google.com/sdk/docs/cheatsheet) for a list of commonly used commands and key concepts.
* Install additional components such as the App Engine emulators or   `kubectl` using the 
[Cloud SDK component manager](https://cloud.google.com/sdk/gcloud/guide/managing-components)

<walkthrough-conclusion-trophy></walkthrough-conclusion-trophy>
