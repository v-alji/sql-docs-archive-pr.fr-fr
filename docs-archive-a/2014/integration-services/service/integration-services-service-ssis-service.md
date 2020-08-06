---
title: Service Integration Services (Service SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, about Integration Services service
- SQL Server Integration Services service
- service [Integration Services],about Integration Services service
- service [Integration Services]
- SQL Server Integration Services, service
ms.assetid: 2c785b3b-4a0c-4df7-b5cd-23756dc87842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 04b24f0f0d54009c50654904d606a208504f229c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709751"
---
# <a name="integration-services-service-ssis-service"></a><span data-ttu-id="aad71-102">Service Integration Services (Service SSIS)</span><span class="sxs-lookup"><span data-stu-id="aad71-102">Integration Services Service (SSIS Service)</span></span>
  <span data-ttu-id="aad71-103">Les rubriques de cette section décrivent le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , un service Windows de gestion des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aad71-103">The topics in this section discuss the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="aad71-104">Ce service n'est pas obligatoire pour créer, enregistrer et exécuter des packages Integration Services.</span><span class="sxs-lookup"><span data-stu-id="aad71-104">This service is not required to create, save, and run Integration Services packages.</span></span> [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] <span data-ttu-id="aad71-105">prend en charge le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aad71-105">supports the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="aad71-106">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stocke des objets, des paramètres et des données opérationnelles dans la `SSISDB` base de données pour les projets que vous avez déployés sur le [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] serveur à l’aide du modèle de déploiement de projet.</span><span class="sxs-lookup"><span data-stu-id="aad71-106">Starting in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] stores objects, settings, and operational data in the `SSISDB` database for projects that you've deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server using the project deployment model.</span></span> <span data-ttu-id="aad71-107">Le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , qui est une instance du moteur de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , héberge la base de données.</span><span class="sxs-lookup"><span data-stu-id="aad71-107">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, which is an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine, hosts the database.</span></span> <span data-ttu-id="aad71-108">Pour plus d’informations sur la base de données, consultez [Catalogue SSIS](../catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="aad71-108">For more information about the database, see [SSIS Catalog](../catalog/ssis-catalog.md).</span></span> <span data-ttu-id="aad71-109">Pour plus d’informations sur le déploiement de projets sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , consultez [Déployer des projets sur le serveur Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="aad71-109">For more information about deploying projects to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
## <a name="management-capabilities"></a><span data-ttu-id="aad71-110">Fonctionnalités de gestion</span><span class="sxs-lookup"><span data-stu-id="aad71-110">Management Capabilities</span></span>  
 <span data-ttu-id="aad71-111">Le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est un service Windows pour la gestion des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aad71-111">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is a Windows service for managing [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="aad71-112">Le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'est disponible que dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aad71-112">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is available only in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="aad71-113">L’exécution du service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] offre les fonctionnalités de gestion suivantes :</span><span class="sxs-lookup"><span data-stu-id="aad71-113">Running the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service provides the following management capabilities:</span></span>  
  
-   <span data-ttu-id="aad71-114">Démarrage des packages stockés localement et à distance</span><span class="sxs-lookup"><span data-stu-id="aad71-114">Starting remote and locally stored packages</span></span>  
  
-   <span data-ttu-id="aad71-115">Arrêt des packages exécutés localement et à distance</span><span class="sxs-lookup"><span data-stu-id="aad71-115">Stopping remote and locally running packages</span></span>  
  
-   <span data-ttu-id="aad71-116">Surveillance des packages exécutés localement et à distance</span><span class="sxs-lookup"><span data-stu-id="aad71-116">Monitoring remote and locally running packages</span></span>  
  
-   <span data-ttu-id="aad71-117">Importation et exportation de packages</span><span class="sxs-lookup"><span data-stu-id="aad71-117">Importing and exporting packages</span></span>  
  
-   <span data-ttu-id="aad71-118">Gestion du stockage des packages</span><span class="sxs-lookup"><span data-stu-id="aad71-118">Managing package storage</span></span>  
  
-   <span data-ttu-id="aad71-119">Personnalisation des dossiers de stockage</span><span class="sxs-lookup"><span data-stu-id="aad71-119">Customizing storage folders</span></span>  
  
-   <span data-ttu-id="aad71-120">Arrêt des packages exécutés si le service est arrêté</span><span class="sxs-lookup"><span data-stu-id="aad71-120">Stopping running packages when the service is stopped</span></span>  
  
-   <span data-ttu-id="aad71-121">Affichage du journal des événements Windows</span><span class="sxs-lookup"><span data-stu-id="aad71-121">Viewing the Windows Event log</span></span>  
  
-   <span data-ttu-id="aad71-122">Connexion à plusieurs serveurs [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aad71-122">Connecting to multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] servers</span></span>  
  
## <a name="startup-type-for-integration-services-service"></a><span data-ttu-id="aad71-123">Type de démarrage du service Integration Services</span><span class="sxs-lookup"><span data-stu-id="aad71-123">Startup Type for Integration Services Service</span></span>  
 <span data-ttu-id="aad71-124">Le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est installé quand vous installez le composant [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aad71-124">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is installed when you install the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aad71-125">Par défaut, le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] est démarré et le type de démarrage du service est défini comme étant automatique.</span><span class="sxs-lookup"><span data-stu-id="aad71-125">By default, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span> <span data-ttu-id="aad71-126">Le service doit être en cours d'exécution pour surveiller les packages stockés dans le magasin de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aad71-126">The service must be running to monitor the packages that are stored in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span> <span data-ttu-id="aad71-127">Le magasin de packages [!INCLUDE[ssIS](../../includes/ssis-md.md)] peut aussi bien être la base de données msdb dans une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que les dossiers désignés dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="aad71-127">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store can be either the msdb database in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the designated folders in the file system.</span></span>  
  
 <span data-ttu-id="aad71-128">Le service [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n’est pas nécessaire si vous souhaitez seulement concevoir et exécuter des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aad71-128">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service is not required if you only want to design and execute [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="aad71-129">Cependant, le service est nécessaire pour répertorier et surveiller les packages à l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aad71-129">However, the service is required to list and monitor packages using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="aad71-130">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="aad71-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="aad71-131">définir les propriétés du service Integration Services</span><span class="sxs-lookup"><span data-stu-id="aad71-131">Set the Properties of the Integration Services Service</span></span>](../set-the-properties-of-the-integration-services-service.md)  
  
-   [<span data-ttu-id="aad71-132">afficher les événements du service Integration Services</span><span class="sxs-lookup"><span data-stu-id="aad71-132">View Events for the Integration Services Service</span></span>](../view-events-for-the-integration-services-service.md)  
  
  
