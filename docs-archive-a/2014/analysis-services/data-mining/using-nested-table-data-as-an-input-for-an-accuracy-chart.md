---
title: Utilisation des données de table imbriquée comme entrée pour un graphique d’exactitude | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600326"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="77e15-102">Utilisation des données de table imbriquée comme entrée pour un graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="77e15-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="77e15-103">Si vous testez l'exactitude d'un modèle d'exploration de données en utilisant des données externes et que le modèle d'exploration de données contient des tables imbriquées, les données externes doivent également contenir une table de cas et une table imbriquée associée.</span><span class="sxs-lookup"><span data-stu-id="77e15-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="77e15-104">Cette rubrique explique comment utiliser des tables imbriquées utilisées pour le test de modèle, comment mapper des tables imbriquées et des tables de cas dans le mode et dans les données externes, et comment appliquer un filtre à une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="77e15-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="77e15-105">Lors de l'utilisation de tables imbriquées, gardez à l'esprit les conseils suivants :</span><span class="sxs-lookup"><span data-stu-id="77e15-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="77e15-106">Si vous sélectionnez l’option **Utiliser des scénarios de test de modèle d’exploration de données** ou **Utiliser des scénarios de test de structure d’exploration de données**, il est inutile de spécifier une table de cas ou une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="77e15-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="77e15-107">Avec ces options, la définition des données de test est stockée dans la structure d'exploration de données et les données de test sont sélectionnées automatiquement lorsque vous créez le graphique d'analyse de précision.</span><span class="sxs-lookup"><span data-stu-id="77e15-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="77e15-108">Si une relation existe déjà entre la table de cas et la table imbriquée dans la source de données, les colonnes de la structure d'exploration de données sont automatiquement associées aux colonnes portant le même nom dans la table d'entrée.</span><span class="sxs-lookup"><span data-stu-id="77e15-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="77e15-109">Vous ne pouvez pas sélectionner de table imbriquée tant que vous n'avez pas spécifié la table de cas.</span><span class="sxs-lookup"><span data-stu-id="77e15-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="77e15-110">Par ailleurs, vous ne pouvez pas spécifier de table imbriquée comme entrée à moins que le modèle d'exploration de données n'utilise également une structure de table de cas et de table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="77e15-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="77e15-111">Utiliser une table imbriquée comme entrée dans un graphique d'analyse de précision</span><span class="sxs-lookup"><span data-stu-id="77e15-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="77e15-112">Double-cliquez sur la structure d'exploration de données pour l'ouvrir dans le Concepteur d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="77e15-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="77e15-113">Sélectionnez l’onglet **Graphique d’analyse de précision de l’exploration de données** puis l’onglet **Sélection d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="77e15-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="77e15-114">Dans **Sélectionner le jeu de données à utiliser pour le graphique d’analyse de précision**, sélectionnez l’option **Spécifier un autre jeu de données**.</span><span class="sxs-lookup"><span data-stu-id="77e15-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="77e15-115">Cliquez sur le bouton Parcourir **(...)** pour choisir le jeu de données externes dans une liste de vues de source de données sur le serveur actuel.</span><span class="sxs-lookup"><span data-stu-id="77e15-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="77e15-116">Cliquez sur **Sélectionner la table de cas**.</span><span class="sxs-lookup"><span data-stu-id="77e15-116">Click **Select Case Table**.</span></span> <span data-ttu-id="77e15-117">Dans la boîte de dialogue **Sélectionner une table** , sélectionnez la table dans la vue de source de données contenant les données de cas, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="77e15-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="77e15-118">Cliquez sur **Sélectionner la table imbriquée**.</span><span class="sxs-lookup"><span data-stu-id="77e15-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="77e15-119">Dans la boîte de dialogue **Sélectionner une table** , sélectionnez la table contenant les données imbriquées, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="77e15-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="77e15-120">Si vous devez modifier la relation entre la table imbriquée et la table de cas, cliquez sur **Modifier la jointure** pour ouvrir la boîte de dialogue **Créer une relation** .</span><span class="sxs-lookup"><span data-stu-id="77e15-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77e15-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77e15-121">See Also</span></span>  
 <span data-ttu-id="77e15-122">[Choisir et mapper les données de test du modèle](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="77e15-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="77e15-123">Appliquer des filtres aux données de test du modèle</span><span class="sxs-lookup"><span data-stu-id="77e15-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
