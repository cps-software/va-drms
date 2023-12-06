# Backend Developer Guide
This guide outlines the steps for setting up a local environment for developing, testing, and deploying the backend component of the VA-DRMS-Prototype application using a Windows based machine. This is due to the target runtime environment being within the VA secure network, which is typically only available via a Windows 10 GFE or via Citrix Access Gateway Windows NT virtual desktop. Note that this guide also assumes the use of `gitbash` as the command line tool.

## Java Programming Language
Since this application works with Spring version 3, you'll need to install Java 17 or higher. To see if Java is already installed locally, run the following commands:  

```bash
java -version
which java
```

My preference these days is Amazon Corretto OpenJDK 17. Begin by navigating to [https://aws.amazon.com/corretto/](https://aws.amazon.com/corretto/) and selecting `Download Amazon Corretto 17`.  

Platform: Windows x64  
Download Link: zip version  
Downloaded File: amazon-corretto-17.0.9.8.1-windows-x64-jdk.zip  
Unzip and copy base folder to: ~/swtool/jdk17.0.9_8  

For now, I'm kind of cheating by using a shell script to set up my environment on demand.  

To run the script, navigate to `~/swscript` and issue command:  

```bash
source ./cpsetup.sh
```

This updates the Windows path to include the location for Java 17 and sets a couple of Java required environment variables.  

To verify that things are good, run these command:  

```bash
echo $PATH  
echo $JRE_HOME  
echo $JAVA_HOME  
```
