---
title: Activer Resource Governor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7b1b0f780457aa5a4d26cbb463c9f31a94185f0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699396"
---
# <a name="enable-resource-governor"></a><span data-ttu-id="3d896-102">Activer Resource Governor</span><span class="sxs-lookup"><span data-stu-id="3d896-102">Enable Resource Governor</span></span>
  <span data-ttu-id="3d896-103">Resource Governor est désactivé par défaut.</span><span class="sxs-lookup"><span data-stu-id="3d896-103">The Resource Governor is turned off by default.</span></span> <span data-ttu-id="3d896-104">Vous pouvez activer Resource Governor à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3d896-104">You can enable the Resource Governor by using either [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or Transact-SQL.</span></span>  
  
-   <span data-ttu-id="3d896-105">**Avant de commencer :**  [Limitations et restrictions](#LimitationsRestrictions), [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="3d896-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="3d896-106">**Pour activer Resource Governor avec :**  [Explorateur d’objets](#RGOnObjEx), [Propriétés de Resource Governor](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span><span class="sxs-lookup"><span data-stu-id="3d896-106">**To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3d896-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3d896-107">Before You Begin</span></span>  
 <span data-ttu-id="3d896-108">L'activation de Resource Governor entraîne les résultats suivants :</span><span class="sxs-lookup"><span data-stu-id="3d896-108">Enabling the resource governor has the following results:</span></span>  
  
-   <span data-ttu-id="3d896-109">La fonction classifieur est exécutée pour les nouvelles connexions afin que leurs charges de travail puissent être assignées aux groupes de charge de travail.</span><span class="sxs-lookup"><span data-stu-id="3d896-109">The classifier function is run for new connections so that their workloads can be assigned to workload groups.</span></span>  
  
-   <span data-ttu-id="3d896-110">Les limites de ressource qui sont spécifiées dans la configuration de Resource Governor sont honorées et appliquées.</span><span class="sxs-lookup"><span data-stu-id="3d896-110">The resource limits that are specified in the Resource Governor configuration are honored and enforced.</span></span>  
  
-   <span data-ttu-id="3d896-111">Les demandes qui ont existé avant d'activer Resource Governor sont affectées par les éventuelles modifications de configuration qui ont été effectuées lorsque Resource Governor était désactivé.</span><span class="sxs-lookup"><span data-stu-id="3d896-111">Requests that existed before enabling Resource Governor are affected by any configuration changes that were made when the Resource Governor was disabled.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="3d896-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="3d896-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3d896-113">Vous ne pouvez pas utiliser l'instruction `ALTER RESOURCE GOVERNOR` pour activer le gouverneur de ressources dans une transaction utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3d896-113">You cannot use the `ALTER RESOURCE GOVERNOR` statement to enable Resource Governor when in a user transaction.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3d896-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3d896-114">Permissions</span></span>  
 <span data-ttu-id="3d896-115">L'activation de Resource Governor requiert l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="3d896-115">Enabling the Resource Governor requires CONTROL SERVER permission.</span></span>  
  
##  <a name="enable-resource-governor-using-object-explorer"></a><a name="RGOnObjEx"></a> <span data-ttu-id="3d896-116">Activer Resource Governor à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="3d896-116">Enable Resource Governor Using Object Explorer</span></span>  
 <span data-ttu-id="3d896-117">**Pour activer Resource Governor à l'aide de l'Explorateur d'objets**</span><span class="sxs-lookup"><span data-stu-id="3d896-117">**To enable the Resource Governor by using Object Explorer**</span></span>  
  
1.  <span data-ttu-id="3d896-118">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'au **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="3d896-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="3d896-119">Cliquez avec le bouton droit sur **Resource Governor**, puis sélectionnez **Activer**.</span><span class="sxs-lookup"><span data-stu-id="3d896-119">Right-click **Resource Governor**, and then click **Enable**.</span></span>  
  
##  <a name="enable-resource-governor-using-resource-governor-properties"></a><a name="RGOnProp"></a> <span data-ttu-id="3d896-120">Activer Resource Governor à l'aide des propriétés de Resource Governor</span><span class="sxs-lookup"><span data-stu-id="3d896-120">Enable Resource Governor Using Resource Governor Properties</span></span>  
 <span data-ttu-id="3d896-121">**Pour activer Resource Governor à l'aide de la page Propriétés de Resource Governor**</span><span class="sxs-lookup"><span data-stu-id="3d896-121">**To enable the Resource Governor by using the Resource Governor Properties page**</span></span>  
  
1.  <span data-ttu-id="3d896-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ouvrez l'Explorateur d'objets et développez de manière récursive le nœud **Gestion** jusqu'au **Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="3d896-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open Object Explorer and recursively expand the **Management** node down to **Resource Governor**.</span></span>  
  
2.  <span data-ttu-id="3d896-123">Cliquez avec le bouton droit sur **Resource Governor** , puis sélectionnez **Propriétés**afin d’ouvrir la page **Propriétés de Resource Governor** .</span><span class="sxs-lookup"><span data-stu-id="3d896-123">Right-click **Resource Governor** and then click **Properties**, this opens the **Resource Governor Properties** page.</span></span>  
  
3.  <span data-ttu-id="3d896-124">Activez la case à cocher **Activer Resource Governor** , puis cliquez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d896-124">Click the **Enable Resource Governor** check box, and then click **OK**.</span></span>  
  
##  <a name="enable-resource-governor-using-transact-sql"></a><a name="RGOnTSQL"></a> <span data-ttu-id="3d896-125">Activer Resource Governor à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3d896-125">Enable Resource Governor Using Transact-SQL</span></span>  
 <span data-ttu-id="3d896-126">**Pour activer Resource Governor à l'aide de Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="3d896-126">**To enable the Resource Governor by using Transact-SQL**</span></span>  
  
1.  <span data-ttu-id="3d896-127">Exécutez l'instruction **ALTER RESOURCE GOVERNOR RECONFIGURE** .</span><span class="sxs-lookup"><span data-stu-id="3d896-127">Run the **ALTER RESOURCE GOVERNOR RECONFIGURE** statement.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="3d896-128">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3d896-128">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="3d896-129">L'exemple suivant active Resource Governor.</span><span class="sxs-lookup"><span data-stu-id="3d896-129">The following example enables the Resource Governor.</span></span>  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d896-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d896-130">See Also</span></span>  
 <span data-ttu-id="3d896-131">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="3d896-131">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="3d896-132">[Désactiver Resource Governor](disable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="3d896-132">[Disable Resource Governor](disable-resource-governor.md) </span></span>  
 <span data-ttu-id="3d896-133">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="3d896-133">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="3d896-134">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="3d896-134">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="3d896-135">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="3d896-135">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 [<span data-ttu-id="3d896-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d896-136">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
