---
title: Fusionner des données à l’aide de la transformation d’union totale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613047"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="dc2b1-102">Fusionner des données à l'aide de la transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="dc2b1-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="dc2b1-103">Pour pouvoir ajouter et configurer une transformation d'union totale, le package doit inclure au moins une tâche de flux de données et deux sources de données.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="dc2b1-104">La transformation d'union totale combine plusieurs entrées.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="dc2b1-105">La première entrée qui est connectée à la transformation est l'entrée de référence ; les entrées connectées par la suite sont les entrées secondaires.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="dc2b1-106">La sortie contient les colonnes de l'entrée de référence.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="dc2b1-107">Pour connecter des entrées dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="dc2b1-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="dc2b1-108">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-cliquez sur le package dans l’Explorateur de solutions pour ouvrir le package dans le concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , puis cliquez sur l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="dc2b1-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="dc2b1-109">Dans la **Boîte à outils**, faites glisser la transformation d’union totale vers l’aire de conception de l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="dc2b1-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="dc2b1-110">Connectez la transformation d'union totale au flux de données en faisant glisser le connecteur à partir de la source de données ou d'une transformation précédente vers la transformation d'union totale.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="dc2b1-111">Double-cliquez sur la transformation d'union totale.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="dc2b1-112">Dans **l’Éditeur de transformation d’union totale**, mappez une colonne d’une entrée à une colonne de la liste **Nom de colonne de sortie** en cliquant sur une ligne, puis en sélectionnant une colonne dans la liste d’entrée.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="dc2b1-113">Sélectionnez **\<ignore>** dans la liste d’entrée pour ignorer le mappage de la colonne.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc2b1-114">Vous ne pouvez mapper deux colonnes que si leurs métadonnées correspondent.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="dc2b1-115">Les colonnes d'une entrée secondaire qui ne sont pas mappées à des colonnes de référence sont définies sur des valeurs null dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="dc2b1-116">Si vous le souhaitez, modifiez le nom des colonnes dans la colonne **Nom de colonne de sortie** .</span><span class="sxs-lookup"><span data-stu-id="dc2b1-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="dc2b1-117">Répétez les étapes 5 et 6 pour chaque colonne de chaque entrée.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="dc2b1-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc2b1-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="dc2b1-119">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="dc2b1-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc2b1-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc2b1-120">See Also</span></span>  
 <span data-ttu-id="dc2b1-121">[Transformation d'union totale](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="dc2b1-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="dc2b1-122">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="dc2b1-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="dc2b1-123">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="dc2b1-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="dc2b1-124">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="dc2b1-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
