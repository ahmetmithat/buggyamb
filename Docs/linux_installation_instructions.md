<h1>Linux Installation Instructions</h1>

* <a href="#net-core-version">.NET Core version</a>
* <a href="#how-to-run-buggyamb">How to run BuggyAmb</a>
    * <a href="#running-buggyamb-as-a-standalone-application-no-web-server-is-needed">Running BuggyAmb as a standalone application (no web server is needed)</a>
    * <a href="#running-buggyamb-behind-a-web-server-nginx-apache)">Running BuggyAmb behind a web server (Nginx or Apache)</a>

<h2>.NET Core version</h2>

BuggyAmb is an ASP.NET Core <code>framework-dependent</code> application so it means that the correct version of ASP.NET Core runtime should be installed on your machine.

The main reason for not publishing BuggyAmb as a self-contained application is simple: the size of the package will be much higher than the framework-dependent one when it is deployed as self-contained application because the required .NET Core libraries will also be included in the deployment package. If you want to deploy BuggyAmb as a self-contained application then you can download the source code and publish like that.

Please check the release information to find out which .NET Core version is required to run that release. The initial release of BuggyAmb is an ASP.NET Core 3.1 application so you will need .NET Core 3.1 runtime or SDK. You can run the following command on a terminal to see which versions are installed on your machine:

> dotnet --info

If you don't have ASP.NET Core 3.1 runtime or SDK on your machine then you can find the installation instructions for different Linux distributions in this page: https://docs.microsoft.com/en-us/dotnet/core/install/linux

I have installed the .NET Core 3.1 SDK on Ubuntu 18.04 by following the instructions on https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu#1804 and replacing the dotnet-sdk-5.0 with dotnet-sdk-3.1:

>sudo apt-get update; \
>  sudo apt-get install -y apt-transport-https && \
>  sudo apt-get update && \
>  sudo apt-get install -y <b>dotnet-sdk-3.1</b>

And here is the <code>dotnet --info</code> output:

![Linux dotnet --info output](Images/linux_dotnet_info.png)

<h2>Downloading the BuggyAmb in Linux</h2>

Simply you can run the following <code>wget</code> command to download BuggyAmb bits on your Linux machine:

>wget https://github.com/ahmetmithat/buggyamb/releases/download/v1.0/BuggyAmbV1.0.tar.gz

Note that the command above downloads the first release of BuggyAmb and actually as of now it is the only release available :smiley:

After the BuggyAmb is downloaded you neee to extract the tar.gz file. The file should be downloaded in the current folder you are in when running the <code>wget</code> command and now you need to use <command>tar</command> to extract the file. I chose to extract the content to the <code>/var/buggyamb</code>, feel free to change it based on your preferences:

>sudo mkdir /var/buggyamb
>sudo tar -xf BuggyAmbV1.0.tar.gz -C /var/buggyamb

The <code>BuggyAmbV1.0</code> folder should be created under <code>/var/buggyamb</code>, so the BuggyAmb application files will be in <code>/var/buggyamb/BuggyAmbV1.0</code> folder:

![Linux extract files](Images/linux_extract_files.png)

