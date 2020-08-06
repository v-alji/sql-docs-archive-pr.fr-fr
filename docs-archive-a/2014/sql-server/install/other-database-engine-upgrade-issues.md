---
title: Autres problèmes de mise à niveau de Moteur de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603217"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="c3d9e-102">Autres problèmes de mise à niveau du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="c3d9e-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="c3d9e-103">Les problèmes de mise à niveau suivants ne peuvent pas être détectés par la version actuelle du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="c3d9e-104">Passez en revue les problèmes répertoriés ci-dessous pour évaluer leur impact potentiel sur vos systèmes.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="c3d9e-105">Plusieurs fonctionnalités déconseillées du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="c3d9e-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="c3d9e-106">Les options ou instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes sont déconseillées :</span><span class="sxs-lookup"><span data-stu-id="c3d9e-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="c3d9e-107">Options NO_LOG et TRUNCATE_ONLY de BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="c3d9e-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="c3d9e-108">BACKUP TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="c3d9e-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="c3d9e-109">RESTORE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="c3d9e-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="c3d9e-110">DUMP</span><span class="sxs-lookup"><span data-stu-id="c3d9e-110">DUMP</span></span>  
  
-   <span data-ttu-id="c3d9e-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="c3d9e-111">LOAD</span></span>  
  
-   <span data-ttu-id="c3d9e-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="c3d9e-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="c3d9e-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="c3d9e-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="c3d9e-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="c3d9e-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="c3d9e-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="c3d9e-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="c3d9e-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="c3d9e-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="c3d9e-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="c3d9e-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="c3d9e-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="c3d9e-118">syssegments</span></span>  
  
 <span data-ttu-id="c3d9e-119">L’utilisation du protocole VIA pour se connecter à l' [!INCLUDE[ssDE](../../includes/ssde-md.md)] est déconseillée.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="c3d9e-120">Nouveaux types de données</span><span class="sxs-lookup"><span data-stu-id="c3d9e-120">New Data Types</span></span>  
 <span data-ttu-id="c3d9e-121">Les éléments suivants sont des types système réservés.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-121">The following will be reserved system types.</span></span> <span data-ttu-id="c3d9e-122">Renommez les types définis par l'utilisateur en conflit avant ou après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="c3d9e-123">Geography</span><span class="sxs-lookup"><span data-stu-id="c3d9e-123">Geography</span></span>  
  
-   <span data-ttu-id="c3d9e-124">Géométrie</span><span class="sxs-lookup"><span data-stu-id="c3d9e-124">Geometry</span></span>  
  
-   <span data-ttu-id="c3d9e-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="c3d9e-125">Datetime2</span></span>  
  
-   <span data-ttu-id="c3d9e-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="c3d9e-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="c3d9e-127">La table cible de la clause OUTPUT INTO ne peut pas contenir de déclencheur défini</span><span class="sxs-lookup"><span data-stu-id="c3d9e-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="c3d9e-128">La sortie dans une table cible lorsque la table contient des déclencheurs activés n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="c3d9e-129">Erreur de compilation des UDF lorsque la cible d'une clause OUTPUT INTO est une table</span><span class="sxs-lookup"><span data-stu-id="c3d9e-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="c3d9e-130">Les fonctions définies par l'utilisateur (UDF) ne permettent pas d'exécuter des actions qui modifient l'état des bases de données.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="c3d9e-131">Par exemple, une fonction définie par l'utilisateur ne peut exécuter aucune action DDL (CREATE/ALTER/DROP) ou DML (INSERT/UPDATE/DELETE) sur des objets, à l'exception des variables de table.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="c3d9e-132">MERGE est un mot clé réservé</span><span class="sxs-lookup"><span data-stu-id="c3d9e-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="c3d9e-133">MERGE est un maintenant un mot clé entièrement réservé.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="c3d9e-134">Les applications ne peuvent plus contenir d'objets (table, colonne, etc.) appelés MERGE.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="c3d9e-135">Renommer le schéma CDC</span><span class="sxs-lookup"><span data-stu-id="c3d9e-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="c3d9e-136">Il y a un nom de schéma appelé CDC.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-136">There is a schema name called CDC.</span></span> <span data-ttu-id="c3d9e-137">Ce nom de schéma ne peut pas être utilisé si la **capture de données modifiées** est activée pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="c3d9e-138">Vous devez supprimer le schéma CDC avant d’activer la **capture de données modifiées** pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="c3d9e-139">Cette procédure peut s'effectuer avant ou après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="c3d9e-140">Pour supprimer le schéma, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3d9e-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="c3d9e-141">Transférez les objets du schéma CDC vers un nouveau schéma à l'aide de l'instruction ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="c3d9e-142">Vérifiez les autorisations pour les objets dans le nouveau schéma.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="c3d9e-143">Apportez les modifications nécessaires à l'application.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="c3d9e-144">Supprimez le schéma CDC à l'aide de l'instruction DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="c3d9e-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3d9e-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3d9e-145">See Also</span></span>  
 [<span data-ttu-id="c3d9e-146">Problèmes de mise à niveau du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="c3d9e-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
