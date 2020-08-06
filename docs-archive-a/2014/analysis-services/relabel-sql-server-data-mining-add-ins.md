---
title: Renommer (SQL Server les compléments d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605740"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="6996a-102">Réétiqueter (Compléments d'exploration de données SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6996a-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="6996a-103">![Icône Office 13 pour l'outil Réétiqueter](media/dm13-relabel.gif "Icône Office 13 pour l'outil Réétiqueter")</span><span class="sxs-lookup"><span data-stu-id="6996a-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="6996a-104">Le client d'exploration de données pour Excel vous permet de créer de nouvelles étiquettes pour les données afin de faciliter la compréhension des résultats de l'analyse.</span><span class="sxs-lookup"><span data-stu-id="6996a-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="6996a-105">Les raisons du réétiquetage incluent les suivantes :</span><span class="sxs-lookup"><span data-stu-id="6996a-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="6996a-106">Les données contiennent des résultats qui ont été codés, comme 1 pour Homme et 2 pour Femme.</span><span class="sxs-lookup"><span data-stu-id="6996a-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="6996a-107">Vous créez des compartiments de valeurs numériques et souhaitez affecter un nom descriptif aux plages.</span><span class="sxs-lookup"><span data-stu-id="6996a-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="6996a-108">Vous souhaitez simplifier les noms longs.</span><span class="sxs-lookup"><span data-stu-id="6996a-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="6996a-109">Utilisation de l'Assistant Réétiquetage</span><span class="sxs-lookup"><span data-stu-id="6996a-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="6996a-110">Dans le ruban **Exploration de données** , cliquez sur **Nettoyer** , puis sélectionnez **Réétiqueter**.</span><span class="sxs-lookup"><span data-stu-id="6996a-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="6996a-111">Sélectionnez la table ou la plage de données qui contiennent les données à corriger.</span><span class="sxs-lookup"><span data-stu-id="6996a-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="6996a-112">Dans la page **Réétiqueter** de l'Assistant, sélectionnez une colonne, dans la liste déroulante, ou en cliquant sur la colonne dans le volet des **Échantillons de données** .</span><span class="sxs-lookup"><span data-stu-id="6996a-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="6996a-113">Le volet **Échantillons de données** affiche environ 50 lignes de données, mais elles sont échantillonnées pour garantir que vous consultez une bonne répartition des valeurs.</span><span class="sxs-lookup"><span data-stu-id="6996a-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="6996a-114">Cliquez sur l'en-tête de colonne **Nombre** pour trier par le nombre de chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="6996a-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="6996a-115">Vous pouvez également trier par **Étiquettes d'origine**, ce qui est pratique si vous souhaitez réétiqueter les valeurs les plus élevées ou les plus faibles en premier.</span><span class="sxs-lookup"><span data-stu-id="6996a-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="6996a-116">Dans la page de données **Réétiqueter** de l'Assistant, examinez les valeurs dans la colonne **Étiquettes d'origine** , et décidez comment vous souhaitez les regrouper ou les modifier.</span><span class="sxs-lookup"><span data-stu-id="6996a-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="6996a-117">Tapez une nouvelle valeur dans la ligne sous **Nouvelles étiquettes**.</span><span class="sxs-lookup"><span data-stu-id="6996a-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="6996a-118">Vous pouvez également choisir une valeur dans la liste de valeurs existantes.</span><span class="sxs-lookup"><span data-stu-id="6996a-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="6996a-119">À mesure que vous entrez des nouvelles valeurs, elles sont disponibles en vue de leur réutilisation.</span><span class="sxs-lookup"><span data-stu-id="6996a-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="6996a-120">Une fois que vous avez entré suffisamment de lignes, cliquez sur **suivant**, puis dans la page **Sélectionner la destination** , choisissez l’emplacement où vous allez enregistrer les données réparties.</span><span class="sxs-lookup"><span data-stu-id="6996a-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="6996a-121">**Ajouter en tant que nouvelle colonne dans la feuille de calcul active**</span><span class="sxs-lookup"><span data-stu-id="6996a-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="6996a-122">Cliquez pour ajouter une nouvelle colonne au tableau qui contient les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="6996a-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="6996a-123">**Copier les données de la feuille comportant les modifications dans une nouvelle feuille de calcul**</span><span class="sxs-lookup"><span data-stu-id="6996a-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="6996a-124">Cliquez pour créer une nouvelle feuille de calcul qui contient les données mises à jour.</span><span class="sxs-lookup"><span data-stu-id="6996a-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="6996a-125">**Changer les données de place**</span><span class="sxs-lookup"><span data-stu-id="6996a-125">**Change data in place**</span></span>

         <span data-ttu-id="6996a-126">Cliquez pour remplacer les données d'origine par les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="6996a-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="6996a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6996a-127">See Also</span></span>
 [<span data-ttu-id="6996a-128">Exploration et nettoyage des données</span><span class="sxs-lookup"><span data-stu-id="6996a-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


