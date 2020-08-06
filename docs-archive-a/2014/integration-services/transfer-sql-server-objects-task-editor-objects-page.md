---
title: Éditeur de tâche de transfert d’objets SQL Server (page objets) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfersqlserverobjects.objects.f1
helpviewer_keywords:
- Transfer SQL Server Objects Task Editor
ms.assetid: 8cc09118-70ac-4013-8308-d87f8411ca0c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7038939b02d17b2449a374be51f7f9fa42eae7d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703108"
---
# <a name="transfer-sql-server-objects-task-editor-objects-page"></a><span data-ttu-id="1b822-102">Éditeur de tâche de transfert d'objets SQL (page Objets)</span><span class="sxs-lookup"><span data-stu-id="1b822-102">Transfer SQL Server Objects Task Editor (Objects Page)</span></span>
  <span data-ttu-id="1b822-103">Utilisez la page **Objets** de la boîte de dialogue **Éditeur de tâche de transfert d’objets SQL** pour spécifier les propriétés de copie d’un ou plusieurs objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à une autre.</span><span class="sxs-lookup"><span data-stu-id="1b822-103">Use the **Objects** page of the **Transfer SQL Server Objects Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="1b822-104">Les tables, les vues, les procédures stockées et les fonctions définies par l’utilisateur représentent quelques exemples des objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que vous pouvez copier.</span><span class="sxs-lookup"><span data-stu-id="1b822-104">Tables, views, stored procedures, and user-defined functions are a few examples of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects that you can copy.</span></span> <span data-ttu-id="1b822-105">Pour plus d'informations sur cette tâche, consultez [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span><span class="sxs-lookup"><span data-stu-id="1b822-105">For more information about this task, see [Transfer SQL Server Objects Task](control-flow/transfer-sql-server-objects-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b822-106">L’utilisateur qui crée la tâche de transfert d’objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit disposer des autorisations suffisantes sur les objets du serveur source pour les sélectionner pour la copie, ainsi que de l’autorisation d’accéder à la base de données du serveur de destination où les objets seront transférés.</span><span class="sxs-lookup"><span data-stu-id="1b822-106">The user who creates the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task must have sufficient permissions on the source server objects to select them for copying, and permission to access the destination server database where the objects will be transferred.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="1b822-107">Options statiques</span><span class="sxs-lookup"><span data-stu-id="1b822-107">Static Options</span></span>  
 <span data-ttu-id="1b822-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="1b822-108">**SourceConnection**</span></span>  
 <span data-ttu-id="1b822-109">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="1b822-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="1b822-110">**SourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="1b822-110">**SourceDatabase**</span></span>  
 <span data-ttu-id="1b822-111">Sélectionnez une base de données sur le serveur source à partir duquel les objets seront copiés.</span><span class="sxs-lookup"><span data-stu-id="1b822-111">Select a database on the source server from which objects will be copied.</span></span>  
  
 <span data-ttu-id="1b822-112">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="1b822-112">**DestinationConnection**</span></span>  
 <span data-ttu-id="1b822-113">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-113">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="1b822-114">**DestinationDatabase**</span><span class="sxs-lookup"><span data-stu-id="1b822-114">**DestinationDatabase**</span></span>  
 <span data-ttu-id="1b822-115">Sélectionnez une base de données sur le serveur de destination dans lequel les objets seront copiés.</span><span class="sxs-lookup"><span data-stu-id="1b822-115">Select a database on the destination server to which objects will be copied.</span></span>  
  
 <span data-ttu-id="1b822-116">**DropObjectsFirst**</span><span class="sxs-lookup"><span data-stu-id="1b822-116">**DropObjectsFirst**</span></span>  
 <span data-ttu-id="1b822-117">Déterminez si les objets sélectionnés sont d'abord supprimés du serveur de destination avant la copie.</span><span class="sxs-lookup"><span data-stu-id="1b822-117">Select whether the selected objects will be dropped first on the destination server before copying.</span></span>  
  
 <span data-ttu-id="1b822-118">**IncludeExtendedProperties**</span><span class="sxs-lookup"><span data-stu-id="1b822-118">**IncludeExtendedProperties**</span></span>  
 <span data-ttu-id="1b822-119">Déterminez si les propriétés étendues sont incluses lorsque les objets sont copiés du serveur source au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-119">Select whether extended properties will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="1b822-120">**CopyData**</span><span class="sxs-lookup"><span data-stu-id="1b822-120">**CopyData**</span></span>  
 <span data-ttu-id="1b822-121">Déterminez si les données sont incluses lorsque les objets sont copiés du serveur source au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-121">Select whether data will be included when objects are copied from the source to the destination server.</span></span>  
  
 <span data-ttu-id="1b822-122">**ExistingData**</span><span class="sxs-lookup"><span data-stu-id="1b822-122">**ExistingData**</span></span>  
 <span data-ttu-id="1b822-123">Spécifiez comment les données seront copiées sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-123">Specify how data will be copied to the destination server.</span></span> <span data-ttu-id="1b822-124">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="1b822-124">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="1b822-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="1b822-125">Value</span></span>|<span data-ttu-id="1b822-126">Description</span><span class="sxs-lookup"><span data-stu-id="1b822-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1b822-127">**Replace**</span><span class="sxs-lookup"><span data-stu-id="1b822-127">**Replace**</span></span>|<span data-ttu-id="1b822-128">Les données du serveur de destination seront remplacées.</span><span class="sxs-lookup"><span data-stu-id="1b822-128">Data on the destination server will be overwritten.</span></span>|  
|<span data-ttu-id="1b822-129">**Append**</span><span class="sxs-lookup"><span data-stu-id="1b822-129">**Append**</span></span>|<span data-ttu-id="1b822-130">Les données copiées à partir du serveur source seront ajoutées aux données existantes sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-130">Data copied from the source server will be appended to existing data on the destination server.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1b822-131">L’option **ExistingData** est disponible uniquement quand **CopyData** a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="1b822-131">The **ExistingData** option is only available when **CopyData** is set to **True**.</span></span>  
  
 <span data-ttu-id="1b822-132">**CopySchema**</span><span class="sxs-lookup"><span data-stu-id="1b822-132">**CopySchema**</span></span>  
 <span data-ttu-id="1b822-133">Déterminez si le schéma est copié pendant la tâche de transfert d’objets [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b822-133">Select whether the schema is copied during the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b822-134">**CopySchema** est disponible uniquement pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-134">**CopySchema** is only available for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-135">**UseCollation**</span><span class="sxs-lookup"><span data-stu-id="1b822-135">**UseCollation**</span></span>  
 <span data-ttu-id="1b822-136">Déterminez si le transfert des objets doit inclure le classement spécifié sur le serveur source.</span><span class="sxs-lookup"><span data-stu-id="1b822-136">Select whether the transfer of objects should include the collation specified on the source server.</span></span>  
  
 <span data-ttu-id="1b822-137">**IncludeDependentObjects**</span><span class="sxs-lookup"><span data-stu-id="1b822-137">**IncludeDependentObjects**</span></span>  
 <span data-ttu-id="1b822-138">Déterminez si la copie des objets sélectionnés inclut en cascade les autres objets qui dépendent de ces objets sélectionnés pour la copie.</span><span class="sxs-lookup"><span data-stu-id="1b822-138">Select whether copying the selected objects will cascade to include other objects that depend on the objects selected for copying.</span></span>  
  
 <span data-ttu-id="1b822-139">**CopyAllObjects**</span><span class="sxs-lookup"><span data-stu-id="1b822-139">**CopyAllObjects**</span></span>  
 <span data-ttu-id="1b822-140">Déterminez si la tâche copie tous les objets de la base de données source spécifiée ou uniquement les objets sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-140">Select whether the task will copy all objects in the specified source database or only selected objects.</span></span>  <span data-ttu-id="1b822-141">Si cette option a la valeur False, vous pouvez sélectionner les objets à transférer et afficher les options dynamiques dans la section **CopyAllObjects**.</span><span class="sxs-lookup"><span data-stu-id="1b822-141">Setting this option to False gives you the option to select the objects to transfer, and displays the dynamic options in the section, **CopyAllObjects**.</span></span>  
  
 <span data-ttu-id="1b822-142">**ObjectsToCopy**</span><span class="sxs-lookup"><span data-stu-id="1b822-142">**ObjectsToCopy**</span></span>  
 <span data-ttu-id="1b822-143">Développez **ObjectsToCopy** pour spécifier les objets qui doivent être copiés de la base de données source dans la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="1b822-143">Expand **ObjectsToCopy** to specify which objects should be copied from the source database to the destination database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b822-144">**ObjectsToCopy** est disponible uniquement quand **CopyAllObjects** a la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="1b822-144">**ObjectsToCopy** is only available when **CopyAllObjects** is set to **False**.</span></span>  
  
 <span data-ttu-id="1b822-145">Les options de copie des types d’objets suivants sont prises en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1b822-145">The options to copy the following types of objects are supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="1b822-146">Assemblys</span><span class="sxs-lookup"><span data-stu-id="1b822-146">Assemblies</span></span>  
  
 <span data-ttu-id="1b822-147">Fonctions de partition</span><span class="sxs-lookup"><span data-stu-id="1b822-147">Partition functions</span></span>  
  
 <span data-ttu-id="1b822-148">Schémas de partition</span><span class="sxs-lookup"><span data-stu-id="1b822-148">Partition schemes</span></span>  
  
 <span data-ttu-id="1b822-149">Schémas</span><span class="sxs-lookup"><span data-stu-id="1b822-149">Schemas</span></span>  
  
 <span data-ttu-id="1b822-150">Fonctions d'agrégation définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1b822-150">User-defined aggregates</span></span>  
  
 <span data-ttu-id="1b822-151">Types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1b822-151">User-defined types</span></span>  
  
 <span data-ttu-id="1b822-152">Collections de schémas XML</span><span class="sxs-lookup"><span data-stu-id="1b822-152">XML schema collections</span></span>  
  
 <span data-ttu-id="1b822-153">**CopyDatabaseUsers**</span><span class="sxs-lookup"><span data-stu-id="1b822-153">**CopyDatabaseUsers**</span></span>  
 <span data-ttu-id="1b822-154">Déterminez si les utilisateurs de la base de données doivent être inclus dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-154">Specify whether database users should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-155">**CopyDatabaseRoles**</span><span class="sxs-lookup"><span data-stu-id="1b822-155">**CopyDatabaseRoles**</span></span>  
 <span data-ttu-id="1b822-156">Déterminez si les rôles de la base de données doivent être inclus dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-156">Specify whether database roles should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-157">**CopySqlServerLogins**</span><span class="sxs-lookup"><span data-stu-id="1b822-157">**CopySqlServerLogins**</span></span>  
 <span data-ttu-id="1b822-158">Déterminez si les connexions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doivent être incluses dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-158">Specify whether [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-159">**CopyObjectLevelPermissions**</span><span class="sxs-lookup"><span data-stu-id="1b822-159">**CopyObjectLevelPermissions**</span></span>  
 <span data-ttu-id="1b822-160">Déterminez si les autorisations au niveau objet doivent être incluses dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-160">Specify whether object-level permissions should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-161">**CopyIndexes**</span><span class="sxs-lookup"><span data-stu-id="1b822-161">**CopyIndexes**</span></span>  
 <span data-ttu-id="1b822-162">Déterminez si les index doivent être inclus dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-162">Specify whether indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-163">**CopyTriggers**</span><span class="sxs-lookup"><span data-stu-id="1b822-163">**CopyTriggers**</span></span>  
 <span data-ttu-id="1b822-164">Déterminez si les déclencheurs doivent être inclus dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-164">Specify whether triggers should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-165">**CopyFullTextIndexes**</span><span class="sxs-lookup"><span data-stu-id="1b822-165">**CopyFullTextIndexes**</span></span>  
 <span data-ttu-id="1b822-166">Déterminez si les index de texte intégral doivent être inclus dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-166">Specify whether full-text indexes should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-167">**CopyPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="1b822-167">**CopyPrimaryKeys**</span></span>  
 <span data-ttu-id="1b822-168">Déterminez si les clés primaires doivent être incluses dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-168">Specify whether primary keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-169">**CopyForeignKeys**</span><span class="sxs-lookup"><span data-stu-id="1b822-169">**CopyForeignKeys**</span></span>  
 <span data-ttu-id="1b822-170">Déterminez si les clés étrangères doivent être incluses dans le transfert.</span><span class="sxs-lookup"><span data-stu-id="1b822-170">Specify whether foreign keys should be included in the transfer.</span></span>  
  
 <span data-ttu-id="1b822-171">**GenerateScriptsInUnicode**</span><span class="sxs-lookup"><span data-stu-id="1b822-171">**GenerateScriptsInUnicode**</span></span>  
 <span data-ttu-id="1b822-172">Déterminez si les scripts de transfert créés sont au format Unicode.</span><span class="sxs-lookup"><span data-stu-id="1b822-172">Specify whether the generated transfer scripts are in Unicode format.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="1b822-173">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="1b822-173">Dynamic Options</span></span>  
  
### <a name="copyallobjects--false"></a><span data-ttu-id="1b822-174">CopyAllObjects = False</span><span class="sxs-lookup"><span data-stu-id="1b822-174">CopyAllObjects = False</span></span>  
 <span data-ttu-id="1b822-175">**CopyAllTables**</span><span class="sxs-lookup"><span data-stu-id="1b822-175">**CopyAllTables**</span></span>  
 <span data-ttu-id="1b822-176">Déterminez si la tâche copie toutes les tables de la base de données source spécifiée ou uniquement les tables sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-176">Select whether the task will copy all tables in the specified source database or only the selected tables.</span></span>  
  
 <span data-ttu-id="1b822-177">**TablesList**</span><span class="sxs-lookup"><span data-stu-id="1b822-177">**TablesList**</span></span>  
 <span data-ttu-id="1b822-178">Cliquez pour ouvrir la boîte de dialogue **Sélectionner des tables** .</span><span class="sxs-lookup"><span data-stu-id="1b822-178">Click to open the **Select Tables** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-179">**CopyAllViews**</span><span class="sxs-lookup"><span data-stu-id="1b822-179">**CopyAllViews**</span></span>  
 <span data-ttu-id="1b822-180">Déterminez si la tâche copie toutes les vues de la base de données source spécifiée ou uniquement les vues sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-180">Select whether the task will copy all views in the specified source database or only the selected views.</span></span>  
  
 <span data-ttu-id="1b822-181">**ViewsList**</span><span class="sxs-lookup"><span data-stu-id="1b822-181">**ViewsList**</span></span>  
 <span data-ttu-id="1b822-182">Cliquez pour ouvrir la boîte de dialogue **Sélectionner des vues** .</span><span class="sxs-lookup"><span data-stu-id="1b822-182">Click to open the **Select Views** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-183">**CopyAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="1b822-183">**CopyAllStoredProcedures**</span></span>  
 <span data-ttu-id="1b822-184">Déterminez si la tâche copie toutes les procédures stockées définies par l'utilisateur dans la base de données source spécifiée ou uniquement celles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-184">Select whether the task will copy all user-defined stored procedures in the specified source database or only the selected procedures.</span></span>  
  
 <span data-ttu-id="1b822-185">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="1b822-185">**StoredProceduresList**</span></span>  
 <span data-ttu-id="1b822-186">Cliquez pour ouvrir la boîte de dialogue **Sélectionner des procédures stockées** .</span><span class="sxs-lookup"><span data-stu-id="1b822-186">Click to open the **Select Stored Procedures** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-187">**CopyAllUserDefinedFunctions**</span><span class="sxs-lookup"><span data-stu-id="1b822-187">**CopyAllUserDefinedFunctions**</span></span>  
 <span data-ttu-id="1b822-188">Déterminez si la tâche copie toutes les fonctions définies par l'utilisateur dans la base de données source spécifiée ou uniquement celles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-188">Select whether the task will copy all user-defined functions in the specified source database or only the selected UDFs.</span></span>  
  
 <span data-ttu-id="1b822-189">**UserDefinedFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="1b822-189">**UserDefinedFunctionsList**</span></span>  
 <span data-ttu-id="1b822-190">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les fonctions définies par l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="1b822-190">Click to open the **Select User Defined Functions** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-191">**CopyAllDefaults**</span><span class="sxs-lookup"><span data-stu-id="1b822-191">**CopyAllDefaults**</span></span>  
 <span data-ttu-id="1b822-192">Déterminez si la tâche copie toutes les valeurs par défaut de la base de données source spécifiée ou uniquement les valeurs par défaut sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-192">Select whether the task will copy all defaults in the specified source database or only the selected defaults.</span></span>  
  
 <span data-ttu-id="1b822-193">**DefaultsList**</span><span class="sxs-lookup"><span data-stu-id="1b822-193">**DefaultsList**</span></span>  
 <span data-ttu-id="1b822-194">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les valeurs par défaut** .</span><span class="sxs-lookup"><span data-stu-id="1b822-194">Click to open the **Select Defaults** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-195">**CopyAllUserDefinedDataTypes**</span><span class="sxs-lookup"><span data-stu-id="1b822-195">**CopyAllUserDefinedDataTypes**</span></span>  
 <span data-ttu-id="1b822-196">Déterminez si la tâche copie tous les types de données définis par l'utilisateur dans la base de données source spécifiée ou uniquement ceux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-196">Select whether the task will copy all user-defined data types in the specified source database or only the selected user-defined data types.</span></span>  
  
 <span data-ttu-id="1b822-197">**UserDefinedDataTypesList**</span><span class="sxs-lookup"><span data-stu-id="1b822-197">**UserDefinedDataTypesList**</span></span>  
 <span data-ttu-id="1b822-198">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les types de données définis par l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="1b822-198">Click to open the **Select User-Defined Data Types** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-199">**CopyAllPartitionFunctions**</span><span class="sxs-lookup"><span data-stu-id="1b822-199">**CopyAllPartitionFunctions**</span></span>  
 <span data-ttu-id="1b822-200">Déterminez si la tâche copie toutes les fonctions de partition définies par l'utilisateur dans la base de données source spécifiée ou uniquement celles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-200">Select whether the task will copy all user-defined partition functions in the specified source database or only the selected partition functions.</span></span> <span data-ttu-id="1b822-201">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-201">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-202">**PartitionFunctionsList**</span><span class="sxs-lookup"><span data-stu-id="1b822-202">**PartitionFunctionsList**</span></span>  
 <span data-ttu-id="1b822-203">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les fonctions de partition** .</span><span class="sxs-lookup"><span data-stu-id="1b822-203">Click to open the **Select Partition Functions** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-204">**CopyAllPartitionSchemes**</span><span class="sxs-lookup"><span data-stu-id="1b822-204">**CopyAllPartitionSchemes**</span></span>  
 <span data-ttu-id="1b822-205">Déterminez si la tâche copie tous les schémas de partition de la base de données source spécifiée ou uniquement ceux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-205">Select whether the task will copy all partition schemes in the specified source database or only the selected partition schemes.</span></span> <span data-ttu-id="1b822-206">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-206">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-207">**PartitionSchemesList**</span><span class="sxs-lookup"><span data-stu-id="1b822-207">**PartitionSchemesList**</span></span>  
 <span data-ttu-id="1b822-208">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les schémas de partition** .</span><span class="sxs-lookup"><span data-stu-id="1b822-208">Click to open the **Select Partition Schemes** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-209">**CopyAllSchemas**</span><span class="sxs-lookup"><span data-stu-id="1b822-209">**CopyAllSchemas**</span></span>  
 <span data-ttu-id="1b822-210">Déterminez si la tâche copie tous les schémas de la base de données source spécifiée ou uniquement les schémas sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-210">Select whether the task will copy all schemas in the specified source database or only the selected schemas.</span></span> <span data-ttu-id="1b822-211">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-211">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-212">**SchemasList**</span><span class="sxs-lookup"><span data-stu-id="1b822-212">**SchemasList**</span></span>  
 <span data-ttu-id="1b822-213">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les schémas** .</span><span class="sxs-lookup"><span data-stu-id="1b822-213">Click to open the **Select Schemas** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-214">**CopyAllSqlAssemblies**</span><span class="sxs-lookup"><span data-stu-id="1b822-214">**CopyAllSqlAssemblies**</span></span>  
 <span data-ttu-id="1b822-215">Déterminez si la tâche copie tous les assemblys SQL de la base de données source spécifiée ou uniquement les assemblys SQL sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-215">Select whether the task will copy all SQL assemblies in the specified source database or only the selected SQL assemblies.</span></span> <span data-ttu-id="1b822-216">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-216">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-217">**SqlAssembliesList**</span><span class="sxs-lookup"><span data-stu-id="1b822-217">**SqlAssembliesList**</span></span>  
 <span data-ttu-id="1b822-218">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les assemblys SQL** .</span><span class="sxs-lookup"><span data-stu-id="1b822-218">Click to open the **Select SQL Assemblies** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-219">**CopyAllUserDefinedAggregates**</span><span class="sxs-lookup"><span data-stu-id="1b822-219">**CopyAllUserDefinedAggregates**</span></span>  
 <span data-ttu-id="1b822-220">Déterminez si la tâche copie toutes les fonctions d'agrégation définies par l'utilisateur dans la base de données source spécifiée ou uniquement celles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-220">Select whether the task will copy all user-defined aggregates in the specified source database or only the selected user-defined aggregates.</span></span> <span data-ttu-id="1b822-221">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-221">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-222">**UserDefinedAggregatesList**</span><span class="sxs-lookup"><span data-stu-id="1b822-222">**UserDefinedAggregatesList**</span></span>  
 <span data-ttu-id="1b822-223">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les fonctions d’agrégation définies par l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="1b822-223">Click to open the **Select User-Defined Aggregates** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-224">**CopyAllUserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="1b822-224">**CopyAllUserDefinedTypes**</span></span>  
 <span data-ttu-id="1b822-225">Déterminez si la tâche copie tous les types définis par l'utilisateur dans la base de données source spécifiée ou uniquement ceux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="1b822-225">Select whether the task will copy all user-defined types in the specified source database or only the selected UDTs.</span></span> <span data-ttu-id="1b822-226">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-226">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-227">**UserDefinedTypes**</span><span class="sxs-lookup"><span data-stu-id="1b822-227">**UserDefinedTypes**</span></span>  
 <span data-ttu-id="1b822-228">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les types définis par l’utilisateur** .</span><span class="sxs-lookup"><span data-stu-id="1b822-228">Click to open the **Select User-Defined Types** dialog box.</span></span>  
  
 <span data-ttu-id="1b822-229">**CopyAllXmlSchemaCollections**</span><span class="sxs-lookup"><span data-stu-id="1b822-229">**CopyAllXmlSchemaCollections**</span></span>  
 <span data-ttu-id="1b822-230">Déterminez si la tâche copie toutes les collections de schémas XML de la base de données source spécifiée ou uniquement celles sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="1b822-230">Select whether the task will copy all XML Schema collections in the specified source database or only the selected XML schema collections.</span></span> <span data-ttu-id="1b822-231">Cette option est prise en charge uniquement sur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b822-231">Supported only on [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1b822-232">**XmlSchemaCollectionsList**</span><span class="sxs-lookup"><span data-stu-id="1b822-232">**XmlSchemaCollectionsList**</span></span>  
 <span data-ttu-id="1b822-233">Cliquez pour ouvrir la boîte de dialogue **Sélectionner les collections du schéma XML** .</span><span class="sxs-lookup"><span data-stu-id="1b822-233">Click to open the **Select XML Schema Collections** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b822-234">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b822-234">See Also</span></span>  
 <span data-ttu-id="1b822-235">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1b822-235">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="1b822-236">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1b822-236">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="1b822-237">[Éditeur de tâche de transfert d’objets SQL Server &#40;page Général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="1b822-237">[Transfer SQL Server Objects Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="1b822-238">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="1b822-238">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="1b822-239">[Formats de données pour l’importation ou l’exportation en bloc &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1b822-239">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](../relational-databases/import-export/data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 [<span data-ttu-id="1b822-240">Considérations sur la sécurité pour une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b822-240">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
