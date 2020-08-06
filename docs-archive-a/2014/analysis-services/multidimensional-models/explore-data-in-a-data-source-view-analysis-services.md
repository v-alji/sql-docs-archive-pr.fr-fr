---
title: Explorer des données dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614862"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="5a335-102">Explorer des données dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5a335-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="5a335-103">Vous pouvez utiliser la boîte de dialogue **Explorer les données** du Concepteur de vue de source de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour parcourir les données d’une table, d’une vue ou d’une requête nommée dans une vue de source de données (DSV).</span><span class="sxs-lookup"><span data-stu-id="5a335-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="5a335-104">Si vous explorez les données dans le Concepteur de vue de source de données, vous pouvez afficher le contenu de chacune des colonnes de données d'une table, d'une vue ou d'une requête nommée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5a335-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="5a335-105">Cet affichage vous permet de déterminer si toutes les colonnes sont nécessaires, si des calculs nommés sont nécessaires pour améliorer la convivialité, et si les requêtes nommées ou les calculs nommés existants retournent les valeurs prévues.</span><span class="sxs-lookup"><span data-stu-id="5a335-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="5a335-106">Pour afficher les données, vous devez disposer d'une connexion active aux sources de données pour l'objet sélectionné dans la vue de source de données (DSV).</span><span class="sxs-lookup"><span data-stu-id="5a335-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="5a335-107">Le cas échéant, tous les calculs nommés d'une table sont également envoyés dans la requête.</span><span class="sxs-lookup"><span data-stu-id="5a335-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="5a335-108">Données retournées dans un format tabulaire que vous pouvez trier et copier.</span><span class="sxs-lookup"><span data-stu-id="5a335-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="5a335-109">Cliquez sur les en-têtes de colonnes pour re-trier les lignes par cette colonne.</span><span class="sxs-lookup"><span data-stu-id="5a335-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="5a335-110">Vous pouvez également mettre en surbrillance des données dans la grille et appuyer sur Ctrl+C pour copier la sélection dans le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="5a335-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="5a335-111">Vous pouvez également contrôler la méthode d'échantillonnage et le nombre d'échantillons.</span><span class="sxs-lookup"><span data-stu-id="5a335-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="5a335-112">Par défaut, les 5000 premières lignes sont retournées.</span><span class="sxs-lookup"><span data-stu-id="5a335-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="5a335-113">Pour parcourir les données ou modifier les options d'échantillonnage</span><span class="sxs-lookup"><span data-stu-id="5a335-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="5a335-114">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez explorer les données.</span><span class="sxs-lookup"><span data-stu-id="5a335-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="5a335-115">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="5a335-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="5a335-116">Cliquez avec le bouton droit sur la table, la vue ou la requête nommée contenant les données que vous voulez consulter, puis sélectionnez **Explorer les données**.</span><span class="sxs-lookup"><span data-stu-id="5a335-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="5a335-117">La source de données sous-jacente de la table, de la vue ou de la requête nommée dans la vue de source de données sont des requêtes et les résultats s’affichent sous l’onglet **Explorer la \<object name> table** .</span><span class="sxs-lookup"><span data-stu-id="5a335-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="5a335-118">Dans la barre d’outils **Explorer la \<object name> table** , cliquez sur l’icône **options d’échantillonnage** .</span><span class="sxs-lookup"><span data-stu-id="5a335-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="5a335-119">La boîte de dialogue **Options d'exploration de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="5a335-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="5a335-120">Dans cette boîte de dialogue, vous pouvez spécifier la méthode d’échantillonnage (et augmenter ou diminuer le nombre d’enregistrements par rapport à la taille d’échantillonnage par défaut de 5000 lignes) ou le nombre d’échantillons.</span><span class="sxs-lookup"><span data-stu-id="5a335-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="5a335-121">Selon le cas, cliquez sur **OK** ou sur **Annuler** .</span><span class="sxs-lookup"><span data-stu-id="5a335-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="5a335-122">Pour rééchantillonner les données, cliquez sur **rééchantillonner les données** dans la barre d’outils **Explorer la \<object name> table** .</span><span class="sxs-lookup"><span data-stu-id="5a335-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a335-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a335-123">See Also</span></span>  
 [<span data-ttu-id="5a335-124">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="5a335-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
