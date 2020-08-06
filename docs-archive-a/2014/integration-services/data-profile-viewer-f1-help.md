---
title: Aide (F1) de la visionneuse du profil des données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dataprofileviewer.f1
helpviewer_keywords:
- Data Profile Viewer [Integration Services]
- Data Profiling task [Integration Services], viewer
ms.assetid: 3469c60a-8f4f-46ba-999a-cb9070197fea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7003e1299938bd53a6d16a5597d4566ba5c46579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602225"
---
# <a name="data-profile-viewer-f1-help"></a><span data-ttu-id="c1477-102">Aide F1 de la Visionneuse du profil des données</span><span class="sxs-lookup"><span data-stu-id="c1477-102">Data Profile Viewer F1 Help</span></span>
  <span data-ttu-id="c1477-103">Utilisez la Visionneuse du profil des données pour afficher la sortie de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="c1477-103">Use the Data Profile Viewer to view the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="c1477-104">Pour plus d’informations sur le mode d’utilisation de la Visionneuse du profil des données, consultez [Visionneuse du profil des données](control-flow/data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="c1477-104">For more information about how to use the Data Profile Viewer, see [Data Profile Viewer](control-flow/data-profile-viewer.md).</span></span> <span data-ttu-id="c1477-105">Pour plus d’informations sur l’utilisation de la tâche de profilage des données, qui crée la sortie de profil que vous analysez dans la Visionneuse du profil des données, consultez [Configuration de la tâche de profilage des données](control-flow/data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="c1477-105">For more information about how to use the Data Profiling task, which creates the profile output that you analyze in the Data Profile Viewer, see [Setup of the Data Profiling Task](control-flow/data-profiling-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c1477-106">Options statiques</span><span class="sxs-lookup"><span data-stu-id="c1477-106">Static Options</span></span>  
 <span data-ttu-id="c1477-107">**Ouvrir**</span><span class="sxs-lookup"><span data-stu-id="c1477-107">**Open**</span></span>  
 <span data-ttu-id="c1477-108">Cliquez pour accéder au fichier enregistré qui contient la sortie de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="c1477-108">Click to browse for the saved file that contains the output of the Data Profiling task.</span></span>  
  
 <span data-ttu-id="c1477-109">Volet**Profils**</span><span class="sxs-lookup"><span data-stu-id="c1477-109">**Profiles** pane</span></span>  
 <span data-ttu-id="c1477-110">Développez l’arborescence du volet **Profils** pour consulter les profils inclus dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="c1477-110">Expand the tree in the **Profiles** pane to see the profiles that are included in the output.</span></span> <span data-ttu-id="c1477-111">Sélectionnez un profil afin d'afficher les résultats de ce profil.</span><span class="sxs-lookup"><span data-stu-id="c1477-111">Select a profile to view the results for that profile.</span></span>  
  
 <span data-ttu-id="c1477-112">Volet**Message**</span><span class="sxs-lookup"><span data-stu-id="c1477-112">**Message** pane</span></span>  
 <span data-ttu-id="c1477-113">Affiche des messages d'état.</span><span class="sxs-lookup"><span data-stu-id="c1477-113">Displays status messages.</span></span>  
  
 <span data-ttu-id="c1477-114">Volet**Exploration vers le bas**</span><span class="sxs-lookup"><span data-stu-id="c1477-114">**Drilldown** pane</span></span>  
 <span data-ttu-id="c1477-115">Affiche les lignes de données qui correspondent à une valeur dans la sortie, si la source de données utilisée par la tâche de profilage des données est disponible.</span><span class="sxs-lookup"><span data-stu-id="c1477-115">Displays the rows of data that match a value in the output, if the data source that is used by the Data Profiling task is available.</span></span>  
  
 <span data-ttu-id="c1477-116">Par exemple, si vous affichez la sortie d’un profil de distribution de valeurs de colonne pour une colonne des états américains, le volet **Distribution de valeurs** peut contenir une ligne pour « WA ».</span><span class="sxs-lookup"><span data-stu-id="c1477-116">For example, if you are viewing the output of a Column Value Distribution profile for a US State column, the **Detailed Value Distribution** pane might contain a row for "WA".</span></span> <span data-ttu-id="c1477-117">Double-cliquez sur la ligne dans le volet **Distribution de valeurs** pour consulter les lignes de données pour lesquelles la valeur de la colonne d’état est « WA » dans le volet d’exploration.</span><span class="sxs-lookup"><span data-stu-id="c1477-117">Double-click the row in the **Detailed Value Distribution** pane to see the rows of data where the value of the state column is "WA" in the drilldown pane.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="c1477-118">Options dynamiques</span><span class="sxs-lookup"><span data-stu-id="c1477-118">Dynamic Options</span></span>  
  
### <a name="profile-type--column-length-distribution-profile"></a><span data-ttu-id="c1477-119">Type de profil = Profil de distribution de longueurs de colonne</span><span class="sxs-lookup"><span data-stu-id="c1477-119">Profile Type = Column Length Distribution Profile</span></span>  
  
#### <a name="column-length-distribution-profile---column-pane"></a><span data-ttu-id="c1477-120">Profil de distribution de longueurs de colonne - Volet \<column></span><span class="sxs-lookup"><span data-stu-id="c1477-120">Column Length Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="c1477-121">**Longueur minimale**</span><span class="sxs-lookup"><span data-stu-id="c1477-121">**Minimum Length**</span></span>  
 <span data-ttu-id="c1477-122">Affiche la longueur minimale des valeurs de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="c1477-122">Displays the minimum length of values in this column.</span></span>  
  
 <span data-ttu-id="c1477-123">**Longueur maximale**</span><span class="sxs-lookup"><span data-stu-id="c1477-123">**Maximum Length**</span></span>  
 <span data-ttu-id="c1477-124">Affiche la longueur maximale des valeurs de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="c1477-124">Displays the maximum length of values in this column.</span></span>  
  
 <span data-ttu-id="c1477-125">**Ignorer les espaces de début**</span><span class="sxs-lookup"><span data-stu-id="c1477-125">**Ignore Leading Spaces**</span></span>  
 <span data-ttu-id="c1477-126">Indique si ce profil a été calculé avec une valeur `IgnoreLeadingSpaces` True ou False.</span><span class="sxs-lookup"><span data-stu-id="c1477-126">Displays whether this profile was computed with an `IgnoreLeadingSpaces` value of True or False.</span></span> <span data-ttu-id="c1477-127">Cette propriété a été définie dans la page **Demandes de profil** de l’éditeur de tâche de profilage de données.</span><span class="sxs-lookup"><span data-stu-id="c1477-127">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="c1477-128">**Ignorez les espaces de fin**</span><span class="sxs-lookup"><span data-stu-id="c1477-128">**Ignore Trailing Spaces**</span></span>  
 <span data-ttu-id="c1477-129">Indique si ce profil a été calculé avec une valeur `IgnoreTrailingSpaces` True ou False.</span><span class="sxs-lookup"><span data-stu-id="c1477-129">Displays whether this profile was computed with an `IgnoreTrailingSpaces` value of True or False.</span></span> <span data-ttu-id="c1477-130">Cette propriété a été définie dans la page **Demandes de profil** de l’éditeur de tâche de profilage de données.</span><span class="sxs-lookup"><span data-stu-id="c1477-130">This property was set on the **Profile Requests** page of the Data Profiling Task Editor.</span></span>  
  
 <span data-ttu-id="c1477-131">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="c1477-131">**Row Count**</span></span>  
 <span data-ttu-id="c1477-132">Affiche le nombre de lignes présentes dans la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c1477-132">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-length-distribution-pane"></a><span data-ttu-id="c1477-133">Volet de distribution de longueurs détaillé</span><span class="sxs-lookup"><span data-stu-id="c1477-133">Detailed Length Distribution pane</span></span>  
 <span data-ttu-id="c1477-134">**Longueur**</span><span class="sxs-lookup"><span data-stu-id="c1477-134">**Length**</span></span>  
 <span data-ttu-id="c1477-135">Affiche les longueurs de colonne trouvées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-135">Displays the column lengths found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-136">**Count**</span><span class="sxs-lookup"><span data-stu-id="c1477-136">**Count**</span></span>  
 <span data-ttu-id="c1477-137">Affiche le nombre de lignes dans lesquelles la valeur de la colonne profilée a la longueur affichée dans la colonne **Longueur** .</span><span class="sxs-lookup"><span data-stu-id="c1477-137">Displays the number of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
 <span data-ttu-id="c1477-138">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="c1477-138">**Percentage**</span></span>  
 <span data-ttu-id="c1477-139">Affiche le pourcentage de lignes dans lesquelles la valeur de la colonne profilée a la longueur affichée dans la colonne **Longueur** .</span><span class="sxs-lookup"><span data-stu-id="c1477-139">Displays the percentage of rows in which the value of the profiled column has the length shown in the **Length** column.</span></span>  
  
### <a name="profile-type--column-null-ratio-profile"></a><span data-ttu-id="c1477-140">Type de profil = Profil de ratio de colonne Null</span><span class="sxs-lookup"><span data-stu-id="c1477-140">Profile Type = Column Null Ratio Profile</span></span>  
  
#### <a name="column-null-ratio-profile---column-pane"></a><span data-ttu-id="c1477-141">Profil de ratio de colonne Null - Volet \<column></span><span class="sxs-lookup"><span data-stu-id="c1477-141">Column Null Ratio Profile - \<column> pane</span></span>  
 <span data-ttu-id="c1477-142">**Nombre null**</span><span class="sxs-lookup"><span data-stu-id="c1477-142">**Null Count**</span></span>  
 <span data-ttu-id="c1477-143">Affiche le nombre de lignes dans lesquelles la colonne profilée possède une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="c1477-143">Displays the number of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="c1477-144">**Pourcentage null**</span><span class="sxs-lookup"><span data-stu-id="c1477-144">**Null Percentage**</span></span>  
 <span data-ttu-id="c1477-145">Affiche le pourcentage de lignes dans lesquelles la colonne profilée possède une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="c1477-145">Displays the percentage of rows in which the profiled column has a null value.</span></span>  
  
 <span data-ttu-id="c1477-146">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="c1477-146">**Row Count**</span></span>  
 <span data-ttu-id="c1477-147">Affiche le nombre de lignes présentes dans la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c1477-147">Displays the number of rows in the table or view.</span></span>  
  
### <a name="profile-type--column-pattern-profile"></a><span data-ttu-id="c1477-148">Type de profil = Profil de modèle de colonne</span><span class="sxs-lookup"><span data-stu-id="c1477-148">Profile Type = Column Pattern Profile</span></span>  
  
#### <a name="column-pattern-profile---column-pane"></a><span data-ttu-id="c1477-149">Profil de motif de colonne - Volet \<column></span><span class="sxs-lookup"><span data-stu-id="c1477-149">Column Pattern Profile - \<column> pane</span></span>  
 <span data-ttu-id="c1477-150">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="c1477-150">**Row Count**</span></span>  
 <span data-ttu-id="c1477-151">Affiche le nombre de lignes présentes dans la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c1477-151">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="pattern-distribution-pane"></a><span data-ttu-id="c1477-152">Volet Distribution de modèles</span><span class="sxs-lookup"><span data-stu-id="c1477-152">Pattern Distribution pane</span></span>  
 <span data-ttu-id="c1477-153">**Modèle**</span><span class="sxs-lookup"><span data-stu-id="c1477-153">**Pattern**</span></span>  
 <span data-ttu-id="c1477-154">Affiche les modèles calculés pour la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-154">Displays the patterns computed for the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-155">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="c1477-155">**Percentage**</span></span>  
 <span data-ttu-id="c1477-156">Affiche le pourcentage de lignes dont les valeurs correspondent au modèle affiché dans la colonne **Modèle** .</span><span class="sxs-lookup"><span data-stu-id="c1477-156">Displays the percentage of rows whose values match the pattern displayed in the **Pattern** column.</span></span>  
  
### <a name="profile-type--column-statistics-profile"></a><span data-ttu-id="c1477-157">Type de profil = Profil de statistiques de colonnes</span><span class="sxs-lookup"><span data-stu-id="c1477-157">Profile Type = Column Statistics Profile</span></span>  
  
#### <a name="column-statistics-profile---column-pane"></a><span data-ttu-id="c1477-158">Profil de statistiques de colonnes - Volet \<column></span><span class="sxs-lookup"><span data-stu-id="c1477-158">Column Statistics Profile - \<column> pane</span></span>  
 <span data-ttu-id="c1477-159">**Minimum**</span><span class="sxs-lookup"><span data-stu-id="c1477-159">**Minimum**</span></span>  
 <span data-ttu-id="c1477-160">Affiche la valeur minimale trouvée dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-160">Displays the minimum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-161">**Maximum**</span><span class="sxs-lookup"><span data-stu-id="c1477-161">**Maximum**</span></span>  
 <span data-ttu-id="c1477-162">Affiche la valeur maximale trouvée dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-162">Displays the maximum value found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-163">**Mean**</span><span class="sxs-lookup"><span data-stu-id="c1477-163">**Mean**</span></span>  
 <span data-ttu-id="c1477-164">Affiche la moyenne des valeurs trouvées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-164">Displays the mean of the values found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-165">**Écart type**</span><span class="sxs-lookup"><span data-stu-id="c1477-165">**Standard Deviation**</span></span>  
 <span data-ttu-id="c1477-166">Affiche l'écart type des valeurs trouvées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-166">Displays the standard deviation of the values found in the profiled column.</span></span>  
  
### <a name="profile-type--column-value-distribution-profile"></a><span data-ttu-id="c1477-167">Type de profil = Profil de distribution de valeurs de colonne</span><span class="sxs-lookup"><span data-stu-id="c1477-167">Profile Type = Column Value Distribution Profile</span></span>  
  
#### <a name="column-value-distribution-profile---column-pane"></a><span data-ttu-id="c1477-168">Profil de distribution de valeurs de colonne - Volet \<column></span><span class="sxs-lookup"><span data-stu-id="c1477-168">Column Value Distribution Profile - \<column> pane</span></span>  
 <span data-ttu-id="c1477-169">**Nombre de valeurs distinctes**</span><span class="sxs-lookup"><span data-stu-id="c1477-169">**Number of Distinct Values**</span></span>  
 <span data-ttu-id="c1477-170">Affiche le nombre de valeurs distinctes trouvées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-170">Displays the count of distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-171">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="c1477-171">**Row Count**</span></span>  
 <span data-ttu-id="c1477-172">Affiche le nombre de lignes présentes dans la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="c1477-172">Displays the number of rows in the table or view.</span></span>  
  
#### <a name="detailed-value-distribution-pane"></a><span data-ttu-id="c1477-173">Volet de distribution de valeurs détaillé</span><span class="sxs-lookup"><span data-stu-id="c1477-173">Detailed Value Distribution pane</span></span>  
 <span data-ttu-id="c1477-174">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="c1477-174">**Value**</span></span>  
 <span data-ttu-id="c1477-175">Affiche les valeurs distinctes trouvées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-175">Displays the distinct values found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-176">**Count**</span><span class="sxs-lookup"><span data-stu-id="c1477-176">**Count**</span></span>  
 <span data-ttu-id="c1477-177">Affiche le nombre de lignes dans lesquelles la colonne profilée a la valeur affichée dans la colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="c1477-177">Displays the number of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
 <span data-ttu-id="c1477-178">**Percentage**</span><span class="sxs-lookup"><span data-stu-id="c1477-178">**Percentage**</span></span>  
 <span data-ttu-id="c1477-179">Affiche le pourcentage de lignes dans lesquelles la colonne profilée a la valeur affichée dans la colonne **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="c1477-179">Displays the percentage of rows in which the profiled column has the value shown in the **Value** column.</span></span>  
  
### <a name="profile-type--candidate-key-profile"></a><span data-ttu-id="c1477-180">Type de profil = Profil de clé candidate</span><span class="sxs-lookup"><span data-stu-id="c1477-180">Profile Type = Candidate Key Profile</span></span>  
  
#### <a name="candidate-key-profile---table-pane"></a><span data-ttu-id="c1477-181">Profil de clé candidate - Volet \<table></span><span class="sxs-lookup"><span data-stu-id="c1477-181">Candidate Key Profile - \<table> pane</span></span>  
 <span data-ttu-id="c1477-182">**Colonnes clés**</span><span class="sxs-lookup"><span data-stu-id="c1477-182">**Key Columns**</span></span>  
 <span data-ttu-id="c1477-183">Affiche les colonnes sélectionnées pour le profilage en tant que clé candidate.</span><span class="sxs-lookup"><span data-stu-id="c1477-183">Displays the columns that were selected for profiling as a candidate key.</span></span>  
  
 <span data-ttu-id="c1477-184">**Puissance de la clé**</span><span class="sxs-lookup"><span data-stu-id="c1477-184">**Key Strength**</span></span>  
 <span data-ttu-id="c1477-185">Affiche la puissance (sous forme de pourcentage) de la colonne ou de la combinaison de colonnes clés candidates.</span><span class="sxs-lookup"><span data-stu-id="c1477-185">Displays the strength (as a percentage) of the candidate key column or combination of columns.</span></span> <span data-ttu-id="c1477-186">Une puissance de clé inférieure à 100 % indique qu'il existe des valeurs dupliquées.</span><span class="sxs-lookup"><span data-stu-id="c1477-186">A key strength of less than 100% indicates that duplicate values exist.</span></span>  
  
#### <a name="key-violations-pane"></a><span data-ttu-id="c1477-187">Volet Violations de clé</span><span class="sxs-lookup"><span data-stu-id="c1477-187">Key Violations pane</span></span>  
 <span data-ttu-id="c1477-188">**\<column1>, \<column2>, etc.**</span><span class="sxs-lookup"><span data-stu-id="c1477-188">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="c1477-189">Affiche les valeurs dupliquées qui ont été détectées dans la colonne profilée.</span><span class="sxs-lookup"><span data-stu-id="c1477-189">Displays the duplicate values that were found in the profiled column.</span></span>  
  
 <span data-ttu-id="c1477-190">**Count**</span><span class="sxs-lookup"><span data-stu-id="c1477-190">**Count**</span></span>  
 <span data-ttu-id="c1477-191">Affiche le nombre de lignes dans lesquelles la colonne spécifiée possède la valeur affichée dans la première colonne.</span><span class="sxs-lookup"><span data-stu-id="c1477-191">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
### <a name="profile-type--functional-dependency-profile"></a><span data-ttu-id="c1477-192">Type de profil = Profil de dépendance fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c1477-192">Profile Type = Functional Dependency Profile</span></span>  
  
#### <a name="functional-dependency-profile-pane"></a><span data-ttu-id="c1477-193">Volet Profil de dépendance fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c1477-193">Functional Dependency Profile pane</span></span>  
 <span data-ttu-id="c1477-194">**Colonnes déterminantes**</span><span class="sxs-lookup"><span data-stu-id="c1477-194">**Determinant Columns**</span></span>  
 <span data-ttu-id="c1477-195">Affiche les colonnes sélectionnées comme colonnes déterminantes.</span><span class="sxs-lookup"><span data-stu-id="c1477-195">Displays the column or columns selected as the determinant column.</span></span> <span data-ttu-id="c1477-196">Dans l'exemple où le même code postal américain doit systématiquement posséder le même état, le code postal est la colonne déterminante.</span><span class="sxs-lookup"><span data-stu-id="c1477-196">In the example where the same United States Zip Code should always have the same state, the Zip Code is the determinant column.</span></span>  
  
 <span data-ttu-id="c1477-197">**Colonnes dépendantes**</span><span class="sxs-lookup"><span data-stu-id="c1477-197">**Dependent Columns**</span></span>  
 <span data-ttu-id="c1477-198">Affiche les colonnes sélectionnées comme colonnes dépendantes.</span><span class="sxs-lookup"><span data-stu-id="c1477-198">Displays the column or columns selected as the dependent column.</span></span> <span data-ttu-id="c1477-199">Dans l'exemple où le même code postal d'état américain doit systématiquement posséder le même état, l'état est la colonne déterminante.</span><span class="sxs-lookup"><span data-stu-id="c1477-199">In the example where the same United States Zip Code should always have the same state, the state is the dependent column.</span></span>  
  
 <span data-ttu-id="c1477-200">**Puissance de la dépendance fonctionnelle**</span><span class="sxs-lookup"><span data-stu-id="c1477-200">**Functional Dependency Strength**</span></span>  
 <span data-ttu-id="c1477-201">Affiche la puissance (sous forme de pourcentage) de la dépendance fonctionnelle entre les colonnes.</span><span class="sxs-lookup"><span data-stu-id="c1477-201">Displays the strength (as a percentage) of the functional dependency between columns.</span></span> <span data-ttu-id="c1477-202">Une puissance de clé inférieure à 100% indique qu'il existe des situations où la valeur déterminante ne détermine pas la valeur dépendante.</span><span class="sxs-lookup"><span data-stu-id="c1477-202">A key strength of less than 100% indicates that there are cases where the determinant value does not determine the dependent value.</span></span> <span data-ttu-id="c1477-203">Dans l'exemple où le même code postal d'état américain doit systématiquement posséder le même état, cela indique probablement que certaines valeurs d'état ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="c1477-203">In the example where the same United States Zip Code should always have the same state, this probably indicates some state values are not valid.</span></span>  
  
#### <a name="functional-dependency-violations-pane"></a><span data-ttu-id="c1477-204">Volet Violations de la dépendance fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c1477-204">Functional Dependency Violations pane</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1477-205">Un pourcentage élevé de valeurs erronées dans les données peut générer des résultats inattendus d'un profil de dépendance fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="c1477-205">A high percentage of erroneous values in the data could lead to unexpected results from a Functional Dependency profile.</span></span> <span data-ttu-id="c1477-206">Par exemple, 90 % des lignes ont une valeur État de « WI » pour une valeur Code postal de « 98052 ».</span><span class="sxs-lookup"><span data-stu-id="c1477-206">For example, 90% of the rows have a State value of "WI" for a Postal Code value of "98052."</span></span> <span data-ttu-id="c1477-207">Le profil signale les lignes qui contiennent la valeur d'état correcte de « WA » en tant que violations.</span><span class="sxs-lookup"><span data-stu-id="c1477-207">The profile reports rows that contain the correct state value of "WA" as violations.</span></span>  
  
 **\<determinant column name>**  
 <span data-ttu-id="c1477-208">Affiche la valeur de la colonne déterminante ou de la combinaison de colonnes dans cette instance d'une violation de dépendance fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="c1477-208">Displays the value of the determinant column or combination of columns in this instance of a functional dependency violation.</span></span>  
  
 **\<dependent column name>**  
 <span data-ttu-id="c1477-209">Affiche la valeur de la colonne dépendante dans cette instance d'une violation de dépendance fonctionnelle.</span><span class="sxs-lookup"><span data-stu-id="c1477-209">Displays the value of the dependent column in this instance of a functional dependency violation.</span></span>  
  
 <span data-ttu-id="c1477-210">**Nombre de supports**</span><span class="sxs-lookup"><span data-stu-id="c1477-210">**Support Count**</span></span>  
 <span data-ttu-id="c1477-211">Affiche le nombre de lignes dans lesquelles la valeur de colonne déterminante détermine la colonne dépendante.</span><span class="sxs-lookup"><span data-stu-id="c1477-211">Displays the number of rows in which the determinant column value determines the dependent column.</span></span>  
  
 <span data-ttu-id="c1477-212">**Nombre de violations**</span><span class="sxs-lookup"><span data-stu-id="c1477-212">**Violation Count**</span></span>  
 <span data-ttu-id="c1477-213">Affiche le nombre de lignes dans lesquelles la valeur de colonne déterminante ne détermine pas la colonne dépendante.</span><span class="sxs-lookup"><span data-stu-id="c1477-213">Displays the number of rows in which the determinant column value does not determine the dependent column.</span></span> <span data-ttu-id="c1477-214">(Il s’agit des lignes sur lesquelles la valeur dépendante est la valeur affichée dans la colonne **\<dependent column name>** .)</span><span class="sxs-lookup"><span data-stu-id="c1477-214">(These are the rows where the dependent value is the value shown in the **\<dependent column name>** column.)</span></span>  
  
 <span data-ttu-id="c1477-215">**Pourcentage de supports**</span><span class="sxs-lookup"><span data-stu-id="c1477-215">**Support Percentage**</span></span>  
 <span data-ttu-id="c1477-216">Affiche le pourcentage de lignes dans lesquelles la colonne déterminante détermine la colonne dépendante.</span><span class="sxs-lookup"><span data-stu-id="c1477-216">Displays the percentage of rows in which the determinant column determines the dependent column.</span></span>  
  
### <a name="profile-type--value-inclusion-profile"></a><span data-ttu-id="c1477-217">Type de profil = Profil d'inclusion de valeur</span><span class="sxs-lookup"><span data-stu-id="c1477-217">Profile Type = Value Inclusion Profile</span></span>  
  
#### <a name="value-inclusion-profile-pane"></a><span data-ttu-id="c1477-218">Volet du profil d'inclusion de valeur</span><span class="sxs-lookup"><span data-stu-id="c1477-218">Value Inclusion Profile pane</span></span>  
 <span data-ttu-id="c1477-219">**Colonnes côté sous-ensemble**</span><span class="sxs-lookup"><span data-stu-id="c1477-219">**Subset Side Columns**</span></span>  
 <span data-ttu-id="c1477-220">Affiche la colonne ou la combinaison de colonnes qui ont été profilées pour déterminer si elles figurent dans les colonnes du sur-ensemble.</span><span class="sxs-lookup"><span data-stu-id="c1477-220">Displays the column or combination of columns that were profiled to determine whether they are in the superset columns.</span></span>  
  
 <span data-ttu-id="c1477-221">**Colonnes côté sur-ensemble**</span><span class="sxs-lookup"><span data-stu-id="c1477-221">**Superset Side Columns**</span></span>  
 <span data-ttu-id="c1477-222">Affiche la colonne ou la combinaison de colonnes qui ont été profilées pour déterminer si elles incluent les valeurs dans les colonnes du sous-ensemble.</span><span class="sxs-lookup"><span data-stu-id="c1477-222">Displays the column or combination of columns that were profiled to determine whether they include the values in the subset columns.</span></span>  
  
 <span data-ttu-id="c1477-223">**Puissance d'inclusion**</span><span class="sxs-lookup"><span data-stu-id="c1477-223">**Inclusion Strength**</span></span>  
 <span data-ttu-id="c1477-224">Affiche la puissance (sous forme de pourcentage) du chevauchement entre les colonnes.</span><span class="sxs-lookup"><span data-stu-id="c1477-224">Displays the strength (as a percentage) of the overlap between columns.</span></span> <span data-ttu-id="c1477-225">Une puissance de clé inférieure à 100 % indique que dans certains cas, la valeur du sous-ensemble est introuvable parmi les valeurs du sur-ensemble.</span><span class="sxs-lookup"><span data-stu-id="c1477-225">A key strength of less than 100% indicates that there are cases where the subset value is not found among the superset values.</span></span>  
  
#### <a name="inclusion-violations-pane"></a><span data-ttu-id="c1477-226">Volet des violations d'inclusion</span><span class="sxs-lookup"><span data-stu-id="c1477-226">Inclusion Violations pane</span></span>  
 <span data-ttu-id="c1477-227">**\<column1>, \<column2>, etc.**</span><span class="sxs-lookup"><span data-stu-id="c1477-227">**\<column1>, \<column2>, etc.**</span></span>  
 <span data-ttu-id="c1477-228">Affiche les valeurs de la colonne ou des colonnes du sous-ensemble qui étaient introuvables dans la colonne ou les colonnes du sur-ensemble.</span><span class="sxs-lookup"><span data-stu-id="c1477-228">Displays the values in the subset column or columns that were not found in the superset column or columns.</span></span>  
  
 <span data-ttu-id="c1477-229">**Count**</span><span class="sxs-lookup"><span data-stu-id="c1477-229">**Count**</span></span>  
 <span data-ttu-id="c1477-230">Affiche le nombre de lignes dans lesquelles la colonne spécifiée possède la valeur affichée dans la première colonne.</span><span class="sxs-lookup"><span data-stu-id="c1477-230">Displays the number of rows in which the specified column has the value shown in the first column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1477-231">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1477-231">See Also</span></span>  
 <span data-ttu-id="c1477-232">[Visionneuse du profil des données](control-flow/data-profile-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="c1477-232">[Data Profile Viewer](control-flow/data-profile-viewer.md) </span></span>  
 [<span data-ttu-id="c1477-233">Tâche de profilage des données et visionneuse</span><span class="sxs-lookup"><span data-stu-id="c1477-233">Data Profiling Task and Viewer</span></span>](control-flow/data-profiling-task-and-viewer.md)  
  
  
