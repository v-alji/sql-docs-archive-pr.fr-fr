---
title: Définition d’une dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600282"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="9f7bf-102">Définition d'une dimension</span><span class="sxs-lookup"><span data-stu-id="9f7bf-102">Defining a Dimension</span></span>
  <span data-ttu-id="9f7bf-103">Dans la tâche suivante, vous allez utiliser l'Assistant Dimension pour générer une dimension Date.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f7bf-104">Avant de commencer cette leçon, vous devez avoir terminé toutes les procédures de la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="9f7bf-105">Pour définir une dimension</span><span class="sxs-lookup"><span data-stu-id="9f7bf-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="9f7bf-106">Dans l’Explorateur de solutions (à droite de Microsoft Visual Studio), cliquez avec le bouton droit sur **Dimensions**, puis cliquez sur **Nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="9f7bf-107">L'Assistant Dimension apparaît.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="9f7bf-108">Dans la page **Assistant Dimension** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="9f7bf-109">Dans la page **Sélectionner la méthode de création** , vérifiez que l’option **Utiliser une table existante** est sélectionnée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="9f7bf-110">Dans la page **Spécifier des informations sur la source** , vérifiez que la vue de source des données **Adventure Works DW 2012** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="9f7bf-111">Dans la liste **Table principale** , sélectionnez **Date**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="9f7bf-112">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="9f7bf-113">Dans la page **Sélectionner les attributs de la dimension** , cochez les cases à côté des attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="9f7bf-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="9f7bf-114">**Date Key**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="9f7bf-115">**Full Date Alternate Key**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="9f7bf-116">**English Month Name**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="9f7bf-117">**Trimestre civil**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="9f7bf-118">**Année civile**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="9f7bf-119">**Calendar Semester**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="9f7bf-120">Modifiez le paramètre de la colonne **Type d’attribut** de l’attribut **Full Date Alternate Key** de **Regular** en **Date**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="9f7bf-121">Pour cela, cliquez sur **Regular** dans la colonne **Type d’attribut** .</span><span class="sxs-lookup"><span data-stu-id="9f7bf-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="9f7bf-122">Puis, cliquez sur la flèche pour développer les options.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="9f7bf-123">Ensuite, cliquez sur **Date**  >  **calendrier**  >  **Date**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="9f7bf-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-124">Click **OK**.</span></span> <span data-ttu-id="9f7bf-125">Répétez ces étapes pour modifier le type d’attribut des attributs suivants comme suit :</span><span class="sxs-lookup"><span data-stu-id="9f7bf-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="9f7bf-126">**English Month Name** en **Month**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="9f7bf-127">**Calendar Quarter** en **Quarter**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="9f7bf-128">**Calendar Year** en **Year**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="9f7bf-129">**Calendar Semester** en **Half Year**</span><span class="sxs-lookup"><span data-stu-id="9f7bf-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="9f7bf-130">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="9f7bf-131">Dans la page **Fin de l’Assistant** , dans le volet de visualisation, vous pouvez consulter la dimension **Date** et ses attributs.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="9f7bf-132">Cliquez sur **Terminer** pour terminer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="9f7bf-133">Dans l’Explorateur de solutions, dans le projet Didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , la dimension Date apparaît dans le dossier **Dimensions** .</span><span class="sxs-lookup"><span data-stu-id="9f7bf-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="9f7bf-134">Au centre de l'environnement de développement, le Concepteur de dimensions affiche la dimension Date.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="9f7bf-135">Dans le menu **Fichier**, cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="9f7bf-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9f7bf-136">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="9f7bf-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9f7bf-137">Définition d’un cube</span><span class="sxs-lookup"><span data-stu-id="9f7bf-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="9f7bf-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f7bf-138">See Also</span></span>  
 <span data-ttu-id="9f7bf-139">[Dimensions dans les modèles multidimensionnels](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="9f7bf-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="9f7bf-140">[Créer une dimension à l’aide d’une table existante](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="9f7bf-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="9f7bf-141">Créer une dimension à l'aide de l'Assistant Dimension</span><span class="sxs-lookup"><span data-stu-id="9f7bf-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
