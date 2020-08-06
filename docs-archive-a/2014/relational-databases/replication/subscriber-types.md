---
title: Types d’abonnés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4d356377dec1f5307fa136c94ea682c0824479a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613990"
---
# <a name="subscriber-types"></a><span data-ttu-id="82081-102">Types d'Abonnés</span><span class="sxs-lookup"><span data-stu-id="82081-102">Subscriber Types</span></span>
  <span data-ttu-id="82081-103">La réplication de fusion vous permet de préciser les types d'Abonnés qu'une publication doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="82081-103">Merge replication allows you to specify the types of Subscribers that a publication must support.</span></span> <span data-ttu-id="82081-104">La sélection des ensembles de types d'Abonnés définit le *niveau de compatibilité de la publication*ce qui détermine les fonctionnalités pouvant être utilisées par la publication.</span><span class="sxs-lookup"><span data-stu-id="82081-104">Selecting Subscriber types sets the *publication compatibility level*, which determines which features can be used by a publication.</span></span>  
  
 <span data-ttu-id="82081-105">Après un instantané de publication, le niveau de compatibilité de la publication peut alors être rehaussé (en d'autres termes, rendue plus restrictif) dans la page **Général** de la boîte de dialogue **Propriétés de la publication** ; le niveau de compatibilité ne peut cependant pas être réduit.</span><span class="sxs-lookup"><span data-stu-id="82081-105">After a publication snapshot is created, the publication compatibility level can be increased (made more restrictive) on the **General** page of the **Publication Properties** dialog box; the compatibility level cannot be decreased.</span></span>  
  
## <a name="options"></a><span data-ttu-id="82081-106">Options</span><span class="sxs-lookup"><span data-stu-id="82081-106">Options</span></span>  
 <span data-ttu-id="82081-107">Sélectionnez chaque type d'Abonné que votre publication doit prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="82081-107">Select each Subscriber type that this publication must support.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 <span data-ttu-id="82081-108">La publication peut utiliser toutes les fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="82081-108">The publication can use all features.</span></span>  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 <span data-ttu-id="82081-109">La publication requiert que les fichiers d'instantané soient au format caractère (ceci est géré automatiquement par l'Agent d'instantané).</span><span class="sxs-lookup"><span data-stu-id="82081-109">The publication requires snapshot files to be in character format (this is handled automatically by the Snapshot Agent).</span></span> [!INCLUDE[ssEW](../../includes/ssew-md.md)] <span data-ttu-id="82081-110">est également limité par un certain nombre de restrictions indépendantes du niveau de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="82081-110">also has a number of restrictions not related to compatibility level.</span></span>  
  
 <span data-ttu-id="82081-111">Si cette option est sélectionnée, l'option de synchronisation Web est alors activée pour la publication en question.</span><span class="sxs-lookup"><span data-stu-id="82081-111">If this option is selected, the Web synchronization option is enabled for the publication.</span></span> <span data-ttu-id="82081-112">Pour plus d'informations sur la synchronisation Web, consultez [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="82081-112">For more information about Web synchronization, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82081-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82081-113">See Also</span></span>  
 <span data-ttu-id="82081-114">[Publier des données et des objets de base de données](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="82081-114">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="82081-115">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="82081-115">[Create a Publication](publish/create-a-publication.md) </span></span>  
 [<span data-ttu-id="82081-116">Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="82081-116">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
