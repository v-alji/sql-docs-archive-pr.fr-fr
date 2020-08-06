---
title: Propriétés de la requête (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69636
- vdt.ppg.querydesigner.query
ms.assetid: 07495669-6ed5-4004-904e-aae1230be5e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6e3c8adfb50e15113228afe8b48218f341f19084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697360"
---
# <a name="query-properties-visual-database-tools"></a><span data-ttu-id="64956-102">Propriétés de la requête (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="64956-102">Query Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="64956-103">Ces propriétés apparaissent dans la fenêtre Propriétés lorsque vous avez une requête ouverte dans le Concepteur de requêtes et de vues.</span><span class="sxs-lookup"><span data-stu-id="64956-103">These properties appear in the Properties window when you have a query open in Query and View Designer.</span></span> <span data-ttu-id="64956-104">Sauf indication contraire, vous pouvez modifier ces propriétés dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="64956-104">Unless otherwise noted, you can edit these properties in the Properties window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64956-105">Les propriétés mentionnées dans cette rubrique sont classées par catégorie et non par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="64956-105">The properties in this topic are ordered by category, rather than alphabetically.</span></span>  
  
## <a name="options"></a><span data-ttu-id="64956-106">Options</span><span class="sxs-lookup"><span data-stu-id="64956-106">Options</span></span>  
 <span data-ttu-id="64956-107">**Catégorie Identité**</span><span class="sxs-lookup"><span data-stu-id="64956-107">**Identity Category**</span></span>  
 <span data-ttu-id="64956-108">Se développe pour afficher la propriété **Nom** .</span><span class="sxs-lookup"><span data-stu-id="64956-108">Expand to show the **Name** property.</span></span>  
  
 <span data-ttu-id="64956-109">**Nom**</span><span class="sxs-lookup"><span data-stu-id="64956-109">**Name**</span></span>  
 <span data-ttu-id="64956-110">Affiche le nom de la requête en cours.</span><span class="sxs-lookup"><span data-stu-id="64956-110">Shows the name of the current query.</span></span> <span data-ttu-id="64956-111">Ne peut pas être modifié dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64956-111">Cannot be changed in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="64956-112">**Database Name**</span><span class="sxs-lookup"><span data-stu-id="64956-112">**Database Name**</span></span>  
 <span data-ttu-id="64956-113">Indique le nom de la source de données pour la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="64956-113">Shows the name of the data source for the selected table.</span></span>  
  
 <span data-ttu-id="64956-114">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="64956-114">**Server Name**</span></span>  
 <span data-ttu-id="64956-115">Affiche le nom du serveur de la source de données.</span><span class="sxs-lookup"><span data-stu-id="64956-115">Shows the name of the server for the data source.</span></span>  
  
 <span data-ttu-id="64956-116">**Catégorie Concepteur de requêtes**</span><span class="sxs-lookup"><span data-stu-id="64956-116">**Query Designer Category**</span></span>  
 <span data-ttu-id="64956-117">S'étend pour afficher les propriétés restantes.</span><span class="sxs-lookup"><span data-stu-id="64956-117">Expands to show the remaining properties.</span></span>  
  
 <span data-ttu-id="64956-118">**Table de destination**</span><span class="sxs-lookup"><span data-stu-id="64956-118">**Destination table**</span></span>  
 <span data-ttu-id="64956-119">Spécifie le nom de la table dans laquelle vous insérez des données.</span><span class="sxs-lookup"><span data-stu-id="64956-119">Specify the name of the table into which you are inserting data.</span></span> <span data-ttu-id="64956-120">Cette liste s'affiche si vous créez une requête INSERT ou MAKE TABLE.</span><span class="sxs-lookup"><span data-stu-id="64956-120">This list appears if you are creating an INSERT query or MAKE TABLE query.</span></span> <span data-ttu-id="64956-121">Pour une requête INSERT, sélectionnez un nom de table dans la liste.</span><span class="sxs-lookup"><span data-stu-id="64956-121">For an INSERT query, select a table name from the list.</span></span>  
  
 <span data-ttu-id="64956-122">Pour une requête MAKE TABLE, tapez le nom de la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="64956-122">For a MAKE TABLE query, type the name of the new table.</span></span> <span data-ttu-id="64956-123">Pour créer une table de destination dans une autre source de données, spécifiez un nom de table qualifié complet, y compris le nom de la source de données cible, le propriétaire (le cas échéant) et le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="64956-123">To create a destination table in another data source, specify a fully qualified table name, including the name of the target data source, the owner (if required), and the name of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64956-124">Le Concepteur de requêtes ne vérifie pas si le nom est déjà utilisé, ni si vous avez l'autorisation de créer la table.</span><span class="sxs-lookup"><span data-stu-id="64956-124">Query Designer does not check whether the name is already in use or whether you have permission to create the table.</span></span>  
  
 <span data-ttu-id="64956-125">**Valeurs DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="64956-125">**Distinct values**</span></span>  
 <span data-ttu-id="64956-126">Spécifie que la requête filtrera les doublons dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64956-126">Specify that the query will filter out duplicates in the result set.</span></span> <span data-ttu-id="64956-127">Cette option est utile lorsque vous utilisez uniquement certaines colonnes de la table ou des tables et que ces colonnes peuvent contenir des valeurs dupliquées, ou encore lorsque le processus de jointure de plusieurs tables crée des lignes en double dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64956-127">This option is useful when you are using only some of the columns from the table or tables and those columns might contain duplicate values, or when the process of joining two or more tables produces duplicate rows in the result set.</span></span> <span data-ttu-id="64956-128">Choisir cette option équivaut à insérer le mot DISTINCT dans l'instruction à l'intérieur du volet SQL.</span><span class="sxs-lookup"><span data-stu-id="64956-128">Choosing this option is equivalent to inserting the word DISTINCT into the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="64956-129">**Extension GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="64956-129">**GROUP BY Extension**</span></span>  
 <span data-ttu-id="64956-130">Spécifie que d'autres options sont disponibles pour les requêtes basées sur des requêtes d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="64956-130">Specify that additional options for queries based on aggregate queries are available.</span></span> <span data-ttu-id="64956-131">(S'applique uniquement à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="64956-131">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="64956-132">**Sélectionne toutes les colonnes**</span><span class="sxs-lookup"><span data-stu-id="64956-132">**Output All Columns**</span></span>  
 <span data-ttu-id="64956-133">Spécifie que l'ensemble des colonnes de toutes les tables dans la requête en cours figureront dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64956-133">Specify that all columns from all tables in the current query will be in the result set.</span></span> <span data-ttu-id="64956-134">Choisir cette option équivaut à spécifier un astérisque (\*) à la place des noms de colonnes individuels après le mot clé SELECT dans l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="64956-134">Choosing this option is equivalent to specifying an asterisk (\*) in place of individual column names after the SELECT keyword in the SQL statement.</span></span>  
  
 <span data-ttu-id="64956-135">**Liste de paramètres de la requête**</span><span class="sxs-lookup"><span data-stu-id="64956-135">**Query Parameter List**</span></span>  
 <span data-ttu-id="64956-136">Affiche les paramètres de la requête.</span><span class="sxs-lookup"><span data-stu-id="64956-136">Shows query parameters.</span></span> <span data-ttu-id="64956-137">Pour modifier les paramètres, cliquez sur la propriété, puis cliquez sur le bouton de sélection **(…)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="64956-137">To edit the parameters click the property and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="64956-138">(S'applique uniquement aux bases de données OLE DB génériques.)</span><span class="sxs-lookup"><span data-stu-id="64956-138">(Applies only to generic OLE DB.)</span></span>  
  
 <span data-ttu-id="64956-139">**Commentaire SQL**</span><span class="sxs-lookup"><span data-stu-id="64956-139">**SQL Comment**</span></span>  
 <span data-ttu-id="64956-140">Affiche une description des instructions SQL.</span><span class="sxs-lookup"><span data-stu-id="64956-140">Shows a description of the SQL statements.</span></span> <span data-ttu-id="64956-141">Pour afficher l’intégralité de la description, ou la modifier, cliquez sur la description, puis sur le bouton de sélection **(…)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="64956-141">To see the entire description or to edit it, click the description and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="64956-142">Vos commentaires peuvent contenir les noms des utilisateurs de la requête et le moment d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="64956-142">Your comments can include information such as who uses the query and when they use it.</span></span> <span data-ttu-id="64956-143">(S'applique uniquement aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="64956-143">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 7.0 databases or later.)</span></span>  
  
 <span data-ttu-id="64956-144">**Catégorie Spécification Top**</span><span class="sxs-lookup"><span data-stu-id="64956-144">**Top Specification Category**</span></span>  
 <span data-ttu-id="64956-145">Se développe pour afficher les propriétés **Haut**, **Pour cent**, **Expression**et **Avec liens** .</span><span class="sxs-lookup"><span data-stu-id="64956-145">Expand to show properties for the **Top**, **Percent**, **Expression**, and **With Ties** properties.</span></span>  
  
 <span data-ttu-id="64956-146">**(Top)**</span><span class="sxs-lookup"><span data-stu-id="64956-146">**(Top)**</span></span>  
 <span data-ttu-id="64956-147">Indique que la requête doit contenir une clause TOP, qui ne renvoie que les *n* premières lignes ou *n* pour cent des lignes du jeu de résultats (en commençant par les premières).</span><span class="sxs-lookup"><span data-stu-id="64956-147">Specify hat the query will include a TOP clause, which returns only the first *n* rows or first *n* percentage of rows in the result set.</span></span> <span data-ttu-id="64956-148">Par défaut, la requête retourne les 10 premières lignes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64956-148">The default is that the query returns the first 10 rows in the result set.</span></span>  
  
 <span data-ttu-id="64956-149">Utilisez cette zone pour modifier le nombre de lignes à retourner ou pour spécifier un autre pourcentage.</span><span class="sxs-lookup"><span data-stu-id="64956-149">Use this box to change the number of rows to return or to specify a different percentage.</span></span> <span data-ttu-id="64956-150">(S'applique uniquement à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="64956-150">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later.)</span></span>  
  
 <span data-ttu-id="64956-151">**Expression**</span><span class="sxs-lookup"><span data-stu-id="64956-151">**Expression**</span></span>  
 <span data-ttu-id="64956-152">Spécifie le nombre ou le pourcentage de lignes que la requête doit retourner.</span><span class="sxs-lookup"><span data-stu-id="64956-152">Specify the number or percentage of rows that the query will return.</span></span> <span data-ttu-id="64956-153">Si vous affectez à **Pour cent** la valeur Oui, le nombre indique le pourcentage de lignes que la requête doit retourner ; si vous affectez à **Pour cent** la valeur Non, le nombre représente le nombre de lignes à retourner.</span><span class="sxs-lookup"><span data-stu-id="64956-153">If you set **Percent** to Yes, this number is the percentage of rows the query will return; if you set **Percent** to No, it represents the number of rows to return.</span></span> <span data-ttu-id="64956-154">(S'applique uniquement aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="64956-154">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="64956-155">**Pourcentage**</span><span class="sxs-lookup"><span data-stu-id="64956-155">**Percent**</span></span>  
 <span data-ttu-id="64956-156">Spécifie que la requête doit retourner uniquement les *n* premiers pour cent de lignes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64956-156">Specify that the query will return only the first *n* percent of rows in the result set.</span></span> <span data-ttu-id="64956-157">(S'applique uniquement aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="64956-157">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
 <span data-ttu-id="64956-158">**Avec liens**</span><span class="sxs-lookup"><span data-stu-id="64956-158">**With Ties**</span></span>  
 <span data-ttu-id="64956-159">Spécifie que la vue inclura une clause WITH TIES.</span><span class="sxs-lookup"><span data-stu-id="64956-159">Specify that the view will include a WITH TIES clause.</span></span> <span data-ttu-id="64956-160">WITH TIES est utile si une vue inclut une clause ORDER BY et une clause TOP basée sur un pourcentage.</span><span class="sxs-lookup"><span data-stu-id="64956-160">WITH TIES is useful if a view includes an ORDER BY clause and a TOP clause based on percentage.</span></span> <span data-ttu-id="64956-161">Si cette option est activée et si le pourcentage s'arrête au milieu d'un groupe de lignes auxquelles correspondent des valeurs identiques dans la clause ORDER BY, la vue est agrandie de façon à inclure ces lignes.</span><span class="sxs-lookup"><span data-stu-id="64956-161">If this option is set, and if the percentage cutoff falls in the middle of a set of rows with identical values in the ORDER BY clause, the view is extended to include all such rows.</span></span> <span data-ttu-id="64956-162">(S'applique uniquement aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure.)</span><span class="sxs-lookup"><span data-stu-id="64956-162">(Applies only to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64956-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64956-163">See Also</span></span>  
 <span data-ttu-id="64956-164">[Interroger avec des paramètres &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="64956-164">[Query with Parameters &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="64956-165">Rubriques de procédures relatives à la conception de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="64956-165">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
