---
title: Création d’une structure de modèle d’exploration de données de publipostage ciblé (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9c67f29-0c47-4a5a-862b-db0f5213c2c9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 6a27f818b29120e40248044091c78205dad945bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703559"
---
# <a name="creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial"></a><span data-ttu-id="4dabd-102">Création d'une structure de modèle d'exploration de données pour le publipostage ciblé (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="4dabd-102">Creating a Targeted Mailing Mining Model Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4dabd-103">La première étape dans la création d'un scénario de publipostage ciblé consiste à utiliser l'Assistant Exploration de données dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour créer une structure d'exploration de données et un modèle d'exploration de données du type Arbres de décision.</span><span class="sxs-lookup"><span data-stu-id="4dabd-103">The first step in creating a targeted mailing scenario is to use the Data Mining Wizard in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create a new mining structure and decision tree mining model.</span></span>  
  
 <span data-ttu-id="4dabd-104">Dans cette tâche, vous allez configurer une nouvelle structure d’exploration de données et ajouter un modèle d’exploration de données initial basé sur l' [!INCLUDE[msCoName](../includes/msconame-md.md)] algorithme MDT (Decision Trees).</span><span class="sxs-lookup"><span data-stu-id="4dabd-104">In this task you will set up a new mining structure, and add an initial mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="4dabd-105">Pour créer la structure, vous allez sélectionner en premier des tables et des vues, puis vous identifierez quelles colonnes seront utilisées pour l'apprentissage et pour le test.</span><span class="sxs-lookup"><span data-stu-id="4dabd-105">To create the structure, you will first select tables and views and then identify which columns will be used for training and which for testing.</span></span>  
  
### <a name="to-create-a-mining-structure-for-the-targeted-mailing-scenario"></a><span data-ttu-id="4dabd-106">Pour créer une structure d'exploration de données pour le scénario de publipostage ciblé</span><span class="sxs-lookup"><span data-stu-id="4dabd-106">To create a mining structure for the targeted mailing scenario</span></span>  
  
1.  <span data-ttu-id="4dabd-107">Dans Explorateur de solutions, cliquez avec le bouton droit sur **structures d’exploration** de données et sélectionnez **nouvelle structure d’exploration** de données pour démarrer l’Assistant Exploration de données.</span><span class="sxs-lookup"><span data-stu-id="4dabd-107">In Solution Explorer, right-click **Mining Structures** and select **New Mining Structure** to start the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="4dabd-108">Dans la page **Assistant Exploration de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-108">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="4dabd-109">Sur la page **Sélectionner la méthode de définition** , vérifiez que **à partir de la base de données relationnelle ou de l’entrepôt de données existant** est sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-109">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="4dabd-110">Dans la page **créer la structure d’exploration de données** , sous **quelle technique d’exploration de données voulez-vous utiliser ?**, sélectionnez **Microsoft Decision Trees**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-110">On the **Create the Data Mining Structure** page, under **Which data mining technique do you want to use?**, select **Microsoft Decision Trees**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dabd-111">Si vous obtenez un avertissement indiquant qu'aucun algorithme d'exploration de données n'a été trouvé, les propriétés du projet ne sont peut-être pas configurées correctement.</span><span class="sxs-lookup"><span data-stu-id="4dabd-111">If you get a warning that no data mining algorithms can be found, the project properties might not be configured correctly.</span></span> <span data-ttu-id="4dabd-112">Cet avertissement se produit lorsque le projet tente d'extraire une liste d'algorithmes d'exploration de données du serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et ne trouve pas le serveur.</span><span class="sxs-lookup"><span data-stu-id="4dabd-112">This warning occurs when the project attempts to retrieve a list of data mining algorithms from the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and cannot find the server.</span></span> <span data-ttu-id="4dabd-113">Par défaut, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] utilise **localhost** comme serveur.</span><span class="sxs-lookup"><span data-stu-id="4dabd-113">By default, [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] will use **localhost** as the server.</span></span> <span data-ttu-id="4dabd-114">Si vous utilisez une instance différente ou une instance nommée, vous devez modifier les propriétés du projet.</span><span class="sxs-lookup"><span data-stu-id="4dabd-114">If you are using a different instance, or a named instance, you must change the project properties.</span></span> <span data-ttu-id="4dabd-115">Pour plus d’informations, consultez [création d’un projet de Analysis Services &#40;didacticiel sur l’exploration de données de base&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4dabd-115">For more information, see [Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="4dabd-116">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4dabd-117">Dans la page **Sélectionner une vue de source de données** , dans le volet vues de sources de **données disponibles** , sélectionnez **Publipostage ciblé**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-117">On the **Select Data Source View** page, in the **Available data source views** pane, select **Targeted Mailing**.</span></span> <span data-ttu-id="4dabd-118">Vous pouvez cliquer sur **Parcourir** pour afficher les tables dans la vue de source de données, puis cliquer sur **Fermer** pour revenir à l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4dabd-118">You can click **Browse** to view the tables in the data source view and then click **Close** to return to the wizard.</span></span>  
  
7.  <span data-ttu-id="4dabd-119">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-119">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="4dabd-120">Dans la page **spécifier les types des tables** , activez la case à cocher dans la colonne **cas** pour que vTargetMail l’utilise comme table de cas, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-120">On the **Specify Table Types** page, select the check box in the **Case** column for vTargetMail to use it as the case table, and then click **Next**.</span></span> <span data-ttu-id="4dabd-121">Vous utiliserez ultérieurement la table ProspectiveBuyer à des fins de test ; ignorez-la pour le moment.</span><span class="sxs-lookup"><span data-stu-id="4dabd-121">You will use the ProspectiveBuyer table later for testing; ignore it for now.</span></span>  
  
9. <span data-ttu-id="4dabd-122">Dans la page **spécifier les données d’apprentissage** , vous allez identifier au moins une colonne prévisible, une colonne clé et une colonne d’entrée pour votre modèle.</span><span class="sxs-lookup"><span data-stu-id="4dabd-122">On the **Specify the Training Data** page, you will identify at least one predictable column, one key column, and one input column for your model.</span></span> <span data-ttu-id="4dabd-123">Activez la case à cocher dans la colonne **prévisible** de la ligne **BikeBuyer** .</span><span class="sxs-lookup"><span data-stu-id="4dabd-123">Select the check box in the **Predictable** column in the **BikeBuyer** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dabd-124">Remarquez l'avertissement en bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="4dabd-124">Notice the warning at the bottom of the window.</span></span> <span data-ttu-id="4dabd-125">Vous ne pouvez pas accéder à la page suivante tant que vous n’avez pas sélectionné au moins une colonne **d’entrée** et une colonne **prévisible** .</span><span class="sxs-lookup"><span data-stu-id="4dabd-125">You will not be able to navigate to the next page until you select at least one **Input** and one **Predictable** column.</span></span>  
  
10. <span data-ttu-id="4dabd-126">Cliquez sur **suggérer** pour ouvrir la boîte de dialogue **suggérer les colonnes associées** .</span><span class="sxs-lookup"><span data-stu-id="4dabd-126">Click **Suggest** to open the **Suggest Related Columns** dialog box.</span></span>  
  
     <span data-ttu-id="4dabd-127">Le bouton **suggérer** est activé chaque fois qu’au moins un attribut prévisible a été sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4dabd-127">The **Suggest** button is enabled whenever at least one predictable attribute has been selected.</span></span> <span data-ttu-id="4dabd-128">La boîte de dialogue **suggérer les colonnes associées** répertorie les colonnes qui sont le plus étroitement liées à la colonne prévisible et classe les attributs en fonction de leur corrélation avec l’attribut prévisible.</span><span class="sxs-lookup"><span data-stu-id="4dabd-128">The **Suggest Related Columns** dialog box lists the columns that are most closely related to the predictable column, and orders the attributes by their correlation with the predictable attribute.</span></span> <span data-ttu-id="4dabd-129">Les colonnes qui contiennent une corrélation significative (confiance supérieure à 95%) sont automatiquement sélectionnées pour être incluses dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4dabd-129">Columns with a significant correlation (confidence greater than 95%) are automatically selected to be included in the model.</span></span>  
  
     <span data-ttu-id="4dabd-130">Passez en revue les suggestions, puis cliquez sur **Annuler** toignore les suggestions.</span><span class="sxs-lookup"><span data-stu-id="4dabd-130">Review the suggestions, and then click **Cancel** toignore the suggestions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dabd-131">Si vous cliquez sur **OK**, toutes les suggestions répertoriées sont marquées comme colonnes d’entrée dans l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="4dabd-131">If you click **OK**, all listed suggestions will be marked as input columns in the wizard.</span></span> <span data-ttu-id="4dabd-132">Si vous acceptez uniquement certaines des suggestions, vous devez modifier les valeurs manuellement.</span><span class="sxs-lookup"><span data-stu-id="4dabd-132">If you agree with only some of the suggestions, you must change the values manually.</span></span>  
  
11. <span data-ttu-id="4dabd-133">Vérifiez que la case à cocher dans la colonne **clé** est sélectionnée dans la ligne **CustomerKey** .</span><span class="sxs-lookup"><span data-stu-id="4dabd-133">Verify that the check box in the **Key** column is selected in the **CustomerKey** row.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4dabd-134">Si la table source de la vue de source de données indique une clé, l'Assistant Exploration de données choisit automatiquement cette colonne comme clé du modèle.</span><span class="sxs-lookup"><span data-stu-id="4dabd-134">If the source table from the data source view indicates a key, the Data Mining Wizard automatically chooses that column as a key for the model.</span></span>  
  
12. <span data-ttu-id="4dabd-135">Activez les cases à cocher dans la colonne **d’entrée** dans les lignes suivantes.</span><span class="sxs-lookup"><span data-stu-id="4dabd-135">Select the check boxes in the **Input** column in the following rows.</span></span> <span data-ttu-id="4dabd-136">Vous pouvez activer plusieurs colonnes en mettant en surbrillance une plage de cellules et en appuyant sur CTRL tout en activant une case à cocher.</span><span class="sxs-lookup"><span data-stu-id="4dabd-136">You can check multiple columns by highlighting a range of cells and pressing CTRL while selecting a check box.</span></span>  
  
    -   <span data-ttu-id="4dabd-137">**Age**</span><span class="sxs-lookup"><span data-stu-id="4dabd-137">**Age**</span></span>  
  
    -   <span data-ttu-id="4dabd-138">**CommuteDistance**</span><span class="sxs-lookup"><span data-stu-id="4dabd-138">**CommuteDistance**</span></span>  
  
    -   <span data-ttu-id="4dabd-139">**EnglishEducation**</span><span class="sxs-lookup"><span data-stu-id="4dabd-139">**EnglishEducation**</span></span>  
  
    -   <span data-ttu-id="4dabd-140">**EnglishOccupation**</span><span class="sxs-lookup"><span data-stu-id="4dabd-140">**EnglishOccupation**</span></span>  
  
    -   <span data-ttu-id="4dabd-141">**Sexe**</span><span class="sxs-lookup"><span data-stu-id="4dabd-141">**Gender**</span></span>  
  
    -   <span data-ttu-id="4dabd-142">**GeographyKey**</span><span class="sxs-lookup"><span data-stu-id="4dabd-142">**GeographyKey**</span></span>  
  
    -   <span data-ttu-id="4dabd-143">**HouseOwnerFlag**</span><span class="sxs-lookup"><span data-stu-id="4dabd-143">**HouseOwnerFlag**</span></span>  
  
    -   <span data-ttu-id="4dabd-144">**MaritalStatus**</span><span class="sxs-lookup"><span data-stu-id="4dabd-144">**MaritalStatus**</span></span>  
  
    -   <span data-ttu-id="4dabd-145">**NumberCarsOwned**</span><span class="sxs-lookup"><span data-stu-id="4dabd-145">**NumberCarsOwned**</span></span>  
  
    -   <span data-ttu-id="4dabd-146">**NumberChildrenAtHome**</span><span class="sxs-lookup"><span data-stu-id="4dabd-146">**NumberChildrenAtHome**</span></span>  
  
    -   <span data-ttu-id="4dabd-147">**Région**</span><span class="sxs-lookup"><span data-stu-id="4dabd-147">**Region**</span></span>  
  
    -   <span data-ttu-id="4dabd-148">**TotalChildren**</span><span class="sxs-lookup"><span data-stu-id="4dabd-148">**TotalChildren**</span></span>  
  
    -   <span data-ttu-id="4dabd-149">**YearlyIncome**</span><span class="sxs-lookup"><span data-stu-id="4dabd-149">**YearlyIncome**</span></span>  
  
13. <span data-ttu-id="4dabd-150">Sur la colonne d'extrême gauche de la page, activez les cases à cocher dans les lignes suivantes.</span><span class="sxs-lookup"><span data-stu-id="4dabd-150">On the far left column of the page, select the check boxes in the following rows.</span></span>  
  
    -   <span data-ttu-id="4dabd-151">**AddressLine1**</span><span class="sxs-lookup"><span data-stu-id="4dabd-151">**AddressLine1**</span></span>  
  
    -   <span data-ttu-id="4dabd-152">**AddressLine2**</span><span class="sxs-lookup"><span data-stu-id="4dabd-152">**AddressLine2**</span></span>  
  
    -   <span data-ttu-id="4dabd-153">**DateFirstPurchase**</span><span class="sxs-lookup"><span data-stu-id="4dabd-153">**DateFirstPurchase**</span></span>  
  
    -   <span data-ttu-id="4dabd-154">**EmailAddress**</span><span class="sxs-lookup"><span data-stu-id="4dabd-154">**EmailAddress**</span></span>  
  
    -   <span data-ttu-id="4dabd-155">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="4dabd-155">**FirstName**</span></span>  
  
    -   <span data-ttu-id="4dabd-156">**LastName**</span><span class="sxs-lookup"><span data-stu-id="4dabd-156">**LastName**</span></span>  
  
     <span data-ttu-id="4dabd-157">Vérifiez que ces lignes n'ont des coches que dans la colonne gauche.</span><span class="sxs-lookup"><span data-stu-id="4dabd-157">Ensure that these rows have checks only in the left column.</span></span> <span data-ttu-id="4dabd-158">Ces colonnes seront ajoutées à votre structure mais ne seront pas incluses dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="4dabd-158">These columns will be added to your structure but will not be included in the model.</span></span> <span data-ttu-id="4dabd-159">Toutefois, une fois le modèle construit, elles seront disponibles pour l'extraction et le test.</span><span class="sxs-lookup"><span data-stu-id="4dabd-159">However, after the model is built, they will be available for drillthrough and testing.</span></span> <span data-ttu-id="4dabd-160">Pour plus d’informations sur l’extraction, consultez [requêtes d’extraction &#40;exploration de données&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="4dabd-160">For more information about drillthrough, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md)</span></span>  
  
14. <span data-ttu-id="4dabd-161">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4dabd-161">Click **Next**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4dabd-162">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4dabd-162">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4dabd-163">Spécification du type de données et du type de contenu &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="4dabd-163">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dabd-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dabd-164">See Also</span></span>  
 <span data-ttu-id="4dabd-165">[Spécifier les types de tables &#40;l’Assistant Exploration de données&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="4dabd-165">[Specify Table Types &#40;Data Mining Wizard&#41;](../../2014/analysis-services/specify-table-types-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="4dabd-166">[Concepteur d’exploration de données](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="4dabd-166">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="4dabd-167">Algorithme MDT (Microsoft Decision Trees)</span><span class="sxs-lookup"><span data-stu-id="4dabd-167">Microsoft Decision Trees Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)  
  
  
