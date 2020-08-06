---
title: Restaurer une base de données jusqu’à une transaction marquée (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restoretlog.markedtransaction.f1
helpviewer_keywords:
- database restores [SQL Server], marked transactions
- restoring databases [SQL Server], marked transactions
- marked transactions [SQL Server], restoring
ms.assetid: 8f0ea144-1819-4832-905f-e5d0f49b066b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8de9ef5bed389f020f14e60ccd99f39698e7110f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612422"
---
# <a name="restore-a-database-to-a-marked-transaction-sql-server-management-studio"></a><span data-ttu-id="9eab0-102">Restaurer une base de données jusqu'à une transaction marquée (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9eab0-102">Restore a Database to a Marked Transaction (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9eab0-103">Quand une base de données se trouve dans l’état de restauration, vous pouvez utiliser la boîte de dialogue **Restaurer le journal des transactions** pour restaurer la base de données jusqu’à une transaction marquée dans les sauvegardes du journal disponibles.</span><span class="sxs-lookup"><span data-stu-id="9eab0-103">When a database is in the restoring state, you can use the **Restore Transaction Log** dialog box to restore the database to a marked transaction in the available log backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9eab0-104">Pour plus d’informations, consultez [Utiliser les transactions marquées pour récupérer des bases de données associées uniformément &#40;mode de récupération complète&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) et [Récupération de bases de données associées contenant une transaction marquée](recovery-of-related-databases-that-contain-marked-transaction.md).</span><span class="sxs-lookup"><span data-stu-id="9eab0-104">For more information, see [Use Marked Transactions to Recover Related Databases Consistently &#40;Full Recovery Model&#41;](use-marked-transactions-to-recover-related-databases-consistently.md) and [Recovery of Related  Databases That Contain Marked Transaction](recovery-of-related-databases-that-contain-marked-transaction.md).</span></span>  
  
### <a name="to-restore-a-marked-transaction"></a><span data-ttu-id="9eab0-105">Pour restaurer une transaction marquée</span><span class="sxs-lookup"><span data-stu-id="9eab0-105">To restore a marked transaction</span></span>  
  
1.  <span data-ttu-id="9eab0-106">Après vous être connecté à l’instance appropriée du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)], dans l’Explorateur d’objets, cliquez sur le nom du serveur pour développer son arborescence.</span><span class="sxs-lookup"><span data-stu-id="9eab0-106">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9eab0-107">Développez **Bases de données**puis, selon la base de données, sélectionnez une base de données utilisateur ou développez **Bases de données système** et sélectionnez une base de données système.</span><span class="sxs-lookup"><span data-stu-id="9eab0-107">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9eab0-108">Cliquez avec le bouton droit sur la base de données, pointez sur **Tâches**, puis cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="9eab0-108">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="9eab0-109">Cliquez sur **Journal des transactions**afin d’ouvrir la boîte de dialogue **Restaurer le journal des transactions** .</span><span class="sxs-lookup"><span data-stu-id="9eab0-109">Click **Transaction Log**, which opens the **Restore Transaction Log** dialog box.</span></span>  
  
5.  <span data-ttu-id="9eab0-110">Dans la page **Général** , dans la section **Restaurer sur** , sélectionnez **Transaction marquée**afin d’ouvrir la boîte de dialogue **Sélectionner une transaction marquée** .</span><span class="sxs-lookup"><span data-stu-id="9eab0-110">On the **General** page, in the **Restore To** section, select **Marked transaction**, which opens the **Select Marked Transaction** dialog box.</span></span> <span data-ttu-id="9eab0-111">Cette boîte de dialogue affiche une grille répertoriant les transactions marquées disponibles dans les sauvegardes du journal des transactions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="9eab0-111">This dialog box displays a grid listing the marked transactions available in the selected transaction log backups.</span></span>  
  
     <span data-ttu-id="9eab0-112">Par défaut, la restauration s'effectue jusqu'à la transaction marquée, en l'excluant.</span><span class="sxs-lookup"><span data-stu-id="9eab0-112">By default, the restore is up to, but excluding, the marked transaction.</span></span> <span data-ttu-id="9eab0-113">Pour restaurer également la transaction marquée, sélectionnez **Inclure la transaction marquée**.</span><span class="sxs-lookup"><span data-stu-id="9eab0-113">To restore the marked transaction also, select **Include marked transaction**.</span></span>  
  
     <span data-ttu-id="9eab0-114">Le tableau suivant répertorie les en-têtes de colonnes de la grille et décrit leur valeur.</span><span class="sxs-lookup"><span data-stu-id="9eab0-114">The following table lists the column headers of the grid and describes their values.</span></span>  
  
    |<span data-ttu-id="9eab0-115">En-tête</span><span class="sxs-lookup"><span data-stu-id="9eab0-115">Header</span></span>|<span data-ttu-id="9eab0-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="9eab0-116">Value</span></span>|  
    |------------|-----------|  
    |\<blank>|<span data-ttu-id="9eab0-117">Affiche une case à cocher pour la sélection de la marque.</span><span class="sxs-lookup"><span data-stu-id="9eab0-117">Displays a checkbox for selecting the mark.</span></span>|  
    |<span data-ttu-id="9eab0-118">**Marque de transaction**</span><span class="sxs-lookup"><span data-stu-id="9eab0-118">**Transaction Mark**</span></span>|<span data-ttu-id="9eab0-119">Nom de la transaction marquée spécifiée par l'utilisateur lors de la validation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="9eab0-119">Name of the marked transaction specified by the user when the transaction was committed.</span></span>|  
    |<span data-ttu-id="9eab0-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="9eab0-120">**Date**</span></span>|<span data-ttu-id="9eab0-121">Date et heure de la validation de la transaction.</span><span class="sxs-lookup"><span data-stu-id="9eab0-121">Date and time of the transaction when it was committed.</span></span> <span data-ttu-id="9eab0-122">La date et l’heure sont affichées telles qu’enregistrées dans la table **msdbgmarkhistory** , et non dans l’option Date et heure de l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="9eab0-122">Transaction date and time are displayed as recorded in the **msdbgmarkhistory** table, not in the client computer's date and time.</span></span>|  
    |<span data-ttu-id="9eab0-123">**Description**</span><span class="sxs-lookup"><span data-stu-id="9eab0-123">**Description**</span></span>|<span data-ttu-id="9eab0-124">Description de la transaction marquée spécifiée par l'utilisateur lorsque la transaction a été validée (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="9eab0-124">Description of marked transaction specified by the user when the transaction was committed (if any).</span></span>|  
    |<span data-ttu-id="9eab0-125">**LSN**</span><span class="sxs-lookup"><span data-stu-id="9eab0-125">**LSN**</span></span>|<span data-ttu-id="9eab0-126">Numéro séquentiel dans le journal de la transaction marquée.</span><span class="sxs-lookup"><span data-stu-id="9eab0-126">Log sequence number of the marked transaction.</span></span>|  
    |<span data-ttu-id="9eab0-127">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="9eab0-127">**Database**</span></span>|<span data-ttu-id="9eab0-128">Nom de la base de données où la transaction marquée a été validée.</span><span class="sxs-lookup"><span data-stu-id="9eab0-128">Name of the database where the marked transaction was committed.</span></span>|  
    |<span data-ttu-id="9eab0-129">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9eab0-129">**User Name**</span></span>|<span data-ttu-id="9eab0-130">Nom de l'utilisateur de la base de données où la transaction marquée a été validée.</span><span class="sxs-lookup"><span data-stu-id="9eab0-130">Name of the database user who committed the marked transaction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9eab0-131"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9eab0-131">See Also</span></span>  
 <span data-ttu-id="9eab0-132">[Restaurer une sauvegarde de base de données &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9eab0-132">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 [<span data-ttu-id="9eab0-133">Restaurer une sauvegarde de journal des transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9eab0-133">Restore a Transaction Log Backup &#40;SQL Server&#41;</span></span>](restore-a-transaction-log-backup-sql-server.md)  
  
  
