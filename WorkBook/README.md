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

Add Something Here

<img src="./media/image4.png" style="width:1.625in;height:0.30208in" />
