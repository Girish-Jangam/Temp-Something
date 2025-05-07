Call
Login
Partners















































































Home » KB » SysAdmin » How to Install Maven on Ubuntu

How to Install Maven on Ubuntu

By
Marko Aleksic
Published:
April 30, 2024
Topics:
maven, ubuntu
Apache Maven is an open-source project management tool primarily used to develop Java applications. It incorporates a POM (Project Object Model) approach, which stores information about projects, configurations, and dependencies in an XML file.

This tutorial explains how to install Maven on Ubuntu using the official repository or the installation file on the Maven website.

How to install Maven on Ubuntu.
Prerequisites

A system running Ubuntu.
Command-line access to the system.
A user with administrative privileges.
Scale yout IT without limits with carrier-neutral conectiviti and compliance ready data center with 24/7 support.
Install Maven on Ubuntu with APT
The apt package manager provides a straightforward way to install Maven on Ubuntu. However, the user is limited to the Maven version currently available in the repository.

Follow these steps to install Maven with APT:

1. Update the local package repository index:

sudo apt update
Copy
2. Install Maven from the official Ubuntu repository:

sudo apt install maven -y
Copy
3. Check the current Maven version to verify the installation:

mvn -version
Copy
If successful, the output shows the program version.

Check the current version of Maven to verify the installation.
Download and Install Maven's Recent Version on Ubuntu
Installing Maven by downloading the installation file from the official website is more complex than using the apt command, but it enables users to install the latest available version. Follow the steps below to install Maven manually.

Step 1: Install OpenJDK
OpenJDK is an open-source Java implementation that is a Maven dependency on Ubuntu. Proceed with the following steps to install OpenJDK on the system:

1. Update the system's package repository index:

sudo apt update
Copy
2. Install the latest OpenJDK version by running:

sudo apt install default-jdk -y
Copy
3. Verify the installation by checking the current OpenJDK version:

java -version
Copy
Verify the installation by checking the current version of OpenJDK.
Step 2: Download and Install Maven
The latest Maven version is listed in the Files section of the official website. Earlier versions are available in the Previous Releases section. Follow the procedure below to download and install Maven on an Ubuntu system:

1. Visit the Maven download page.

2. Right-click the version of Maven you want to install and copy the link.

Copying the link to the latest Maven version.
3. Download the Maven installation file to the /tmp directory using the wget command. The syntax is:

wget [link] -P /tmp
Copy
Replace [link] with the link to the Maven version you copied in the previous step.

Download the Maven installation file
4. Once the download is complete, extract the installation file to the /opt directory:

sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
Copy
5. Create a symbolic link leading to the Maven installation directory:

sudo ln -s /opt/apache-maven-[version] /opt/maven
Copy
Replace [version] with the Maven version you downloaded. For example:

sudo ln -s /opt/apache-maven-3.9.6 /opt/maven
Copy
Step 3: Set Up Environment Variables
1. Use a text editor like Nano to create and open the maven.sh script file in the /etc/profile.d/ directory:

sudo nano /etc/profile.d/maven.sh
Copy
2. Add the following lines to the maven.sh file:

export JAVA_HOME=/usr/lib/jvm/default-java
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}
Copy
Creating the maven.sh script file.
Save the file and exit.

3. Use the chmod command to make the maven.sh file executable:

sudo chmod +x /etc/profile.d/maven.sh
Copy
4. Execute the maven.sh script file with the source command to set up the new environment variables:

source /etc/profile.d/maven.sh
Copy
Step 4: Verify Maven Installation
Check the current version of Maven to verify the installation:

mvn -version
Copy
The example output below shows the 3.9.6 version of Maven installed on the system.

Check the current version of Maven to verify the installation.
Scale yout IT without limits with carrier-neutral conectiviti and compliance ready data center with 24/7 support.
Conclusion

After following this tutorial, you should have a copy of Maven installed and ready to use on your Ubuntu system. The article explained the steps for installing Maven via the official Ubuntu APT repository and the official website.

If you want to try Maven in a different environment, check out our guides on installing Maven on Debian 9 and installing Maven on Windows.

Was this article helpful?
YesNo
Contents
Install Maven on Ubuntu with APT
Download and Install Maven's Recent Version on Ubuntu
Step 1: Install OpenJDK
Step 2: Download and Install Maven
Step 3: Set Up Environment Variables
Step 4: Verify Maven Installation
Subscribe to our newsletter
SUBSCRIBE
Next you should read
What is Jenkins in CI/CD - Everything You Need To Know
DevOps and Development
What is Jenkins?
Jenkins Tutorial: Basics for Beginners
DevOps and Development SysAdmin
Jenkins Tutorial: Basics for Beginners

DevOps and Development SysAdmin
13 Best Java IDEs {With Pros and Cons}

SysAdmin
How to Install Java on Ubuntu
CONTACT US
Get a Quote
Support (1-855-330-1509)
Sales (1-877-588-5918)
Colocation
Phoenix
Ashburn
Amsterdam
Atlanta
Belgrade
Singapore
Shipping Instructions
RECENT POSTS
Python time.sleep(): How to Delay Code Execution
How to Install Docker on Windows
chmod Command in Linux: Syntax, Options, Examples
How to Use Linux shutdown Command With Examples
How to Kill a Process in Linux from Command Line?
Servers
Bare Metal Cloud
Dedicated Servers
Database Servers
Virtualization Servers
High Performance Computing (HPC) Servers
Dedicated Streaming Servers
Dedicated Game Servers
Dedicated Storage Servers
SQL Server Hosting
Dedicated Servers in Amsterdam
Cloud Servers in Europe
Big Memory Infrastructure
Buy Now
BMC portal
CLOUD SERVICES
Data Security Cloud
Managed Private Cloud
Object Storage
Solutions
Disaster Recovery
Web Hosting Reseller
SaaS Hosting
COMPLIANCE
HIPAA Ready Hosting
PCI Compliant Hosting
Privacy Center
Do not sell or share my personal information
NEEDS
Disaster Recovery Solutions
High Availability Solutions
Cloud Evaluation
INDUSTRIES
Web Hosting Providers
Legal
MSPs & VARs
Media Hosting
Online Gaming
SaaS Hosting Solutions
Ecommerce Hosting Solutions
COMPANY
About phoenixNAP
IaaS Solutions
Customer Experience
Platform
Schedule Virtual Tour
Open Source Community
Resource Library
Press
Events
Careers
Promotions
Contact Us
Legal
Privacy Policy
Terms of Use
DMCA
GDPR
Sitemap
Blog
Resources
Knowledge Base
IT Glossary
GitHub
RFP Template
© 2025 phoenixNAP | Global IT Services. All Rights Reserved.
