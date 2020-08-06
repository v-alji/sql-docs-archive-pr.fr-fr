---
title: Propriétés de SQL Server Browser (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 98ace9b0-72d5-4b72-9b7b-11fbc490981a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 200e45648b94e26c5e808e9a817cfe01866e6a65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601245"
---
# <a name="sql-server-browser-properties-service-tab"></a><span data-ttu-id="09fc1-102">Propriétés de SQL Server Browser (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="09fc1-102">SQL Server Browser Properties (Service Tab)</span></span>
  <span data-ttu-id="09fc1-103">Le programme [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser s'exécute sur le serveur en tant que service.</span><span class="sxs-lookup"><span data-stu-id="09fc1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="09fc1-104">Browser est à l’écoute des demandes entrantes pour les ressources [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et fournit des informations sur les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="09fc1-104">Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 <span data-ttu-id="09fc1-105">L'onglet **Service** de la boîte de dialogue **Propriétés de SQL Server Browser** vous permet d'afficher les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="09fc1-105">Use the **Service** tab on the **SQL Server Browser Properties** dialog box to view the following options.</span></span> <span data-ttu-id="09fc1-106">Toutes les propriétés, à l’exception de **Mode de démarrage** , sont accessibles en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="09fc1-106">All properties except **Start Mode** are read-only.</span></span>  
  
## <a name="options"></a><span data-ttu-id="09fc1-107">Options</span><span class="sxs-lookup"><span data-stu-id="09fc1-107">Options</span></span>  
 <span data-ttu-id="09fc1-108">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="09fc1-108">**Binary Path**</span></span>  
 <span data-ttu-id="09fc1-109">Affiche l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="09fc1-109">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="09fc1-110">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="09fc1-110">**Error Control**</span></span>  
 <span data-ttu-id="09fc1-111">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="09fc1-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="09fc1-112">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="09fc1-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="09fc1-113">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="09fc1-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="09fc1-114">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="09fc1-114">**Exit Code**</span></span>  
 <span data-ttu-id="09fc1-115">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="09fc1-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="09fc1-116">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="09fc1-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="09fc1-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="09fc1-117">**Host Name**</span></span>  
 <span data-ttu-id="09fc1-118">Affiche le nom de l’ordinateur ou du cluster exécutant le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="09fc1-118">Displays the name of the computer or cluster running the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="09fc1-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="09fc1-119">**Name**</span></span>  
 <span data-ttu-id="09fc1-120">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="09fc1-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="09fc1-121">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="09fc1-121">**Process ID**</span></span>  
 <span data-ttu-id="09fc1-122">Affiche l'ID de processus Windows.</span><span class="sxs-lookup"><span data-stu-id="09fc1-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="09fc1-123">**Type de service**</span><span class="sxs-lookup"><span data-stu-id="09fc1-123">**Service Type**</span></span>  
 <span data-ttu-id="09fc1-124">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="09fc1-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="09fc1-125">installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="09fc1-125">installs several services.</span></span>  
  
 <span data-ttu-id="09fc1-126">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="09fc1-126">**Start Mode**</span></span>  
 <span data-ttu-id="09fc1-127">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="09fc1-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="09fc1-128">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="09fc1-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="09fc1-129">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="09fc1-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="09fc1-130">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="09fc1-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="09fc1-131">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="09fc1-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="09fc1-132">**State**</span><span class="sxs-lookup"><span data-stu-id="09fc1-132">**State**</span></span>  
 <span data-ttu-id="09fc1-133">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="09fc1-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="09fc1-134">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="09fc1-134">"**...**" indicates a state change is pending.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09fc1-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09fc1-135">See Also</span></span>  
 [<span data-ttu-id="09fc1-136">Service SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="09fc1-136">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
