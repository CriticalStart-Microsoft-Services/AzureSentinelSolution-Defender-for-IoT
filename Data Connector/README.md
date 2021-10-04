# **Azure Defender for IoT Data Connector Configuration**

## **Table of Contents**

1.  <u>Getting Started</u>

    -   <u>Prerequisites</u>

    -   <u>Installation</u>

2.  <u>Usage</u>

3.  <u>Contact</u>

<br/>

## **Getting Started**

Use the following steps to correctly configure Defender for IoT data
connector in your Azure Sentinel instance

This Data connector contains the following components:

1.  Configuration of Syslog Server

2.  Installing of Azure Sentinel Parser

3.  Configuration of Azure Sentinel Watchlist

<br/>

## **Prerequisites**

-   Instance of Azure Sentinel
    [Deployed](https://docs.microsoft.com/en-us/azure/sentinel/quickstart-onboard).

<br/>

## **Installation** 

<br/><br/>

  ## ***<u>Syslog Server Configuration</u>*** 

**1. Linux Syslog agent configuration**

Install and configure the Linux agent to collect your Common Event
Format (CEF) Syslog messages and forward them to Azure Sentinel.

Notice that the data from all regions will be stored in the selected
workspace

**1.1 Select or create a Linux machine**
Select or create a Linux machine that Azure Sentinel will use as the
proxy between your security solution and Azure Sentinel this machine
can be on your on-prem environment, Azure or other clouds.

**1.2 Install the CEF collector on the Linux machine**

Install the Microsoft Monitoring Agent on your Linux machine and
configure the machine to listen on the necessary port and forward
messages to your Azure Sentinel workspace. The CEF collector collects
CEF messages on port 514 TCP.

1.  Make sure that you have Python on your machine using the following
    

2.  You must have elevated permissions (sudo) on your machine.

3.  Execute the install script. The install script can be located under
    **CEF data connector** in Azure Sentinel

> <img src="./media/image1.png" style="width:4.125in;height:4.18588in" alt="Graphical user interface, text, application Description automatically generated" />

**2. Forward Common Event Format (CEF) logs to Syslog agent**

To create a new forwarding rule on a IoT sensor:

1.  Sign into the sensor.

2.  Select **Forwarding** on the side menu.

3.  Select **Create** Forwarding Rule.

> <img src="./media/image2.png" style="width:6.5in;height:0.98264in" alt="Create a Forwarding Rule icon." />

4.  Enter a name for the forwarding rule.

5.  Select **Warning and Above** option from severity level drop down.

6.  Set protocols drop down to **ALL**.

7.  Set the Engines drop down to **ALL**.

8.  Select Send To SYSLOG Server (CEF Format) for actions drop down

9.  Enter syslog host IP address and set port to 514

<img src="./media/image3.png" style="width:6.5in;height:4.42708in" alt="Graphical user interface, application, email Description automatically generated" />

10. Click Submit to create the forwarding rule

<br/><br/>

## ***<u>Installing Azure Sentinel Parser</u>***

**1. Install Log Analytics Parser**

1.  Navigate to [Parser.txt file](https://github.com/CriticalStart-Microsoft-Services/AzureSentinelSolution-Defender-for-IoT/blob/main/Parser/KQLFunction.txt)

2.  Copy parser query available

3.  Navigate to **Azure Sentinel->Logs** and paste the parser query

4.  Select **Save As Function**

5.  Provide function name as **DefenderForIoT_CL** and save

> <img src="./media/image4.png" style="width:6.49919in;height:4.61401in" alt="Graphical user interface, text, application Description automatically generated" />
>
> <img src="./media/image5.png" style="width:6.5in;height:3.64722in" alt="Graphical user interface, text Description automatically generated" />

## 

<br/><br/>

## ***<u>Configuration of Azure Sentinel Watchlist</u>***

Watchlist is only required if you want the IoT-Hub Device name to be
 included in the **DefenderForIoT_CL** table. If not need than edit the
 Function query in the previous step to remove WatchList dependency.
 Having IoT-Device name will help identify the correct IoT-Hub for
 incident response.

 <img src="./media/image6.PNG" style="width:6.17708in;height:3.19545in" alt="Graphical user interface, text, application, email Description automatically generated" />

 **1. Create CSV Upload File**

1.  Create a two column CSV file. Column names should set as below

***<u>Note:</u>*** Column name should be exactly as shown below. Use the
template provided here.

 <img src="./media/image7.png" style="width:3.39583in;height:2.95833in" alt="Graphical user interface, application, table, Excel Description automatically generated" />

2.  SrcIP Column should have IP address assigned to individual IoT
    Devices and IoTHubDevice_Name column should have the corresponding
    IoT Service Device name (e.g. Azure IoT Hub Device name)

## **2. Create a new watchlist**

1.  From the Azure portal, navigate to **Azure
    Sentinel** > **Configuration** > **Watchlist** and then select **+
     Add new**.

 <img src="./media/image8.png" style="width:6.5in;height:4.15417in" alt="new watchlist" />

2.  On the **General** page, provide the following details

        Name: **D4IoT_Watchlist**

        Description: **Used by DefenderForIoT parser Function**

        Alias: **D4IoT_Watchlist**

 <img src="./media/image9.png" style="width:5.42708in;height:4.28125in" alt="Graphical user interface, text, application, email Description automatically generated" />

3.  Select **Next: Source**.


4.  On the **Source** page, select the dataset type (currently only CSV
     is available)

    1.  Click the **Browse for files** link in the **Upload file** box
         and select the CSV file create in the previous step and
         upload.

    2.  You will see a preview of the first 50 rows of results in the
         wizard screen.

4.  In the **SearchKey** field, Select **SrcIP**

5.  Select **Next: Review and Create**.

 <img src="./media/image10.png" style="width:6.5in;height:3.99792in" alt="Graphical user interface, text, application, email Description automatically generated" />

<br/><br/>

## **Usage**

After the parser is install correctly, you can query
**DefenderForIoT_CL** table in Azure Sentinel logs.

 <img src="./media/image11.PNG" style="width:6.5in;height:3.11111in" alt="Graphical user interface, application Description automatically generated" />

<br/>

## **Contact**

Email: <MicrosoftTeam@criticalstart.com>

<br/>

## **About**

What we do:</br></br>
**Managed Detection and Response (MDR) Services:*** CRITICALSTART is the only MDR provider committed to eliminating acceptable risk and leaving nothing to chance. That’s why our security experts built a system, platform & service that quickly detects every event, resolves every alert & stops breaches.
Expertise beyond MDR, through our TEAMARES red and blue teams, including class-leading security practitioners (pen testers, assessors, forensic examiners) that provide hands-on support and expertise. </br></br>
**Cybersecurity Consulting services for Microsoft:** Delivered by highly trained and certified specialists, these services including educational workshops, assessments, design and implementation of Microsoft Security solutions.

<img src="./media/image12.png" style="width:1.625in;height:0.30208in" />
