---
title: Déplacer une base de données compatible FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695731"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="02c6b-102">Déplacer une base de données compatible FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="02c6b-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="02c6b-103">Cette rubrique montre comment déplacer une base de données compatible FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="02c6b-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02c6b-104">Les exemples de cette rubrique exigent la base de données Archive créée dans [Créer une base de données compatible FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="02c6b-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="02c6b-105">Pour déplacer une base de données compatible FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="02c6b-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="02c6b-106">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez sur **Nouvelle requête** pour ouvrir l’Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="02c6b-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="02c6b-107">Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02c6b-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="02c6b-108">Ce script affiche l'emplacement des fichiers de base de données physiques utilisés par la base de données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="02c6b-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="02c6b-109">Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02c6b-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="02c6b-110">Ce code met la base de données `Archive` hors connexion.</span><span class="sxs-lookup"><span data-stu-id="02c6b-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="02c6b-111">Créez le dossier `C:\moved_location`dans lequel vous allez placer les fichiers et les dossiers listés à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="02c6b-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="02c6b-112">Copiez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant dans l’Éditeur de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="02c6b-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="02c6b-113">Ce script met la base de données `Archive` en ligne.</span><span class="sxs-lookup"><span data-stu-id="02c6b-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="02c6b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02c6b-114">See Also</span></span>  
 [<span data-ttu-id="02c6b-115">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="02c6b-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
