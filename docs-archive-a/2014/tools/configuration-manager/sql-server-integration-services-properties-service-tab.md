---
title: Propriétés de SQL Server Integration Services (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 37f0acd9-c96f-48fd-9b53-2ca0097af242
author: stevestein
ms.author: sstein
ms.openlocfilehash: a752bdeab3c99ac97445e3281d3165a2d8f79866
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613711"
---
# <a name="sql-server-integration-services-properties-service-tab"></a><span data-ttu-id="11b15-102">Propriétés de SQL Server Integration Services (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="11b15-102">SQL Server Integration Services Properties (Service Tab)</span></span>
  <span data-ttu-id="11b15-103">Utilisez l’onglet **Service** de la boîte de dialogue [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Propriétés** pour afficher ou spécifier les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="11b15-103">Use the **Service**tab on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="11b15-104">Options</span><span class="sxs-lookup"><span data-stu-id="11b15-104">Options</span></span>  
 <span data-ttu-id="11b15-105">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="11b15-105">**Binary Path**</span></span>  
 <span data-ttu-id="11b15-106">Affiche l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="11b15-106">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="11b15-107">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="11b15-107">**Error Control**</span></span>  
 <span data-ttu-id="11b15-108">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="11b15-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="11b15-109">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="11b15-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="11b15-110">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="11b15-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="11b15-111">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="11b15-111">**Exit Code**</span></span>  
 <span data-ttu-id="11b15-112">Code d’erreur [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows définissant tout problème rencontré au démarrage ou à l’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="11b15-112">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows error code defining any problems encountered in starting or stopping the service.</span></span> <span data-ttu-id="11b15-113">Cette propriété a pour valeur **ERROR_SERVICE_SPECIFIC_ERROR** (1066) quand l’erreur est unique pour le service représenté par cette classe, et les informations sur l’erreur sont disponibles dans la propriété **ServiceSpecificExitCode** .</span><span class="sxs-lookup"><span data-stu-id="11b15-113">This property is set to **ERROR_SERVICE_SPECIFIC_ERROR** (1066) when the error is unique to the service represented by this class, and information about the error is available in the **ServiceSpecificExitCode** property.</span></span> <span data-ttu-id="11b15-114">Le service définit cette valeur à NO_ERROR (0) lors du fonctionnement, et à nouveau lors d'une fin normale.</span><span class="sxs-lookup"><span data-stu-id="11b15-114">The service sets this value to NO_ERROR (0) when running, and again upon normal termination.</span></span>  
  
 <span data-ttu-id="11b15-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="11b15-115">**Host Name**</span></span>  
 <span data-ttu-id="11b15-116">Affiche le nom de l'ordinateur ou du cluster exécutant le service [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11b15-116">Displays the name of the computer or cluster running the [!INCLUDE[ssIS](../../includes/ssis-md.md)] service.</span></span>  
  
 <span data-ttu-id="11b15-117">**Nom**</span><span class="sxs-lookup"><span data-stu-id="11b15-117">**Name**</span></span>  
 <span data-ttu-id="11b15-118">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="11b15-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="11b15-119">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="11b15-119">**Process ID**</span></span>  
 <span data-ttu-id="11b15-120">Affiche l'ID de processus Windows.</span><span class="sxs-lookup"><span data-stu-id="11b15-120">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="11b15-121">**Type de service SQL**</span><span class="sxs-lookup"><span data-stu-id="11b15-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="11b15-122">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="11b15-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="11b15-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="11b15-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="11b15-124">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="11b15-124">**Start Mode**</span></span>  
 <span data-ttu-id="11b15-125">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="11b15-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="11b15-126">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11b15-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="11b15-127">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="11b15-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="11b15-128">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11b15-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="11b15-129">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="11b15-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="11b15-130">**State**</span><span class="sxs-lookup"><span data-stu-id="11b15-130">**State**</span></span>  
 <span data-ttu-id="11b15-131">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="11b15-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="11b15-132">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="11b15-132">"**...**" indicates a state change is pending.</span></span>  
  
  
