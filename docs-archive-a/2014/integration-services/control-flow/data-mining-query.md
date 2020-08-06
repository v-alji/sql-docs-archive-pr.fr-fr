---
title: Requête d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610809"
---
# <a name="data-mining-query"></a><span data-ttu-id="8ecd4-102">Requête d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="8ecd4-102">Data Mining Query</span></span>
  <span data-ttu-id="8ecd4-103">Le volet de conception contient le Générateur de requêtes de prévisions d'exploration de données, qui peut servir à créer des requêtes de prévisions d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="8ecd4-104">Vous pouvez concevoir des requêtes de prévisions basées sur des tables d'entrée ou des requêtes de prévisions singleton.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="8ecd4-105">Passez à la vue de résultat pour exécuter la requête et afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="8ecd4-106">La vue de la requête affiche la requête DMX (Data Mining Extensions) créée par le Générateur de requêtes de prévisions d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ecd4-107">Options</span><span class="sxs-lookup"><span data-stu-id="8ecd4-107">Options</span></span>  
 <span data-ttu-id="8ecd4-108">Bouton de basculement entre les vues</span><span class="sxs-lookup"><span data-stu-id="8ecd4-108">Switch view button</span></span>  
 <span data-ttu-id="8ecd4-109">Cliquez sur une icône pour basculer entre le volet de conception et le volet de requête.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="8ecd4-110">Par défaut, le volet de conception est ouvert.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="8ecd4-111">Pour basculer vers le volet de conception, cliquez sur l’icône ![Icône de conception](../media/ssis-designicon.gif "Icône de conception").</span><span class="sxs-lookup"><span data-stu-id="8ecd4-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="8ecd4-112">Pour basculer vers le volet de requête, cliquez sur l’icône ![Icône SQL](../media/ssis-queryicon.gif "Icône SQL").</span><span class="sxs-lookup"><span data-stu-id="8ecd4-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="8ecd4-113">**Modèle d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-113">**Mining Model**</span></span>  
 <span data-ttu-id="8ecd4-114">Choisissez le modèle d'exploration de données sur lequel vous souhaitez baser vos prévisions.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="8ecd4-115">**Sélectionner un modèle**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-115">**Select Model**</span></span>  
 <span data-ttu-id="8ecd4-116">Ouvre la boîte de dialogue **Sélectionnez un modèle d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="8ecd4-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="8ecd4-117">**Colonnes d'entrée**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-117">**Input Columns**</span></span>  
 <span data-ttu-id="8ecd4-118">Affiche les colonnes d'entrée sélectionnées utilisées pour générer les prévisions.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="8ecd4-119">**Source**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-119">**Source**</span></span>  
 <span data-ttu-id="8ecd4-120">Sélectionnez dans la liste déroulante la source contenant le champ qui sera utilisé pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="8ecd4-121">Vous pouvez utiliser le modèle d’exploration de données sélectionné dans la table **Modèle d’exploration de données** , la ou les tables d’entrée sélectionnées dans la table **Sélectionner une ou plusieurs tables d’entrée** , une fonction de prédiction ou une expression personnalisée.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="8ecd4-122">Les colonnes des tables contenant le modèle d'exploration de données et les colonnes d'entrée peuvent être glissées et déplacées sur la cellule.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="8ecd4-123">**Champ**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-123">**Field**</span></span>  
 <span data-ttu-id="8ecd4-124">Sélectionnez une colonne dans la liste des colonnes dérivées de la table source.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="8ecd4-125">Si vous avez sélectionné **Fonction de prédiction** dans **Source**, cette cellule contient une liste déroulante des fonctions de prédiction disponibles pour le modèle d’exploration de données sélectionné.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="8ecd4-126">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-126">**Alias**</span></span>  
 <span data-ttu-id="8ecd4-127">Nom de la colonne retourné par le serveur.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="8ecd4-128">**Afficher**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-128">**Show**</span></span>  
 <span data-ttu-id="8ecd4-129">Sélectionnez cette option pour retourner la colonne ou pour utiliser la colonne uniquement dans la clause WHERE.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="8ecd4-130">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-130">**Group**</span></span>  
 <span data-ttu-id="8ecd4-131">Utilisez cette option avec la colonne **et/ou** pour regrouper les expressions.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="8ecd4-132">Par exemple, (expr1 OU expr2) ET expr3.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="8ecd4-133">**et/ou**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-133">**And/Or**</span></span>  
 <span data-ttu-id="8ecd4-134">Utilisez cette option pour créer une requête logique.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-134">Use to create a logical query.</span></span> <span data-ttu-id="8ecd4-135">Par exemple, (expr1 OU expr2) ET expr3.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="8ecd4-136">**Critères/Argument**</span><span class="sxs-lookup"><span data-stu-id="8ecd4-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="8ecd4-137">Spécifiez une condition ou une expression utilisateur qui s'applique à la colonne.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="8ecd4-138">Les colonnes des tables contenant le modèle d'exploration de données et les colonnes d'entrée peuvent être glissées et déplacées sur la cellule.</span><span class="sxs-lookup"><span data-stu-id="8ecd4-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ecd4-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ecd4-139">See Also</span></span>  
 <span data-ttu-id="8ecd4-140">[Interfaces de requête d’exploration de données](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="8ecd4-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="8ecd4-141">Guide de référence des instructions DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="8ecd4-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
