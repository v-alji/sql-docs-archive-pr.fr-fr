---
title: Propriétés du travail et nouveau travail (page général) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699185"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="c8ece-102">Propriétés du travail et Nouveau travail (page Général)</span><span class="sxs-lookup"><span data-stu-id="c8ece-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="c8ece-103">Utilisez cette page pour afficher et modifier les propriétés générales d’un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travail de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c8ece-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8ece-104">Options</span><span class="sxs-lookup"><span data-stu-id="c8ece-104">Options</span></span>  
 <span data-ttu-id="c8ece-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="c8ece-105">**Name**</span></span>  
 <span data-ttu-id="c8ece-106">Permet de modifier le nom du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="c8ece-107">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="c8ece-107">**Owner**</span></span>  
 <span data-ttu-id="c8ece-108">Permet de sélectionner le propriétaire du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="c8ece-109">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="c8ece-109">**Category**</span></span>  
 <span data-ttu-id="c8ece-110">Permet de sélectionner la catégorie du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="c8ece-111">**...**</span><span class="sxs-lookup"><span data-stu-id="c8ece-111">**...**</span></span>  
 <span data-ttu-id="c8ece-112">Affiche les travaux de la catégorie sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c8ece-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="c8ece-113">**Description**</span><span class="sxs-lookup"><span data-stu-id="c8ece-113">**Description**</span></span>  
 <span data-ttu-id="c8ece-114">Permet de modifier la description du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="c8ece-115">**Activé**</span><span class="sxs-lookup"><span data-stu-id="c8ece-115">**Enabled**</span></span>  
 <span data-ttu-id="c8ece-116">Permet d'activer le travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-116">Enable the job.</span></span> <span data-ttu-id="c8ece-117">Quand le travail n’est pas activé, il ne s’exécute pas en réponse à une planification ou une alerte, mais vous pouvez toujours le démarrer à l’aide de la procédure stockée **sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="c8ece-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="c8ece-118">**Source**</span><span class="sxs-lookup"><span data-stu-id="c8ece-118">**Source**</span></span>  
 <span data-ttu-id="c8ece-119">Affiche le serveur principal du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-119">Displays the master server for the job.</span></span> <span data-ttu-id="c8ece-120">Cette option est disponible uniquement dans la page **Général** des Propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="c8ece-121">**Créé le**</span><span class="sxs-lookup"><span data-stu-id="c8ece-121">**Created**</span></span>  
 <span data-ttu-id="c8ece-122">Affiche la date et l'heure de création du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="c8ece-123">Cette option est disponible uniquement dans la page **Général** des Propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="c8ece-124">**Date de la dernière modification**</span><span class="sxs-lookup"><span data-stu-id="c8ece-124">**Last modified**</span></span>  
 <span data-ttu-id="c8ece-125">Affiche la date et l'heure de la dernière modification du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="c8ece-126">Cette option est disponible uniquement dans la page **Général** des Propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="c8ece-127">**Dernière exécution**</span><span class="sxs-lookup"><span data-stu-id="c8ece-127">**Last executed**</span></span>  
 <span data-ttu-id="c8ece-128">Affiche la date et l'heure de la dernière exécution du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="c8ece-129">Cette option est disponible uniquement dans la page **Général** des Propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="c8ece-130">**Afficher l’historique des travaux**</span><span class="sxs-lookup"><span data-stu-id="c8ece-130">**View Job History**</span></span>  
 <span data-ttu-id="c8ece-131">Affiche l'historique des travaux.</span><span class="sxs-lookup"><span data-stu-id="c8ece-131">View the job history for the job.</span></span> <span data-ttu-id="c8ece-132">Cette option est disponible uniquement dans la page **Général** des Propriétés du travail.</span><span class="sxs-lookup"><span data-stu-id="c8ece-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ece-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8ece-133">See Also</span></span>  
 <span data-ttu-id="c8ece-134">[Implémenter des travaux](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="c8ece-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="c8ece-135">Catégories de travaux : Gérer les catégories de travaux</span><span class="sxs-lookup"><span data-stu-id="c8ece-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
