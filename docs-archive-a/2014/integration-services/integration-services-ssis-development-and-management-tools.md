---
title: Integration Services (SSIS) et environnements de Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- studio environments [Integration Services]
- tools [Integration Services], Business Intelligence Development Studio
- Business Intelligence Development Studio, Integration Services in
- SQL Server Management Studio [Integration Services]
- SSIS, studio environments
- SQL Server Integration Services, studio environments
- tools [Integration Services], SQL Server Management Studio
ms.assetid: 4eb73e65-d9f3-4ac6-a408-abfa85afc537
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfe0cf7ef482dce3870db8c730c597daf1d539e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605621"
---
# <a name="integration-services-ssis-and-studio-environments"></a><span data-ttu-id="91a8b-102">Integration Services (SSIS) et environnements de Studio</span><span class="sxs-lookup"><span data-stu-id="91a8b-102">Integration Services (SSIS) and Studio Environments</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="91a8b-103">inclut deux studios de travail pour travailler avec [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="91a8b-103">includes two studios for working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="91a8b-104">pour le développement des packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] requis par une solution métier.</span><span class="sxs-lookup"><span data-stu-id="91a8b-104">for developing the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that a business solution requires.</span></span> [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="91a8b-105">fournit le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans lequel vous créez des packages.</span><span class="sxs-lookup"><span data-stu-id="91a8b-105">provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you create packages.</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="91a8b-106">pour la gestion de packages dans un environnement de production.</span><span class="sxs-lookup"><span data-stu-id="91a8b-106">for managing packages in a production environment.</span></span>  
  
## <a name="sql-server-data-tools"></a><span data-ttu-id="91a8b-107">SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="91a8b-107">SQL Server Data Tools</span></span>  
 <span data-ttu-id="91a8b-108">Vous pouvez réaliser les tâches suivantes dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="91a8b-108">Working in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="91a8b-109">exécuter l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour créer des packages de base qui copient des données entre une source et une destination ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-109">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to create basic packages that copy data from a source to a destination.</span></span>  
  
-   <span data-ttu-id="91a8b-110">créer des packages qui incluent un flux de contrôle complexe, un flux de données, une logique piloté par les événements et la journalisation ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-110">Create packages that include complex control flow, data flow, event-driven logic, and logging.</span></span>  
  
-   <span data-ttu-id="91a8b-111">tester et déboguer les packages à l'aide des fonctionnalités de résolution des problèmes et de surveillance du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] et des fonctionnalités de débogage de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)];</span><span class="sxs-lookup"><span data-stu-id="91a8b-111">Test and debug packages by using the troubleshooting and monitoring features in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, and the debugging features in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="91a8b-112">créer des configurations qui mettent à jour les propriétés des packages et les objets de package au moment de l'exécution ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-112">Create configurations that update the properties of packages and package objects at run time.</span></span>  
  
-   <span data-ttu-id="91a8b-113">créer un utilitaire de déploiement qui peut installer les packages et leurs dépendances sur d'autres ordinateurs ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-113">Create a deployment utility that can install packages and their dependencies on other computers.</span></span>  
  
-   <span data-ttu-id="91a8b-114">enregistrer des copies des packages dans la base de données msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], le magasin de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] et le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="91a8b-114">Save copies of packages to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
 <span data-ttu-id="91a8b-115">Pour plus d'informations sur [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], consultez [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span><span class="sxs-lookup"><span data-stu-id="91a8b-115">For more information about [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], see [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="91a8b-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="91a8b-116">SQL Server Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="91a8b-117">fournit le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que vous utilisez pour gérer des packages, surveiller les packages en cours d'exécution, et déterminer l'impact et le lignage des données pour les objets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91a8b-117">provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that you use to manage packages, monitor running packages, and determine impact and data lineage for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="91a8b-118">Vous pouvez réaliser les tâches suivantes dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="91a8b-118">Working in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="91a8b-119">créer des dossiers pour organiser les packages de manière significative pour votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-119">Create folders to organize packages in a way that is meaningful to your organization.</span></span>  
  
-   <span data-ttu-id="91a8b-120">exécuter les packages stockés sur l'ordinateur local à l'aide de l'utilitaire d'exécution de package ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-120">Run packages that are stored on the local computer by using the Execute Package utility.</span></span>  
  
-   <span data-ttu-id="91a8b-121">exécuter l’utilitaire d’exécution de package pour générer une ligne de commande à utiliser lors de l’exécution de l’utilitaire de ligne de commande **dtexec** (dtexec.exe) ;</span><span class="sxs-lookup"><span data-stu-id="91a8b-121">Run the Execute Package utility to generate a command line to use when you run the **dtexec** command prompt utility (dtexec.exe).</span></span>  
  
-   <span data-ttu-id="91a8b-122">importer et exporter des packages dans la base de données msdb [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], la banque de packages [!INCLUDE[ssIS](../includes/ssis-md.md)] et le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="91a8b-122">Import and export packages to and from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
