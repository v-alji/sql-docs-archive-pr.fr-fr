---
title: Options Demande de profil de distribution de longueurs de colonne (tâche de profilage des données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604686"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="a88ef-102">Options Demande de profil de distribution de longueurs de colonne (tâche de profilage des données)</span><span class="sxs-lookup"><span data-stu-id="a88ef-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="a88ef-103">Utilisez le volet **Propriétés de demandes** de la page **Demandes de profil** pour définir les options de la **Demande de profil de distribution de longueurs de colonne** sélectionnée dans le volet Demandes.</span><span class="sxs-lookup"><span data-stu-id="a88ef-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="a88ef-104">Un profil de distribution de longueurs de colonne signale toutes les longueurs distinctes des valeurs de chaîne dans la colonne sélectionnée, et le pourcentage de lignes dans la table que chaque longueur représente.</span><span class="sxs-lookup"><span data-stu-id="a88ef-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="a88ef-105">Ce profil peut vous aider à identifier les problèmes dans vos données, tels que les valeurs non valides.</span><span class="sxs-lookup"><span data-stu-id="a88ef-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="a88ef-106">Par exemple, vous profilez une colonne de codes d'états des États-Unis à deux caractères et découvrez des valeurs excédant deux caractères.</span><span class="sxs-lookup"><span data-stu-id="a88ef-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a88ef-107">Les options décrites dans cette rubrique apparaissent sur la page **Demandes de profil** de l' **Éditeur de tâche de profilage de données**.</span><span class="sxs-lookup"><span data-stu-id="a88ef-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="a88ef-108">Pour plus d’informations sur cette page de l’éditeur, consultez [Éditeur de tâche de profilage de données &#40;page Demandes de profil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="a88ef-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="a88ef-109">Pour plus d’informations sur l’utilisation de la tâche de profilage des données, consultez [Configuration de la tâche de profilage des données](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="a88ef-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="a88ef-110">Pour plus d’informations sur l’utilisation de la visionneuse du profil des données pour analyser le résultat de la tâche de profilage des données, consultez [Visionneuse du profil des données](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="a88ef-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="a88ef-111">Options Propriétés de la demande</span><span class="sxs-lookup"><span data-stu-id="a88ef-111">Request Properties Options</span></span>  
 <span data-ttu-id="a88ef-112">Pour une **Demande de profil de distribution de longueurs de colonne**, le volet **Propriétés de la demande** affiche les groupes d’options suivants :</span><span class="sxs-lookup"><span data-stu-id="a88ef-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="a88ef-113">**Données**, qui incluent les options **TableOrView** et **Column**</span><span class="sxs-lookup"><span data-stu-id="a88ef-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="a88ef-114">**Généralités**</span><span class="sxs-lookup"><span data-stu-id="a88ef-114">**General**</span></span>  
  
-   <span data-ttu-id="a88ef-115">**Options**</span><span class="sxs-lookup"><span data-stu-id="a88ef-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="a88ef-116">Options de données</span><span class="sxs-lookup"><span data-stu-id="a88ef-116">Data Options</span></span>  
 <span data-ttu-id="a88ef-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="a88ef-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="a88ef-118">Sélectionnez le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existant qui utilise le fournisseur de données .NET pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) pour établir la connexion à la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contient la table ou la vue à profiler.</span><span class="sxs-lookup"><span data-stu-id="a88ef-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="a88ef-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="a88ef-119">**TableOrView**</span></span>  
 <span data-ttu-id="a88ef-120">Sélectionnez la table ou la vue existante qui contient la colonne à profiler.</span><span class="sxs-lookup"><span data-stu-id="a88ef-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="a88ef-121">Pour plus d'informations, consultez la section « Options TableorView » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a88ef-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="a88ef-122">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a88ef-122">**Column**</span></span>  
 <span data-ttu-id="a88ef-123">Sélectionnez la colonne existante à profiler.</span><span class="sxs-lookup"><span data-stu-id="a88ef-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="a88ef-124">Sélectionnez **(\*)** pour profiler toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="a88ef-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="a88ef-125">Pour plus d'informations, consultez la section « Options de colonne » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a88ef-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="a88ef-126">Options TableOrView</span><span class="sxs-lookup"><span data-stu-id="a88ef-126">TableOrView Options</span></span>  
 <span data-ttu-id="a88ef-127">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="a88ef-127">**Schema**</span></span>  
 <span data-ttu-id="a88ef-128">Spécifiez le schéma auquel la table sélectionnée appartient.</span><span class="sxs-lookup"><span data-stu-id="a88ef-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="a88ef-129">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a88ef-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="a88ef-130">**Table**</span><span class="sxs-lookup"><span data-stu-id="a88ef-130">**Table**</span></span>  
 <span data-ttu-id="a88ef-131">Affiche le nom de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a88ef-131">Displays the name of the selected table.</span></span> <span data-ttu-id="a88ef-132">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a88ef-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="a88ef-133">Options de colonne</span><span class="sxs-lookup"><span data-stu-id="a88ef-133">Column Options</span></span>  
 <span data-ttu-id="a88ef-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="a88ef-134">**IsWildCard**</span></span>  
 <span data-ttu-id="a88ef-135">Indique si le caractère générique **(\*)** a été sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a88ef-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="a88ef-136">Cette option a la valeur **True** si vous avez sélectionné **(\*)** pour générer le profil de toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="a88ef-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="a88ef-137">Sa valeur est **False** si vous avez sélectionné une colonne spécifique dont le profil doit être généré.</span><span class="sxs-lookup"><span data-stu-id="a88ef-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="a88ef-138">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a88ef-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="a88ef-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="a88ef-139">**ColumnName**</span></span>  
 <span data-ttu-id="a88ef-140">Affiche le nom de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a88ef-140">Displays the name of the selected column.</span></span> <span data-ttu-id="a88ef-141">Cette option est vide si vous avez sélectionné **(\*)** pour générer le profil de toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="a88ef-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="a88ef-142">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a88ef-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="a88ef-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="a88ef-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="a88ef-144">Cette option ne s'applique pas au profil de distribution de longueurs de colonne.</span><span class="sxs-lookup"><span data-stu-id="a88ef-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="a88ef-145">Options générales</span><span class="sxs-lookup"><span data-stu-id="a88ef-145">General Options</span></span>  
 <span data-ttu-id="a88ef-146">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="a88ef-146">**RequestID**</span></span>  
 <span data-ttu-id="a88ef-147">Tapez un nom descriptif pour identifier cette demande de profil.</span><span class="sxs-lookup"><span data-stu-id="a88ef-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="a88ef-148">En règle générale, il n'est pas nécessaire de modifier la valeur générée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a88ef-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="a88ef-149">Options</span><span class="sxs-lookup"><span data-stu-id="a88ef-149">Options</span></span>  
 <span data-ttu-id="a88ef-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="a88ef-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="a88ef-151">Indiquez si les espaces de début doivent être ignorés lorsque le profil compare des valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="a88ef-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="a88ef-152">La valeur par défaut de cette option est **False**.</span><span class="sxs-lookup"><span data-stu-id="a88ef-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="a88ef-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="a88ef-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="a88ef-154">Indiquez si les espaces de fin doivent être ignorés lorsque le profil compare des valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="a88ef-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="a88ef-155">La valeur par défaut de cette option est **True**.</span><span class="sxs-lookup"><span data-stu-id="a88ef-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88ef-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a88ef-156">See Also</span></span>  
 <span data-ttu-id="a88ef-157">[Éditeur de tâche de profilage de données &#40;page Général&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a88ef-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="a88ef-158">Formulaire de profil rapide de table simple &#40;tâche de profilage des données&#41;</span><span class="sxs-lookup"><span data-stu-id="a88ef-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
