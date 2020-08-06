---
title: Bases de données système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695671"
---
# <a name="system-databases"></a><span data-ttu-id="e3143-102">Bases de données système</span><span class="sxs-lookup"><span data-stu-id="e3143-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3143-103">inclut les bases de données système suivantes.</span><span class="sxs-lookup"><span data-stu-id="e3143-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="e3143-104">Base de données système</span><span class="sxs-lookup"><span data-stu-id="e3143-104">System database</span></span>|<span data-ttu-id="e3143-105">Description</span><span class="sxs-lookup"><span data-stu-id="e3143-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="e3143-106">Base de données master</span><span class="sxs-lookup"><span data-stu-id="e3143-106">master Database</span></span>](master-database.md)|<span data-ttu-id="e3143-107">Enregistre toutes les informations système relatives à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3143-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="e3143-108">Base de données msdb</span><span class="sxs-lookup"><span data-stu-id="e3143-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="e3143-109">Utilisée par l'Agent SQL Server pour planifier les alertes et les travaux.</span><span class="sxs-lookup"><span data-stu-id="e3143-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="e3143-110">Base de données model</span><span class="sxs-lookup"><span data-stu-id="e3143-110">model Database</span></span>](model-database.md)|<span data-ttu-id="e3143-111">Fait office de modèle pour toutes les bases de données créées sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3143-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e3143-112">Les modifications apportées à la base de données **model** , telles que la taille de la base de données, le classement, le mode de récupération et les autres options de base de données, s'appliquent aux bases de données créées par la suite.</span><span class="sxs-lookup"><span data-stu-id="e3143-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="e3143-113">Base de données Resource</span><span class="sxs-lookup"><span data-stu-id="e3143-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="e3143-114">Base de données en lecture seule contenant des objets système fournis avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3143-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e3143-115">Les objets système sont conservés physiquement dans la base de données **Resource** , mais ils figurent logiquement dans le schéma **sys** de chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="e3143-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="e3143-116">Base de données tempdb</span><span class="sxs-lookup"><span data-stu-id="e3143-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="e3143-117">Espace de travail destiné à accueillir les objets temporaires ou les ensembles de résultats intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="e3143-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="e3143-118">modification de données système</span><span class="sxs-lookup"><span data-stu-id="e3143-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3143-119">ne permet pas aux utilisateurs de mettre directement à jour les informations contenues dans les objets système, tels que les tables système, les procédures stockées système et les vues de catalogue.</span><span class="sxs-lookup"><span data-stu-id="e3143-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="e3143-120">En revanche, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] propose un jeu complet d'outils d'administration qui permettent aux utilisateurs d'administrer complètement leur système et de gérer tous les utilisateurs et objets d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="e3143-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="e3143-121">Ces options en question sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e3143-121">These include the following:</span></span>  
  
-   <span data-ttu-id="e3143-122">Utilitaires d'administration, tels que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3143-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="e3143-123">API SQL-SMO.</span><span class="sxs-lookup"><span data-stu-id="e3143-123">SQL-SMO API.</span></span> <span data-ttu-id="e3143-124">Cet outil permet aux programmeurs d'inclure des fonctionnalités complètes visant à administrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans leurs applications.</span><span class="sxs-lookup"><span data-stu-id="e3143-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e3143-125">.</span><span class="sxs-lookup"><span data-stu-id="e3143-125">scripts and stored procedures.</span></span> <span data-ttu-id="e3143-126">Ceux-ci peuvent utiliser des procédures stockées système et des instructions DDL [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3143-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="e3143-127">Ces outils prémunissent les applications contre les modifications des objets système.</span><span class="sxs-lookup"><span data-stu-id="e3143-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="e3143-128">Par exemple, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est parfois amené à modifier les tables système dans les nouvelles versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] afin de prendre en charge les nouvelles fonctionnalités ajoutées à cette version.</span><span class="sxs-lookup"><span data-stu-id="e3143-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="e3143-129">Les applications qui lancent des instructions SELECT référençant directement les tables système dépendent souvent de l'ancien format des tables système.</span><span class="sxs-lookup"><span data-stu-id="e3143-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="e3143-130">Il est possible que les sites ne soient pas en mesure de procéder à la mise à niveau vers une nouvelle version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tant qu'ils n'ont pas réécrit les applications de sélection dans les tables système.</span><span class="sxs-lookup"><span data-stu-id="e3143-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3143-131">considère les procédures stockées système, DDL et SQL-SMO comme des interfaces publiées, et veille à en maintenir la compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="e3143-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3143-132">ne prend pas en charge les déclencheurs définis sur les tables système, car ils peuvent perturber le bon fonctionnement du système.</span><span class="sxs-lookup"><span data-stu-id="e3143-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e3143-133">Les bases de données système ne peuvent pas résider dans les répertoires partagés UNC.</span><span class="sxs-lookup"><span data-stu-id="e3143-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="e3143-134">affichage de données de bases de données système</span><span class="sxs-lookup"><span data-stu-id="e3143-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="e3143-135">Vous ne devez pas coder les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] qui interrogent directement les tables système, sauf s'il s'agit de la seule méthode d'obtention des informations requises par l'application.</span><span class="sxs-lookup"><span data-stu-id="e3143-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="e3143-136">Au lieu de cela, les applications doivent obtenir les informations de catalogue et du système par l'un des moyens suivants :</span><span class="sxs-lookup"><span data-stu-id="e3143-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="e3143-137">Vues de catalogue système</span><span class="sxs-lookup"><span data-stu-id="e3143-137">System catalog views</span></span>  
  
-   <span data-ttu-id="e3143-138">SQL-SMO</span><span class="sxs-lookup"><span data-stu-id="e3143-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="e3143-139">Interface WMI (Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="e3143-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="e3143-140">Fonctions de catalogue, méthodes, attributs ou propriétés de l'API de données utilisée dans l'application, notamment ADO, OLE DB ou ODBC.</span><span class="sxs-lookup"><span data-stu-id="e3143-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e3143-141">Procédures stockées système et fonctions intégrées.</span><span class="sxs-lookup"><span data-stu-id="e3143-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e3143-142">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e3143-142">Related Tasks</span></span>  
 [<span data-ttu-id="e3143-143">Sauvegarde et restauration des bases de données système &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e3143-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="e3143-144">Masquer les objets système dans l’Explorateur d’objets</span><span class="sxs-lookup"><span data-stu-id="e3143-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="e3143-145">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="e3143-145">Related Content</span></span>  
 [<span data-ttu-id="e3143-146">Affichages catalogue &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e3143-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="e3143-147">Bases de données</span><span class="sxs-lookup"><span data-stu-id="e3143-147">Databases</span></span>](databases.md)  
  
  
