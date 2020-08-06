---
title: Les tables d’historique de sauvegarde ou de restauration volumineuses semblent ne pas répondre à la mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601272"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="b9d70-102">Les tables d'historique de sauvegarde ou de restauration importantes donnent l'impression que la mise à niveau ne répond pas</span><span class="sxs-lookup"><span data-stu-id="b9d70-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="b9d70-103">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], de nouvelles colonnes ont été ajoutées dans certaines tables d'historique de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="b9d70-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="b9d70-104">La mise à niveau de ces tables implique de les modifier pour ajouter les nouvelles colonnes.</span><span class="sxs-lookup"><span data-stu-id="b9d70-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="b9d70-105">Si une ou plusieurs de ces tables contiennent un grand nombre de lignes, la mise à niveau semblera bloquée pendant une durée substantielle sur l'instruction ALTER TABLE qui ajoute des colonnes à ces tables.</span><span class="sxs-lookup"><span data-stu-id="b9d70-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b9d70-106">Composant</span><span class="sxs-lookup"><span data-stu-id="b9d70-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b9d70-107">Description</span><span class="sxs-lookup"><span data-stu-id="b9d70-107">Description</span></span>  
 <span data-ttu-id="b9d70-108">La mise à niveau peut sembler ne plus répondre si l’une des tables d’historique de sauvegarde ou de restauration suivantes contient un grand nombre de lignes :</span><span class="sxs-lookup"><span data-stu-id="b9d70-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="b9d70-109">**backupfile**</span><span class="sxs-lookup"><span data-stu-id="b9d70-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="b9d70-110">**backupmediafamily**</span><span class="sxs-lookup"><span data-stu-id="b9d70-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="b9d70-111">**backupmediaset**</span><span class="sxs-lookup"><span data-stu-id="b9d70-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="b9d70-112">**backupset**</span><span class="sxs-lookup"><span data-stu-id="b9d70-112">**backupset**</span></span>  
  
-   <span data-ttu-id="b9d70-113">**restorefile**</span><span class="sxs-lookup"><span data-stu-id="b9d70-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="b9d70-114">**restorefilegroup**</span><span class="sxs-lookup"><span data-stu-id="b9d70-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="b9d70-115">**restorehistory**</span><span class="sxs-lookup"><span data-stu-id="b9d70-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="b9d70-116">Si l'une de ces tables possède 10 000 lignes ou plus, le Conseiller de mise à niveau signale un échec de non-conformité.</span><span class="sxs-lookup"><span data-stu-id="b9d70-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="b9d70-117">Il ne signale pas la table dont le nombre de lignes dépasse le nombre autorisé.</span><span class="sxs-lookup"><span data-stu-id="b9d70-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="b9d70-118">La première table qui possède plus de 10 000 lignes provoque l'échec.</span><span class="sxs-lookup"><span data-stu-id="b9d70-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b9d70-119">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b9d70-119">Corrective Action</span></span>  
 <span data-ttu-id="b9d70-120">Avant la mise à niveau d'une base de données, si l'une de ces tables possède plus de 10 000 lignes, nous vous recommandons de réduire ce nombre à moins de 10 000.</span><span class="sxs-lookup"><span data-stu-id="b9d70-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="b9d70-121">Pour réduire les lignes de toutes ces tables, vous pouvez exécuter la procédure stockée **sp_delete_backuphistory** .</span><span class="sxs-lookup"><span data-stu-id="b9d70-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="b9d70-122">Cette procédure supprime les entrées dans toutes les tables d'historique de sauvegarde et de restauration correspondant aux jeux de sauvegarde antérieurs à la date spécifiée.</span><span class="sxs-lookup"><span data-stu-id="b9d70-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="b9d70-123">Pour plus d’informations, consultez [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9d70-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9d70-124">Vous pouvez mettre à niveau une base de données dont les tables d'historique de sauvegarde et de restauration possèdent plus de 10 000 lignes.</span><span class="sxs-lookup"><span data-stu-id="b9d70-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="b9d70-125">Toutefois, la mise à niveau peut paraître bloquée pendant que les tables de grande taille sont modifiées.</span><span class="sxs-lookup"><span data-stu-id="b9d70-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="b9d70-126">Plus les tables sont grandes, plus l'exécution du programme d'installation dure.</span><span class="sxs-lookup"><span data-stu-id="b9d70-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9d70-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9d70-127">See Also</span></span>  
 <span data-ttu-id="b9d70-128">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b9d70-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b9d70-129">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="b9d70-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
