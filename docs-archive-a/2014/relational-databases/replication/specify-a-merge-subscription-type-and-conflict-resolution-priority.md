---
title: Spécifier un type d’abonnement de fusion et une priorité pour la résolution des conflits (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710568"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a><span data-ttu-id="c8883-102">spécifier un type d'abonnement de fusion et une priorité pour la résolution des conflits (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c8883-102">Specify a Merge Subscription Type and Conflict Resolution Priority (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c8883-103">Spécifiez un type d'abonnement de fusion et une priorité pour la résolution des conflits dans la page **Type d'abonnement** de l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="c8883-103">Specify a merge subscription type and conflict resolution priority on the **Subscription Type** page of the New Subscription Wizard.</span></span> <span data-ttu-id="c8883-104">Pour plus d'informations sur l'utilisation de cet Assistant, consultez [Create a Pull Subscription](create-a-pull-subscription.md) et [Create a Push Subscription](create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c8883-104">For more information about using this wizard, see [Create a Pull Subscription](create-a-pull-subscription.md) and [Create a Push Subscription](create-a-push-subscription.md).</span></span>  
  
 <span data-ttu-id="c8883-105">Le type d'abonnement ne peut pas être modifié après la création d'un abonnement, mais la priorité peut être modifiée pour le type d'abonnement serveur dans la **boîte de dialogue Propriétés de l'abonnement - \<Publisher>: \<PublicationDatabase>** .</span><span class="sxs-lookup"><span data-stu-id="c8883-105">Subscription type cannot be modified after a subscription is created, but priority can be modified for the server subscription type in the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** dialog box.</span></span> <span data-ttu-id="c8883-106">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) et [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c8883-106">For more information about accessing this dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a><span data-ttu-id="c8883-107">Pour spécifier un type d'abonnement de fusion et une priorité pour la résolution des conflits</span><span class="sxs-lookup"><span data-stu-id="c8883-107">To specify a merge subscription type and conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="c8883-108">Dans la page **Type d'abonnement** de l'Assistant Nouvel abonnement, sélectionnez **Client** ou **Serveur** pour l'option **Type d'abonnement** .</span><span class="sxs-lookup"><span data-stu-id="c8883-108">On the **Subscription Type** page of the New Subscription Wizard, select **Client** or **Server** for the **Subscription Type** option.</span></span>  
  
2.  <span data-ttu-id="c8883-109">Si vous sélectionnez le type d'abonnement **Serveur**, affectez également une valeur (0,00 à 99,99) à l'option **Priorité pour la résolution des conflits** .</span><span class="sxs-lookup"><span data-stu-id="c8883-109">If you select a subscription type of **Server**, also enter a value (0.00 to 99.99) for the **Priority for Conflict Resolution** option.</span></span>  
  
### <a name="to-modify-the-conflict-resolution-priority"></a><span data-ttu-id="c8883-110">Pour modifier la priorité pour la résolution des conflits</span><span class="sxs-lookup"><span data-stu-id="c8883-110">To modify the conflict resolution priority</span></span>  
  
1.  <span data-ttu-id="c8883-111">Dans la boîte de dialogue **Propriétés de l'abonnement - \<Publisher>: \<PublicationDatabase>** sur le serveur de publication, affectez une valeur (de 0,00 à 99,99) à l'option **Priorité**.</span><span class="sxs-lookup"><span data-stu-id="c8883-111">In the **Subscription Properties - \<Publisher>: \<PublicationDatabase>** at the Publisher, enter a value (0.00 to 99.99) for the **Priority** option.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8883-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8883-112">See Also</span></span>  
 <span data-ttu-id="c8883-113">[Détection et résolution des conflits de réplication de fusion avancée](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="c8883-113">[Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md) </span></span>  
 [<span data-ttu-id="c8883-114">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="c8883-114">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
