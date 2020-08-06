---
title: Boîte de dialogue Propriétés du package | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackageprop.general.f1
- sql12.ssis.ssms.packageproperties.f1
ms.assetid: a70acbf4-5f5c-4606-8ce4-8eb3684233de
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b386bf4e75ff784cd8d4a96363515786d242d2a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604091"
---
# <a name="package-properties-dialog-box"></a><span data-ttu-id="5cc1c-102">Propriétés du package, boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="5cc1c-102">Package Properties Dialog Box</span></span>
  <span data-ttu-id="5cc1c-103">Utilisez la boîte de dialogue **Propriétés du package** pour afficher et gérer les propriétés des packages stockés sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cc1c-103">Use the **Package Properties** dialog box to view properties for packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="5cc1c-104">Pour plus d’informations, consultez [Serveur Integration Services &#40;SSIS&#41;](integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="5cc1c-104">For more information, see [Integration Services &#40;SSIS&#41; Server](integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="5cc1c-105">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="5cc1c-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="5cc1c-106">Ouvrir la boîte de dialogue Propriétés du package</span><span class="sxs-lookup"><span data-stu-id="5cc1c-106">Open the Package Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="5cc1c-107">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="5cc1c-107">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-package-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="5cc1c-108">Ouvrir la boîte de dialogue Propriétés du package</span><span class="sxs-lookup"><span data-stu-id="5cc1c-108">Open the Package Properties dialog box</span></span>  
  
1.  <span data-ttu-id="5cc1c-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cc1c-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="5cc1c-110">Vous vous connectez à l’instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données SSISDB.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="5cc1c-111">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="5cc1c-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="5cc1c-112">Développez le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="5cc1c-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="5cc1c-113">Développez le dossier qui contient le package dont vous souhaitez afficher les propriétés.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-113">Expand the folder that contains the package you want to view properties for.</span></span>  
  
5.  <span data-ttu-id="5cc1c-114">Cliquez avec le bouton droit sur le package, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-114">Right-click the package, and then select **Properties**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="5cc1c-115">Configurer les options</span><span class="sxs-lookup"><span data-stu-id="5cc1c-115">Configure the Options</span></span>  
 <span data-ttu-id="5cc1c-116">Utilisez la page **Général** pour afficher les propriétés du package sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-116">Use the **General** page to view the properties of the selected package.</span></span>  
  
 <span data-ttu-id="5cc1c-117">Toutes les propriétés affichées dans la page **Général** sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-117">All properties on the **General** page are read-only.</span></span>  
  
 <span data-ttu-id="5cc1c-118">**Nom**</span><span class="sxs-lookup"><span data-stu-id="5cc1c-118">**Name**</span></span>  
 <span data-ttu-id="5cc1c-119">Affiche le nom du package.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-119">Displays the name of the package.</span></span>  
  
 <span data-ttu-id="5cc1c-120">**Identificateur**</span><span class="sxs-lookup"><span data-stu-id="5cc1c-120">**Identifier**</span></span>  
 <span data-ttu-id="5cc1c-121">Indique l'ID du package.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-121">Lists the package ID.</span></span>  
  
 <span data-ttu-id="5cc1c-122">**Point d’entrée**</span><span class="sxs-lookup"><span data-stu-id="5cc1c-122">**Entry Point**</span></span>  
 <span data-ttu-id="5cc1c-123">La valeur `True` indique que le package est démarré directement.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-123">The value of `True` indicates that the package is started directly.</span></span> <span data-ttu-id="5cc1c-124">La valeur `False` indique que le package est démarré par un autre package via la tâche d'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-124">The value of `False` indicates that the package is started by another package using the Execute Package task.</span></span> <span data-ttu-id="5cc1c-125">La valeur par défaut est `True`.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-125">The default value is `True`.</span></span>  
  
 <span data-ttu-id="5cc1c-126">Vous définissez cette propriété dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour les packages parent et enfant en cliquant avec le bouton droit sur le package dans l’Explorateur de solutions et en sélectionnant **Package de point d’entrée**.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-126">You set this property in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] for both the parent package and the child packages by right-clicking the package in Solution Explorer and then clicking **Entry-point Package**.</span></span>  
  
 <span data-ttu-id="5cc1c-127">**Description**</span><span class="sxs-lookup"><span data-stu-id="5cc1c-127">**Description**</span></span>  
 <span data-ttu-id="5cc1c-128">Affiche la description facultative du package.</span><span class="sxs-lookup"><span data-stu-id="5cc1c-128">Displays the optional description of the package.</span></span>  
  
  
