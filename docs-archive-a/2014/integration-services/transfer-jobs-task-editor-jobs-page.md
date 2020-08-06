---
title: Éditeur de tâche de transfert de travaux (page travaux) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferjobstask.jobs.f1
helpviewer_keywords:
- Transfer Jobs Task Editor
ms.assetid: e72b1dc7-8cda-4ee6-abb5-d438370f04df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d2d506da6997965e40d66521f7dccb8218e165fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615207"
---
# <a name="transfer-jobs-task-editor-jobs-page"></a><span data-ttu-id="5339c-102">Éditeur de tâche de transfert de travaux (page Travaux)</span><span class="sxs-lookup"><span data-stu-id="5339c-102">Transfer Jobs Task Editor (Jobs Page)</span></span>
  <span data-ttu-id="5339c-103">Utilisez la page **Travaux** de la boîte de dialogue **Éditeur de tâche de transfert de travaux** pour spécifier les propriétés de copie d’un ou plusieurs travaux [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à une autre.</span><span class="sxs-lookup"><span data-stu-id="5339c-103">Use the **Jobs** page of the **Transfer Jobs Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="5339c-104">Pour plus d'informations sur la tâche de transfert de travaux, consultez [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span><span class="sxs-lookup"><span data-stu-id="5339c-104">For more information about the Transfer Jobs task, see [Transfer Jobs Task](control-flow/transfer-jobs-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5339c-105">Pour accéder à des travaux sur le serveur source, les utilisateurs doivent au moins y être membres du rôle de base de données fixe **SQLAgentUserRole** .</span><span class="sxs-lookup"><span data-stu-id="5339c-105">To access jobs on the source server, users must be a member of at least the **SQLAgentUserRole** fixed database role on the server.</span></span> <span data-ttu-id="5339c-106">Pour créer des travaux sur le serveur de destination, l’utilisateur doit être membre du rôle serveur fixe **sysadmin** ou de l’un des rôles de base de données fixe de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="5339c-106">To successfully create jobs on the destination server, the user must be a member of the **sysadmin** fixed server role or one of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles.</span></span> <span data-ttu-id="5339c-107">Pour plus d’informations sur les rôles de base de données fixe de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent et leurs autorisations, consultez [Rôles de base de données fixe de l’Agent SQL Server](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5339c-107">For more information about [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent fixed database roles and their permissions, see [SQL Server Agent Fixed Database Roles](../ssms/agent/sql-server-agent-fixed-database-roles.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5339c-108">Options</span><span class="sxs-lookup"><span data-stu-id="5339c-108">Options</span></span>  
 <span data-ttu-id="5339c-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="5339c-109">**SourceConnection**</span></span>  
 <span data-ttu-id="5339c-110">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="5339c-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="5339c-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="5339c-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="5339c-112">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="5339c-113">**TransferAllJobs**</span><span class="sxs-lookup"><span data-stu-id="5339c-113">**TransferAllJobs**</span></span>  
 <span data-ttu-id="5339c-114">Déterminez si la tâche doit copier du serveur source au serveur de destination tous les travaux de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou seulement ceux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5339c-114">Select whether the task should copy all or only the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs from the source to the destination server.</span></span>  
  
 <span data-ttu-id="5339c-115">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="5339c-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="5339c-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="5339c-116">Value</span></span>|<span data-ttu-id="5339c-117">Description</span><span class="sxs-lookup"><span data-stu-id="5339c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5339c-118">**True**</span><span class="sxs-lookup"><span data-stu-id="5339c-118">**True**</span></span>|<span data-ttu-id="5339c-119">Copie tous les travaux.</span><span class="sxs-lookup"><span data-stu-id="5339c-119">Copy all jobs.</span></span>|  
|<span data-ttu-id="5339c-120">**False**</span><span class="sxs-lookup"><span data-stu-id="5339c-120">**False**</span></span>|<span data-ttu-id="5339c-121">Copie uniquement les travaux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="5339c-121">Copy only the specified jobs.</span></span>|  
  
 <span data-ttu-id="5339c-122">**JobsList**</span><span class="sxs-lookup"><span data-stu-id="5339c-122">**JobsList**</span></span>  
 <span data-ttu-id="5339c-123">Cliquez sur le bouton Parcourir **(...)** pour sélectionner les travaux à copier.</span><span class="sxs-lookup"><span data-stu-id="5339c-123">Click the browse button **(...)** to select the jobs to copy.</span></span> <span data-ttu-id="5339c-124">Un travail au moins doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5339c-124">At least one job must be selected.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5339c-125">Spécifiez **SourceConnection** avant de sélectionner les travaux à copier.</span><span class="sxs-lookup"><span data-stu-id="5339c-125">Specify the **SourceConnection** before selecting jobs to copy.</span></span>  
  
 <span data-ttu-id="5339c-126">L’option **JobsList** n’est pas disponible quand **TransferAllJobs** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="5339c-126">The **JobsList** option is unavailable when **TransferAllJobs** is set to **True**.</span></span>  
  
 <span data-ttu-id="5339c-127">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="5339c-127">**IfObjectExists**</span></span>  
 <span data-ttu-id="5339c-128">Sélectionnez la façon dont la tâche doit gérer les travaux de même nom que ceux existant sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-128">Select how the task should handle jobs of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="5339c-129">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="5339c-129">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="5339c-130">Valeur</span><span class="sxs-lookup"><span data-stu-id="5339c-130">Value</span></span>|<span data-ttu-id="5339c-131">Description</span><span class="sxs-lookup"><span data-stu-id="5339c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5339c-132">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="5339c-132">**FailTask**</span></span>|<span data-ttu-id="5339c-133">La tâche échoue si des travaux de même nom existent déjà sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-133">Task fails if jobs of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="5339c-134">**Remplacer**</span><span class="sxs-lookup"><span data-stu-id="5339c-134">**Overwrite**</span></span>|<span data-ttu-id="5339c-135">La tâche remplace les travaux de même nom sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-135">Task overwrites jobs of the same name on the destination server.</span></span>|  
|<span data-ttu-id="5339c-136">**Skip**</span><span class="sxs-lookup"><span data-stu-id="5339c-136">**Skip**</span></span>|<span data-ttu-id="5339c-137">La tâche ignore les travaux de même nom qui existent sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-137">Task skips jobs of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="5339c-138">**EnableJobsAtDestination**</span><span class="sxs-lookup"><span data-stu-id="5339c-138">**EnableJobsAtDestination**</span></span>  
 <span data-ttu-id="5339c-139">Déterminez si les travaux copiés sur le serveur de destination doivent être activés.</span><span class="sxs-lookup"><span data-stu-id="5339c-139">Select whether the jobs copied to the destination server should be enabled.</span></span>  
  
 <span data-ttu-id="5339c-140">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="5339c-140">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="5339c-141">Valeur</span><span class="sxs-lookup"><span data-stu-id="5339c-141">Value</span></span>|<span data-ttu-id="5339c-142">Description</span><span class="sxs-lookup"><span data-stu-id="5339c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5339c-143">**True**</span><span class="sxs-lookup"><span data-stu-id="5339c-143">**True**</span></span>|<span data-ttu-id="5339c-144">Active les travaux sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-144">Enable jobs on destination server.</span></span>|  
|<span data-ttu-id="5339c-145">**False**</span><span class="sxs-lookup"><span data-stu-id="5339c-145">**False**</span></span>|<span data-ttu-id="5339c-146">Désactive les travaux sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="5339c-146">Disable jobs on destination server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5339c-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5339c-147">See Also</span></span>  
 <span data-ttu-id="5339c-148">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5339c-148">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5339c-149">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="5339c-149">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="5339c-150">[Éditeur de tâche de transfert de travaux &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5339c-150">[Transfer Jobs Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="5339c-151">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="5339c-151">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="5339c-152">Gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="5339c-152">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
