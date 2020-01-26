---
title: "Cloud-native backup solution for workloads hosted in Azure"
collection: projects
type: "Software Engineering"
permalink: /projects/2018-07-02-project-mercury
excerpt: 'In this project, I worked on building an Azure IaaS VM extension to deliver on cloud-native, zero-infrastructure backup solution for workloads hosted in Azure (like SQL Server, SAP Hana etc.). To do this, I designed and built key infrastructural components of the extension to
support various operations like backup and recovery on any given workload. This service was released [publicly](https://azure.microsoft.com/en-us/blog/azure-backup-for-sql-server-in-azure-virtual-machines-now-generally-available/) for all customers of Azure in March 2019.'
venue: "Microsoft Corp"
date: 2018-07-02
location: "Hyderabad, India"
---

## Context
[Azure Backup](https://azure.microsoft.com/en-in/services/backup/) is the team within Microsoft Azure with the expertise for all things backup and recovery. Traditionally, before cloud computing picked up, companies hosted their servers in their data centers (on-premises), and various vendors provided centralized backup solutions. For example, [Microsoft Data Protection Manager](https://docs.microsoft.com/en-us/system-center/dpm/dpm-overview?view=sc-dpm-1801) is a backup software which runs on a secondary server and monitors all the prescribed workloads, backing them up at appropriate intervals and orchestrating the recovery of the same in case a need arises. In the last decade, as cloud computing picked up and companies began migrating their workloads to Virtual Machines (VMs) in Azure, a similar need for the backup of those VMs arose. One solution which many sought was replicating what had been working for them on-premises in the cloud, i.e., setting up a centralized VM which ran the backup software and which monitored all the remaining VMs for backup and recovery. But there are several problems with doing this. Firstly, in terms of money, it costs more to run another VM and acquiring the backup software license. Secondly, replicating what worked on-premises to the cloud is not the most optimal solution - especially, because we are not using the advantage of being in the cloud. Another ad-hoc solution that many sysadmins currently use is to use customized workload-specific scripts (like SQL server script), which creates a backup copy of the data locally and which they then manually maintain. None of these solutions is optimal or scalable.

## Solution
To address these concerns, our team worked on building a cloud-native, zero-infrastructure backup solution for workloads hosted in Azure (like SQL Server, SAP Hana, etc.). This involved building an Azure IaaS VM extension, which would be auto-installed on all newly created VMs and which would orchestrate the backup and recovery for all workloads which are either hosted on the VM or of which the VM is a part. This extension was built ground up in a generic plug-and-play fashion so that tomorrow third parties can write their plugins for this extension, giving them the capability to back up their own workload. For starters, we focused on Microsoft SQL Server and SAP Hana. 

## Technical details
The extension was designed to abstract out the backup and recovery steps for any workload through a Finite State Machine (FSM). To do this, I designed and built a generic, albeit lightweight, FSM infrastructure, which could run any given FSM on the VM. Backup and recovery are then just two of the many possible FSMs which run on the VM. To orchestrate the backup and recovery operations, the extension syncs and talks to Azure Backup services, which coordinate and convey the user actions on the Azure Portal. For example, when the user triggers a recovery operation to an alternate VM, the Azure Backup services spin up another VM onto which the extension is installed and which then copies the data from the data archive. For backup, depending on the workload and user preferences, a schedule is created on the VM, which runs the backup FSM every now and checks if a churn has occurred in the data. If so, the FSM initiates the backup and copies over the change to the data archive. 

There are several nuances to this technical design. For example, to keep the backup lightweight, a throttling needs to happen on the number of parallel backups running on the VM. Besides, workload-specific concurrency requirements need to be followed. To do this, I designed a throttling/concurrency module on top of the FSM infrastructure, which abstracted out the workload-specific requirements. 

## Other details
I was a core team member of the above team and helped to build the Azure IaaS VM extension infrastructure and the associated Azure Backup services.

## Current status
This project went [public preview](https://azure.microsoft.com/en-in/blog/why-you-should-bet-on-azure-for-your-infrastructure-needs-today-and-in-the-future/) on June 4th, 2018 and was made [publicly available](https://azure.microsoft.com/en-us/blog/azure-backup-for-sql-server-in-azure-virtual-machines-now-generally-available/) for all customers of Azure in March 2019.
