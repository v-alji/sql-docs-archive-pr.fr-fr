---
title: Boîte de dialogue Parcourir tous les principaux | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601635"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="37489-102">Parcourir tous les principaux, boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="37489-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="37489-103">Utilisez la boîte de dialogue **Parcourir tous les principaux** pour sélectionner un principal de base de données et modifier les autorisations du principal sur le projet sélectionné ou sur tous les projets contenus dans un dossier sélectionné.</span><span class="sxs-lookup"><span data-stu-id="37489-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="37489-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="37489-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="37489-105">Ouvrir la boîte de dialogue Parcourir tous les principaux</span><span class="sxs-lookup"><span data-stu-id="37489-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="37489-106">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="37489-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="37489-107">Ouvrir la boîte de dialogue Parcourir tous les principaux</span><span class="sxs-lookup"><span data-stu-id="37489-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="37489-108">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37489-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="37489-109">Vous devez vous connecter à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="37489-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="37489-110">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="37489-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="37489-111">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="37489-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="37489-112">Pour changer les autorisations du principal sur tous les projets contenus dans un dossier sélectionné, cliquez avec le bouton droit sur le dossier, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37489-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="37489-113">Pour changer les autorisations du principal sur un projet sélectionné, développez le dossier qui contient le projet, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37489-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="37489-114">Sélectionnez la page **Autorisations** , puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="37489-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="37489-115">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="37489-115">Configure the Options</span></span>  
 <span data-ttu-id="37489-116">Cette page affiche les principaux de la vue catalogue, sys.database_principals, de la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="37489-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="37489-117">La sélection de principaux les ajoute à la liste **Connexions ou rôles** dans la page **Autorisations** de la boîte de dialogue parent lorsque vous cliquez sur **OK** et fermez la boîte de dialogue **Parcourir tous les principaux** .</span><span class="sxs-lookup"><span data-stu-id="37489-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="37489-118">Après avoir ajouté des principaux à la liste **Connexions ou rôles** , vous pouvez modifier leurs autorisations sur le projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="37489-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="37489-119">**Sélection de colonne**</span><span class="sxs-lookup"><span data-stu-id="37489-119">**Selection column**</span></span>  
 <span data-ttu-id="37489-120">Sélectionnez cette option pour ajouter le principal à la liste **Connexions ou rôles** dans la page **Autorisations** de la boîte de dialogue parent.</span><span class="sxs-lookup"><span data-stu-id="37489-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="37489-121">**Colonne Icône**</span><span class="sxs-lookup"><span data-stu-id="37489-121">**Icon column**</span></span>  
 <span data-ttu-id="37489-122">Icône qui correspond au **Type** du principal.</span><span class="sxs-lookup"><span data-stu-id="37489-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="37489-123">**Nom**</span><span class="sxs-lookup"><span data-stu-id="37489-123">**Name**</span></span>  
 <span data-ttu-id="37489-124">Nom du principal.</span><span class="sxs-lookup"><span data-stu-id="37489-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="37489-125">**Type**</span><span class="sxs-lookup"><span data-stu-id="37489-125">**Type**</span></span>  
 <span data-ttu-id="37489-126">Type du principal.</span><span class="sxs-lookup"><span data-stu-id="37489-126">The type of the principal.</span></span> <span data-ttu-id="37489-127">Les types courants sont :</span><span class="sxs-lookup"><span data-stu-id="37489-127">The common types are:</span></span>  
  
-   <span data-ttu-id="37489-128">Utilisateur SQL</span><span class="sxs-lookup"><span data-stu-id="37489-128">SQL User</span></span>  
  
-   <span data-ttu-id="37489-129">Utilisateur Windows</span><span class="sxs-lookup"><span data-stu-id="37489-129">Windows User</span></span>  
  
-   <span data-ttu-id="37489-130">Rôle de base de données</span><span class="sxs-lookup"><span data-stu-id="37489-130">Database Role</span></span>  
  
  
