---
title: Plans de maintenance de base de données remplacés | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600492"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="b575b-102">Les plans de maintenance de la base de données sont obsolètes</span><span class="sxs-lookup"><span data-stu-id="b575b-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="b575b-103">Composant</span><span class="sxs-lookup"><span data-stu-id="b575b-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="b575b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent</span><span class="sxs-lookup"><span data-stu-id="b575b-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="b575b-105">Description</span><span class="sxs-lookup"><span data-stu-id="b575b-105">Description</span></span>  
 <span data-ttu-id="b575b-106">Les plans de maintenance de base de données existants sont mis à niveau et peuvent encore être utilisés.</span><span class="sxs-lookup"><span data-stu-id="b575b-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="b575b-107">Cependant, vous ne pourrez pas créer de nouveaux plans de maintenance de base de données en utilisant [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b575b-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b575b-108">Pour afficher les plans de maintenance dans l'Explorateur d'objets, développez Gestion, puis Existant.</span><span class="sxs-lookup"><span data-stu-id="b575b-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="b575b-109">Vous pouvez migrer des plans de maintenance de base de données existants vers le nouveau format en sélectionnant **migrer** dans le menu contextuel de n’importe quel plan de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="b575b-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="b575b-110">Certaines fonctionnalités peuvent être perdues après la migration, car la fonction de nouveau plan de maintenance ne remplace pas directement les plans de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="b575b-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="b575b-111">Étant donné que la migration d'un plan de maintenance de base de données ne supprime pas le plan existant, vous avez la possibilité de tester les fonctionnalités du nouveau plan de maintenance avant de supprimer le plan antérieur.</span><span class="sxs-lookup"><span data-stu-id="b575b-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="b575b-112">Les fonctionnalités suivantes ne sont plus prises en charge dans les plans de maintenance de base de données :</span><span class="sxs-lookup"><span data-stu-id="b575b-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="b575b-113">Copie des journaux de transaction</span><span class="sxs-lookup"><span data-stu-id="b575b-113">Log shipping</span></span>  
  
-   <span data-ttu-id="b575b-114">L’option **tenter de réparer les problèmes mineurs** de la tâche **de vérification de l’intégrité de la base de données**</span><span class="sxs-lookup"><span data-stu-id="b575b-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b575b-115">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b575b-115">Corrective Action</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b575b-116">empêche que l'envoi des journaux soit inclus dans un plan de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="b575b-116">prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="b575b-117">Pour plus d'informations, consultez « Copie des journaux de transaction » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b575b-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
