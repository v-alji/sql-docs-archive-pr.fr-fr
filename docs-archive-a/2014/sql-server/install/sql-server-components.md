---
title: Composants de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Upgrade Advisor, components
- listing components to analyze
- Upgrade Advisor [SQL Server], components
- component analysis [Upgrade Advisor]
- finding components to analyze
- locating components to analyze
- detecting components to analyze
- server names [Upgrade Advisor]
- analyzing system [Upgrade Advisor], component list
- identifying components to analyze
ms.assetid: 539b9525-ce3f-4950-9146-5527a5a297ee
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 95fe39ce8e616b238cf7c70763e7cf1819341f16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710140"
---
# <a name="sql-server-components"></a><span data-ttu-id="46fef-102">Composants SQL Server</span><span class="sxs-lookup"><span data-stu-id="46fef-102">SQL Server Components</span></span>
  <span data-ttu-id="46fef-103">Vous pouvez exécuter l’Assistant analyse du conseiller de mise à niveau sur un ordinateur local ou distant sur lequel [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ,, [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ou est [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installé.</span><span class="sxs-lookup"><span data-stu-id="46fef-103">You can run the Upgrade Advisor Analysis Wizard against a local or remote computer that has [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] installed.</span></span> <span data-ttu-id="46fef-104">La première étape de l'analyse de pré-mise à niveau consiste à identifier l'ordinateur et les composants à analyser.</span><span class="sxs-lookup"><span data-stu-id="46fef-104">The first step in the pre-upgrade analysis is to identify the computer and components for analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="46fef-105">Options</span><span class="sxs-lookup"><span data-stu-id="46fef-105">Options</span></span>  
 <span data-ttu-id="46fef-106">**Nom de l’ordinateur**</span><span class="sxs-lookup"><span data-stu-id="46fef-106">**Computer name**</span></span>  
 <span data-ttu-id="46fef-107">Spécifie le nom de l'ordinateur à analyser.</span><span class="sxs-lookup"><span data-stu-id="46fef-107">Specifies the name of the computer to analyze.</span></span> <span data-ttu-id="46fef-108">Le conseiller de mise à niveau remplit la zone **nom du serveur** avec le nom de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="46fef-108">Upgrade Advisor populates the **Server name** box with the local computer name.</span></span> <span data-ttu-id="46fef-109">Vous pouvez également utiliser "." et "localhost" pour vous connecter à l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="46fef-109">You can also use "." and "localhost" to connect to the local computer.</span></span>  
  
 <span data-ttu-id="46fef-110">Pour analyser un autre ordinateur, appliquez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="46fef-110">To analyze a different computer, use the following guidelines:</span></span>  
  
-   <span data-ttu-id="46fef-111">Pour analyser les instances non cluster, entrez le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-111">To scan nonclustered instances, enter the computer name.</span></span>  
  
-   <span data-ttu-id="46fef-112">Pour analyser les instances cluster, entrez le nom de l'instance de cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46fef-112">To scan clustered instances, enter the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
-   <span data-ttu-id="46fef-113">Pour analyser les composants non-cluster installés sur un nœud d’un cluster, entrez le nom d’ordinateur du nœud de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="46fef-113">To scan nonclustered components that are installed on a node of a cluster, enter the computer name of the failover cluster node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="46fef-114">N'incluez pas le nom de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46fef-114">Do not include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name.</span></span>  
  
 <span data-ttu-id="46fef-115">Au lieu de spécifier le nom de l'ordinateur, vous pouvez spécifier l'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="46fef-115">Instead of specifying the computer name, you can specify the IP address.</span></span>  
  
 <span data-ttu-id="46fef-116">Lors de l'analyse de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous devez spécifier le nom de l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="46fef-116">If scanning [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must specify the name of the local computer.</span></span> <span data-ttu-id="46fef-117">Le Conseiller de mise à niveau analyse uniquement les serveurs de rapports locaux.</span><span class="sxs-lookup"><span data-stu-id="46fef-117">Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="46fef-118">**Detect**</span><span class="sxs-lookup"><span data-stu-id="46fef-118">**Detect**</span></span>  
 <span data-ttu-id="46fef-119">Le bouton **détecter** accède à l’ordinateur spécifié et détecte les composants à analyser :</span><span class="sxs-lookup"><span data-stu-id="46fef-119">The **Detect** button accesses the specified computer and detects components to analyze:</span></span>  
  
-   <span data-ttu-id="46fef-120">Si vous analysez une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un ordinateur distant, vous devez activer les services Registre distant sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="46fef-120">If you are analyzing a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a remote computer, you must enable the remote registry services on the remote computer.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="46fef-121">est détecté si une instance de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], ou [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] se trouve dans le Registre de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-121">is detected if an instance of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="46fef-122">est détecté si une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se trouve dans le Registre de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-122">is detected if an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is found in the computer's registry.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="46fef-123">est détecté si [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se trouve dans le Registre de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-123">is detected if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is found in the computer's registry.</span></span> <span data-ttu-id="46fef-124">Cependant, le Conseiller de mise à niveau analyse uniquement les serveurs de rapports locaux.</span><span class="sxs-lookup"><span data-stu-id="46fef-124">However, Upgrade Advisor scans local report servers only.</span></span>  
  
 <span data-ttu-id="46fef-125">**Composants**</span><span class="sxs-lookup"><span data-stu-id="46fef-125">**Components**</span></span>  
 <span data-ttu-id="46fef-126">Sélectionnez les composants à analyser.</span><span class="sxs-lookup"><span data-stu-id="46fef-126">Select the components to analyze.</span></span> <span data-ttu-id="46fef-127">Vous pouvez cliquer sur le bouton **détecter** pour sélectionner tous les composants installés sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-127">You can click the **Detect** button to select all the components installed on the computer.</span></span> <span data-ttu-id="46fef-128">Une coche apparaît en regard des composants détectés comme étant installés sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="46fef-128">A check mark will appear next to the components that are detected as installed on the computer.</span></span> <span data-ttu-id="46fef-129">Vous pouvez également sélectionner manuellement les composants à analyser en activant ou désactivant la case à cocher en regard de chaque composant.</span><span class="sxs-lookup"><span data-stu-id="46fef-129">You can also manually select the components to analyze by selecting or clearing the check box next to each component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46fef-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46fef-130">See Also</span></span>  
 <span data-ttu-id="46fef-131">[Utilisation du conseiller de mise à niveau](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="46fef-131">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="46fef-132">Guide de référence de l'interface utilisateur du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="46fef-132">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
