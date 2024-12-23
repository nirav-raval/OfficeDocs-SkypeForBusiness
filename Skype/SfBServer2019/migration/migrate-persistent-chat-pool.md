---
ms.date: 11/21/2024
title: "Migrate Persistent Chat pool"
ms.reviewer: 
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: skype-for-business-server
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: "Migrate Persistent Chat pool from Skype for Business Server 2015 to Skype for Business Server 2019."
---

# Migrate Persistent Chat pool

If you are migrating from Skype for Business Server 2015 (with Persistent Chat enabled) to Skype for Business Server 2019 and you want to migrate your Persistent Chat data, follow these steps:  

Ensure that admin has the `RTCUniversalServerAdmins` permission assigned.

1. **Export Persistent Chat data from Skype for Business Server 2015:**<br> 
Run the following cmdlet on the Skype for Business 2015 front-end server to export Persistent Chat data (categories, rooms, chats etc.):

   ```powershell
   Export-CsPersistentChatData -DBInstance "<backend-FQDN\instance-name>" -FileName "C:\PersistentChatData.zip"
   ```

2. **Import Persistent Chat data into Skype for Business Server 2019:**<br> 
Bring in the exported Persistent Chat data (zip file) from Skype for Business 2015 front-end server to Skype for Business 2019 front-end server (at C:\PersistentChatData.zip). Run the following cmdlet on the Skype for Business 2019 front-end server to import Persistent Chat data:

   ```powershell
   Import-CsPersistentChatData -DBInstance "<backend-FQDN\instance-name>" -FileName "C:\PersistentChatData.zip"
   ```

3. **Update default Persistent Chat pool URL in Skype for Business Server 2019:** 

   1. Open the Topology Builder of Skype for Business Server 2019 and right-click the site-name. 
   2. Select **Edit Properties** and go to **Persistent Chat setting**. 

      :::image type="content" source="../media/migration/right-click.png" alt-text="Screenshot of Topology builder." lightbox="../media/migration/right-click.png":::

   1. You'll notice that **Default Persistent Chat pool** has Skype for Business Server 2015 value selected in the dropdown. Change that to select Skype for Business 2019 Server pool value, and select **OK**. 
    
      :::image type="content" source="../media/migration/default-pool.png" alt-text="Screenshot of Edit Properties.":::

   1. To publish the topology, in the Topology Builder, select **Topology** and select **Publish**. 
       
      :::image type="content" source="../media/migration/topo-1.png" alt-text="Screenshot of publishing topology.":::  
    

4. **Verify duplicate categories in Skype for Business Server 2019:**
After importing the database, ensure that duplicate categories from Skype for Business Server 2015 are created in Skype for Business Server 2019. This can be checked in the Modern Admin Control Panel (MACP). 

    :::image type="content" source="../media/migration/duplicate-1.png" alt-text="Screenshot of MACP." lightbox="../media/migration/duplicate-1.png":::

5. **Move users from Skype for Business Server 2015 to Skype for Business Server 2019:** <br> 
Move users from Skype for Business Server 2015 to Skype for Business Server 2019 using the **Users** section in Modern Admin Control Panel (MACP). 

    :::image type="content" source="../media/migration/bulk-action.png" alt-text="Screenshot of MACP users." lightbox="../media/migration/bulk-action.png":::

6. **Add users as Creators:**<br> 
Add users in the imported categories as creators. This step is necessary because the import process might not include this information.

    :::image type="content" source="../media/migration/creator.png" alt-text="Screenshot of adding users as creators." lightbox="../media/migration/creator.png":::

7. **Create Persistent Chat rooms:**<br> 
You should now be able to create Persistent Chat rooms with Skype for Business 2019 users in the Skype for Business 2019 Persistent Chat pool.

Additionally, if you have multiple Skype for Business 2015 Persistent Chat server pools, you need to export every database in a similar manner. Then import into Skype for Business 2019 Server and follow the steps as given above.

## Related articles

- For more information about backing up and restoring Persistent Chat databases in Skype for Business, see [Back up and restore Persistent Chat databases in Skype for Business Server.](../../SfbServer/manage/persistent-chat/back-up-and-restore-databases.md)    
