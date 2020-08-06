---
title: Règles d’installation | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: cb87c511-c5ca-48c9-a866-4d15a04bb879
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 46457357a523dcb836545d981bb52d1b6e55c771
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612109"
---
# <a name="installation-rules"></a><span data-ttu-id="eb674-102">Règles d'installation</span><span class="sxs-lookup"><span data-stu-id="eb674-102">Installation Rules</span></span>
  <span data-ttu-id="eb674-103">Le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide la configuration de votre ordinateur avant la fin de l'opération d'installation.</span><span class="sxs-lookup"><span data-stu-id="eb674-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="eb674-104">Lors de l'exécution du programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l'outil d'analyse de configuration système (SCC) analyse l'ordinateur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sera installé.</span><span class="sxs-lookup"><span data-stu-id="eb674-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="eb674-105">L'outil SCC recherche toute anomalie susceptible d'empêcher une installation correcte de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb674-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="eb674-106">Avant que le programme d'installation ne démarre l'Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le SCC extrait l'état de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="eb674-106">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="eb674-107">Puis, il compare le résultat avec les conditions requises et fournit une aide pour la suppression des problèmes importants.</span><span class="sxs-lookup"><span data-stu-id="eb674-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="eb674-108">La vérification de la configuration du système génère un rapport qui contient une brève description de chaque règle exécutée et de l'état d'exécution.</span><span class="sxs-lookup"><span data-stu-id="eb674-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="eb674-109">Le rapport d’analyse de la configuration système se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="eb674-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="eb674-110">Avant d'exécuter l'opération d'installation, examinez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb674-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="eb674-111">Configuration matérielle et logicielle requise pour l’installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="eb674-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="eb674-112">Fonctionnalités prises en charge par les éditions de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="eb674-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="eb674-113">Considérations sur la sécurité pour une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb674-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="eb674-114">Versions linguistiques locales dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb674-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="eb674-115">Autres références :</span><span class="sxs-lookup"><span data-stu-id="eb674-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="eb674-116">Mises à niveau de la version et de l’édition prises en charge</span><span class="sxs-lookup"><span data-stu-id="eb674-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="eb674-117">Avant l'installation du clustering de basculement</span><span class="sxs-lookup"><span data-stu-id="eb674-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb674-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb674-118">See Also</span></span>  
 [<span data-ttu-id="eb674-119">Règles d'installation</span><span class="sxs-lookup"><span data-stu-id="eb674-119">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
