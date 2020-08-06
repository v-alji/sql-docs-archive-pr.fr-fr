---
title: Activer l’initialisation avec une sauvegarde pour les publications transactionnelles (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e22614c8c4f5250db3966e747b686091512774
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601355"
---
# <a name="enable-initialization-with-a-backup-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="31375-102">activer l'initialisation avec une sauvegarde pour les publications transactionnelles (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="31375-102">Enable Initialization with a Backup for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="31375-103">Pour initialiser un abonnement à une publication transactionnelle à partir d'une sauvegarde, vous devez configurer la publication de telle sorte qu'elle autorise une initialisation à partir d'une sauvegarde puis spécifier les informations de sauvegarde lors de la création de l'abonnement :</span><span class="sxs-lookup"><span data-stu-id="31375-103">To initialize a subscription to a transactional publication from a backup, enable the publication to allow initialization from a backup, and then specify backup information when creating the subscription:</span></span>  
  
-   <span data-ttu-id="31375-104">Activez la publication dans la page **Options d’abonnement** de la boîte de dialogue **Propriétés de la publication - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="31375-104">Enable the publication on the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="31375-105">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="31375-105">For more information about accessing this dialog box, see [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="31375-106">Spécifiez les informations de sauvegarde avec la procédure stockée [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="31375-106">Specify backup information with the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="31375-107">Pour plus d’informations sur les paramètres requis par **sp_addsubscription**, consultez [Initialiser un abonnement transactionnel à partir d’une sauvegarde &#40;programmation Transact-SQL de la réplication&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span><span class="sxs-lookup"><span data-stu-id="31375-107">For more information about the parameters required by **sp_addsubscription**, see [Initialize a Transactional Subscription from a Backup &#40;Replication Transact-SQL Programming&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span></span>  
  
### <a name="to-enable-initialization-with-a-backup"></a><span data-ttu-id="31375-108">Pour activer l'initialisation avec une sauvegarde</span><span class="sxs-lookup"><span data-stu-id="31375-108">To enable initialization with a backup</span></span>  
  
1.  <span data-ttu-id="31375-109">Dans la page **Options d’abonnement** de la boîte de dialogue **Propriétés de la publication - \<Publication>** , sélectionnez la valeur **True** pour l’option **Autoriser l’initialisation à partir des fichiers de sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="31375-109">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, select a value of **True** for the **Allow initialization from backup files** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31375-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31375-110">See Also</span></span>  
 [<span data-ttu-id="31375-111">Initialiser un abonnement transactionnel sans instantané</span><span class="sxs-lookup"><span data-stu-id="31375-111">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
