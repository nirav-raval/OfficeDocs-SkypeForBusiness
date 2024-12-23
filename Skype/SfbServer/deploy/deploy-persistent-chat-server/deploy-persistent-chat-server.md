---
title: "Deploy Persistent Chat Server in Skype for Business Server"
ms.reviewer: 
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.service: skype-for-business-server
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: "Summary: Read this topic to learn how to deploy Skype for Business Server Persistent Chat Server."
---

# Deploy Persistent Chat Server in Skype for Business Server
 
**Summary:** Read this topic to learn how to deploy Skype for Business Server Persistent Chat Server.
  
To deploy Persistent Chat Server, you: 
  
- Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy
    
- Prepare your environment for deploying Persistent Chat Server components
    
- Install and configure Persistent Chat Server components for your deployment
    
Before you deploy Persistent Chat Server, you should read [Plan for Persistent Chat Server in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). The planning topics describe hardware and software requirements, possible topologies, and collocation scenarios. 
  
## Deployment checklist

You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Skype for Business Server Front End pool or one Skype for Business Standard Edition Server. The deployment checklist describes the basic steps required to deploy Persistent Chat Server and provides links for more details.
  
**Persistent Chat Server Deployment Process**

|**Task**|**Steps**|**Required roles and group memberships**|**Related topics**|
|:-----|:-----|:-----|:-----|
|**Install prerequisite hardware and software** <br/> | On hardware that meets system requirements, install the following: <br/> On the Persistent Chat Server Front End Servers: <br/><li>  An operating system that meets system requirements <br/><li>  Software prerequisites for computers running Skype for Business Server <br/>  On the server that will host the Persistent Chat Server database: <br/><li>  A supported version of SQL Server <br/><li>  If Persistent Chat Server compliance is required: <br/>  SQL Server on the server that will host the Persistent Chat Server compliance database <br/> |Any user who is a member of the local Administrators group.  <br/> |<li>[Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/><li> [Hardware and software requirements for Persistent Chat Server in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/><li> For Skype for Business Server 2015, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and for Skype for Business Server 2019, see [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) |
|**Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)** <br/> | Run Topology Builder to add a Persistent Chat Server pool to your topology: <br/><li>  Add Persistent Chat Server components to the topology <br/><li>  Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery) <br/><li> Define a new Skype for Business File Store or use an existing Skype for Business File Store for Persistent Chat Server files <br/>  <li>Associate the Skype for Business Server pool that can route requests to this Persistent Chat Server pool <br/><br>  If Persistent Chat compliance is required: <br/><li>  Add Persistent Chat Compliance Store <br/><li>  Click the Persistent Chat Server pool definition check box for enabling compliance <br/><li>  Publish the topology <br/><li>  If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server <br/> |<li>To define a topology, an account that is a member of the local Users group.  <br/><li> To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Skype for Business File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).  <br/> |<li>[Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md) <br/><li> [Add Persistent Chat Server to your Skype for Business Server topology](add-persistent-chat-server.md) <br/> |
|**Deploy Persistent Chat Server** <br/> | Run the Skype for Business Server setup on all the computers running Persistent Chat Server. The Persistent Chat Server setup is integrated into the Skype for Business Server Deployment wizard that provides the following instructions: <br/><li>  Deploy local management store <br/><li>  Install Persistent Chat services <br/><li>  Request and assign certificates <br/><li>  Run and start the services <br/> |Any user who is a member of the local Administrators group.  <br/> |[Deploy Persistent Chat Server in Skype for Business Server](deploy-persistent-chat-server.md) <br/> |
|**Create a Persistent Chat administrator** <br/> |Add users to the CsPersistentChatAdministrator security group.  <br/> |Any user who is a member of domain administrators.  <br/> |[Create a Persistent Chat administrator in Skype for Business Server](create-a-persistent-chat-administrator.md) <br/> |
|**Configure Persistent Chat Server** <br/> | Configure users: <br/>  User has to be enabled by policy to access Persistent Chat Server. By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes. <br/>  Configure settings <br/> |User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.  <br/> |[Manage Persistent Chat Server in Skype for Business Server](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

