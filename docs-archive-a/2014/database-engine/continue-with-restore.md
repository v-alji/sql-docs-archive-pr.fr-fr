---
title: Continuer la restauration | Microsoft Docs
description: Dans SQL Server, utilisez la boîte de dialogue continuer la restauration pour indiquer si vous voulez restaurer le prochain jeu de sauvegarde.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.continuerestore.f1
ms.assetid: 987ac05f-57c0-49a9-9903-9889717aae4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c7a438ac7b8696d2f57bdf93ff86030cf607e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707784"
---
# <a name="continue-with-restore"></a><span data-ttu-id="1c684-103">Continuer la restauration</span><span class="sxs-lookup"><span data-stu-id="1c684-103">Continue with Restore</span></span>
  <span data-ttu-id="1c684-104">Utilisez la boîte de dialogue **Continuer la restauration** pour indiquer si vous voulez restaurer le prochain jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1c684-104">Use the **Continue with Restore** dialog box to indicate whether you want to restore the next backup set.</span></span> <span data-ttu-id="1c684-105">Pour différer l'opération de restauration, par exemple pour échanger des bandes, attendez d'être prêt à continuer avant de cliquer sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c684-105">To delay the restore operation, for example, to swap tapes, wait until you are ready to proceed before you click **OK**.</span></span>  
  
 <span data-ttu-id="1c684-106">Si vous cliquez sur **Non** , la séquence de restauration s'arrête et la base de données est laissée en état de restauration.</span><span class="sxs-lookup"><span data-stu-id="1c684-106">Clicking **No** terminates the restore sequence, leaving the database in the restoring state.</span></span> <span data-ttu-id="1c684-107">Pour continuer ultérieurement la restauration, utilisez, selon les cas, la tâche **Restaurer la base de données** ou **Restaurer le journal des transactions** .</span><span class="sxs-lookup"><span data-stu-id="1c684-107">To continue with the restore later, use either the **Restore Database** or **Restore Transaction Log** task, as appropriate.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1c684-108">Options</span><span class="sxs-lookup"><span data-stu-id="1c684-108">Options</span></span>  
 <span data-ttu-id="1c684-109">**Support de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="1c684-109">**Media set**</span></span>  
 <span data-ttu-id="1c684-110">Affiche le nom du support de sauvegarde suivant (si disponible).</span><span class="sxs-lookup"><span data-stu-id="1c684-110">Displays the next media set name (if available).</span></span>  
  
 <span data-ttu-id="1c684-111">**Jeu de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="1c684-111">**Backup set**</span></span>  
 <span data-ttu-id="1c684-112">Affiche le nom du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1c684-112">Displays the backup set name.</span></span>  
  
 <span data-ttu-id="1c684-113">**Description du jeu de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="1c684-113">**Backup set description**</span></span>  
 <span data-ttu-id="1c684-114">Affiche la description du jeu de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1c684-114">Displays the backup set description.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c684-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c684-115">See Also</span></span>  
 <span data-ttu-id="1c684-116">[Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c684-116">[View the Contents of a Backup Tape or File &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-contents-of-a-backup-tape-or-file-sql-server.md) </span></span>  
 <span data-ttu-id="1c684-117">[Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1c684-117">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](../relational-databases/backup-restore/view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="1c684-118">[Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="1c684-118">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="1c684-119">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1c684-119">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server.md)  
  
  
