---
title: '&lt;Propriétés de nom du service NS $ &gt; (onglet Service) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 57c6b791-1663-4a01-9de2-cf1bdd8adb2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: ddd80cf1c84e3fe7acc538e6aa65230b45870219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705772"
---
# <a name="nsltservice-namegt-properties-service-tab"></a><span data-ttu-id="1cd2f-102">Propriétés de NS$&lt;service name&gt; (onglet Service)</span><span class="sxs-lookup"><span data-stu-id="1cd2f-102">NS$&lt;service name&gt; Properties (Service Tab)</span></span>
  <span data-ttu-id="1cd2f-103">Ce service est le service [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cd2f-103">This service is the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNS](../../includes/ssns-md.md)] service.</span></span> <span data-ttu-id="1cd2f-104">Les valeurs des propriétés en gris clair ne peuvent pas être modifiées à l'aide de cette application.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-104">The property values in light gray cannot be changed using this application.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1cd2f-105">Options</span><span class="sxs-lookup"><span data-stu-id="1cd2f-105">Options</span></span>  
 <span data-ttu-id="1cd2f-106">**Chemin d'accès binaire**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-106">**Binary Path**</span></span>  
 <span data-ttu-id="1cd2f-107">Affiche l'emplacement des fichiers programme utilisés par ce service.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-107">Displays the location of the program files used by this service.</span></span>  
  
 <span data-ttu-id="1cd2f-108">**Contrôle d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-108">**Error Control**</span></span>  
 <span data-ttu-id="1cd2f-109">1 indique `SERVICE_ERROR_NORMAL`.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-109">1 indicates `SERVICE_ERROR_NORMAL`.</span></span> <span data-ttu-id="1cd2f-110">Si le lancement du service échoue pendant le démarrage de l'ordinateur, le programme de démarrage consigne l'erreur et affiche une boîte de message, mais poursuit l'opération de démarrage.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-110">If the service fails to start during computer start up, the startup program logs the error and displays a pop-up message box but continues the startup operation.</span></span> <span data-ttu-id="1cd2f-111">Cette valeur ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-111">This value cannot be changed.</span></span>  
  
 <span data-ttu-id="1cd2f-112">**Code de sortie**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-112">**Exit Code**</span></span>  
 <span data-ttu-id="1cd2f-113">Lorsqu'une erreur se produit, le numéro d'erreur apparaît dans cette zone.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-113">When an error occurs, the error number appears in this box.</span></span> <span data-ttu-id="1cd2f-114">Pour dépanner des incidents, recherchez ce numéro dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou communiquez-le au personnel en charge du support technique.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-114">Use this number to troubleshoot failures by searching for the number in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base or provide the number to your technical support staff.</span></span>  
  
 <span data-ttu-id="1cd2f-115">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-115">**Host Name**</span></span>  
 <span data-ttu-id="1cd2f-116">Affiche le nom de l'ordinateur ou du cluster exécutant la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-116">Displays the name of the computer or cluster running the full text search.</span></span>  
  
 <span data-ttu-id="1cd2f-117">**Nom**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-117">**Name**</span></span>  
 <span data-ttu-id="1cd2f-118">Indique le nom d'affichage du service.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-118">Indicates the display name of the service.</span></span>  
  
 <span data-ttu-id="1cd2f-119">**ID de processus**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-119">**Process ID**</span></span>  
 <span data-ttu-id="1cd2f-120">Affiche l'ID de processus [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-120">Displays the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows process ID.</span></span>  
  
 <span data-ttu-id="1cd2f-121">**Type de service SQL**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-121">**SQL Service Type**</span></span>  
 <span data-ttu-id="1cd2f-122">Type de service fourni aux processus appelants.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-122">Type of service provided to calling processes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1cd2f-123">installe plusieurs services.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-123">installs several services.</span></span>  
  
 <span data-ttu-id="1cd2f-124">**Mode de démarrage**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-124">**Start Mode**</span></span>  
 <span data-ttu-id="1cd2f-125">Les options disponibles pour ce service sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cd2f-125">Set this service to the following choices:</span></span>  
  
-   <span data-ttu-id="1cd2f-126">Manuel : ce service n'est pas automatiquement lancé au démarrage de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-126">Manual: This service does not automatically start when the computer starts.</span></span> <span data-ttu-id="1cd2f-127">Vous devez démarrer le service à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou d'un autre outil.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-127">You must start the service using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or some other tool.</span></span>  
  
-   <span data-ttu-id="1cd2f-128">Automatique : ce service essaie de se lancer au démarrage de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-128">Automatic: This service attempts to start when this computer starts.</span></span>  
  
-   <span data-ttu-id="1cd2f-129">Désactivé : ce service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-129">Disabled: This service cannot be started.</span></span>  
  
 <span data-ttu-id="1cd2f-130">**State**</span><span class="sxs-lookup"><span data-stu-id="1cd2f-130">**State**</span></span>  
 <span data-ttu-id="1cd2f-131">Indique si ce service est en cours d'exécution, arrêté ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="1cd2f-131">Indicates whether this service is running, stopped, or disabled.</span></span>  
  
  
