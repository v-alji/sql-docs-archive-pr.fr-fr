---
title: 'Tâche 8 : ajout d’une transformation de fractionnement conditionnel pour fractionner la sortie de nettoyage | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: d4ebe420-a4a9-4076-89d3-41abe726fc5c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9be7ea6f5330382ad0417df99e18bcba5b59a4e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600380"
---
# <a name="task-8-adding-conditional-split-transform-to-split-cleansing-output"></a><span data-ttu-id="a84aa-102">Tâche 8 : Ajout de la transformation de fractionnement conditionnel pour fractionner la sortie du nettoyage</span><span class="sxs-lookup"><span data-stu-id="a84aa-102">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>
  <span data-ttu-id="a84aa-103">Dans cette tâche, vous allez ajouter une transformation de fractionnement conditionnel au flux de données.</span><span class="sxs-lookup"><span data-stu-id="a84aa-103">In this transform, you add a Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="a84aa-104">La transformation de fractionnement conditionnel peut acheminer les lignes vers différentes sorties, suivant le contenu des données.</span><span class="sxs-lookup"><span data-stu-id="a84aa-104">The Conditional Split transformation can route rows to different outputs based on the content of the data.</span></span> <span data-ttu-id="a84aa-105">Pour ce didacticiel, vous utilisez la colonne de sortie de l’état de l' **enregistrement** à partir de la transformation de nettoyage DQS.</span><span class="sxs-lookup"><span data-stu-id="a84aa-105">For this tutorial, you use the **Record Status** output column from the DQS Cleansing transform.</span></span> <span data-ttu-id="a84aa-106">Vous téléchargerez uniquement les enregistrements corrects ou corrigés sur le serveur MDS.</span><span class="sxs-lookup"><span data-stu-id="a84aa-106">You will upload only correct or corrected records to MDS server in this tutorial.</span></span> <span data-ttu-id="a84aa-107">Par conséquent, vous pouvez vérifier si l’état de l' **enregistrement** est **correct** ou **corrigé**et combiner les enregistrements avant de charger les enregistrements dans MDS.</span><span class="sxs-lookup"><span data-stu-id="a84aa-107">Therefore you check if the **Record Status** is **Correct** or **Corrected**, and combine the records before uploading the records to MDS.</span></span>  
  
1.  <span data-ttu-id="a84aa-108">Glissez-déplacez la **transformation de fractionnement conditionnel** de la section **commun** dans la **boîte à outils SSIS** vers l’onglet de **Workflow** sous **nettoyer les données des fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="a84aa-108">Drag-drop **Conditional Split Transform** from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab under **Cleanse Supplier Data**.</span></span>  
  
2.  <span data-ttu-id="a84aa-109">Cliquez avec le bouton droit sur **fractionnement conditionnel**, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="a84aa-109">Right-click **Conditional Split**, and click **Rename**.</span></span> <span data-ttu-id="a84aa-110">Tapez **Choisissez les enregistrements corrects et corrigés** , puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="a84aa-110">Type **Pick Correct and Corrected Records** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="a84aa-111">Connectez **nettoyer les données des fournisseurs** et **sélectionnez les enregistrements corrects et corrigés** à l’aide du connecteur bleu.</span><span class="sxs-lookup"><span data-stu-id="a84aa-111">Connect **Cleanse Supplier Data** and **Pick Correct and Corrected Records** using the blue connector.</span></span>  
  
     <span data-ttu-id="a84aa-112">![Nettoyer les données du fournisseur-> choix correct & corrigé](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Nettoyer les données des fournisseurs -> Choisir les correctes et les corrigées")</span><span class="sxs-lookup"><span data-stu-id="a84aa-112">![Cleanse Supplier Data -> Pick Correct & Corrected](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-01.jpg "Cleanse Supplier Data -> Pick Correct & Corrected")</span></span>  
  
4.  <span data-ttu-id="a84aa-113">Double-cliquez sur **choisir les enregistrements corrects et corrigés** dans l’onglet **Data Flow** .</span><span class="sxs-lookup"><span data-stu-id="a84aa-113">Double-click **Pick Correct and Corrected Records** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="a84aa-114">Modifiez le **nom de sortie par défaut** en bas de l’écran pour **corriger**le nom.</span><span class="sxs-lookup"><span data-stu-id="a84aa-114">Change the **Default Output Name** at the bottom of the screen to **Correct**.</span></span>  
  
6.  <span data-ttu-id="a84aa-115">Développez **colonnes** dans le **volet en haut à gauche**.</span><span class="sxs-lookup"><span data-stu-id="a84aa-115">Expand **Columns** in the **top-left pane**.</span></span>  
  
     <span data-ttu-id="a84aa-116">![Éditeur de transformation de fractionnement conditionnel](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Éditeur de transformation de fractionnement conditionnel")</span><span class="sxs-lookup"><span data-stu-id="a84aa-116">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingcsttosplitcleansingoutput-02.jpg "Conditional Split Transformation Editor")</span></span>  
  
7.  <span data-ttu-id="a84aa-117">Glissez-déplacez l’état de l' **enregistrement** vers la colonne **condition** .</span><span class="sxs-lookup"><span data-stu-id="a84aa-117">Drag-drop **Record Status** to the **Condition** column.</span></span>  
  
8.  <span data-ttu-id="a84aa-118">Tapez **= = "corrigé"** en regard de **[État de l’enregistrement]** pour la colonne **condition** .</span><span class="sxs-lookup"><span data-stu-id="a84aa-118">Type **=="Corrected"** next to **[Record Status]** for the **Condition** column.</span></span>  
  
9. <span data-ttu-id="a84aa-119">Cliquez sur **cas 1** dans la **colonne nom**de la sortie, puis remplacez le nom par **corrigé**.</span><span class="sxs-lookup"><span data-stu-id="a84aa-119">Click **Case 1** in the **Output Name Column**, and change the name to **Corrected**.</span></span>  
  
10. <span data-ttu-id="a84aa-120">Cliquez sur **OK** pour fermer la boîte de dialogue **éditeur de transformation de fractionnement conditionnel** .</span><span class="sxs-lookup"><span data-stu-id="a84aa-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a84aa-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="a84aa-121">Next Step</span></span>  
 [<span data-ttu-id="a84aa-122">Tâche 9 : Ajout d’une transformation d’union totale pour combiner des enregistrements corrects et corrigés</span><span class="sxs-lookup"><span data-stu-id="a84aa-122">Task 9: Adding Union All Transform to Combine Correct and Corrected Records</span></span>](../../2014/tutorials/task-9-adding-union-all-transform-to-combine-correct-and-corrected-records.md)  
  
  
