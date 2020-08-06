---
title: Boîte de dialogue opérations actives | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602274"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="a6c0c-102">Boîte de dialogue Opérations actives</span><span class="sxs-lookup"><span data-stu-id="a6c0c-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="a6c0c-103">Utilisez la boîte de dialogue **Opérations actives** pour afficher l'état des opérations [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en cours d'exécution sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , par exemple les opérations de déploiement, de validation et d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="a6c0c-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="a6c0c-104">Ces données sont stockées dans le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="a6c0c-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="a6c0c-105">Pour plus d’informations sur les vues [!INCLUDE[tsql](../includes/tsql-md.md)] associées, consultez [catalog.operations &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database) et [catalog.executions &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span><span class="sxs-lookup"><span data-stu-id="a6c0c-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="a6c0c-106">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="a6c0c-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="a6c0c-107">Ouvrir la boîte de dialogue opérations actives</span><span class="sxs-lookup"><span data-stu-id="a6c0c-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="a6c0c-108">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="a6c0c-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="a6c0c-109">Ouvrir la boîte de dialogue Opérations actives</span><span class="sxs-lookup"><span data-stu-id="a6c0c-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="a6c0c-110">Ouvrir [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6c0c-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="a6c0c-111">Se connecter au moteur de base de données Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6c0c-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="a6c0c-112">Dans l’Explorateur d’objets, développez le nœud **Integration Services** , cliquez avec le bouton droit sur **SSISDB**, puis cliquez sur **Opérations actives**.</span><span class="sxs-lookup"><span data-stu-id="a6c0c-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="a6c0c-113">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="a6c0c-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="a6c0c-114">Options</span><span class="sxs-lookup"><span data-stu-id="a6c0c-114">Options</span></span>  
 <span data-ttu-id="a6c0c-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="a6c0c-115">**Type**</span></span>  
 <span data-ttu-id="a6c0c-116">Spécifie le type d'opération.</span><span class="sxs-lookup"><span data-stu-id="a6c0c-116">Specifies the type of operation.</span></span> <span data-ttu-id="a6c0c-117">Voici les valeurs possibles pour le champ **type** et les valeurs correspondantes dans la colonne operations_type de la vue Transact-SQL `catalog.operations` .</span><span class="sxs-lookup"><span data-stu-id="a6c0c-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6c0c-118">Initialisation d'Integration Services</span><span class="sxs-lookup"><span data-stu-id="a6c0c-118">Integration Services initialization</span></span>|<span data-ttu-id="a6c0c-119">1</span><span class="sxs-lookup"><span data-stu-id="a6c0c-119">1</span></span>|  
|<span data-ttu-id="a6c0c-120">Nettoyage des opérations (travail de l'Agent SQL)</span><span class="sxs-lookup"><span data-stu-id="a6c0c-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="a6c0c-121">2</span><span class="sxs-lookup"><span data-stu-id="a6c0c-121">2</span></span>|  
|<span data-ttu-id="a6c0c-122">Nettoyage des versions du projet (travail de l'Agent SQL)</span><span class="sxs-lookup"><span data-stu-id="a6c0c-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="a6c0c-123">3</span><span class="sxs-lookup"><span data-stu-id="a6c0c-123">3</span></span>|  
|<span data-ttu-id="a6c0c-124">Déployer le projet</span><span class="sxs-lookup"><span data-stu-id="a6c0c-124">Deploy project</span></span>|<span data-ttu-id="a6c0c-125">101</span><span class="sxs-lookup"><span data-stu-id="a6c0c-125">101</span></span>|  
|<span data-ttu-id="a6c0c-126">Restaurer le projet</span><span class="sxs-lookup"><span data-stu-id="a6c0c-126">Restore project</span></span>|<span data-ttu-id="a6c0c-127">106</span><span class="sxs-lookup"><span data-stu-id="a6c0c-127">106</span></span>|  
|<span data-ttu-id="a6c0c-128">Créer et démarrer l'exécution du package</span><span class="sxs-lookup"><span data-stu-id="a6c0c-128">Create and start package execution</span></span>|<span data-ttu-id="a6c0c-129">200</span><span class="sxs-lookup"><span data-stu-id="a6c0c-129">200</span></span>|  
|<span data-ttu-id="a6c0c-130">Arrêter l'opération (arrêt d'une validation ou d'une exécution)</span><span class="sxs-lookup"><span data-stu-id="a6c0c-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="a6c0c-131">202</span><span class="sxs-lookup"><span data-stu-id="a6c0c-131">202</span></span>|  
|<span data-ttu-id="a6c0c-132">Valider le projet</span><span class="sxs-lookup"><span data-stu-id="a6c0c-132">Validate project</span></span>|<span data-ttu-id="a6c0c-133">300</span><span class="sxs-lookup"><span data-stu-id="a6c0c-133">300</span></span>|  
|<span data-ttu-id="a6c0c-134">Valider le package</span><span class="sxs-lookup"><span data-stu-id="a6c0c-134">Validate package</span></span>|<span data-ttu-id="a6c0c-135">301</span><span class="sxs-lookup"><span data-stu-id="a6c0c-135">301</span></span>|  
|<span data-ttu-id="a6c0c-136">Configurer le catalogue</span><span class="sxs-lookup"><span data-stu-id="a6c0c-136">Configure catalog</span></span>|<span data-ttu-id="a6c0c-137">1 000</span><span class="sxs-lookup"><span data-stu-id="a6c0c-137">1000</span></span>|  
  
 <span data-ttu-id="a6c0c-138">**Stop**</span><span class="sxs-lookup"><span data-stu-id="a6c0c-138">**Stop**</span></span>  
 <span data-ttu-id="a6c0c-139">Cliquez pour arrêter une opération en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="a6c0c-139">Click to stop a currently running operation.</span></span>  
  
  
