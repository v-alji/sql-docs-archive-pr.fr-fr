---
title: Volet requête (vue prévision de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603696"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="e73c7-102">Volet Requête (vue Prévision de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="e73c7-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="e73c7-103">Le volet **Requête** affiche les instructions DMX (Data Mining Extensions) créées par le Générateur de requêtes de prévisions.</span><span class="sxs-lookup"><span data-stu-id="e73c7-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="e73c7-104">Vous pouvez modifier les instructions, puis cliquer sur le bouton **Basculer vers l'affichage du résultat de la requête** pour retourner les résultats.</span><span class="sxs-lookup"><span data-stu-id="e73c7-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="e73c7-105">Si vous basculez de nouveau vers la vue **Conception**, les modifications éventuelles apportées à l'instruction seront perdues.</span><span class="sxs-lookup"><span data-stu-id="e73c7-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="e73c7-106">**Pour plus d’informations :** [Instructions de manipulations de données DMX &#40;Data Mining Extensions&#41;](/sql/dmx/dmx-statements-data-manipulation), [Créer une requête DMX dans SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="e73c7-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="e73c7-107">Options</span><span class="sxs-lookup"><span data-stu-id="e73c7-107">Options</span></span>  
 <span data-ttu-id="e73c7-108">**Basculer vers l'affichage du résultat de la requête**</span><span class="sxs-lookup"><span data-stu-id="e73c7-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="e73c7-109">Sélectionnez cette option pour basculer entre les volets **Conception**, **Requête**et **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="e73c7-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="e73c7-110">Lorsque vous basculez vers le volet **Résultat** , la requête est exécutée.</span><span class="sxs-lookup"><span data-stu-id="e73c7-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="e73c7-111">**Enregistrer le résultat de la requête**</span><span class="sxs-lookup"><span data-stu-id="e73c7-111">**Save the query result**</span></span>  
 <span data-ttu-id="e73c7-112">Ouvre la boîte de dialogue **Enregistrer le résultat de la requête d’exploration de données** .</span><span class="sxs-lookup"><span data-stu-id="e73c7-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="e73c7-113">**Requête singleton**</span><span class="sxs-lookup"><span data-stu-id="e73c7-113">**Singleton query**</span></span>  
 <span data-ttu-id="e73c7-114">Permet de créer une requête singleton, dans laquelle vous fournissez les données d'entrée directement dans votre requête au lieu de fournir une référence à une table de valeur d'entrée.</span><span class="sxs-lookup"><span data-stu-id="e73c7-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="e73c7-115">Le tableau **Sélectionner une ou plusieurs tables d’entrée** est remplacé par un tableau **Entrée de requête singleton** .</span><span class="sxs-lookup"><span data-stu-id="e73c7-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="e73c7-116">La requête de prévision actuelle est perdue si vous basculez vers une requête singleton.</span><span class="sxs-lookup"><span data-stu-id="e73c7-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="e73c7-117">**Actualiser les résultats de la requête**</span><span class="sxs-lookup"><span data-stu-id="e73c7-117">**Refresh query results**</span></span>  
 <span data-ttu-id="e73c7-118">Traite une nouvelle fois la requête de prévision.</span><span class="sxs-lookup"><span data-stu-id="e73c7-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="e73c7-119">Cette option est activée uniquement dans le volet **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="e73c7-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e73c7-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e73c7-120">See Also</span></span>  
 <span data-ttu-id="e73c7-121">[Interfaces de requête d’exploration de données](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="e73c7-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="e73c7-122">[Informations de référence sur les instructions DMX&#41; &#40;Data Mining Extensions](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="e73c7-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="e73c7-123">Générateur de requêtes de prédiction &#40;exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e73c7-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
