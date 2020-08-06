---
title: Définir des dimensions de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696247"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="3b309-102">Définir des dimensions de base de données</span><span class="sxs-lookup"><span data-stu-id="3b309-102">Define Database Dimensions</span></span>
  <span data-ttu-id="3b309-103">Utilisez le concepteur de dimensions dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour configurer une dimension de base de données existante dans un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet ou une base de données.</span><span class="sxs-lookup"><span data-stu-id="3b309-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="3b309-104">Le Concepteur de dimensions permet d'effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="3b309-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="3b309-105">Configuration des propriétés de niveau dimension.</span><span class="sxs-lookup"><span data-stu-id="3b309-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="3b309-106">Ajout et configuration des attributs de dimension.</span><span class="sxs-lookup"><span data-stu-id="3b309-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="3b309-107">Définition et configuration de hiérarchies définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b309-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="3b309-108">Définition et configuration de relations entre attributs.</span><span class="sxs-lookup"><span data-stu-id="3b309-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="3b309-109">Définition de traductions de dimensions.</span><span class="sxs-lookup"><span data-stu-id="3b309-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="3b309-110">Pour les dimensions traitées, vous pouvez parcourir la structure de la dimension et consulter les données.</span><span class="sxs-lookup"><span data-stu-id="3b309-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="3b309-111">Après avoir modifié une dimension, un attribut ou une hiérarchie, vous devez traiter cette dimension pour pouvoir afficher les modifications.</span><span class="sxs-lookup"><span data-stu-id="3b309-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="3b309-112">Quand vous travaillez en mode projet, vous déployez les modifications sur l’instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] avant le traitement.</span><span class="sxs-lookup"><span data-stu-id="3b309-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="3b309-113">Pour plus d’informations sur l’ouverture d’une dimension dans le Concepteur de dimensions, consultez [Modifier ou supprimer une dimension de base de données dans l’Explorateur de solutions](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="3b309-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="3b309-114">Le Concepteur de dimensions contient trois onglets différents qui sont décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3b309-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="3b309-115">Onglet</span><span class="sxs-lookup"><span data-stu-id="3b309-115">Tab</span></span>|<span data-ttu-id="3b309-116">Description</span><span class="sxs-lookup"><span data-stu-id="3b309-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="3b309-117">**Structure de la dimension**</span><span class="sxs-lookup"><span data-stu-id="3b309-117">**Dimension Structure**</span></span>|<span data-ttu-id="3b309-118">Utilisez cet onglet pour travailler avec la structure d’une dimension, pour examiner ou créer le schéma de vue de source de données d’une dimension, pour utiliser des attributs et pour organiser les attributs dans des hiérarchies définies par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b309-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="3b309-119">**Relations d’attributs**</span><span class="sxs-lookup"><span data-stu-id="3b309-119">**Attribute Relationships**</span></span>|<span data-ttu-id="3b309-120">Cet onglet permet de créer, de modifier ou de supprimer les relations d'attributs d'une dimension.</span><span class="sxs-lookup"><span data-stu-id="3b309-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="3b309-121">**Translations**</span><span class="sxs-lookup"><span data-stu-id="3b309-121">**Translations**</span></span>|<span data-ttu-id="3b309-122">Cet onglet vous permet d'ajouter et de modifier des traductions de métadonnées de dimensions dans différentes langues.</span><span class="sxs-lookup"><span data-stu-id="3b309-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="3b309-123">**Browser**</span><span class="sxs-lookup"><span data-stu-id="3b309-123">**Browser**</span></span>|<span data-ttu-id="3b309-124">Cet onglet vous permet d'examiner les membres d'une dimension traitée et les traductions des métadonnées de dimensions.</span><span class="sxs-lookup"><span data-stu-id="3b309-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="3b309-125">Les rubriques suivantes décrivent les tâches que vous pouvez effectuer dans le Concepteur de dimensions.</span><span class="sxs-lookup"><span data-stu-id="3b309-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="3b309-126">Référence des propriétés d’attribut de dimension</span><span class="sxs-lookup"><span data-stu-id="3b309-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="3b309-127">Décrit comment définir et configurer un attribut de dimension.</span><span class="sxs-lookup"><span data-stu-id="3b309-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="3b309-128">Créer des hiérarchies définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="3b309-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="3b309-129">Décrit comment définir et configurer une hiérarchie définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3b309-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="3b309-130">Définir des relations d'attributs</span><span class="sxs-lookup"><span data-stu-id="3b309-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="3b309-131">Décrit comment définir et configurer une relation d'attribut.</span><span class="sxs-lookup"><span data-stu-id="3b309-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="3b309-132">Utiliser l’Assistant Business Intelligence pour améliorer des dimensions</span><span class="sxs-lookup"><span data-stu-id="3b309-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="3b309-133">Décrit comment utiliser l'Assistant Business Intelligence pour améliorer une dimension.</span><span class="sxs-lookup"><span data-stu-id="3b309-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
