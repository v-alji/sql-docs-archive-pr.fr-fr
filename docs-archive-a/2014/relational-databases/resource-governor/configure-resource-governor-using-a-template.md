---
title: Configurer Resource Governor à l’aide d’un modèle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613421"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="2a571-102">Configurer Resource Governor à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="2a571-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="2a571-103">Vous pouvez configurer Resource Governor à l'aide d'un modèle fourni dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a571-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="2a571-104">**Avant de commencer :**  [Autorisations](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="2a571-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="2a571-105">**Pour créer un groupe de charge de travail, avec :** [un modèle](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="2a571-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2a571-106">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2a571-106">Before You Begin</span></span>  
 <span data-ttu-id="2a571-107">Utilisez les étapes suivantes pour ouvrir et modifier un modèle qui crée un pool de ressources et un groupe de charge de travail pour le pool.</span><span class="sxs-lookup"><span data-stu-id="2a571-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="2a571-108">De plus, ce modèle vous permet de créer une fonction classifieur définie par l'utilisateur qui achemine de nouvelles connexions vers le groupe par défaut ou le groupe de charge de travail que vous créez.</span><span class="sxs-lookup"><span data-stu-id="2a571-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2a571-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2a571-109">Permissions</span></span>  
 <span data-ttu-id="2a571-110">Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] de Resource Governor dans le modèle requièrent l'autorisation CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="2a571-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="2a571-111">Configurer Resource Governor à l'aide d'un modèle</span><span class="sxs-lookup"><span data-stu-id="2a571-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="2a571-112">**Pour configurer Resource Governor à l'aide d'un modèle dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2a571-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="2a571-113">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], dans le menu **Affichage** , cliquez sur **Explorateur de modèles**.</span><span class="sxs-lookup"><span data-stu-id="2a571-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="2a571-114">Dans **Explorateur de modèles**, développez **Resource Governor**, puis double-cliquez sur **Configurer Resource Governor**.</span><span class="sxs-lookup"><span data-stu-id="2a571-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="2a571-115">Dans **Se connecter au moteur de base de données**, entrez les informations requises, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a571-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="2a571-116">Le modèle Configure Ressource Governor.sql est fourni dans l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="2a571-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="2a571-117">Utilisez ce modèle pour créer et configurer un pool de ressources, un groupe de charges de travail et une fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="2a571-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="2a571-118">Pour modifier les valeurs dans le modèle, appuyez sur CTRL+Maj+M.</span><span class="sxs-lookup"><span data-stu-id="2a571-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="2a571-119">Dans la fenêtre **Spécifier les valeurs des paramètres du modèle** , entrez les valeurs de votre choix.</span><span class="sxs-lookup"><span data-stu-id="2a571-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="2a571-120">Pour enregistrer les modifications que vous apportez au modèle, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a571-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="2a571-121">Pour exécuter la requête, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="2a571-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a571-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a571-122">See Also</span></span>  
 <span data-ttu-id="2a571-123">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="2a571-124">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="2a571-125">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="2a571-126">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="2a571-127">[Fonction classifieur de Resource Governor](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="2a571-128">[Afficher les propriétés de Resource Governor](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2a571-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="2a571-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a571-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="2a571-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a571-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="2a571-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2a571-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="2a571-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2a571-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
