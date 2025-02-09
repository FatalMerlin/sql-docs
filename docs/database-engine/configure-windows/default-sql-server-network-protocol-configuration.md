---
title: "Default SQL Server Network Protocol Configuration | Microsoft Docs"
description: View factors that affect whether network protocols are turned on or off during SQL Server installation. See how to configure protocols after installation.
ms.custom: ""
ms.date: 01/19/2019
ms.prod: sql
ms.prod_service: high-availability
ms.reviewer: ""
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords: 
  - "protocols [SQL Server], default settings"
  - "default protocols, after install"
ms.assetid: 635ea361-a797-4971-bd05-e3415862bc5c
author: rwestMSFT
ms.author: randolphwest
---
# Default SQL Server Network Protocol Configuration
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
To enhance security, [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] disables network connectivity for some new installations. Network connectivity using TCP/IP is not disabled if you are using the Enterprise, Standard, Evaluation, or Workgroup edition, or if a previous installation of [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] is present. For all installations, shared memory protocol is enabled to allow local connections to the server. The [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Browser service might be stopped, depending on installation conditions and installation options.

Use the [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Network Configuration node of [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Configuration Manager to configure the network protocols after installation. Use the [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Services node of [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Configuration Manager to configure the [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Browser service to start automatically. For more information, see [Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md).


## Default Configuration

The following table describes the configuration after installation.

|Edition | New installation vs. previous installation is present | Shared memory | TCP/IP | Named pipes|
| -------- | -- | -- | -- | --  |  
|Enterprise | New installation | Enabled | Enabled | Disabled for network connections.|
|Standard | New installation | Enabled | Enabled | Disabled for network connections.|
|Web | New installation | Enabled | Enabled | Disabled for network connections.|
|Developer | New installation | Enabled | Disabled | Disabled for network connections.|
|Evaluation | New installation | Enabled | Enabled | Disabled for network connections.|
|SQL Server Express | New installation | Enabled | Disabled | Disabled for network connections.|
|All editions | Previous installation is present but is not being upgraded. | Same as new installation | Same as new installation | Same as new installation|
|All editions | Upgrade | Enabled | Settings from the previous installation are preserved. | Settings from the previous installation are preserved.|


>[!NOTE]
> If the instance is running on a [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] failover cluster, it listens on those ports on each IP address selected for [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] during [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] setup.
 
>[!NOTE]
> When you are installing [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] with command-prompt arguments, you can specify the protocols to enable by using the `TCPENABLED` and `NPENABLED` parameters. For more information, see [Install SQL Server from the Command Prompt](../install-windows/install-sql-server-from-the-command-prompt.md).

## Creating a Connection String

See the following topics for samples of connection strings:
* [Creating a Valid Connection String Using Shared Memory Protocol](../../tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)
* [Creating a Valid Connection String Using TCP IP](../../tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)



## [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Browser Settings

The [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Browser service can be configured to start automatically during setup. The default is to start automatically under the following conditions:

* When upgrading an installation.
* When installing side by side with another instance of [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)].
* When installing on a cluster.
* When installing a named instance of the Database Engine including all instances of [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] Express.
* When installing a named instance of Analysis Services.

## See Also

[Hardware and Software Requirements for Installing SQL Server 2016](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md)

[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md)