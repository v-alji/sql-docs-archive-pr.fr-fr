---
title: 'Tâche 4 (facultatif) : combinaison, correspondance et publication d’un nouveau jeu de données | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601194"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="a4cad-102">Tâche 4 (facultatif) : Combinaison, mise en correspondance et publication d’un nouvel ensemble de données</span><span class="sxs-lookup"><span data-stu-id="a4cad-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="a4cad-103">Au fil du temps, vous souhaiterez ajouter des données au référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="a4cad-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="a4cad-104">Avant d’ajouter des données, il peut être utile de comparer les nouvelles données aux données qui sont déjà gérées dans MDS, pour vous assurer que vous n’ajoutez pas de données dupliquées ou inexactes.</span><span class="sxs-lookup"><span data-stu-id="a4cad-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="a4cad-105">Dans le complément Master Data Services pour Excel, vous pouvez combiner les données de deux feuilles de calcul et les comparer afin d'identifier et supprimer les doublons, avant de les publier dans MDS.</span><span class="sxs-lookup"><span data-stu-id="a4cad-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="a4cad-106">La fonctionnalité de correspondance dans le complément MDS pour Excel utilise la fonctionnalité de correspondance de DQS pour identifier les correspondances de données.</span><span class="sxs-lookup"><span data-stu-id="a4cad-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="a4cad-107">Dans cette tâche, vous allez combiner les données de deux feuilles de calcul dans une seule feuille, puis vous allez exercer l'activité de correspondance pour identifier et supprimer les doublons avant la publication dans MDS.</span><span class="sxs-lookup"><span data-stu-id="a4cad-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="a4cad-108">Pour plus d’informations, consultez [correspondance de la qualité des données dans les rubriques complément MDS pour Excel](https://msdn.microsoft.com/library/hh548681.aspx) et [combiner les données](https://msdn.microsoft.com/library/hh548680.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a4cad-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="a4cad-109">Lancez une nouvelle instance d' **Excel**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="a4cad-110">Cliquez sur **Démarrer**, pointez sur **exécuter**, tapez **Excel**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="a4cad-111">Basculez vers l’onglet **données** de référence en cliquant sur **données** de référence dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="a4cad-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="a4cad-112">Cliquez sur **connexion** sur le ruban dans le groupe **se connecter et charger** pour vous connecter au **serveur MDS**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="a4cad-113">Vous avez configuré cette connexion précédemment dans cette leçon.</span><span class="sxs-lookup"><span data-stu-id="a4cad-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="a4cad-114">![Excel - Afficher le bouton d'explorateur dans l'onglet des données de référence](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Afficher le bouton d'explorateur dans l'onglet des données de référence")</span><span class="sxs-lookup"><span data-stu-id="a4cad-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="a4cad-115">Le volet **Explorateur de données maître** doit s’afficher à droite.</span><span class="sxs-lookup"><span data-stu-id="a4cad-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="a4cad-116">Si le Explorateur de données maître ne s’affiche pas, cliquez sur le bouton **afficher l’Explorateur** sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="a4cad-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="a4cad-117">Dans la fenêtre **Explorateur de données principale** , sélectionnez **fournisseurs** dans la liste déroulante du **modèle**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="a4cad-118">Vous devez voir que le modèle a une entité : **Supplier**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="a4cad-119">![Excel - Fenêtre Explorateur de données de référence](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Fenêtre Explorateur de données de référence")</span><span class="sxs-lookup"><span data-stu-id="a4cad-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="a4cad-120">Double-cliquez sur **Supplier** dans la liste d’entités pour charger les membres d’entité dans la feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="a4cad-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="a4cad-121">Cliquez sur **Feuil2** en bas pour basculer vers l’onglet **Feuil2** . Si vous ne voyez pas **Feuil2**, ajoutez une nouvelle feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="a4cad-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="a4cad-122">Ouvrez **Suppliers.xls** fichier (le fichier d’entrée d’origine inclus dans les fichiers du didacticiel) et copiez toutes les lignes (trois) de la feuille de calcul **CombineAndCleanse** dans **Feuil2**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="a4cad-123">Revenez à la feuille du **fournisseur** dans le **livre 1 : Microsoft Excel** (pas le **nettoyage et le correspondance des fournisseurs** Excel) qui est connecté à **MDS**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="a4cad-124">Dans la barre de menus, cliquez sur **données** de référence.</span><span class="sxs-lookup"><span data-stu-id="a4cad-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="a4cad-125">Cliquez sur **combiner des données** sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="a4cad-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="a4cad-126">La boîte de dialogue **combiner des données** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="a4cad-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="a4cad-127">Dans la boîte de dialogue **combiner des données** , cliquez sur le bouton en regard de la zone **de texte plage à combiner avec les données MDS** , comme indiqué dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="a4cad-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="a4cad-128">![Excel - Boîte de dialogue Combiner des données](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Boîte de dialogue Combiner des données")</span><span class="sxs-lookup"><span data-stu-id="a4cad-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="a4cad-129">Vous devez maintenant voir la boîte de dialogue réduite.</span><span class="sxs-lookup"><span data-stu-id="a4cad-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="a4cad-130">Maintenant, cliquez sur **Feuil2** pour basculer vers l’onglet **Feuil2** qui contient les nouvelles données de fournisseur avec 4 lignes (y compris une ligne d’en-tête).</span><span class="sxs-lookup"><span data-stu-id="a4cad-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="a4cad-131">Dans **Feuil2**, sélectionnez **toutes les lignes, y compris la ligne d’en-tête** (même si elles semblent être déjà sélectionnées).</span><span class="sxs-lookup"><span data-stu-id="a4cad-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="a4cad-132">Vous devez voir la **plage à combiner avec les données MDS** est automatiquement mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a4cad-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="a4cad-133">![Excel - Boîte de dialogue Combiner des données - Réduit](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Boîte de dialogue Combiner des données - Réduit")</span><span class="sxs-lookup"><span data-stu-id="a4cad-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="a4cad-134">Revenez à l’onglet **fournisseurs** sans fermer la boîte de dialogue **combiner des données** .</span><span class="sxs-lookup"><span data-stu-id="a4cad-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="a4cad-135">Cliquez sur le **bouton** en regard de la **zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="a4cad-136">Vous devez maintenant voir la boîte de dialogue développée.</span><span class="sxs-lookup"><span data-stu-id="a4cad-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="a4cad-137">Vous devez voir que tous les mappages entre les colonnes de l' **entité** MDS du **fournisseur** et les colonnes **Excel** sont renseignés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="a4cad-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="a4cad-138">![Excel - Boîte de dialogue Combiner des données comme étant rempli des données](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Boîte de dialogue Combiner des données comme étant rempli des données")</span><span class="sxs-lookup"><span data-stu-id="a4cad-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="a4cad-139">Vérifiez que la colonne d’entité **code** est mappée à la colonne **RéfFournisseur** dans la feuille de calcul et que la colonne d’entité **Code postal** est mappée à la colonne **Code postal** de la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="a4cad-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="a4cad-140">Dans la boîte de dialogue **combiner des données** , cliquez sur **combiner**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="a4cad-141">Vérifiez que trois lignes de données sont ajoutées au bas de la feuille de calcul et qu'elles sont codées par couleur.</span><span class="sxs-lookup"><span data-stu-id="a4cad-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="a4cad-142">![Excel - Nouveaux éléments après la combinaison](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - Nouveaux éléments après la combinaison")</span><span class="sxs-lookup"><span data-stu-id="a4cad-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="a4cad-143">Cliquez sur **données mathématiques** sur le ruban pour identifier les doublons.</span><span class="sxs-lookup"><span data-stu-id="a4cad-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="a4cad-144">Cette fonction utilise la fonctionnalité de correspondance de DQS.</span><span class="sxs-lookup"><span data-stu-id="a4cad-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="a4cad-145">Dans la boîte de dialogue **correspondance des données** , sélectionnez **Suppliers** pour la **base de connaissances DQS**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="a4cad-146">![Excel - Boîte de dialogue Mettre en correspondance les données](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Boîte de dialogue Mettre en correspondance les données")</span><span class="sxs-lookup"><span data-stu-id="a4cad-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="a4cad-147">Mappez les colonnes de la feuille de calcul aux domaines, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a4cad-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="a4cad-148">Colonne de feuille de calcul</span><span class="sxs-lookup"><span data-stu-id="a4cad-148">Worksheet Column</span></span>|<span data-ttu-id="a4cad-149">Domain</span><span class="sxs-lookup"><span data-stu-id="a4cad-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="a4cad-150">Code (vous avez téléchargé l'ID du fournisseur en tant que code de l'entité du fournisseur dans MDS)</span><span class="sxs-lookup"><span data-stu-id="a4cad-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="a4cad-151">ID du fournisseur</span><span class="sxs-lookup"><span data-stu-id="a4cad-151">Supplier ID</span></span>|  
    |<span data-ttu-id="a4cad-152">Nom (vous avez téléchargé le nom du fournisseur en tant que nom de l'entité du fournisseur sur MDS)</span><span class="sxs-lookup"><span data-stu-id="a4cad-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="a4cad-153">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="a4cad-153">Supplier Name</span></span>|  
    |<span data-ttu-id="a4cad-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="a4cad-154">ContactEmailAddress</span></span>|<span data-ttu-id="a4cad-155">ContactEmail</span><span class="sxs-lookup"><span data-stu-id="a4cad-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="a4cad-156">Sélectionnez **condition préalable** pour le mappage de colonne de **code** .</span><span class="sxs-lookup"><span data-stu-id="a4cad-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="a4cad-157">Entrez **70%** comme **poids** pour le **nom du fournisseur** et **30%** comme **poids** de l' **e-mail du contact** , comme indiqué dans l’image.</span><span class="sxs-lookup"><span data-stu-id="a4cad-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="a4cad-158">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="a4cad-159">Le processus de correspondance doit identifier un doublon pour le fournisseur avec le **Code : S1**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="a4cad-160">![Excel - Résultats de correspondance](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Résultats de correspondance")</span><span class="sxs-lookup"><span data-stu-id="a4cad-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="a4cad-161">Sélectionnez la **ligne dupliquée (orange)**, cliquez avec le bouton droit, puis cliquez sur **supprimer** pour supprimer la ligne.</span><span class="sxs-lookup"><span data-stu-id="a4cad-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="a4cad-162">Supprimez la colonne **CLUSTER_ID** , car vous n’en avez plus besoin.</span><span class="sxs-lookup"><span data-stu-id="a4cad-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="a4cad-163">Cliquez sur **publier** pour publier les deux nouveaux enregistrements avec les **codes S66** et **S57** pour MDS.</span><span class="sxs-lookup"><span data-stu-id="a4cad-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="a4cad-164">Dans la boîte de dialogue **publier et annoter** , ajoutez une **annotation**, puis cliquez sur **publier**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="a4cad-165">Basculez vers l' **application Web Data Manager maître**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="a4cad-166">Sur la page d’hébergement, vérifiez que **fournisseurs** est sélectionné pour le **modèle**, puis cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="a4cad-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="a4cad-167">Si vous avez déjà ouvert l' **Explorateur** , actualisez le navigateur Internet.</span><span class="sxs-lookup"><span data-stu-id="a4cad-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="a4cad-168">**Triez** la liste par **code** et recherchez les enregistrements avec **S57** et **S66** en tant que codes.</span><span class="sxs-lookup"><span data-stu-id="a4cad-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="a4cad-169">Vous pouvez également utiliser le bouton **filtre** de la barre d’outils pour rechercher un enregistrement spécifique dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a4cad-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="a4cad-170">Maintenant, fermez le fichier **Classeur1-fenêtre Microsoft Excel** sans enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="a4cad-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a4cad-171">étape suivante</span><span class="sxs-lookup"><span data-stu-id="a4cad-171">Next Step</span></span>  
 [<span data-ttu-id="a4cad-172">Tâche 5 : Création d’un attribut basé sur un domaine à partir d’Excel</span><span class="sxs-lookup"><span data-stu-id="a4cad-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
