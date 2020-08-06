---
title: Propriétés de SQL Server (onglet Service) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e4ae0c6b-6fd8-4325-b54e-1758fc659958
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5822a02d5631e0d0e9318b20a1dcee87b8a4ded1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707996"
---
# <a name="sql-server-properties-service-tab"></a><span data-ttu-id="01965-102">Propriétés de SQL Server (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="01965-102">SQL Server Properties (Service Tab)</span></span>
  <span data-ttu-id="01965-103">L’onglet **Service**de la boîte de dialogue **Propriétés de MSSQLSERVER** permet d’afficher ou de spécifier les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="01965-103">Use the **Service**tab on the **MSSQLSERVER Properties** dialog box to view or specify the following options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01965-104">Options</span><span class="sxs-lookup"><span data-stu-id="01965-104">Options</span></span>  
 <span data-ttu-id="01965-105">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="01965-105">**Binary Path**</span></span>  
 <span data-ttu-id="01965-106">Répertorie l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="01965-106">Lists the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="01965-107">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="01965-107">**Error Control**</span></span>  
 <span data-ttu-id="01965-108">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="01965-108">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="01965-109">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="01965-109">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="01965-110">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="01965-110">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="01965-111">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="01965-111">**Exit Code**</span></span>  
 <span data-ttu-id="01965-112">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="01965-112">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="01965-113">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="01965-113">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="01965-114">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="01965-114">**Host Name**</span></span>  
 <span data-ttu-id="01965-115">Affiche le nom de l’ordinateur ou du cluster exécutant le service [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01965-115">Displays the name of the computer or cluster running the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="01965-116">**Nom**</span><span class="sxs-lookup"><span data-stu-id="01965-116">**Name**</span></span>  
 <span data-ttu-id="01965-117">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="01965-117">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="01965-118">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="01965-118">**Process ID**</span></span>  
 <span data-ttu-id="01965-119">Affiche l'ID de processus Windows.</span><span class="sxs-lookup"><span data-stu-id="01965-119">Displays the Windows process ID.</span></span>  
  
 <span data-ttu-id="01965-120">**Type de service**</span><span class="sxs-lookup"><span data-stu-id="01965-120">**Service Type**</span></span>  
 <span data-ttu-id="01965-121">Affiche le type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="01965-121">Displays the type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="01965-122">installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="01965-122">installs several services.</span></span>  
  
 <span data-ttu-id="01965-123">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="01965-123">**Start Mode**</span></span>  
 <span data-ttu-id="01965-124">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="01965-124">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="01965-125">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01965-125">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="01965-126">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="01965-126">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="01965-127">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="01965-127">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="01965-128">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="01965-128">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="01965-129">**State**</span><span class="sxs-lookup"><span data-stu-id="01965-129">**State**</span></span>  
 <span data-ttu-id="01965-130">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="01965-130">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="01965-131">« **…** » indique qu’un changement d’état est en attente.</span><span class="sxs-lookup"><span data-stu-id="01965-131">"**...**" indicates a state change is pending.</span></span>  
  
  
