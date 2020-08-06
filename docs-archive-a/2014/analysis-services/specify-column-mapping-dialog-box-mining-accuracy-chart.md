---
title: Boîte de dialogue spécifier le mappage des colonnes (graphique d’analyse de précision de l’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612520"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="7a5d6-102">Boîte de dialogue Spécifier le mappage des colonnes (Graphique d'analyse de précision de l'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="7a5d6-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="7a5d6-103">Utilisez l’onglet **Spécifier le mappage des colonnes** pour sélectionner des tables d’une source de données externe et mapper les colonnes à un modèle d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="7a5d6-104">Vous pouvez ensuite utiliser les données externes pour tester la précision d'un modèle d'exploration de données et afficher les résultats dans le graphique d'analyse de précision.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="7a5d6-105">**Pour plus d’informations :** [Test et validation &#40;exploration de données&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="7a5d6-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a5d6-106">Options</span><span class="sxs-lookup"><span data-stu-id="7a5d6-106">Options</span></span>  
 <span data-ttu-id="7a5d6-107">**Structure d'exploration de données**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-107">**Mining Structure**</span></span>  
 <span data-ttu-id="7a5d6-108">Affiche la structure d'exploration de données sélectionnée qui contient le modèle à tester.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="7a5d6-109">**Sélectionner une structure**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-109">**Select Structure**</span></span>  
 <span data-ttu-id="7a5d6-110">Cliquez pour ouvrir la boîte de dialogue **Sélectionner la structure d’exploration de données** et sélectionner une structure d’exploration de données différente.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="7a5d6-111">**Sélectionner une ou plusieurs tables d'entrée**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="7a5d6-112">Affiche les tables d'entrée sélectionnées utilisées pour générer le graphique de courbes d'élévation.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="7a5d6-113">Sélectionnez la table qui contient les données de test que vous utiliserez pour tester la précision des modèles.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a5d6-114">Si le volet ne contient aucune table, cliquez sur **Sélectionner la table de cas** pour ajouter des tables d’une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="7a5d6-115">**Supprimer la table**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-115">**Remove Table**</span></span>  
 <span data-ttu-id="7a5d6-116">Supprime la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-116">Removes the selected table.</span></span> <span data-ttu-id="7a5d6-117">Ce bouton est désactivé si aucune table n’a été sélectionnée ou si aucune table ne figure dans la liste **Sélectionner une ou plusieurs tables d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="7a5d6-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="7a5d6-118">**Sélectionner la table de cas**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-118">**Select Case Table**</span></span>  
 <span data-ttu-id="7a5d6-119">Cliquez pour ouvrir la boîte de dialogue **Sélectionner une table** , puis sélectionnez une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="7a5d6-120">**Remarque** Ce bouton s’affiche uniquement si aucune table de cas n’a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="7a5d6-121">Pour activer le bouton afin de pouvoir sélectionner une table de cas différente, effacez la liste en sélectionnant toutes les tables existantes, puis en cliquant sur **Supprimer la table**.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="7a5d6-122">**Sélectionner la table imbriquée**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="7a5d6-123">Ouvre la boîte de dialogue **Sélectionner une table** .</span><span class="sxs-lookup"><span data-stu-id="7a5d6-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="7a5d6-124">Ce bouton s'affiche uniquement si une table de cas a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="7a5d6-125">Si la structure d'exploration de données associée ne contient pas de table imbriquée, ce bouton est désactivé.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="7a5d6-126">**Modifier la jointure**</span><span class="sxs-lookup"><span data-stu-id="7a5d6-126">**Modify Join**</span></span>  
 <span data-ttu-id="7a5d6-127">Ouvre la boîte de dialogue **Spécifier la jointure imbriquée** .</span><span class="sxs-lookup"><span data-stu-id="7a5d6-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="7a5d6-128">Ce bouton est activé uniquement si la table imbriquée est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7a5d6-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5d6-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a5d6-129">See Also</span></span>  
 <span data-ttu-id="7a5d6-130">[Tâches de test et de validation et &#40;d’exploration de données&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="7a5d6-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="7a5d6-131">Concepteur graphique d’analyse de précision de l’exploration de données &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="7a5d6-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
