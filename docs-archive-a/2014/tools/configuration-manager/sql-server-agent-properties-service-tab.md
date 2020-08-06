---
title: Propriétés de SQL Server Agent (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 452857fb-be1b-4e1e-851c-dd2216640f35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d3526026a45af6375f5c881616c476d80737795
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703660"
---
# <a name="sql-server-agent-properties-service-tab"></a><span data-ttu-id="01adc-102">Propriétés de l'Agent SQL Server (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="01adc-102">SQL Server Agent Properties (Service Tab)</span></span>
  <span data-ttu-id="01adc-103">Ce service est le service de l’Agent [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01adc-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="01adc-104">Les valeurs des propriétés en gris clair ne peuvent pas être modifiées à l'aide de cette application.</span><span class="sxs-lookup"><span data-stu-id="01adc-104">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01adc-105">Options</span><span class="sxs-lookup"><span data-stu-id="01adc-105">Options</span></span>  
 <span data-ttu-id="01adc-106">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="01adc-106">**Binary Path**</span></span>  
 <span data-ttu-id="01adc-107">Affiche l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="01adc-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="01adc-108">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="01adc-108">**Error Control**</span></span>  
 <span data-ttu-id="01adc-109">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="01adc-109">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="01adc-110">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="01adc-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="01adc-111">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="01adc-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="01adc-112">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="01adc-112">**Exit Code**</span></span>  
 <span data-ttu-id="01adc-113">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="01adc-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="01adc-114">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="01adc-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="01adc-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="01adc-115">**Host Name**</span></span>  
 <span data-ttu-id="01adc-116">Affiche le nom de l’ordinateur ou du cluster exécutant l’Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01adc-116">Displays the name of the computer or cluster running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="01adc-117">**Nom**</span><span class="sxs-lookup"><span data-stu-id="01adc-117">**Name**</span></span>  
 <span data-ttu-id="01adc-118">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="01adc-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="01adc-119">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="01adc-119">**Process ID**</span></span>  
 <span data-ttu-id="01adc-120">Affiche l'ID de processus [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="01adc-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="01adc-121">**Type de service SQL**</span><span class="sxs-lookup"><span data-stu-id="01adc-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="01adc-122">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="01adc-122">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="01adc-123">installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="01adc-123">installs several services.</span></span>  
  
 <span data-ttu-id="01adc-124">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="01adc-124">**Start Mode**</span></span>  
 <span data-ttu-id="01adc-125">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="01adc-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="01adc-126">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01adc-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="01adc-127">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="01adc-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="01adc-128">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01adc-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="01adc-129">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="01adc-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="01adc-130">**State**</span><span class="sxs-lookup"><span data-stu-id="01adc-130">**State**</span></span>  
 <span data-ttu-id="01adc-131">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="01adc-131">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="01adc-132">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="01adc-132">"**...**" indicates a state change is pending.</span></span>  
  
  
