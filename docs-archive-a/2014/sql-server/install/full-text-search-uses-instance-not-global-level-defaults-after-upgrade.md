---
title: La mise à niveau entraînera l’utilisation par défaut d’analyseurs lexicaux et de filtres de niveau d’instance, et non globaux, de la recherche en texte intégral | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filters [Full-Text Search]
- word breakers [Full-Text Search]
ms.assetid: 93ee8fcb-d11c-49fa-8fac-51ed31a8f008
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0b6cea7ab63351fad25f0205a614e364328171a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614995"
---
# <a name="upgrading-will-cause-full-text-search-to-use-instance-level-not-global-word-breakers-and-filters-by-default"></a><span data-ttu-id="41b0e-102">La mise à niveau entraînera l'utilisation par défaut d'analyseurs lexicaux et de filtres de niveau d'instance, et non globaux, pour la recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="41b0e-102">Upgrading will cause Full-Text Search to use instance-level, not global, word breakers and filters by default</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41b0e-103">permet d'autoriser l'inscription au niveau des instances de nouveaux analyseurs lexicaux et filtres.</span><span class="sxs-lookup"><span data-stu-id="41b0e-103">provides a way to allow instance-level registration of new word breakers and filters.</span></span>  
  
## <a name="component"></a><span data-ttu-id="41b0e-104">Composant</span><span class="sxs-lookup"><span data-stu-id="41b0e-104">Component</span></span>  
 <span data-ttu-id="41b0e-105">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="41b0e-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="41b0e-106">Description</span><span class="sxs-lookup"><span data-stu-id="41b0e-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="41b0e-107">autorise l'inscription au niveau des instances de nouveaux analyseurs lexicaux et filtres.</span><span class="sxs-lookup"><span data-stu-id="41b0e-107">allows the instance-level registration of new word breakers and filters.</span></span> <span data-ttu-id="41b0e-108">Cette inscription au niveau des instances permet d'isoler ces dernières tant pour leur fonctionnalité que leur sécurité.</span><span class="sxs-lookup"><span data-stu-id="41b0e-108">This instance-level registration provides functional and security isolation between instances.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="41b0e-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="41b0e-109">Corrective Action</span></span>  
 <span data-ttu-id="41b0e-110">Après la mise à niveau, utilisez `sp_fulltext_service` pour définir la propriété de service et `load_os_resources`, qui permet de charger les composants.</span><span class="sxs-lookup"><span data-stu-id="41b0e-110">After upgrading, use the `sp_fulltext_service` to set the service property and `load_os_resources`, which allows the components to be loaded.</span></span> <span data-ttu-id="41b0e-111">Vous devez exécuter la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="41b0e-111">You must run the following:</span></span>  
  
 `sp_fulltext_service 'load_os_resources', 1`  
  
## <a name="see-also"></a><span data-ttu-id="41b0e-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41b0e-112">See Also</span></span>  
 [<span data-ttu-id="41b0e-113">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="41b0e-113">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
