---
title: Propriétés d’Analysis Server (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 8dbe4bc5-6aa9-48ee-857e-0b4ea764b9cb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91200120d87224c8e7733b0ff41ed423d3086c34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708871"
---
# <a name="analysis-server-properties-service-tab"></a><span data-ttu-id="7cc2e-102">Propriétés de Analysis Server (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="7cc2e-102">Analysis Server Properties (Service Tab)</span></span>
  <span data-ttu-id="7cc2e-103">Ce service est le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc2e-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="7cc2e-104">Ce service doit être en cours d'exécution pour que [!INCLUDE[ssAS](../../includes/ssas-md.md)] fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-104">This service must be running for [!INCLUDE[ssAS](../../includes/ssas-md.md)] to work properly.</span></span> <span data-ttu-id="7cc2e-105">Les valeurs des propriétés en gris clair ne peuvent pas être modifiées à l'aide de cette application.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-105">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7cc2e-106">Options</span><span class="sxs-lookup"><span data-stu-id="7cc2e-106">Options</span></span>  
 <span data-ttu-id="7cc2e-107">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-107">**Binary Path**</span></span>  
 <span data-ttu-id="7cc2e-108">Affiche l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-108">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="7cc2e-109">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-109">**Error Control**</span></span>  
 <span data-ttu-id="7cc2e-110">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-110">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="7cc2e-111">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-111">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="7cc2e-112">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-112">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="7cc2e-113">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-113">**Exit Code**</span></span>  
 <span data-ttu-id="7cc2e-114">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-114">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="7cc2e-115">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-115">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="7cc2e-116">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-116">**Host Name**</span></span>  
 <span data-ttu-id="7cc2e-117">Affiche le nom de l'ordinateur ou du cluster exécutant [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cc2e-117">Displays the name of the computer or cluster running [!INCLUDE[ssAS](../../includes/ssas-md.md)].</span></span>  
  
 <span data-ttu-id="7cc2e-118">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-118">**Name**</span></span>  
 <span data-ttu-id="7cc2e-119">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-119">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="7cc2e-120">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-120">**Process ID**</span></span>  
 <span data-ttu-id="7cc2e-121">Affiche le numéro qu’utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows pour effectuer le suivi des processus de ce programme.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-121">Displays the number used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows to keep track of this program's processes.</span></span>  
  
 <span data-ttu-id="7cc2e-122">**Type de service SQL**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-122">**SQL Service Type**</span></span>  
 <span data-ttu-id="7cc2e-123">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-123">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7cc2e-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-124">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installs several services.</span></span>  
  
 <span data-ttu-id="7cc2e-125">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-125">**Start Mode**</span></span>  
 <span data-ttu-id="7cc2e-126">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="7cc2e-126">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="7cc2e-127">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-127">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="7cc2e-128">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-128">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="7cc2e-129">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-129">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="7cc2e-130">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-130">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="7cc2e-131">**State**</span><span class="sxs-lookup"><span data-stu-id="7cc2e-131">**State**</span></span>  
 <span data-ttu-id="7cc2e-132">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="7cc2e-132">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
