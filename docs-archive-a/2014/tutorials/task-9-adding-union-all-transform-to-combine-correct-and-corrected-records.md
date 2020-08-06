---
title: 'Tâche 9 : ajout d’une transformation d’Union totale pour combiner des enregistrements corrects et corrigés | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 24ba466d-a7d3-49e7-9111-b348399c9e58
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 83afb5ea9367660048fe36d00ab59d808da17b81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710043"
---
# <a name="task-9-adding-union-all-transform-to-combine-correct-and-corrected-records"></a><span data-ttu-id="aa66e-102">Tâche 9 : Ajout d’une transformation d’union totale pour combiner des enregistrements corrects et corrigés</span><span class="sxs-lookup"><span data-stu-id="aa66e-102">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>
  <span data-ttu-id="aa66e-103">Dans cette tâche, vous allez ajouter une transformation d'union totale au flux de données.</span><span class="sxs-lookup"><span data-stu-id="aa66e-103">In this task, you add the Union All Transform to the data flow.</span></span> <span data-ttu-id="aa66e-104">La transformation d'union totale combine plusieurs entrées en une seule sortie.</span><span class="sxs-lookup"><span data-stu-id="aa66e-104">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="aa66e-105">Dans votre scénario, elle combine les enregistrements corrects et corrigés dans un seul flux.</span><span class="sxs-lookup"><span data-stu-id="aa66e-105">In your scenario, it combine both Correct and Corrected records into one stream.</span></span>  
  
1.  <span data-ttu-id="aa66e-106">Faites glisser la transformation **Union All** de la section **commun** de la **boîte à outils SSIS** vers l’onglet de **Workflow** et placez-la sous **Sélectionner les enregistrements corrects et corrigés**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-106">Drag-drop **Union All** Transform from **Common** section of the **SSIS Toolbox** to the **Data Flow** tab and place it under **Pick Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="aa66e-107">Cliquez avec le bouton droit sur la transformation d' **Union** totale sous l’onglet **Data Flow** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-107">Right-click **Union All** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="aa66e-108">Tapez **combiner les enregistrements corrects et corrigés**, puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-108">Type **Combine Correct and Corrected Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="aa66e-109">![Combiner des enregistrements corrects et corrigés](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combiner des enregistrements corrects et corrigés")</span><span class="sxs-lookup"><span data-stu-id="aa66e-109">![Combine Correct and Corrected Reocrds](../../2014/tutorials/media/et-addinguattocombinecacrecords-01.jpg "Combine Correct and Corrected Reocrds")</span></span>  
  
3.  <span data-ttu-id="aa66e-110">Connecter **Choisissez les enregistrements corrects et corrigés** pour **combiner les enregistrements corrects et corrigés** dans l’onglet de **Workflow** à l’aide du connecteur bleu.</span><span class="sxs-lookup"><span data-stu-id="aa66e-110">Connect **Pick Correct and Corrected Records** to **Combine Correct and Corrected Records** in the **Data Flow** tab by using the blue connector.</span></span> <span data-ttu-id="aa66e-111">La boîte de dialogue **sélection de sortie d’entrée** doit s’afficher.</span><span class="sxs-lookup"><span data-stu-id="aa66e-111">You should see the **Input Output Selection** dialog box.</span></span>  
  
4.  <span data-ttu-id="aa66e-112">Dans la boîte de dialogue **sortie d’entrée** , sélectionnez **correct** pour la **sortie** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-112">In the **Input Output** dialog box, select **Correct** for **Output** and click **OK**.</span></span>  
  
     <span data-ttu-id="aa66e-113">![Boîte de dialogue Sélection entrée et sortie](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Boîte de dialogue Sélection entrée et sortie")</span><span class="sxs-lookup"><span data-stu-id="aa66e-113">![Input Output Selection Dialog Box](../../2014/tutorials/media/et-addinguattocombinecacrecords-02.jpg "Input Output Selection Dialog Box")</span></span>  
  
5.  <span data-ttu-id="aa66e-114">Déplacez le connecteur intitulé **correct** vers la gauche en faisant glisser le point à la fin du connecteur vers la gauche.</span><span class="sxs-lookup"><span data-stu-id="aa66e-114">Move the connector titled **Correct** to the left by dragging and dropping the dot at the end of the connector to left.</span></span>  
  
     <span data-ttu-id="aa66e-115">![Connexion des corrects à Combiner des enregistrements corrects et corrigés](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connexion des corrects à Combiner des enregistrements corrects et corrigés")</span><span class="sxs-lookup"><span data-stu-id="aa66e-115">![Connect Correct to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-03.jpg "Connect Correct to Combine Correct and Corrected")</span></span>  
  
6.  <span data-ttu-id="aa66e-116">Si vous sélectionnez la transformation **choisir les enregistrements corrects et corrigés** , vous devez voir un autre connecteur bleu.</span><span class="sxs-lookup"><span data-stu-id="aa66e-116">If you select **Pick Correct and Corrected Records** transform, you should see another blue connector.</span></span> <span data-ttu-id="aa66e-117">Faites glisser ce connecteur bleu pour **combiner les enregistrements corrects et corrigés**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-117">Drag that blue connector to **Combine Correct and Corrected Records**.</span></span>  
  
     <span data-ttu-id="aa66e-118">![Connexion des corrigés à Combiner des enregistrements corrects et corrigés](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connexion des corrigés à Combiner des enregistrements corrects et corrigés")</span><span class="sxs-lookup"><span data-stu-id="aa66e-118">![Connect Corrected to Combine Correct and Corrected](../../2014/tutorials/media/et-addinguattocombinecacrecords-04.jpg "Connect Corrected to Combine Correct and Corrected")</span></span>  
  
7.  <span data-ttu-id="aa66e-119">Ce **connecteur** doit être **corrigé**.</span><span class="sxs-lookup"><span data-stu-id="aa66e-119">This **connector** should be titled **Corrected**.</span></span> <span data-ttu-id="aa66e-120">Étant donné que deux conditions sont **correctes** et **corrigées**et que l’une d’elles a déjà été utilisée, la boîte de dialogue **sélection de sortie d’entrée** ne s’affiche pas cette fois.</span><span class="sxs-lookup"><span data-stu-id="aa66e-120">Since you have only two conditions **Correct** and **Corrected**, and one condition was already used, the **Input Output Selection** dialog box is not displayed this time.</span></span> <span data-ttu-id="aa66e-121">Si les connecteurs se chevauchent, déplacez un connecteur à gauche et l'autre à droite en les faisant glisser.</span><span class="sxs-lookup"><span data-stu-id="aa66e-121">If the connectors overlap, move one to left and the other one to right by dragging the connector to left or right.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="aa66e-122">étape suivante</span><span class="sxs-lookup"><span data-stu-id="aa66e-122">Next Step</span></span>  
 [<span data-ttu-id="aa66e-123">Tâche 10 : Ajout d’une transformation de regroupement probable pour identifier des doublons</span><span class="sxs-lookup"><span data-stu-id="aa66e-123">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>](../../2014/tutorials/task-10-adding-fuzzy-group-transform-to-identify-duplicates.md)  
  
  
