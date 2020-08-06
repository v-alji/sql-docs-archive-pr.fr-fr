---
title: Contrôle de code source Explorateur de solutions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Visual SourceSafe
- SQL Server Management Studio [SQL Server], source control services
- source-controlled files [SQL Server]
- source controls [SQL Server Management Studio], services
- version control services [SQL Server]
- file source control services [SQL Server]
- VSS [Visual SourceSafe]
ms.assetid: 6373adb8-3d81-4945-a9fc-1d0d5799d29a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46471ba8149c26f80e78006bc3a8befc2e81b416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611940"
---
# <a name="solution-explorer-source-control"></a><span data-ttu-id="84156-102">Contrôle de code source de l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="84156-102">Solution Explorer Source Control</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="84156-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Explorateur de solutions peut être intégré à un système de contrôle de code source distinct.</span><span class="sxs-lookup"><span data-stu-id="84156-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Solution Explorer can be integrated into a separate source control system.</span></span> <span data-ttu-id="84156-104">Après intégration d'une solution ou d'un projet à un système de contrôle de code source, vous pouvez contrôler l'accès aux fichiers et les versions pour les scripts et les requêtes de vos projets.</span><span class="sxs-lookup"><span data-stu-id="84156-104">Once a solution or project is integrated into a source control system, you can control file access and versioning for the scripts and queries in your projects.</span></span>  
  
## <a name="solution-and-project-source-control"></a><span data-ttu-id="84156-105">Contrôle de code source de solution et de projet</span><span class="sxs-lookup"><span data-stu-id="84156-105">Solution and Project Source Control</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="84156-106">Le contrôle de code source fait référence à un système dans lequel un logiciel serveur central stocke et effectue le suivi des versions de fichiers et contrôle l'accès aux fichiers.</span><span class="sxs-lookup"><span data-stu-id="84156-106">Source control refers to a system in which a central piece of server software stores and tracks file versions, and also controls access to files.</span></span> <span data-ttu-id="84156-107">Un système de contrôle de code source comprend généralement un fournisseur de contrôle de code source et deux (voire plus) clients de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-107">A typical source control system includes a source control provider and two or more source control clients.</span></span> [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="84156-108">peut être intégré à un service de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-108">can be integrated with a source control service.</span></span> <span data-ttu-id="84156-109">Cela signifie que vous pouvez utiliser cet outil comme client pour votre fournisseur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-109">This means you can use the tool as a client for your source control provider.</span></span> <span data-ttu-id="84156-110">Sans quitter votre environnement, vous êtes ainsi en mesure de gérer en toute facilité vos projets individuels et collaboratifs.</span><span class="sxs-lookup"><span data-stu-id="84156-110">Without leaving the environment, you can manage your individual and team projects easily.</span></span> <span data-ttu-id="84156-111">Le fournisseur de contrôle du code source n'est pas inclus dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84156-111">The source control provider is not included with [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
#### <a name="to-select-a-source-control-provider"></a><span data-ttu-id="84156-112">Pour sélectionner un fournisseur de contrôle du code source</span><span class="sxs-lookup"><span data-stu-id="84156-112">To select a source control provider</span></span>  
  
1.  <span data-ttu-id="84156-113">Installez la partie cliente de votre fournisseur de contrôle du code source.</span><span class="sxs-lookup"><span data-stu-id="84156-113">Install the client portion of your source control provider.</span></span>  
  
2.  <span data-ttu-id="84156-114">Dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], dans le menu **Outils** , cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="84156-114">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="84156-115">Dans la boîte de dialogue **options** , développez **contrôle de code source**, puis cliquez sur la page **sélection du plug-** in.</span><span class="sxs-lookup"><span data-stu-id="84156-115">In the **Options** dialog box, expand **Source Control**, and then click the **Plug-in Selection** page.</span></span>  
  
4.  <span data-ttu-id="84156-116">Dans la zone plug-in de **contrôle de code source actuel** , sélectionnez le plug-in de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-116">In the **Current source control plug-in** box, select the source control plug-in.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84156-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="84156-117">In This Section</span></span>  
  
|<span data-ttu-id="84156-118">Rubrique</span><span class="sxs-lookup"><span data-stu-id="84156-118">Topic</span></span>|<span data-ttu-id="84156-119">Description</span><span class="sxs-lookup"><span data-stu-id="84156-119">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="84156-120">Présentation du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="84156-120">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)|<span data-ttu-id="84156-121">Indique la terminologie de base du contrôle de code source et détermine les avantages présentés par les services de contrôle de code source dans le cadre d'un projet.</span><span class="sxs-lookup"><span data-stu-id="84156-121">Defines basic source control terminology, and explains how your project can benefit from using source control services.</span></span>|  
|[<span data-ttu-id="84156-122">Ajouter des solutions et des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="84156-122">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)|<span data-ttu-id="84156-123">Explique comment utiliser l'environnement [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] pour ajouter des solutions et des projets au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-123">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to add solutions and projects to source control.</span></span>|  
|[<span data-ttu-id="84156-124">Ouvrir des solutions et des projets à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="84156-124">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)|<span data-ttu-id="84156-125">Explique comment utiliser l'environnement [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] pour ouvrir des solutions et des projets sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-125">Explains how to use the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment to open source-controlled solutions and projects.</span></span>|  
|[<span data-ttu-id="84156-126">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="84156-126">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)|<span data-ttu-id="84156-127">Indique le mode d'extraction de solutions et de fichiers du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-127">Explains how to check out solutions and files from source control.</span></span>|  
|[<span data-ttu-id="84156-128">Gérer les archivages</span><span class="sxs-lookup"><span data-stu-id="84156-128">Manage Checkins</span></span>](../../2014/database-engine/manage-checkins.md)|<span data-ttu-id="84156-129">Indique le mode d'archivage de solutions et de fichiers dans le contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="84156-129">Explains how to check solutions and files into source control.</span></span>|  
|[<span data-ttu-id="84156-130">Définir et récupérer des informations sur la version</span><span class="sxs-lookup"><span data-stu-id="84156-130">Set and Retrieve Version Information</span></span>](../../2014/database-engine/set-and-retrieve-version-information.md)|<span data-ttu-id="84156-131">Indique le mode de récupération de l'historique d'un projet ou d'un élément, le mode de récupération d'une copie locale d'un élément et le mode de comparaison de deux versions d'un élément.</span><span class="sxs-lookup"><span data-stu-id="84156-131">Explains how to retrieve the history of a project or item, retrieve a local copy of an item, or compare two item versions.</span></span>|  
|||  
  
## <a name="see-also"></a><span data-ttu-id="84156-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="84156-132">See Also</span></span>  
 <span data-ttu-id="84156-133">[Explorateur de solutions](../ssms/solution/solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="84156-133">[Solution Explorer](../ssms/solution/solution-explorer.md) </span></span>  
 <span data-ttu-id="84156-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="84156-134">[Solutions &#40;SQL Server Management Studio&#41;](../ssms/sql-server-management-studio-ssms.md) </span></span>  
 <span data-ttu-id="84156-135">[Projets &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="84156-135">[Projects &#40;SQL Server Management Studio&#41;](../ssms/solution/projects-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="84156-136">Fichiers gérant les solutions et les projets</span><span class="sxs-lookup"><span data-stu-id="84156-136">Files That Manage Solutions and Projects</span></span>](../ssms/solution/files-that-manage-solutions-and-projects.md)  
  
  
