---
title: 'Leçon 6 : Ajouter un regroupement et des totaux (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e3d61228-2aa4-42cc-955e-602dbf3406a7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b98798005a984edf00aff469d4c1b09aa2e34d98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613826"
---
# <a name="lesson-6-adding-grouping-and-totals-reporting-services"></a><span data-ttu-id="20dab-102">Leçon 6 : Ajout d'un regroupement et de totaux (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="20dab-102">Lesson 6: Adding Grouping and Totals (Reporting Services)</span></span>
  <span data-ttu-id="20dab-103">Ajoutez un regroupement et des totaux à votre rapport pour organiser et synthétiser vos données.</span><span class="sxs-lookup"><span data-stu-id="20dab-103">Add grouping and totals to your report to organize and summarize your data.</span></span>  
  
 <span data-ttu-id="20dab-104">Pour plus d’informations sur l’ajout de totaux cumulés à des rapports, voir : [Ajout de totaux à des rapports Reporting Services (SSRS)](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span><span class="sxs-lookup"><span data-stu-id="20dab-104">For information about adding running totals to reports, see: [Adding totals to Reporting Services (SSRS) reports](https://www.tutorialgateway.org/add-total-and-subtotal-to-ssrs-report/).</span></span>  
  
 <span data-ttu-id="20dab-105">**Dans cette rubrique :**</span><span class="sxs-lookup"><span data-stu-id="20dab-105">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="20dab-106">Pour regrouper des données dans un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-106">To group data in a report</span></span>](#bkmk_groupdata)  
  
-   [<span data-ttu-id="20dab-107">Pour ajouter des totaux à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-107">To add totals to a report</span></span>](#bkmk_addtotals)  
  
-   [<span data-ttu-id="20dab-108">Pour ajouter un total quotidien à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-108">To add a daily total to a report</span></span>](#bkmk_adddailytotal)  
  
-   [<span data-ttu-id="20dab-109">Pour ajouter un total général à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-109">To add a grand total to a report</span></span>](#bkmk_addgrandtotal)  
  
-   [<span data-ttu-id="20dab-110">Pour publier le rapport sur le serveur de rapports (facultatif)</span><span class="sxs-lookup"><span data-stu-id="20dab-110">To Publish the Report to the Report Server (Optional)</span></span>](#bkmk_publishreport)  
  
##  <a name="to-group-data-in-a-report"></a><a name="bkmk_groupdata"></a><span data-ttu-id="20dab-111">Pour regrouper des données dans un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-111">To group data in a report</span></span>  
  
1.  <span data-ttu-id="20dab-112">Cliquez sur l'onglet **Conception** .</span><span class="sxs-lookup"><span data-stu-id="20dab-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="20dab-113">Si vous ne voyez pas le volet **Groupes de lignes** , cliquez avec le bouton droit sur l'aire de conception, puis sélectionnez **Vue** et cliquez sur **Regroupement**.</span><span class="sxs-lookup"><span data-stu-id="20dab-113">If you do not see the **Row Groups** pane , right-click the design surface and click **view** and then click **Grouping**.</span></span>  
  
3.  <span data-ttu-id="20dab-114">Faites glisser le champ `Date` du volet **Données du rapport** vers le volet **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="20dab-114">From the **Report Data** pane, drag the `Date` field to the **Row Groups** pane.</span></span> <span data-ttu-id="20dab-115">Placez-le au-dessus de la ligne appelée **(Details)**.</span><span class="sxs-lookup"><span data-stu-id="20dab-115">Place it above the row called **(Details)**.</span></span>  
  
     <span data-ttu-id="20dab-116">Notez que le descripteur de ligne comporte maintenant un crochet, qui indique un groupe.</span><span class="sxs-lookup"><span data-stu-id="20dab-116">Note that the row handle now has a bracket in it, to show a group.</span></span> <span data-ttu-id="20dab-117">En outre, le tableau présente désormais deux colonnes Date, placées de part et d'autre d'une ligne verticale en pointillé.</span><span class="sxs-lookup"><span data-stu-id="20dab-117">The table now also has two Date columns -- one on either side of a vertical dotted line.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablegroups1design.gif "rs_BasicTableGroups1Design")  
  
4.  <span data-ttu-id="20dab-118">Faites glisser le champ `Order` du volet **Données du rapport** vers le volet **Groupes de lignes**.</span><span class="sxs-lookup"><span data-stu-id="20dab-118">From the **Report Data** pane, drag the `Order` field to the **Row Groups** pane.</span></span> <span data-ttu-id="20dab-119">Placez-le au-dessous du champ Date et au-dessus de la ligne **(Details)**.</span><span class="sxs-lookup"><span data-stu-id="20dab-119">Place it below Date and above **(Details)**.</span></span>  
  
     <span data-ttu-id="20dab-120">Notez que le descripteur de ligne comporte maintenant deux crochets, qui indiquent deux groupes.</span><span class="sxs-lookup"><span data-stu-id="20dab-120">Note that the row handle now has two brackets in it, to show two groups.</span></span> <span data-ttu-id="20dab-121">La table comporte désormais deux `Order` colonnes.</span><span class="sxs-lookup"><span data-stu-id="20dab-121">The table now has two `Order` columns, too.</span></span>  
  
5.  <span data-ttu-id="20dab-122">Supprimez les colonnes Date et Order d’origine, à **droite** du double trait.</span><span class="sxs-lookup"><span data-stu-id="20dab-122">Delete the original Date and Order columns to the **right** of the double line.</span></span> <span data-ttu-id="20dab-123">Cette opération supprime les différentes valeurs d'enregistrement afin que seule la valeur de groupe soit affichée.</span><span class="sxs-lookup"><span data-stu-id="20dab-123">This removes this individual record values so that only the group value is displayed.</span></span> <span data-ttu-id="20dab-124">Sélectionnez les descripteurs des deux colonnes, cliquez avec le bouton droit, puis cliquez sur **Supprimer les colonnes**.</span><span class="sxs-lookup"><span data-stu-id="20dab-124">Select the column handles for the two columns, right-click and click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="20dab-125">![Sélectionner les colonnes à supprimer](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Sélectionner les colonnes à supprimer")</span><span class="sxs-lookup"><span data-stu-id="20dab-125">![Select columns to delete](../../2014/tutorials/media/rs-basictablegroupsdeletecols.gif "Select columns to delete")</span></span>  
  
     <span data-ttu-id="20dab-126">Vous pouvez de nouveau mettre en forme la date et les en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="20dab-126">You can format the column headers and date again.</span></span>  
  
6.  <span data-ttu-id="20dab-127">Sélectionnez l'onglet **Aperçu** pour afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="20dab-127">Switch to the **Preview** tab to preview the report.</span></span> <span data-ttu-id="20dab-128">Il doit présenter un aspect similaire à l'illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="20dab-128">It should look similar to the following illustration:</span></span>  
  
     <span data-ttu-id="20dab-129">![Table regroupée par date, puis par commande](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table regroupée par date, puis par commande")</span><span class="sxs-lookup"><span data-stu-id="20dab-129">![Table grouped by date and then order](../../2014/tutorials/media/rs-basictablegroupspreview.gif "Table grouped by date and then order")</span></span>  
  
##  <a name="to-add-totals-to-a-report"></a><a name="bkmk_addtotals"></a><span data-ttu-id="20dab-130">Pour ajouter des totaux à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-130">To add totals to a report</span></span>  
  
1.  <span data-ttu-id="20dab-131">Basculez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="20dab-131">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="20dab-132">Cliquez avec le bouton droit dans la cellule de région de données qui contient le champ `[LineTotal]`, puis sélectionnez **Ajouter un total**.</span><span class="sxs-lookup"><span data-stu-id="20dab-132">Right-click the data region cell that contains the field `[LineTotal]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="20dab-133">Cette opération ajoute une ligne avec la somme des montants en dollars de chaque commande.</span><span class="sxs-lookup"><span data-stu-id="20dab-133">This adds a row with a sum of the dollar amount for each order.</span></span>  
  
3.  <span data-ttu-id="20dab-134">Cliquez avec le bouton droit dans la cellule qui contient le champ `[Qty]`, puis cliquez sur **Ajouter un total**.</span><span class="sxs-lookup"><span data-stu-id="20dab-134">Right-click the cell that contains the field `[Qty]`, and click **Add Total**.</span></span>  
  
     <span data-ttu-id="20dab-135">Cette opération ajoute la somme des quantités de chaque commande à la ligne des totaux.</span><span class="sxs-lookup"><span data-stu-id="20dab-135">This adds a sum of the quantity for each order to the totals row.</span></span>  
  
4.  <span data-ttu-id="20dab-136">Dans la cellule vide à gauche de `Sum[Qty]`, tapez l'étiquette «**Total des commandes**».</span><span class="sxs-lookup"><span data-stu-id="20dab-136">In the empty cell to the left of `Sum[Qty]`, type the label "**Order Total"**.</span></span>  
  
5.  <span data-ttu-id="20dab-137">Vous pouvez ajouter une couleur d'arrière-plan à la ligne des totaux.</span><span class="sxs-lookup"><span data-stu-id="20dab-137">You can add a background color to the totals row.</span></span> <span data-ttu-id="20dab-138">Sélectionnez les deux cellules de somme et la cellule d'étiquette.</span><span class="sxs-lookup"><span data-stu-id="20dab-138">Select the two sum cells and the label cell.</span></span>  
  
6.  <span data-ttu-id="20dab-139">Dans le menu **Format** , cliquez sur **Couleur d'arrière-plan**, sur **Gris clair**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20dab-139">On the **Format** menu, click **Background Color**, click **Light Gray**, and click **OK**.</span></span>  
  
     <span data-ttu-id="20dab-140">![Mode Conception : table de base avec total des commandes](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Mode Conception : table de base avec total des commandes")</span><span class="sxs-lookup"><span data-stu-id="20dab-140">![Design view: Basic table with order total](../../2014/tutorials/media/rs-basictablesumlinetotaldesign.gif "Design view: Basic table with order total")</span></span>  
  
##  <a name="to-add-a-daily-total-to-a-report"></a><a name="bkmk_adddailytotal"></a><span data-ttu-id="20dab-141">Pour ajouter un total quotidien à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-141">To add a daily total to a report</span></span>  
  
1.  <span data-ttu-id="20dab-142">Cliquez avec le bouton droit dans la cellule Order , pointez sur **Ajouter un total**, puis cliquez sur **Après**.</span><span class="sxs-lookup"><span data-stu-id="20dab-142">Right-click the Order cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="20dab-143">Cela ajoute une nouvelle ligne contenant les sommes des quantités et des montants en dollars pour chaque jour, et l’étiquette «**total**» dans la colonne Order.</span><span class="sxs-lookup"><span data-stu-id="20dab-143">This adds a new row containing sums of the quantity and dollar amount for each day, and the label "**Total**" in the Order column.</span></span>  
  
2.  <span data-ttu-id="20dab-144">Tapez le mot **quotidien** après le mot **Total** dans la même cellule. Vous obtenez : **Total quotidien**.</span><span class="sxs-lookup"><span data-stu-id="20dab-144">Type the word **Daily** before the word **Total** in the same cell, so it reads **Daily Total**.</span></span>  
  
3.  <span data-ttu-id="20dab-145">Sélectionnez la cellule **Total quotidien** , les deux cellules de **somme** et la cellule vide qui les sépare.</span><span class="sxs-lookup"><span data-stu-id="20dab-145">Select the **Daily Total** cell, the two **Sum** cells and the empty cell between them.</span></span>  
  
4.  <span data-ttu-id="20dab-146">Dans le menu **Format** , cliquez sur **Couleur d'arrière-plan**, sur **Orange**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20dab-146">On the **Format** menu, click **Background Color**, click **Orange**, and click **OK**.</span></span>  
  
     ![](../../2014/tutorials/media/rs-basictablesumdaytotaldesign.gif "rs_BasicTableSumDayTotalDesign")  
  
##  <a name="to-add-a-grand-total-to-a-report"></a><a name="bkmk_addgrandtotal"></a><span data-ttu-id="20dab-147">Pour ajouter un total général à un rapport</span><span class="sxs-lookup"><span data-stu-id="20dab-147">To add a grand total to a report</span></span>  
  
1.  <span data-ttu-id="20dab-148">Cliquez avec le bouton droit dans la cellule Date, pointez sur **Ajouter un total**, puis cliquez sur **Après**.</span><span class="sxs-lookup"><span data-stu-id="20dab-148">Right-click the Date cell, point to **Add Total**, and click **After**.</span></span>  
  
     <span data-ttu-id="20dab-149">Cette opération ajoute une nouvelle ligne contenant la somme des quantités et des montants en dollars pour l’intégralité du rapport, ainsi que l’étiquette **totale** de la `Date` colonne.</span><span class="sxs-lookup"><span data-stu-id="20dab-149">This adds a new row containing sums of the quantity and dollar amount for the entire report, and the **Total** label in the `Date` column.</span></span>  
  
2.  <span data-ttu-id="20dab-150">Tapez le mot **général** après le mot **Total** dans la même cellule. Vous obtenez : **Total général**.</span><span class="sxs-lookup"><span data-stu-id="20dab-150">Type the word **Grand** before the word **Total** in the same cell, so it reads **Grand Total**.</span></span>  
  
3.  <span data-ttu-id="20dab-151">Sélectionnez la cellule **Total général** , les deux cellules de **somme** et les cellules vides qui les séparent.</span><span class="sxs-lookup"><span data-stu-id="20dab-151">Select the **Grand Total** cell, the two **Sum** cells and the empty cells between them.</span></span>  
  
4.  <span data-ttu-id="20dab-152">Dans le menu **Format** , cliquez sur **Couleur d'arrière-plan**, sur **Bleu clair**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="20dab-152">On the **Format** menu, click **Background Color**, click **Light Blue**, and click **OK**.</span></span>  
  
     <span data-ttu-id="20dab-153">![Mode Conception : total général dans table de base](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Mode Conception : total général dans table de base")</span><span class="sxs-lookup"><span data-stu-id="20dab-153">![Design view: Grand total in basic table](../../2014/tutorials/media/rs-basictablesumgrandtotaldesign.gif "Design view: Grand total in basic table")</span></span>  
  
5.  <span data-ttu-id="20dab-154">Cliquez sur Aperçu.</span><span class="sxs-lookup"><span data-stu-id="20dab-154">Click Preview.</span></span>  
  
     <span data-ttu-id="20dab-155">La dernière page doit avoir l'aspect suivant :</span><span class="sxs-lookup"><span data-stu-id="20dab-155">The last page should look something like this:</span></span>  
  
     <span data-ttu-id="20dab-156">![Aperçu : table de base avec total général](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Aperçu : table de base avec total général")</span><span class="sxs-lookup"><span data-stu-id="20dab-156">![Preview: Basic table with grand total](../../2014/tutorials/media/rs-basictablesumgrandtotalpreview.gif "Preview: Basic table with grand total")</span></span>  
  
##  <a name="to-publish-the-report-to-the-report-server-optional"></a><a name="bkmk_publishreport"></a><span data-ttu-id="20dab-157">Pour publier le rapport sur le serveur de rapports (facultatif)</span><span class="sxs-lookup"><span data-stu-id="20dab-157">To Publish the Report to the Report Server (Optional)</span></span>  
  
1.  <span data-ttu-id="20dab-158">Une étape facultative consiste à publier le rapport terminé sur le serveur de rapports en mode natif afin de pouvoir consulter le rapport à partir du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="20dab-158">An optional step is to publish the completed report to the native mode report server so you can view the report from Report Manager.</span></span>  
  
2.  <span data-ttu-id="20dab-159">Dans la barre d'outils, cliquez sur **Projet** , puis sur **Propriétés du didacticiel...**</span><span class="sxs-lookup"><span data-stu-id="20dab-159">On the toolbar click **Project** and then click **tutorial Properties...**</span></span>  
  
3.  <span data-ttu-id="20dab-160">Dans **TargetServerURL** , tapez le nom du serveur de rapports, par exemple **http:// \<servername> /reportserver** .</span><span class="sxs-lookup"><span data-stu-id="20dab-160">In the **TargetServerURL** type the name of the name of your report server, for example **http://\<servername>/reportserver**</span></span>  
  
4.  <span data-ttu-id="20dab-161">Cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="20dab-161">Click **OK**</span></span>  
  
5.  <span data-ttu-id="20dab-162">Dans la barre d'outils, cliquez sur **Générer** , puis sur **Déployer le didacticiel**.</span><span class="sxs-lookup"><span data-stu-id="20dab-162">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>  
  
     <span data-ttu-id="20dab-163">Si vous voyez un message semblable à ce qui suit dans la fenêtre de sortie, c'est que le déploiement a été réalisé avec succès.</span><span class="sxs-lookup"><span data-stu-id="20dab-163">If you see a message similar to the following in the output window, it indicates a successful deployment.</span></span>  
  
    > <span data-ttu-id="20dab-164">------ Création démarrée : Projet : didacticiel, Configuration : débogage ------« Sales Orders.rdl » ignoré.</span><span class="sxs-lookup"><span data-stu-id="20dab-164">------ Build started: Project: tutorial, Configuration: Debug ------Skipping 'Sales Orders.rdl'.</span></span> <span data-ttu-id="20dab-165">L’élément est à jour. Fin de la génération--0 erreur, 0 avertissement------le déploiement a démarré : projet : didacticiel, configuration : déboguer------déploiement dans http:// \<server name> /reportserverDeploying rapport « /Tutorial/Sales Orders ». Fin du déploiement--0 erreur, 0 AVERTISSEMENT = = = = = = = = = = Build : 1 a réussi ou à jour, 0 a échoué, 0 a été ignoré = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =</span><span class="sxs-lookup"><span data-stu-id="20dab-165">Item is up to date.Build complete -- 0 errors, 0 warnings------ Deploy started: Project: tutorial, Configuration: Debug ------Deploying to http://\<server name>/reportserverDeploying report '/tutorial/Sales Orders'.Deploy complete -- 0 errors, 0 warnings========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==================== Deploy: 1 succeeded, 0 failed, 0 skipped ==========</span></span>  
  
     <span data-ttu-id="20dab-166">Si un message d'erreur semblable au suivant s'affiche, vérifiez que vous disposez d'autorisations sur le serveur de rapports et que vous avez démarré [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] avec des privilèges d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="20dab-166">If you see an error message similar to the following, verify you have permissions on the report server and you have started [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] with administrator privileges.</span></span>  
  
    > <span data-ttu-id="20dab-167">« Les autorisations accordées à l’utilisateur «XXXXXXXX \\<votre nom \> d’utilisateur » ne sont pas suffisantes pour effectuer cette opération»</span><span class="sxs-lookup"><span data-stu-id="20dab-167">"The permissions granted to user 'XXXXXXXX\\<your user name\>' are insufficient for performing this operation"</span></span>  
  
6.  <span data-ttu-id="20dab-168">Démarrez le Gestionnaire de rapports avec des privilèges d'administrateur ; cliquez, par exemple, avec le bouton droit sur l'icône d'Internet Explorer et sélectionnez **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="20dab-168">Start Report Manager with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>  
  
     <span data-ttu-id="20dab-169">Accédez à l'URL du Gestionnaire de rapports, par exemple : `http://<server name>/reports`.</span><span class="sxs-lookup"><span data-stu-id="20dab-169">Browse to the Report Manager URL, for example: `http://<server name>/reports`.</span></span>  
  
7.  <span data-ttu-id="20dab-170">Accédez au dossier qui contient le rapport et cliquez sur le nom du rapport `Sales Orders` afin de consulter le rapport rendu dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="20dab-170">Browse to the folder that contains the report and click the name of the report `Sales Orders` to view the rendered report in the browser.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20dab-171">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="20dab-171">Next Steps</span></span>  
 <span data-ttu-id="20dab-172">Vous avez réalisé le didacticiel de création d'un rapport de tableau de base.</span><span class="sxs-lookup"><span data-stu-id="20dab-172">You have successfully completed the Creating a Basic Table Report tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20dab-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20dab-173">See Also</span></span>  
 [<span data-ttu-id="20dab-174">Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="20dab-174">Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
