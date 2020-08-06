---
title: Lanceur de démon de filtre de texte intégral SQL (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 6aad7ebe-c4be-4d37-8536-61502f51faa2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8f0d9c76d7d92947dd17fe2ed6e912e3d6baa6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613716"
---
# <a name="sql-full-text-filter-daemon-launcher-service-tab"></a><span data-ttu-id="11b94-102">Lanceur de démon de filtre de texte intégral SQL (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="11b94-102">SQL Full-text Filter Daemon Launcher (Service Tab)</span></span>
  <span data-ttu-id="11b94-103">À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], le lanceur de démon de filtre de texte intégral SQL (service de lancement FDHOST) est utilisé par la recherche en texte intégral [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11b94-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text.</span></span> <span data-ttu-id="11b94-104">Ce service doit être en cours d'exécution pendant que vous utilisez la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="11b94-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="11b94-105">Pour plus d'informations sur les processus hôte de démon de filtre, consultez « Architecture de la recherche en texte intégral » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11b94-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="11b94-106">Utilisez l’onglet **Service**de la boîte de dialogue **Propriétés de Lanceur de démon de filtre de texte intégral SQL** pour afficher ou indiquer les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="11b94-106">Use the **Service**tab on the **SQL Full-text Filter Daemon LauncherProperties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="11b94-107">Options</span><span class="sxs-lookup"><span data-stu-id="11b94-107">Options</span></span>  
 <span data-ttu-id="11b94-108">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="11b94-108">**Binary Path**</span></span>  
 <span data-ttu-id="11b94-109">Répertorie l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="11b94-109">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="11b94-110">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="11b94-110">**Error Control**</span></span>  
 <span data-ttu-id="11b94-111">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="11b94-111">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="11b94-112">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="11b94-112">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="11b94-113">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="11b94-113">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="11b94-114">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="11b94-114">**Exit Code**</span></span>  
 <span data-ttu-id="11b94-115">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="11b94-115">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="11b94-116">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="11b94-116">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="11b94-117">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="11b94-117">**Host Name**</span></span>  
 <span data-ttu-id="11b94-118">Affiche le nom de l’ordinateur ou du cluster exécutant le service [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11b94-118">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="11b94-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="11b94-119">**Name**</span></span>  
 <span data-ttu-id="11b94-120">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="11b94-120">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="11b94-121">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="11b94-121">**Process ID**</span></span>  
 <span data-ttu-id="11b94-122">Affiche l'ID de processus Windows.</span><span class="sxs-lookup"><span data-stu-id="11b94-122">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="11b94-123">**Type de service SQL**</span><span class="sxs-lookup"><span data-stu-id="11b94-123">**SQL Service Type**</span></span>  
 <span data-ttu-id="11b94-124">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="11b94-124">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="11b94-125">installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="11b94-125">installs several services.</span></span>  
  
 <span data-ttu-id="11b94-126">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="11b94-126">**Start Mode**</span></span>  
 <span data-ttu-id="11b94-127">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="11b94-127">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="11b94-128">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11b94-128">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="11b94-129">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="11b94-129">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="11b94-130">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="11b94-130">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="11b94-131">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="11b94-131">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="11b94-132">**State**</span><span class="sxs-lookup"><span data-stu-id="11b94-132">**State**</span></span>  
 <span data-ttu-id="11b94-133">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="11b94-133">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="11b94-134">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="11b94-134">"**...**" indicates a state change is pending.</span></span>  
  
  
