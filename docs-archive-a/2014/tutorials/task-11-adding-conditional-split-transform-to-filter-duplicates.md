---
title: 'Tâche 11 : ajout d’une transformation de fractionnement conditionnel pour filtrer les doublons | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710047"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="ba697-102">Tâche 11 : Ajout d’une transformation de fractionnement conditionnel pour filtrer les doublons</span><span class="sxs-lookup"><span data-stu-id="ba697-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="ba697-103">Dans cette tâche, vous allez ajouter la transformation de fractionnement conditionnel au flux de données.</span><span class="sxs-lookup"><span data-stu-id="ba697-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="ba697-104">Cette transformation vous permet de filtrer les doublons à partir d'un jeu d'enregistrements entrant.</span><span class="sxs-lookup"><span data-stu-id="ba697-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="ba697-105">La transformation de regroupement probable regroupe les enregistrements qu'elle identifie comme étant correspondants et choisit l'un des enregistrements comme enregistrement pivot.</span><span class="sxs-lookup"><span data-stu-id="ba697-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="ba697-106">Tous les enregistrements d'un groupe possèdent la même valeur _key_out.</span><span class="sxs-lookup"><span data-stu-id="ba697-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="ba697-107">L'enregistrement pivot dans le groupe a un _key_in identique à la valeur _key_out.</span><span class="sxs-lookup"><span data-stu-id="ba697-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="ba697-108">Les autres enregistrements du groupe ont des valeurs différentes pour _key_in et _key_out.</span><span class="sxs-lookup"><span data-stu-id="ba697-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="ba697-109">Par conséquent, lorsque vous filtrez en utilisant la condition _key_in==_key_out, vous obtenez uniquement la ligne pivot du groupe.</span><span class="sxs-lookup"><span data-stu-id="ba697-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="ba697-110">Glissez-déplacez la transformation de **fractionnement conditionnel** de la section **commun** dans la **boîte à outils SSIS** vers l’onglet de **Workflow** .</span><span class="sxs-lookup"><span data-stu-id="ba697-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="ba697-111">Cliquez avec le bouton droit sur **transformation de fractionnement conditionnel** sous l’onglet **Flow Data** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="ba697-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="ba697-112">Tapez **Filtrer les doublons** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="ba697-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="ba697-113">Connectez **les fournisseurs avec des ID correspondants** pour **Filtrer les doublons**.</span><span class="sxs-lookup"><span data-stu-id="ba697-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="ba697-114">Double-cliquez sur **Filtrer les doublons** pour ouvrir la boîte de dialogue **éditeur de transformation de fractionnement conditionnel** .</span><span class="sxs-lookup"><span data-stu-id="ba697-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="ba697-115">Développez **colonnes** dans le volet en haut à gauche.</span><span class="sxs-lookup"><span data-stu-id="ba697-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="ba697-116">Glisser-déplacer **_key_in** vers la colonne **condition** .</span><span class="sxs-lookup"><span data-stu-id="ba697-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="ba697-117">Type = = (est égal à) en regard de **_key_in** et glisser-déplacer **_key_out**.</span><span class="sxs-lookup"><span data-stu-id="ba697-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="ba697-118">Cliquez sur **cas 1** dans la colonne **nom** de la sortie, tapez **enregistrements uniques**, puis appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="ba697-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="ba697-119">![Éditeur de transformation de fractionnement conditionnel](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Éditeur de transformation de fractionnement conditionnel")</span><span class="sxs-lookup"><span data-stu-id="ba697-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="ba697-120">Cliquez sur **OK** pour fermer la boîte de dialogue **éditeur de transformation de fractionnement conditionnel** .</span><span class="sxs-lookup"><span data-stu-id="ba697-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ba697-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="ba697-121">Next Step</span></span>  
 [<span data-ttu-id="ba697-122">Tâche 12 : Ajout d’une transformation de colonne dérivée pour ajouter les colonnes requises par MDS</span><span class="sxs-lookup"><span data-stu-id="ba697-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  
