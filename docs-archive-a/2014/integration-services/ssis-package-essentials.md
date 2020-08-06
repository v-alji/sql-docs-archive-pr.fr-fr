---
title: Notions fondamentales sur le package SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703148"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="a8a12-102">Notions fondamentales sur le package SSIS</span><span class="sxs-lookup"><span data-stu-id="a8a12-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="a8a12-103">Un package est l'objet qui implémente les fonctionnalités [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour extraire, transformer et charger des données.</span><span class="sxs-lookup"><span data-stu-id="a8a12-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="a8a12-104">Vous créez un package en utilisant le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8a12-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="a8a12-105">Vous pouvez aussi créer un package en exécutant l'Assistant Importation et Exportation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou l'Assistant Projet de connexions [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8a12-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="a8a12-106">Pour plus d’informations, [créez des packages dans SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) dans le concepteur SSIS et l' [Assistant importation de projet](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a8a12-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="a8a12-107">Un package de base inclut les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a8a12-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="a8a12-108">**Éléments de flux de contrôle**</span><span class="sxs-lookup"><span data-stu-id="a8a12-108">**Control flow elements**</span></span>  
 <span data-ttu-id="a8a12-109">Ces éléments requis effectuent différentes fonctions, fournissent une structure et contrôlent l'ordre dans lequel les éléments s'exécutent.</span><span class="sxs-lookup"><span data-stu-id="a8a12-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="a8a12-110">Les éléments de flux de contrôle principaux sont les tâches, les conteneurs et les contraintes de précédence.</span><span class="sxs-lookup"><span data-stu-id="a8a12-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="a8a12-111">Il doit y avoir au moins un élément de flux de contrôle dans un package.</span><span class="sxs-lookup"><span data-stu-id="a8a12-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="a8a12-112">Pour plus d’informations, consultez [Control Flow](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a8a12-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="a8a12-113">**Éléments de flux de données**</span><span class="sxs-lookup"><span data-stu-id="a8a12-113">**Data flow elements**</span></span>  
 <span data-ttu-id="a8a12-114">Ces éléments facultatifs extraient, modifient et chargent des données dans des sources de données.</span><span class="sxs-lookup"><span data-stu-id="a8a12-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="a8a12-115">Les principaux éléments de flux de données sont les sources, les transformations et les destinations.</span><span class="sxs-lookup"><span data-stu-id="a8a12-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="a8a12-116">Il n'est pas nécessaire qu'un package contienne des éléments de flux de données.</span><span class="sxs-lookup"><span data-stu-id="a8a12-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="a8a12-117">Pour en savoir plus, voir [Data Flow](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="a8a12-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="a8a12-118">Pour obtenir un exemple de création d’un package de base, consultez [la leçon 1 : création du projet et du package de base](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="a8a12-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a8a12-119">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a8a12-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a8a12-120">Créer des packages dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="a8a12-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="a8a12-121">Ajouter ou supprimer une tâche ou un conteneur dans un flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="a8a12-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="a8a12-122">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="a8a12-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="a8a12-123">Ajouter ou supprimer un composant dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="a8a12-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="a8a12-124">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="a8a12-124">Related Content</span></span>  
  
1.  <span data-ttu-id="a8a12-125">Vidéo, [Création d’un package de base (vidéo liée à SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131023)sur MSDN.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a8a12-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a12-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8a12-126">See Also</span></span>  
 <span data-ttu-id="a8a12-127">[Integration Services &#40;des packages de&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a8a12-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="a8a12-128">Contraintes de précédence</span><span class="sxs-lookup"><span data-stu-id="a8a12-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
