---
title: Boîte de dialogue Propriétés du projet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700140"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="9868a-102">Propriétés du projet, boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="9868a-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="9868a-103">Un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est une unité de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9868a-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="9868a-104">Chaque projet peut contenir des packages, des paramètres et des références d'environnement.</span><span class="sxs-lookup"><span data-stu-id="9868a-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="9868a-105">Un projet est un objet sécurisable et peut définir des autorisations pour les principaux de base de données.</span><span class="sxs-lookup"><span data-stu-id="9868a-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="9868a-106">Quand un projet est redéployé, la version précédente du projet peut être stockée dans le catalogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9868a-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="9868a-107">Les paramètres du projet et les paramètres du package peuvent être utilisés pour affecter des valeurs aux propriétés dans des packages au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9868a-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="9868a-108">Certains paramètres requièrent des valeurs avant que le package puisse être exécuté.</span><span class="sxs-lookup"><span data-stu-id="9868a-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="9868a-109">Les valeurs de paramètre qui référencent des variables d'environnement requièrent que le projet utilise la référence d'environnement correspondante avant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="9868a-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="9868a-110">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="9868a-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="9868a-111">Ouvrir la boîte de dialogue Propriétés du projet</span><span class="sxs-lookup"><span data-stu-id="9868a-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="9868a-112">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="9868a-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="9868a-113">Définir les options sur la page Autorisations</span><span class="sxs-lookup"><span data-stu-id="9868a-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="9868a-114">Ouvrir la boîte de dialogue Propriétés du projet</span><span class="sxs-lookup"><span data-stu-id="9868a-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="9868a-115">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9868a-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="9868a-116">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="9868a-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="9868a-117">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="9868a-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="9868a-118">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="9868a-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="9868a-119">Développez le dossier qui contient le projet dont vous souhaitez définir les propriétés.</span><span class="sxs-lookup"><span data-stu-id="9868a-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="9868a-120">Cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9868a-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="9868a-121">Définir les options sur la page Général</span><span class="sxs-lookup"><span data-stu-id="9868a-121">Set the options on the General page</span></span>  
 <span data-ttu-id="9868a-122">Utilisez la page Général pour afficher les propriétés du projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="9868a-123">**Nom**</span><span class="sxs-lookup"><span data-stu-id="9868a-123">**Name**</span></span>  
 <span data-ttu-id="9868a-124">Indique le nom du projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="9868a-125">**Identificateur**</span><span class="sxs-lookup"><span data-stu-id="9868a-125">**Identifier**</span></span>  
 <span data-ttu-id="9868a-126">Indique l'ID de projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="9868a-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="9868a-127">**Description**</span></span>  
 <span data-ttu-id="9868a-128">Affiche la description facultative du projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="9868a-129">**Version du projet**</span><span class="sxs-lookup"><span data-stu-id="9868a-129">**Project Version**</span></span>  
 <span data-ttu-id="9868a-130">Indique la version du projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="9868a-131">**Date du déploiement**</span><span class="sxs-lookup"><span data-stu-id="9868a-131">**Deployment Date**</span></span>  
 <span data-ttu-id="9868a-132">Indique la date et l'heure auxquelles le projet a été déployé ou redéployé.</span><span class="sxs-lookup"><span data-stu-id="9868a-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="9868a-133">Définir les options sur la page Autorisations</span><span class="sxs-lookup"><span data-stu-id="9868a-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="9868a-134">Utilisez la page **Autorisations** pour afficher et définir les autorisations explicites du projet.</span><span class="sxs-lookup"><span data-stu-id="9868a-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="9868a-135">...</span><span class="sxs-lookup"><span data-stu-id="9868a-135">Browse</span></span>  
 <span data-ttu-id="9868a-136">Cliquez sur **Parcourir** pour sélectionner les utilisateurs et les rôles auxquels vous souhaitez affecter des autorisations à l’aide de la boîte de dialogue **Parcourir tous les principaux** .</span><span class="sxs-lookup"><span data-stu-id="9868a-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="9868a-137">**Nom**</span><span class="sxs-lookup"><span data-stu-id="9868a-137">**Name**</span></span>  
 <span data-ttu-id="9868a-138">Indique le nom de l'utilisateur ou du rôle.</span><span class="sxs-lookup"><span data-stu-id="9868a-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="9868a-139">**Type**</span><span class="sxs-lookup"><span data-stu-id="9868a-139">**Type**</span></span>  
 <span data-ttu-id="9868a-140">Indique le type d'utilisateur ou de rôle.</span><span class="sxs-lookup"><span data-stu-id="9868a-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="9868a-141">**Permission**</span><span class="sxs-lookup"><span data-stu-id="9868a-141">**Permission**</span></span>  
 <span data-ttu-id="9868a-142">Indique les autorisations.</span><span class="sxs-lookup"><span data-stu-id="9868a-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="9868a-143">**Fournisseur d'autorisations**</span><span class="sxs-lookup"><span data-stu-id="9868a-143">**Grantor**</span></span>  
 <span data-ttu-id="9868a-144">Indique l'utilisateur ou le rôle qui accorde l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="9868a-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="9868a-145">**Octroyer**</span><span class="sxs-lookup"><span data-stu-id="9868a-145">**Grant**</span></span>  
 <span data-ttu-id="9868a-146">Si **Accorder** est sélectionné, l’autorisation est accordée à l’utilisateur ou au rôle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9868a-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="9868a-147">**Deny**</span><span class="sxs-lookup"><span data-stu-id="9868a-147">**Deny**</span></span>  
 <span data-ttu-id="9868a-148">Si **Refuser** est sélectionné, l’autorisation est refusée à l’utilisateur ou au rôle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9868a-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
