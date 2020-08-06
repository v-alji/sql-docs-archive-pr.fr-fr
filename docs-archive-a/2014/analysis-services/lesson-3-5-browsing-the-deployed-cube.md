---
title: Exploration du cube déployé | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 849c6109-1453-4fe4-a892-c49a982cfadb
author: minewiskan
ms.author: owend
ms.openlocfilehash: b876c8b2876aaf4ad28b0f4ea3fb8bab32cd787b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611385"
---
# <a name="browsing-the-deployed-cube"></a><span data-ttu-id="7c5d1-102">Exploration du cube déployé</span><span class="sxs-lookup"><span data-stu-id="7c5d1-102">Browsing the Deployed Cube</span></span>
  <span data-ttu-id="7c5d1-103">Dans la tâche suivante, vous parcourez le cube du didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7c5d1-103">In the following task, you browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="7c5d1-104">Étant donné que notre analyse compare la mesure entre plusieurs dimensions, utilisez un tableau croisé dynamique Excel pour parcourir vos données.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-104">Because our analysis compares measure across multiple dimensions, you will use an Excel PivotTable to browse your data.</span></span> <span data-ttu-id="7c5d1-105">Un tableau croisé dynamique permet de placer le client, la date et les informations produit sur différents axes afin que vous pouvoir voir les disparités des ventes sur Internet en fonction des points dans le temps, des caractéristiques démographiques de la clientèle et des gammes de produits.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-105">Using a PivotTable lets you place customer, date, and product information on different axes so that you can see how Internet Sales change when viewed across specific time periods, customer demographics, and product lines.</span></span>  
  
### <a name="to-browse-the-deployed-cube"></a><span data-ttu-id="7c5d1-106">Pour parcourir le cube déployé</span><span class="sxs-lookup"><span data-stu-id="7c5d1-106">To browse the deployed cube</span></span>  
  
1.  <span data-ttu-id="7c5d1-107">Pour basculer vers le concepteur de cube dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , double-cliquez sur le cube \*\* [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial\*\* dans le dossier **cubes** de l’Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-107">To switch to Cube Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], double-click the **[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial** cube in the **Cubes** folder of the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="7c5d1-108">Ouvrez l'onglet **Navigateur** , puis cliquez sur le bouton **Reconnecter** dans la barre d'outils du Concepteur.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-108">Open the **Browser** tab, and then click the **Reconnect** button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="7c5d1-109">Cliquez sur l'icône Excel pour lancer Excel avec la base de données d'espace de travail comme source de données.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-109">Click the Excel icon to launch Excel using the workspace database as the data source.</span></span> <span data-ttu-id="7c5d1-110">Lorsque vous êtes invité à activer les connexions, cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-110">When prompted to enable connections, click **Enable**.</span></span>  
  
4.  <span data-ttu-id="7c5d1-111">Dans la liste des champs de tableau croisé dynamique, développez **Internet Sales**, puis faites glisser la mesure **Sales Amount** vers la zone **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="7c5d1-111">In the PivotTable Field List, expand **Internet Sales**, and then drag the **Sales Amount** measure to the **Values** area.</span></span>  
  
5.  <span data-ttu-id="7c5d1-112">Dans la liste des champs de tableau croisé dynamique, développez **Product**.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-112">In the PivotTable Field List, expand **Product**.</span></span>  
  
6.  <span data-ttu-id="7c5d1-113">Faites glisser la hiérarchie utilisateur **Product Model Lines** vers la zone **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="7c5d1-113">Drag the **Product Model Lines** user hierarchy to the **Columns** area.</span></span>  
  
7.  <span data-ttu-id="7c5d1-114">Dans la liste de champs de tableau croisé dynamique, développez **Customer**, puis **Location**et faites glisser la hiérarchie **Customer Geography** du dossier d'affichage Location de la dimension Customer vers la zone **Lignes** .</span><span class="sxs-lookup"><span data-stu-id="7c5d1-114">In the PivotTable Field List, expand **Customer**, expand **Location**, and then drag the **Customer Geography** hierarchy from the Location display folder in the Customer dimension to the **Rows** area.</span></span>  
  
8.  <span data-ttu-id="7c5d1-115">Dans la liste de champs du tableau croisé dynamique, développez **Order Date**, puis faites glisser la hiérarchie **Order Date.Calendar Date** vers la zone **Filtre de rapport** .</span><span class="sxs-lookup"><span data-stu-id="7c5d1-115">In the PivotTable Field List, expand **Order Date**, and then drag the **Order Date.Calendar Date** hierarchy to the **Report Filter** area.</span></span>  
  
9. <span data-ttu-id="7c5d1-116">Cliquez sur la flèche à droite du filtre **Order Date.Calendar Date** dans le volet de données, décochez la case des niveaux **(All)** , développez **2006**, **H1 CY 2006**, **Q1 CY 2006**, cochez la case **February 2006**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-116">Click the arrow to the right of the **Order Date.Calendar Date** filter in the data pane, clear the check box for the **(All)** level, expand **2006**, expand **H1 CY 2006**, expand **Q1 CY 2006**, select the check box for **February 2006**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7c5d1-117">Les ventes Internet par région et ligne de produits pour le mois de février 2006 s'affichent comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="7c5d1-117">Internet sales by region and product line for the month of February, 2006 appear as shown in the following image.</span></span>  
  
     <span data-ttu-id="7c5d1-118">![Ventes sur Internet par région et ligne de produits](../../2014/tutorials/media/l3-cube-browser-finish.gif "Ventes sur Internet par région et ligne de produits")</span><span class="sxs-lookup"><span data-stu-id="7c5d1-118">![Internet sales by region and product line](../../2014/tutorials/media/l3-cube-browser-finish.gif "Internet sales by region and product line")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7c5d1-119">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="7c5d1-119">Next Lesson</span></span>  
 [<span data-ttu-id="7c5d1-120">Leçon 4 : Définition des attributs avancés et des propriétés de dimension</span><span class="sxs-lookup"><span data-stu-id="7c5d1-120">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>](lesson-4-defining-advanced-attribute-and-dimension-properties.md)  
  
  
