---
title: 'Leçon 4 : effectuer une restauration à partir d’une sauvegarde complète de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604321"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="2eb41-102">Leçon 4 : Effectuer une restauration d’une sauvegarde de base de données complète</span><span class="sxs-lookup"><span data-stu-id="2eb41-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="2eb41-103">Cette leçon illustre l'utilisation d'une instruction TSQL pour effectuer une restauration d'une sauvegarde de base de données complète créée au cours de la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="2eb41-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="2eb41-104">Effectuer une restauration d'une sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="2eb41-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="2eb41-105">Pour restaurer une sauvegarde de base de données complète, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2eb41-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="2eb41-106">Se connecter à [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb41-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2eb41-107">Dans l' **Explorateur d'objets**, connectez-vous à l'instance de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2eb41-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="2eb41-108">Dans la barre de menus standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2eb41-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2eb41-109">Copiez et collez l'exemple suivant dans la fenêtre de requête et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2eb41-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="2eb41-110">Vérifiez l'instruction T-SQL et cliquez sur **Exécuter**</span><span class="sxs-lookup"><span data-stu-id="2eb41-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="2eb41-111">Revenir au portail des didacticiels</span><span class="sxs-lookup"><span data-stu-id="2eb41-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="2eb41-112">[Didacticiel : SQL Server la sauvegarde et la restauration dans le service de stockage d’objets BLOB Azure](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="2eb41-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
