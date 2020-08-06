---
title: Options Demande de profil de ratio de colonne Null (tâche de profilage des données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604684"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="53a24-102">Options Demande de profil de ratio de colonne Null (tâche de profilage des données)</span><span class="sxs-lookup"><span data-stu-id="53a24-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="53a24-103">Utilisez le volet **Propriétés de la demande** de la page **Demandes de profil** pour définir les options de la **Demande de profil de ratio de colonne Null** sélectionnée dans le volet Demandes.</span><span class="sxs-lookup"><span data-stu-id="53a24-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="53a24-104">Un profil de ratio de colonne Null signale le pourcentage de valeurs Null dans la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="53a24-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="53a24-105">Ce profil peut vous aider à identifier des problèmes dans vos données, tels qu'un ratio élevé inattendu de valeurs Null dans une colonne.</span><span class="sxs-lookup"><span data-stu-id="53a24-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="53a24-106">Par exemple, un profil de ratio de colonne Null peut profiler une colonne Code postal et découvrir un pourcentage beaucoup trop élevé de codes postaux manquants.</span><span class="sxs-lookup"><span data-stu-id="53a24-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53a24-107">Les options décrites dans cette rubrique apparaissent sur la page **Demandes de profil** de l' **Éditeur de tâche de profilage de données**.</span><span class="sxs-lookup"><span data-stu-id="53a24-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="53a24-108">Pour plus d’informations sur cette page de l’éditeur, consultez [Éditeur de tâche de profilage de données &#40;page Demandes de profil&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="53a24-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="53a24-109">Pour plus d’informations sur l’utilisation de la tâche de profilage des données, consultez [Configuration de la tâche de profilage des données](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="53a24-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="53a24-110">Pour plus d’informations sur l’utilisation de la visionneuse du profil des données pour analyser le résultat de la tâche de profilage des données, consultez [Visionneuse du profil des données](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="53a24-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="53a24-111">Options Propriétés de la demande</span><span class="sxs-lookup"><span data-stu-id="53a24-111">Request Properties Options</span></span>  
 <span data-ttu-id="53a24-112">Pour une **Demande de profil de ratio de colonne Null**, le volet **Propriétés de la demande** affiche les groupes d'options suivants :</span><span class="sxs-lookup"><span data-stu-id="53a24-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="53a24-113">**Données**, qui incluent les options **TableOrView** et **Column**</span><span class="sxs-lookup"><span data-stu-id="53a24-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="53a24-114">**Généralités**</span><span class="sxs-lookup"><span data-stu-id="53a24-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="53a24-115">Options de données</span><span class="sxs-lookup"><span data-stu-id="53a24-115">Data Options</span></span>  
 <span data-ttu-id="53a24-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="53a24-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="53a24-117">Sélectionnez le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existant qui utilise le fournisseur de données .NET pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) pour se connecter à la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contient la table ou la vue à profiler.</span><span class="sxs-lookup"><span data-stu-id="53a24-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="53a24-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="53a24-118">**TableOrView**</span></span>  
 <span data-ttu-id="53a24-119">Sélectionnez la table ou la vue existante qui contient la colonne à profiler.</span><span class="sxs-lookup"><span data-stu-id="53a24-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="53a24-120">Pour plus d'informations, consultez la section « Options TableorView » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="53a24-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="53a24-121">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="53a24-121">**Column**</span></span>  
 <span data-ttu-id="53a24-122">Sélectionnez la colonne existante à profiler.</span><span class="sxs-lookup"><span data-stu-id="53a24-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="53a24-123">Sélectionnez **(\*)** pour profiler toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="53a24-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="53a24-124">Pour plus d'informations, consultez la section « Options de colonne » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="53a24-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="53a24-125">Options TableOrView</span><span class="sxs-lookup"><span data-stu-id="53a24-125">TableOrView Options</span></span>  
 <span data-ttu-id="53a24-126">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="53a24-126">**Schema**</span></span>  
 <span data-ttu-id="53a24-127">Spécifie le schéma auquel la table sélectionnée appartient.</span><span class="sxs-lookup"><span data-stu-id="53a24-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="53a24-128">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="53a24-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="53a24-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="53a24-129">**Table**</span></span>  
 <span data-ttu-id="53a24-130">Affiche le nom de la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="53a24-130">Displays the name of the selected table.</span></span> <span data-ttu-id="53a24-131">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="53a24-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="53a24-132">Options de colonne</span><span class="sxs-lookup"><span data-stu-id="53a24-132">Column Options</span></span>  
 <span data-ttu-id="53a24-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="53a24-133">**IsWildCard**</span></span>  
 <span data-ttu-id="53a24-134">Indique si le caractère générique **(\*)** a été sélectionné.</span><span class="sxs-lookup"><span data-stu-id="53a24-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="53a24-135">Cette option a la valeur **True** si vous avez sélectionné **(\*)** pour générer le profil de toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="53a24-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="53a24-136">Sa valeur est **False** si vous avez sélectionné une colonne spécifique dont le profil doit être généré.</span><span class="sxs-lookup"><span data-stu-id="53a24-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="53a24-137">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="53a24-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="53a24-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="53a24-138">**ColumnName**</span></span>  
 <span data-ttu-id="53a24-139">Affiche le nom de la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="53a24-139">Displays the name of the selected column.</span></span> <span data-ttu-id="53a24-140">Cette option est vide si vous avez sélectionné **(\*)** pour générer le profil de toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="53a24-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="53a24-141">Cette option est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="53a24-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="53a24-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="53a24-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="53a24-143">Cette option ne s'applique pas au Profil de ratio de colonne Null.</span><span class="sxs-lookup"><span data-stu-id="53a24-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="53a24-144">Options générales</span><span class="sxs-lookup"><span data-stu-id="53a24-144">General Options</span></span>  
 <span data-ttu-id="53a24-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="53a24-145">**RequestID**</span></span>  
 <span data-ttu-id="53a24-146">Tapez un nom descriptif pour identifier cette demande de profil.</span><span class="sxs-lookup"><span data-stu-id="53a24-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="53a24-147">En règle générale, il n'est pas nécessaire de modifier la valeur générée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="53a24-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a24-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53a24-148">See Also</span></span>  
 <span data-ttu-id="53a24-149">[Éditeur de tâche de profilage de données &#40;page Général&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="53a24-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="53a24-150">Formulaire de profil rapide de table simple &#40;tâche de profilage des données&#41;</span><span class="sxs-lookup"><span data-stu-id="53a24-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
