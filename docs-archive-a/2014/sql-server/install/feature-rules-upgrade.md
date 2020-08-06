---
title: Règles de fonctionnalité (mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0527c1ba26fed86a6c1a3d3a2ea7c11b096474f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612136"
---
# <a name="feature-rules-upgrade"></a><span data-ttu-id="da10c-102">Règles de fonctionnalité (mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="da10c-102">Feature Rules (Upgrade)</span></span>
  <span data-ttu-id="da10c-103">Le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide la configuration de votre ordinateur avant la fin de l'opération d'installation.</span><span class="sxs-lookup"><span data-stu-id="da10c-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="da10c-104">Pendant l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le système analyse l'ordinateur où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sera installé et vérifie les conditions qui empêchent une installation réussie de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da10c-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the system scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed and checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="da10c-105">Avant que le programme d'installation ne démarre l'Assistant Mise à niveau, il extrait l'état de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="da10c-105">Before Setup starts the upgrade wizard, it retrieves the status of each item.</span></span> <span data-ttu-id="da10c-106">Puis, il compare le résultat avec les conditions requises et fournit une aide pour la suppression des problèmes importants.</span><span class="sxs-lookup"><span data-stu-id="da10c-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="da10c-107">La vérification de la configuration du système génère un rapport qui contient une brève description de chaque règle exécutée et de l'état d'exécution.</span><span class="sxs-lookup"><span data-stu-id="da10c-107">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="da10c-108">Le rapport d’analyse de la configuration système se trouve à l’emplacement% ProgramFiles% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="da10c-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="da10c-109">Avant d'exécuter l'opération d'installation, examinez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="da10c-109">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="da10c-110">Configuration matérielle et logicielle requise pour l’installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="da10c-110">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="da10c-111">Fonctionnalités prises en charge par les éditions de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="da10c-111">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="da10c-112">Considérations sur la sécurité pour une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="da10c-112">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="da10c-113">Versions linguistiques locales dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="da10c-113">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="da10c-114">Autres références :</span><span class="sxs-lookup"><span data-stu-id="da10c-114">Other references:</span></span>  
  
1.  [<span data-ttu-id="da10c-115">Mises à niveau de la version et de l’édition prises en charge</span><span class="sxs-lookup"><span data-stu-id="da10c-115">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="da10c-116">Avant l'installation du clustering de basculement</span><span class="sxs-lookup"><span data-stu-id="da10c-116">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="da10c-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da10c-117">See Also</span></span>  
 [<span data-ttu-id="da10c-118">Règles d'installation</span><span class="sxs-lookup"><span data-stu-id="da10c-118">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
