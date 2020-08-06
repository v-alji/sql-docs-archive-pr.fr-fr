---
title: Éditeur de requête d’exploration de données avancé | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 27e7fc46-689d-43a4-9647-1c27d182bdd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2aadf4df75b1ccf6001ad8e97d589ce5666f56ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602689"
---
# <a name="advanced-data-mining-query-editor"></a><span data-ttu-id="b3327-102">Éditeur de requêtes d’exploration de données avancée</span><span class="sxs-lookup"><span data-stu-id="b3327-102">Advanced Data Mining Query Editor</span></span>
  <span data-ttu-id="b3327-103">La **éditeur avancé requête d’exploration de données** est un outil qui vous aide à créer des modèles et des requêtes personnalisés.</span><span class="sxs-lookup"><span data-stu-id="b3327-103">The **Data Mining Query Advanced Editor** is a tool to help you build custom models and queries.</span></span>  
  
 <span data-ttu-id="b3327-104">L'éditeur fournit un ensemble de modèles avec des liens interactifs.</span><span class="sxs-lookup"><span data-stu-id="b3327-104">The editor provides a set of templates with clickable links.</span></span> <span data-ttu-id="b3327-105">Cliquez simplement sur chaque lien, puis utilisez les boîtes de dialogue pour sélectionner des objets ou des valeurs et générer des instructions DMX (Data Mining Extensions) complexes.</span><span class="sxs-lookup"><span data-stu-id="b3327-105">Just click each link, and use the dialog boxes to select objects or values and build complex Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="b3327-106">Basculez la vue vers le modèle d'édition de texte pour modifier l'instruction DMX manuellement.</span><span class="sxs-lookup"><span data-stu-id="b3327-106">You can switch the view to text editing model to modify the DMX statement manually.</span></span>  
  
 <span data-ttu-id="b3327-107">Pour accéder à la **éditeur avancé de requête d’exploration de données**, cliquez sur **requête** , puis sur **avancé**.</span><span class="sxs-lookup"><span data-stu-id="b3327-107">To get to the **Data Mining Query Advanced Editor**, click **Query** and then click **Advanced**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b3327-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="b3327-108">UI element list</span></span>  
 <span data-ttu-id="b3327-109">**Volet Requête DMX**</span><span class="sxs-lookup"><span data-stu-id="b3327-109">**DMX Query pane**</span></span>  
 <span data-ttu-id="b3327-110">L'instruction DMX active s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b3327-110">Here you can see the current DMX statement.</span></span>  
  
 <span data-ttu-id="b3327-111">Cliquez avec le bouton droit sur le volet pour copier l'instruction DMX active.</span><span class="sxs-lookup"><span data-stu-id="b3327-111">Right-click in the pane to copy the current DMX statement.</span></span>  
  
 <span data-ttu-id="b3327-112">Cliquez sur une partie sélectionnée de l'instruction pour obtenir des options spécifiques à cette clause.</span><span class="sxs-lookup"><span data-stu-id="b3327-112">You can click any highlighted part of the statement to get options specific to that clause.</span></span> <span data-ttu-id="b3327-113">Par exemple, pour supprimer, ajouter ou modifier une sortie, cliquez avec le bouton droit sur le **\<Output>** lien.</span><span class="sxs-lookup"><span data-stu-id="b3327-113">For example, to delete, add, or edit an output, right-click the **\<Output>** link.</span></span>  
  
 <span data-ttu-id="b3327-114">**Modifier la requête/Générateur de requêtes**</span><span class="sxs-lookup"><span data-stu-id="b3327-114">**Edit Query/Query Builder**</span></span>  
 <span data-ttu-id="b3327-115">Utilisez ce bouton pour basculer l’éditeur entre un éditeur de texte, dans lequel vous pouvez écrire des instructions DMX directement. et le **Générateur de requêtes**, qui vous aide à générer une instruction DMX.</span><span class="sxs-lookup"><span data-stu-id="b3327-115">Use this button to switch the editor between a text editor, where you can write DMX statements directly; and the **Query Builder**, which helps you build a DMX statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3327-116">**Avertissement :** Si vous changez de vue avant l’exécution de la requête, un message s’affiche indiquant que vous risquez de perdre certaines modifications.</span><span class="sxs-lookup"><span data-stu-id="b3327-116">**Warning:** If you switch views before the query has been run, a message appears stating that you might lose some changes.</span></span> <span data-ttu-id="b3327-117">Si l’instruction DMX est valide, dans de nombreux cas, l' **Générateur de requêtes** peut convertir correctement ces modifications.</span><span class="sxs-lookup"><span data-stu-id="b3327-117">If the DMX statement is valid, in many cases the **Query Builder** might successfully convert these changes.</span></span> <span data-ttu-id="b3327-118">Toutefois, si vous avez généré une instruction DMX particulièrement complexe, vous devez enregistrer votre travail avant de changer de vue.</span><span class="sxs-lookup"><span data-stu-id="b3327-118">However, if you have built a particularly complex DMX statement, you should definitely save your work before switching views.</span></span>  
  
 <span data-ttu-id="b3327-119">**Modèles DMX**</span><span class="sxs-lookup"><span data-stu-id="b3327-119">**DMX Templates**</span></span>  
 <span data-ttu-id="b3327-120">Cliquez et sélectionnez à partir d'une liste de modèles qui contient des exemples DMX.</span><span class="sxs-lookup"><span data-stu-id="b3327-120">Click and select from a list of templates that contain DMX examples.</span></span> <span data-ttu-id="b3327-121">Les modèles fournissent tous les types de modèle ou requête de prédiction nécessaires, notamment les requêtes qui utilisent des tables imbriquées, et les instructions DMX pour gérer des modèles.</span><span class="sxs-lookup"><span data-stu-id="b3327-121">The templates provide just about every type of model or prediction query that you might need, including queries that use nested tables, and DMX statements to manage models.</span></span> <span data-ttu-id="b3327-122">Même si vous connaissez certaines instructions DMX, les modèles permettent de gagner du temps en obtenant la syntaxe correcte.</span><span class="sxs-lookup"><span data-stu-id="b3327-122">Even if you know some DMX, the templates can save you time by getting the syntax right.</span></span>  
  
 <span data-ttu-id="b3327-123">**Choisir un modèle**</span><span class="sxs-lookup"><span data-stu-id="b3327-123">**Choose Model**</span></span>  
 <span data-ttu-id="b3327-124">Cliquez pour afficher la liste des modèles d'exploration de données disponibles sur la connexion actuelle.</span><span class="sxs-lookup"><span data-stu-id="b3327-124">Click to view a list of data mining models available on the current connection.</span></span>  
  
 <span data-ttu-id="b3327-125">Vous pouvez également afficher une liste des modèles disponibles en cliquant sur le nom du modèle dans l’instruction DMX dans le volet **requête DMX** .</span><span class="sxs-lookup"><span data-stu-id="b3327-125">You can also display a list of available models by clicking on the model name in the DMX statement in the **DMX Query** pane.</span></span> <span data-ttu-id="b3327-126">Le nom du modèle est généralement surligné en rouge.</span><span class="sxs-lookup"><span data-stu-id="b3327-126">The model name is typically highlighted in red.</span></span>  
  
 <span data-ttu-id="b3327-127">**Sélectionner l’entrée**</span><span class="sxs-lookup"><span data-stu-id="b3327-127">**Select Input**</span></span>  
 <span data-ttu-id="b3327-128">Cliquez pour sélectionner les données à utiliser comme entrée dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="b3327-128">Click to choose the data to use as input to the mining model.</span></span> <span data-ttu-id="b3327-129">Si aucune source de données n’a été spécifiée, vous pouvez également cliquer sur le **\<Input>** lien, qui est mis en surbrillance en rouge dans le volet **requête DMX** .</span><span class="sxs-lookup"><span data-stu-id="b3327-129">If no data source has been specified, you can also click the **\<Input>** link, which is highlighted in red in the **DMX Query** pane.</span></span>  
  
 <span data-ttu-id="b3327-130">Sélectionnez \*\* \@ InputRowset\*\* dans la liste déroulante pour ouvrir la boîte de dialogue **remplacer InputRowset** et modifier une entrée existante.</span><span class="sxs-lookup"><span data-stu-id="b3327-130">Select **\@InputRowset** from the dropdown list to open the **Replace InputRowset** dialog box and modify an existing input.</span></span>  
  
 <span data-ttu-id="b3327-131">Sélectionnez **Ajouter une entrée** pour ouvrir la boîte de dialogue **Ajouter une entrée** et spécifier une nouvelle source de données.</span><span class="sxs-lookup"><span data-stu-id="b3327-131">Select **Add Input** to open the **Add Input** dialog box and specify a new data source.</span></span>  
  
 <span data-ttu-id="b3327-132">Vous pouvez également modifier une entrée existante en cliquant sur le lien \*\* \@ InputRowset\*\* , qui est mis en surbrillance en rouge dans le volet requête DMX.</span><span class="sxs-lookup"><span data-stu-id="b3327-132">You can also modify an existing input by clicking the **\@InputRowset** link, which is highlighted in red in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b3327-133">**Mapper les colonnes**</span><span class="sxs-lookup"><span data-stu-id="b3327-133">**Map Columns**</span></span>  
 <span data-ttu-id="b3327-134">Sélectionnez des colonnes dans le modèle d'exploration de données et mappez-les aux colonnes de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="b3327-134">Select columns from the mining model and then map them to columns in the external data source.</span></span>  
  
 <span data-ttu-id="b3327-135">Vous pouvez également cliquer sur le lien mis en surbrillance **\<Mapping>** dans le volet requête DMX.</span><span class="sxs-lookup"><span data-stu-id="b3327-135">You can also click the highlighted **\<Mapping>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b3327-136">**Ajouter une sortie**</span><span class="sxs-lookup"><span data-stu-id="b3327-136">**Add Output**</span></span>  
 <span data-ttu-id="b3327-137">Cliquez pour sélectionner les colonnes qui correspondent à la sortie dans la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="b3327-137">Click to choose the columns that should be output as part of a prediction query.</span></span>  
  
 <span data-ttu-id="b3327-138">Vous pouvez également cliquer sur le lien mis en surbrillance **\<Add Output>** dans le volet requête DMX.</span><span class="sxs-lookup"><span data-stu-id="b3327-138">You can also click the highlighted **\<Add Output>** link in the DMX Query pane.</span></span>  
  
 <span data-ttu-id="b3327-139">**Colonnes de modèles**</span><span class="sxs-lookup"><span data-stu-id="b3327-139">**Model Columns**</span></span>  
 <span data-ttu-id="b3327-140">Répertorie les colonnes du modèle d'exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b3327-140">Lists the columns in the selected mining model.</span></span> <span data-ttu-id="b3327-141">Une marque en forme de losange en regard du nom de la colonne indique que celle-ci est une colonne prévisible.</span><span class="sxs-lookup"><span data-stu-id="b3327-141">A diamond mark next to the column name indicates that the column is a predictable column.</span></span>  
  
 <span data-ttu-id="b3327-142">**Colonnes d'entrée**</span><span class="sxs-lookup"><span data-stu-id="b3327-142">**Input Columns**</span></span>  
 <span data-ttu-id="b3327-143">Répertorie les colonnes issues de la source de données externes ajoutées comme entrées.</span><span class="sxs-lookup"><span data-stu-id="b3327-143">Lists the columns from the external data source that have been added as inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3327-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3327-144">See Also</span></span>  
 [<span data-ttu-id="b3327-145">&#40;de requêtes SQL Server des compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="b3327-145">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
  
