---
title: Fonctionnalités désactivées par défaut (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9529edf-337e-4fdd-9a13-99cfe96b4fa1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87752b8760ffc80e80c87ac1132cae36f2f151b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698784"
---
# <a name="features-off-by-default-analysis-services"></a><span data-ttu-id="23216-102">Fonctionnalités désactivées par défaut (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="23216-102">Features off by default (Analysis Services)</span></span>
  <span data-ttu-id="23216-103">Une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est conçue de façon à être sécurisée par défaut.</span><span class="sxs-lookup"><span data-stu-id="23216-103">An instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is designed to be secure by default.</span></span> <span data-ttu-id="23216-104">Par conséquent, les fonctionnalités qui pourraient compromettre la sécurité sont désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="23216-104">Therefore, features that might compromise security are disabled by default.</span></span> <span data-ttu-id="23216-105">Les fonctionnalités suivantes sont désactivées après leur installation et doivent être activées explicitement si vous voulez les utiliser.</span><span class="sxs-lookup"><span data-stu-id="23216-105">The following features are installed in a disabled state and must specifically be enabled if you want to use them.</span></span>  
  
## <a name="feature-list"></a><span data-ttu-id="23216-106">Liste des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="23216-106">Feature List</span></span>  
 <span data-ttu-id="23216-107">Pour activer les fonctionnalités suivantes, connectez-vous à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23216-107">To enable the following features, connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="23216-108">Cliquez avec le bouton droit sur le nom de l’instance, puis sélectionnez **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="23216-108">Right-click the instance name and choose **Facets**.</span></span> <span data-ttu-id="23216-109">Vous pouvez également activer ces fonctionnalités via les propriétés du serveur, comme décrit dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="23216-109">Alternatively, you can enable these features through server properties, as described in the next section.</span></span>  
  
-   <span data-ttu-id="23216-110">Requêtes d'exploration de données ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="23216-110">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="23216-111">Objets liés (Vers)</span><span class="sxs-lookup"><span data-stu-id="23216-111">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="23216-112">Objets liés (De)</span><span class="sxs-lookup"><span data-stu-id="23216-112">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="23216-113">Écouter uniquement les connexions locales</span><span class="sxs-lookup"><span data-stu-id="23216-113">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="23216-114">Fonctions définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="23216-114">User Defined Functions</span></span>  
  
## <a name="server-properties"></a><span data-ttu-id="23216-115">Propriétés du serveur</span><span class="sxs-lookup"><span data-stu-id="23216-115">Server properties</span></span>  
 <span data-ttu-id="23216-116">Les autres fonctionnalités qui sont désactivées par défaut peuvent être activées via les propriétés du serveur.</span><span class="sxs-lookup"><span data-stu-id="23216-116">Additional features that are off by default can be enabled through server properties.</span></span> <span data-ttu-id="23216-117">Se connecter à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23216-117">Connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="23216-118">Cliquez avec le bouton droit sur le nom de l’instance, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="23216-118">Right-click the instance name and choose **Properties**.</span></span> <span data-ttu-id="23216-119">Cliquez sur **Général**, puis cliquez sur **Afficher les options avancées** pour afficher une liste de propriétés plus longue.</span><span class="sxs-lookup"><span data-stu-id="23216-119">Click **General**, and then click **Show Advanced** to display a larger property list.</span></span>  
  
-   <span data-ttu-id="23216-120">Requêtes d'exploration de données ad hoc (OpenRowset)</span><span class="sxs-lookup"><span data-stu-id="23216-120">Ad Hoc Data Mining (OpenRowset) Queries</span></span>  
  
-   <span data-ttu-id="23216-121">Autoriser les modèles d'exploration de données de session (exploration de données)</span><span class="sxs-lookup"><span data-stu-id="23216-121">Allow Session Mining Models (Data Mining)</span></span>  
  
-   <span data-ttu-id="23216-122">Objets liés (Vers)</span><span class="sxs-lookup"><span data-stu-id="23216-122">Linked Objects (To)</span></span>  
  
-   <span data-ttu-id="23216-123">Objets liés (De)</span><span class="sxs-lookup"><span data-stu-id="23216-123">Linked Objects (From)</span></span>  
  
-   <span data-ttu-id="23216-124">Fonctions COM définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="23216-124">COM based user-defined functions</span></span>  
  
-   <span data-ttu-id="23216-125">Définitions de traces de boîte noire (modèles).</span><span class="sxs-lookup"><span data-stu-id="23216-125">Flight Recorder Trace Definitions (templates).</span></span>  
  
-   <span data-ttu-id="23216-126">Journalisation des requêtes</span><span class="sxs-lookup"><span data-stu-id="23216-126">Query logging</span></span>  
  
-   <span data-ttu-id="23216-127">Écouter uniquement les connexions locales</span><span class="sxs-lookup"><span data-stu-id="23216-127">Listen Only On Local Connections</span></span>  
  
-   <span data-ttu-id="23216-128">XML binaire</span><span class="sxs-lookup"><span data-stu-id="23216-128">Binary XML</span></span>  
  
-   <span data-ttu-id="23216-129">Compression</span><span class="sxs-lookup"><span data-stu-id="23216-129">Compression</span></span>  
  
-   <span data-ttu-id="23216-130">Affinité de groupe.</span><span class="sxs-lookup"><span data-stu-id="23216-130">Group affinity.</span></span> <span data-ttu-id="23216-131">Pour plus d'informations, consultez [Thread Pool Properties](../server-properties/thread-pool-properties.md) .</span><span class="sxs-lookup"><span data-stu-id="23216-131">See [Thread Pool Properties](../server-properties/thread-pool-properties.md) for details.</span></span>  
  
  
