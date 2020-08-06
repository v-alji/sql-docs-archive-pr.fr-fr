---
title: Paramètres de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704679"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="185be-102">Paramètres du serveur SQL Server</span><span class="sxs-lookup"><span data-stu-id="185be-102">SQL Server Parameters</span></span>
  <span data-ttu-id="185be-103">Dans cette page, définissez les paramètres que l’analyseur utilisera pour l' [!INCLUDE[ssDE](../../includes/ssde-md.md)] analyse.</span><span class="sxs-lookup"><span data-stu-id="185be-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="185be-104"> ous pouvez analyser une, plusieurs ou toutes les bases de données, des fichiers de trace créés à l'aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] et des fichiers de commandes SQL.</span><span class="sxs-lookup"><span data-stu-id="185be-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="185be-105">Certains problèmes de mise à niveau ne peuvent être détectés que si vous faites analyser des fichiers de trace ou des fichiers de commandes SQL.</span><span class="sxs-lookup"><span data-stu-id="185be-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="185be-106">Options</span><span class="sxs-lookup"><span data-stu-id="185be-106">Options</span></span>  
 <span data-ttu-id="185be-107">**Base(s) de données à analyser**</span><span class="sxs-lookup"><span data-stu-id="185be-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="185be-108">Pour analyser toutes les bases de données, activez la case à cocher **toutes les bases de données** .</span><span class="sxs-lookup"><span data-stu-id="185be-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="185be-109">Pour analyser une sélection de bases de données, activez la case à cocher située en regard de chaque base de données à inclure dans l'analyse.</span><span class="sxs-lookup"><span data-stu-id="185be-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="185be-110">**Analyser les fichiers de trace**</span><span class="sxs-lookup"><span data-stu-id="185be-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="185be-111">Activez cette case à cocher pour analyser les fichiers de trace du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="185be-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="185be-112">**Che. d'accès aux fich. de trace**</span><span class="sxs-lookup"><span data-stu-id="185be-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="185be-113">Vous pouvez analyser un ou plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="185be-113">You can analyze one or more files.</span></span> <span data-ttu-id="185be-114">Vous pouvez accéder à un emplacement et sélectionner plusieurs fichiers, ou vous pouvez fournir plusieurs noms de fichiers.</span><span class="sxs-lookup"><span data-stu-id="185be-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="185be-115">Utilisez le chemin d'accès complet à chaque fichier, incluez le nom de fichier et séparez les entrées à l'aide de la barre verticale (|).</span><span class="sxs-lookup"><span data-stu-id="185be-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="185be-116">Si vous activez **analyser les fichiers de trace**, l' **étape suivante** est désactivée jusqu’à ce que vous entriez un nom de chemin d’accès et un nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="185be-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="185be-117">**Analyser le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou les fichiers de commandes**</span><span class="sxs-lookup"><span data-stu-id="185be-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="185be-118">Activez cette case à cocher pour analyser les fichiers de commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="185be-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="185be-119">**Chemin d’accès au [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (x) fichier (s) batch**</span><span class="sxs-lookup"><span data-stu-id="185be-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="185be-120">Vous pouvez analyser un ou plusieurs fichiers de commandes.</span><span class="sxs-lookup"><span data-stu-id="185be-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="185be-121">Vous pouvez accéder à un emplacement et sélectionner plusieurs fichiers, ou vous pouvez taper plusieurs noms de fichiers.</span><span class="sxs-lookup"><span data-stu-id="185be-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="185be-122">Utilisez le chemin d'accès complet à chaque fichier, incluez le nom de fichier et séparez les entrées à l'aide de la barre verticale (|).</span><span class="sxs-lookup"><span data-stu-id="185be-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="185be-123">Si vous activez **analyser les fichiers de commandes SQL**, le bouton **suivant** est désactivé jusqu’à ce que vous entriez un nom de chemin d’accès et un nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="185be-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="185be-124">**Délimiteur de lot SQL**</span><span class="sxs-lookup"><span data-stu-id="185be-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="185be-125">Texte utilisé pour séparer des lots d'instructions [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="185be-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="185be-126">La valeur par défaut est **Go**.</span><span class="sxs-lookup"><span data-stu-id="185be-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="185be-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="185be-127">See Also</span></span>  
 <span data-ttu-id="185be-128">[Utilisation du conseiller de mise à niveau](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="185be-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="185be-129">Guide de référence de l'interface utilisateur du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="185be-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
