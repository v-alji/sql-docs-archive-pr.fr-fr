---
title: Copier des bases de données sur d’autres serveurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699768"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="1aa79-102">Copier des bases de données sur d'autres serveurs</span><span class="sxs-lookup"><span data-stu-id="1aa79-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="1aa79-103">Il est parfois utile de copier une base de données d'un ordinateur vers un autre, notamment pour des tests, la vérification de cohérence, le développement de logiciels, l'exécution de rapports, la création d'une base de données miroir ou éventuellement pour rendre la base de données disponible pour des opérations à distance.</span><span class="sxs-lookup"><span data-stu-id="1aa79-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="1aa79-104">Il existe plusieurs méthodes pour copier une base de données :</span><span class="sxs-lookup"><span data-stu-id="1aa79-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="1aa79-105">Utilisation de l'Assistant Copie de base de données</span><span class="sxs-lookup"><span data-stu-id="1aa79-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="1aa79-106">Vous pouvez utiliser l'Assistant Copie de base de données pour copier ou déplacer des bases de données entre des serveurs ou pour mettre à niveau une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="1aa79-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="1aa79-107">Pour plus d'informations, consultez [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1aa79-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="1aa79-108">Restauration d'une sauvegarde de base de données</span><span class="sxs-lookup"><span data-stu-id="1aa79-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="1aa79-109">Pour copier la totalité d'une base de données, vous pouvez utiliser les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] BACKUP et RESTORE.</span><span class="sxs-lookup"><span data-stu-id="1aa79-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="1aa79-110">La restauration d'une sauvegarde complète d'une base de données est généralement utilisée pour copier la base de données d'un ordinateur à un autre pour diverses raisons.</span><span class="sxs-lookup"><span data-stu-id="1aa79-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="1aa79-111">Pour plus d’informations sur l’utilisation des opérations de sauvegarde et de restauration pour copier une base de données, consultez [Copier des bases de données avec la sauvegarde et la restauration](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="1aa79-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1aa79-112">Pour configurer une base de données miroir en vue d’une mise en miroir, restaurez la base de données sur le serveur miroir à l’aide de RESTORE DATABASE *<nom_base_de_données>* WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1aa79-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="1aa79-113">Pour plus d’informations, consultez [Préparer une base de données miroir pour la mise en miroir &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1aa79-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="1aa79-114">Utilisation de l'Assistant Génération de scripts pour publier des bases de données</span><span class="sxs-lookup"><span data-stu-id="1aa79-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="1aa79-115">Vous pouvez utiliser l'Assistant Génération de scripts pour transférer une base de données d'un ordinateur local à un fournisseur d'hébergement Web.</span><span class="sxs-lookup"><span data-stu-id="1aa79-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="1aa79-116">Pour plus d’informations, consultez [Assistant Générer et publier des scripts](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="1aa79-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
