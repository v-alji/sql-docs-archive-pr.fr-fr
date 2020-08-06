---
title: Créer un type de données d’alias défini par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600072"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="5f376-102">Créer un type de données d'alias défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f376-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="5f376-103">Cette rubrique explique comment créer un nouvel alias de type de données défini par l'utilisateur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f376-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5f376-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5f376-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5f376-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5f376-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5f376-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5f376-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5f376-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5f376-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5f376-108">**Pour créer un alias de type de données défini par l'utilisateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5f376-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="5f376-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f376-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5f376-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f376-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5f376-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5f376-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5f376-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5f376-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5f376-113">Le nom d'un alias de type de données défini par l'utilisateur doit être conforme aux règles des identificateurs.</span><span class="sxs-lookup"><span data-stu-id="5f376-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5f376-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5f376-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5f376-115">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5f376-115">Permissions</span></span>  
 <span data-ttu-id="5f376-116">Nécessite l’autorisation CREATE TYPE dans la base de données actuelle et l’autorisation ALTER sur *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="5f376-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="5f376-117">Si *schema_name* n’est pas spécifié, les règles de résolution de noms par défaut pour la détermination du schéma de l’utilisateur actuel s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="5f376-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5f376-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5f376-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="5f376-119">Pour créer un type de données défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f376-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="5f376-120">Dans l’Explorateur d’objets, développez successivement **Bases de données**, une base de données, **Programmabilité**et **Types**, cliquez avec le bouton droit sur **Types de données définis par l’utilisateur**, puis cliquez sur **Nouveau type de données défini par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="5f376-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="5f376-121">**Autoriser les valeurs NULL**</span><span class="sxs-lookup"><span data-stu-id="5f376-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="5f376-122">Spécifiez si le type de données défini par l'utilisateur accepte les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="5f376-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="5f376-123">L'acceptation de valeurs Null par un type de données défini par l'utilisateur existant n'est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="5f376-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="5f376-124">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="5f376-124">**Data type**</span></span>  
     <span data-ttu-id="5f376-125">Sélectionnez le type de données de base dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="5f376-125">Select the base data type from the list box.</span></span> <span data-ttu-id="5f376-126">La zone de liste affiche tous les types de données, à l'exception des types de données `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` et `xml`.</span><span class="sxs-lookup"><span data-stu-id="5f376-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="5f376-127">Le type de données d'un type de données défini par l'utilisateur existant n'est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="5f376-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="5f376-128">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="5f376-128">**Default**</span></span>  
     <span data-ttu-id="5f376-129">(Facultatif) Sélectionnez une règle ou une valeur par défaut pour la liaison à l'alias de type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f376-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="5f376-130">**Longueur/Précision**</span><span class="sxs-lookup"><span data-stu-id="5f376-130">**Length/Precision**</span></span>  
     <span data-ttu-id="5f376-131">Affiche la longueur ou la précision du type de données.</span><span class="sxs-lookup"><span data-stu-id="5f376-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="5f376-132">**Longueur** s’applique aux types de données définis par l’utilisateur basés sur les caractères ; **Précision** s’applique uniquement aux types de données définis par l’utilisateur qui sont numériques.</span><span class="sxs-lookup"><span data-stu-id="5f376-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="5f376-133">Le nom change en fonction du type de données sélectionné précédemment.</span><span class="sxs-lookup"><span data-stu-id="5f376-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="5f376-134">Cette zone ne peut pas être modifiée si la longueur ou la précision du type de données sélectionné est fixe.</span><span class="sxs-lookup"><span data-stu-id="5f376-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="5f376-135">La longueur n'est pas affichée pour les types de données `nvarchar(max)`, `varchar(max)` ou `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="5f376-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="5f376-136">**Nom**</span><span class="sxs-lookup"><span data-stu-id="5f376-136">**Name**</span></span>  
     <span data-ttu-id="5f376-137">Si vous créez un nouvel alias de type de données défini par l'utilisateur, tapez un nom unique à utiliser dans la base de données pour représenter le type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f376-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="5f376-138">Le nombre maximal de caractères doit correspondre au `sysname` type de données système.</span><span class="sxs-lookup"><span data-stu-id="5f376-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="5f376-139">Le nom d'un alias de type de données défini par l'utilisateur existant n'est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="5f376-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="5f376-140">**Règle**</span><span class="sxs-lookup"><span data-stu-id="5f376-140">**Rule**</span></span>  
     <span data-ttu-id="5f376-141">(Facultatif) Sélectionnez une règle pour la liaison à l'alias de type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f376-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="5f376-142">**Mettre à l'échelle**</span><span class="sxs-lookup"><span data-stu-id="5f376-142">**Scale**</span></span>  
     <span data-ttu-id="5f376-143">Spécifie le nombre maximal de chiffres décimaux pouvant figurer à droite de la virgule décimale.</span><span class="sxs-lookup"><span data-stu-id="5f376-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="5f376-144">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="5f376-144">**Schema**</span></span>  
     <span data-ttu-id="5f376-145">Sélectionnez un schéma dans la liste de tous les schémas disponibles pour l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="5f376-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="5f376-146">La sélection par défaut est le schéma par défaut de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="5f376-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="5f376-147">**Stockage**</span><span class="sxs-lookup"><span data-stu-id="5f376-147">**Storage**</span></span>  
     <span data-ttu-id="5f376-148">Affiche la taille de stockage maximale pour l'alias de type de données défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f376-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="5f376-149">Les tailles de stockage maximales varient en fonction de la précision.</span><span class="sxs-lookup"><span data-stu-id="5f376-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="5f376-150">1-9</span><span class="sxs-lookup"><span data-stu-id="5f376-150">1 - 9</span></span>|<span data-ttu-id="5f376-151">5</span><span class="sxs-lookup"><span data-stu-id="5f376-151">5</span></span>|  
    |<span data-ttu-id="5f376-152">10 - 19</span><span class="sxs-lookup"><span data-stu-id="5f376-152">10 - 19</span></span>|<span data-ttu-id="5f376-153">9</span><span class="sxs-lookup"><span data-stu-id="5f376-153">9</span></span>|  
    |<span data-ttu-id="5f376-154">20 - 28</span><span class="sxs-lookup"><span data-stu-id="5f376-154">20 - 28</span></span>|<span data-ttu-id="5f376-155">13</span><span class="sxs-lookup"><span data-stu-id="5f376-155">13</span></span>|  
    |<span data-ttu-id="5f376-156">29 - 38</span><span class="sxs-lookup"><span data-stu-id="5f376-156">29 - 38</span></span>|<span data-ttu-id="5f376-157">17</span><span class="sxs-lookup"><span data-stu-id="5f376-157">17</span></span>|  
  
     <span data-ttu-id="5f376-158">Pour `nchar` les `nvarchar` types de données et, la valeur de stockage est toujours deux fois supérieure à la valeur de **longueur**.</span><span class="sxs-lookup"><span data-stu-id="5f376-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="5f376-159">Le stockage n'est pas affiché pour les types de données `nvarchar(max)`, `varchar(max)` ou `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="5f376-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="5f376-160">Dans la boîte de dialogue **Nouveau type de données défini par l’utilisateur** , dans la zone **Schéma** , entrez le schéma qui doit détenir cet alias de type de données ou utilisez le bouton Parcourir pour sélectionner le schéma.</span><span class="sxs-lookup"><span data-stu-id="5f376-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="5f376-161">Dans la zone **Nom** , entrez le nom du nouvel alias de type de données.</span><span class="sxs-lookup"><span data-stu-id="5f376-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="5f376-162">Dans la zone **Type de données** , sélectionnez le type de données sur lequel le nouvel alias de type de données doit reposer.</span><span class="sxs-lookup"><span data-stu-id="5f376-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="5f376-163">Renseignez les zones **Longueur**, **Précision**et **Échelle** du type de données, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5f376-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="5f376-164">Activez **Autoriser les valeurs NULL** si le nouvel alias de type de données peut autoriser les valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="5f376-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="5f376-165">Dans la zone **Liaison** , renseignez les zones **Par défaut** ou **Règle** pour lier une valeur par défaut ou une règle au nouvel alias de type de données.</span><span class="sxs-lookup"><span data-stu-id="5f376-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="5f376-166">Vous ne pouvez pas créer de valeurs par défaut, ni de règles dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f376-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5f376-167">Utilisez [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f376-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5f376-168">Un exemple de code de création de valeurs par défaut et de règles est disponible dans l'Explorateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="5f376-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5f376-169">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5f376-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="5f376-170">Pour créer un alias de type de données défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f376-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="5f376-171">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f376-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5f376-172">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="5f376-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5f376-173">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="5f376-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="5f376-174">Cet exemple crée un alias de type de données basé sur le type de données `varchar` fourni par le système.</span><span class="sxs-lookup"><span data-stu-id="5f376-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="5f376-175">L'alias de type de données `ssn` est utilisé pour les colonnes comportant des numéros de sécurité sociale à 11 chiffres (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="5f376-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="5f376-176">Cette colonne ne peut pas avoir la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="5f376-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f376-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f376-177">See Also</span></span>  
 <span data-ttu-id="5f376-178">[Identificateur de la base de données](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="5f376-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="5f376-179">CREATE TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5f376-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
