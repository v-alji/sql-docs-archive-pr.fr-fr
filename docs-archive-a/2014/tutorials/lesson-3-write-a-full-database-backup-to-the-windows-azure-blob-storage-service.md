---
title: 'Leçon 3 : écrire une sauvegarde de base de données complète dans le service de stockage d’objets BLOB Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694880"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="1bb9c-102">Leçon 3 : Écrire une sauvegarde de base de données complète dans le service Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="1bb9c-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="1bb9c-103">Cette leçon illustre l’utilisation de l’instruction TSQL pour effectuer une sauvegarde de base de données complète dans le service de stockage d’objets BLOB Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="1bb9c-104">Effectuer une sauvegarde de base de données complète dans le service de stockage d’objets BLOB Azure</span><span class="sxs-lookup"><span data-stu-id="1bb9c-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="1bb9c-105">Pour créer une sauvegarde de base de données complète, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1bb9c-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="1bb9c-106">Se connecter à [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb9c-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="1bb9c-107">Dans l' **Explorateur d'objets**, connectez-vous à l'instance de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1bb9c-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="1bb9c-108">Dans la barre de menus standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="1bb9c-109">Copiez et collez l'exemple suivant dans la fenêtre de requête, modifiez-le si nécessaire, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="1bb9c-110">Dans l'Explorateur d'objets, connectez-vous au stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="1bb9c-111">Recherchez le conteneur et les fichiers de sauvegarde récemment créés.</span><span class="sxs-lookup"><span data-stu-id="1bb9c-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1bb9c-112">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="1bb9c-112">Next Lesson</span></span>  
 <span data-ttu-id="1bb9c-113">[Leçon 4 : effectuer une restauration à partir d’une sauvegarde complète de base de données](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span><span class="sxs-lookup"><span data-stu-id="1bb9c-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
