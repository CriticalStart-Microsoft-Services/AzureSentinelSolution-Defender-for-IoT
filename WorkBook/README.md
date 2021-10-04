# Azure Sentinel Workbook - Defender for IoT

Interactive dashboard for Defender for IoT

<br/>

<img src="./media/image1.PNG" style="width:6.5in;height:5.94514in" alt="Graphical user interface, application, table Description automatically generated" />

<img src="./media/image2.PNG" style="width:6.5in;height:4.86667in" alt="Graphical user interface, text, application Description automatically generated" />

<br/><br/>

## Table of Contents

1.  <u>Getting Started</u>

    -   <u>Prerequisites</u>

    -   <u>Installation</u>

2.  <u>Usage</u>

3.  <u>Contact</u>

<br/>

## Getting Started

Use the following steps to correctly configure Defender for IoT Workbook
in your Azure Sentinel instance.

<br/>

## Prerequisites

The workbook require you have Syslog data connector enabled and parser
installed.

-   Please refer to the data connector content here.

<br/>

## Installation

1.  Download Workbook template

2.  Use Azure PowerShell to deploy Workbook in the same resource group
    as Azure Sentinel.

> $projectName = Read-Host -Prompt "Enter the same project name"
>
> $templateFile = Read-Host -Prompt "Enter the template file path and
> file name"
>
> $resourceGroupName = "${projectName}rg"
>
> New-AzResourceGroupDeployment \`
>
> -Name DeployLocalTemplate \`
>
> -ResourceGroupName $resourceGroupName \`
>
> -TemplateFile $templateFile \`
>
> -projectName $projectName \`
>
> -verbose

<br/>

## Usage

To use the new workbook, navigate to Azure Sentinel->Workbooks->My
Workbooks

> <img src="./media/image3.PNG" style="width:4.78912in;height:4.89861in" alt="Graphical user interface, application Description automatically generated" />

<br/>

## Contact

Email: <MicrosoftTeam@criticalstart.com>

## About

What we do:</br></br>
**Managed Detection and Response (MDR) Services:*** CRITICALSTART is the only MDR provider committed to eliminating acceptable risk and leaving nothing to chance. That’s why our security experts built a system, platform & service that quickly detects every event, resolves every alert & stops breaches.
Expertise beyond MDR, through our TEAMARES red and blue teams, including class-leading security practitioners (pen testers, assessors, forensic examiners) that provide hands-on support and expertise. </br></br>
**Cybersecurity Consulting services for Microsoft:** Delivered by highly trained and certified specialists, these services including educational workshops, assessments, design and implementation of Microsoft Security solutions.

<img src="./media/image4.png" style="width:1.625in;height:0.30208in" />
