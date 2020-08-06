---
title: Présentation de la console CDC Designer | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 45298179-4ac1-4723-8b3c-56f5926be40a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 888b111790cf3979e9d08a78502d24880fa034b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601023"
---
# <a name="the-cdc-designer-console-introduction"></a><span data-ttu-id="b27d0-102">Présentation de la console du concepteur de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="b27d0-102">The CDC Designer Console Introduction</span></span>
  <span data-ttu-id="b27d0-103">Cette section décrit les procédures d'installation du concepteur de capture de données modifiées pour Oracle par Attunity.</span><span class="sxs-lookup"><span data-stu-id="b27d0-103">The section describes the installation procedures for the Change Data Capture Designer for Oracle by Attunity.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="b27d0-104">Installation</span><span class="sxs-lookup"><span data-stu-id="b27d0-104">Installation</span></span>  
 <span data-ttu-id="b27d0-105">Cette section décrit les procédures d'installation du concepteur de capture de données modifiées pour Oracle par Attunity.</span><span class="sxs-lookup"><span data-stu-id="b27d0-105">The section describes the installation procedures for the Change Data Capture Designer for Oracle by Attunity.</span></span> <span data-ttu-id="b27d0-106">Pour installer la console CDC Designer, exécutez manuellement **AttunityOracleCdcDesigner.msi** à partir du support d’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b27d0-106">To install the CDC Designer Console, manually run **AttunityOracleCdcDesigner.msi** from the SQL Server installation media.</span></span>  <span data-ttu-id="b27d0-107">Les packages d’installation pour x86 et x64 se trouvent dans \*\*.\Tools\AttunityCDCOracle \\ \*\* sur le support d’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b27d0-107">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="b27d0-108">Environnements Windows pris en charge</span><span class="sxs-lookup"><span data-stu-id="b27d0-108">Supported Windows Environments</span></span>  
 <span data-ttu-id="b27d0-109">La console du concepteur de capture de données modifiées s'exécute dans les environnements Windows suivants :</span><span class="sxs-lookup"><span data-stu-id="b27d0-109">The CDC Designer Console can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="b27d0-110">Windows Vista 32 bits (x86) et 64 bits (x64) avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="b27d0-110">Windows Vista 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
-   <span data-ttu-id="b27d0-111">Windows 7 32 bits (x86) et 64 bits (x64)</span><span class="sxs-lookup"><span data-stu-id="b27d0-111">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="b27d0-112">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b27d0-112">Windows Server 2008 R2</span></span>  
  
-   <span data-ttu-id="b27d0-113">Windows Server 2008 32 bits (x86) et 64 bits (x64) avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="b27d0-113">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="b27d0-114">Composants requis pour la base de données</span><span class="sxs-lookup"><span data-stu-id="b27d0-114">Database Prerequisites</span></span>  
 <span data-ttu-id="b27d0-115">Pour utiliser le concepteur de capture de données modifiées pour Oracle par Attunity, vous utilisez une base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="b27d0-115">To work with the Change Data Capture Designer for Oracle by Attunity, you work with an Oracle database.</span></span> <span data-ttu-id="b27d0-116">Le concepteur de capture de données modifiées pour Oracle par Attunity prend en charge les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="b27d0-116">The Change Data Capture Designer for Oracle by Attunity supports the following versions:</span></span>  
  
 <span data-ttu-id="b27d0-117">**Base de données Oracle**</span><span class="sxs-lookup"><span data-stu-id="b27d0-117">**Oracle Database**</span></span>  
  
-   <span data-ttu-id="b27d0-118">Oracle Database 10g Version 2 : 10.2.0.1-10.2.0.5 (ensemble de correctifs à partir d'avril 2010)</span><span class="sxs-lookup"><span data-stu-id="b27d0-118">Oracle Database 10g Release 2: 10.2.0.1-10.2.0.5 (patchset as of April 2010)</span></span>  
  
-   <span data-ttu-id="b27d0-119">Oracle Database 11g Version 1 : 11.1.0.6-11.1.0.7 (ensemble de correctifs à partir de septembre 2008)</span><span class="sxs-lookup"><span data-stu-id="b27d0-119">Oracle Database 11g Release 1: 11.1.0.6-11.1.0.7 (patchset as of September 2008)</span></span>  
  
-   <span data-ttu-id="b27d0-120">Oracle Database 11g Version 2 : 11.2.0.1-11.2.0.3 (ensemble de correctifs à partir de septembre 2011)</span><span class="sxs-lookup"><span data-stu-id="b27d0-120">Oracle Database 11g Release 2: 11.2.0.1-11.2.0.3 (patchset as of September 2011)</span></span>  
  
 <span data-ttu-id="b27d0-121">**Base de données SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b27d0-121">**SQL Server Database**</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="b27d0-122">avec prise en charge de SQL Server CDC</span><span class="sxs-lookup"><span data-stu-id="b27d0-122">edition with support for SQL Server CDC</span></span>  
  
## <a name="software-prerequisites"></a><span data-ttu-id="b27d0-123">Composants logiciels requis</span><span class="sxs-lookup"><span data-stu-id="b27d0-123">Software Prerequisites</span></span>  
 <span data-ttu-id="b27d0-124">Les logiciels suivants sont requis :</span><span class="sxs-lookup"><span data-stu-id="b27d0-124">The following software is required:</span></span>  
  
-   <span data-ttu-id="b27d0-125">Client Oracle 10. x</span><span class="sxs-lookup"><span data-stu-id="b27d0-125">Oracle 10.x client</span></span>  
  
-   <span data-ttu-id="b27d0-126">Client Oracle 11.x</span><span class="sxs-lookup"><span data-stu-id="b27d0-126">Oracle 11.x client</span></span>  
  
 <span data-ttu-id="b27d0-127">**Remarque**: vous devez utiliser la version 32 bits ou 64 bits de ce logiciel en fonction de la version de la console CDC designer Oracle installée.</span><span class="sxs-lookup"><span data-stu-id="b27d0-127">**Note**: You must use the 32-bit or 64-bit version of this software according to the version of the Oracle CDC Designer console installed.</span></span>  
  
 <span data-ttu-id="b27d0-128">La console du concepteur de capture de données modifiées Oracle utilise le fournisseur Oracle ODBC pour communiquer avec la base de données Oracle source.</span><span class="sxs-lookup"><span data-stu-id="b27d0-128">The Oracle CDC Designer Console uses the Oracle ODBC provider to communicate with the source Oracle database.</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="b27d0-129">Exécution du programme d'installation</span><span class="sxs-lookup"><span data-stu-id="b27d0-129">Running the Installation Program</span></span>  
 <span data-ttu-id="b27d0-130">Cette section explique comment installer la console du concepteur de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="b27d0-130">This section describes how to install the CDC Designer Console.</span></span>  
  
 <span data-ttu-id="b27d0-131">**Pour installer la console du concepteur CDC**</span><span class="sxs-lookup"><span data-stu-id="b27d0-131">**To install the CDC Designer Console**</span></span>  
  
 <span data-ttu-id="b27d0-132">Double-cliquez sur le kit d'installation de la console du concepteur CDC et suivez les instructions de l'Assistant Installation.</span><span class="sxs-lookup"><span data-stu-id="b27d0-132">Double-click the CDC Designer Console installation kit and follow the directions in the installation wizard.</span></span>  
  
## <a name="uninstalling-the-cdc-designer-console"></a><span data-ttu-id="b27d0-133">Désinstallation de la console du concepteur CDC</span><span class="sxs-lookup"><span data-stu-id="b27d0-133">Uninstalling the CDC Designer Console</span></span>  
 <span data-ttu-id="b27d0-134">Vous désinstallez la console du concepteur CDC à l'aide du composant Programmes et fonctionnalités du Panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="b27d0-134">You uninstall the CDC Designer Console using Control Panel, Programs and Features.</span></span>  
  
  
