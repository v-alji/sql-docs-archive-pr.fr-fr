---
title: 'Leçon 5 : mise en forme d’un rapport (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 00f0d780e957fd9ff995fefb1d033275a7da428d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613834"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a><span data-ttu-id="8afb8-102">Lesson 5: Formatting a Report (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="8afb8-102">Lesson 5: Formatting a Report (Reporting Services)</span></span>
  <span data-ttu-id="8afb8-103">Maintenant que vous avez ajouté une région de données et quelques champs au rapport Sales Orders, vous pouvez mettre en forme les champs de date et de valeurs monétaires, ainsi que les en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="8afb8-103">Now that you've added a data region and some fields to the Sales Orders report, you can format the date and currency fields and the column headers.</span></span>  
  
 <span data-ttu-id="8afb8-104">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="8afb8-104">In this topic:</span></span>  
  
-   [<span data-ttu-id="8afb8-105">Mettre en forme la date</span><span class="sxs-lookup"><span data-stu-id="8afb8-105">Format the Date</span></span>](#bkmk_format_date)  
  
-   [<span data-ttu-id="8afb8-106">Mettre en forme la devise</span><span class="sxs-lookup"><span data-stu-id="8afb8-106">Format the Currency</span></span>](#bkmk_format_currency)  
  
-   [<span data-ttu-id="8afb8-107">Modification du style du texte et de la largeur des colonnes</span><span class="sxs-lookup"><span data-stu-id="8afb8-107">Change Text Style and Column Widths</span></span>](#bkmk_change_textstyle)  
  
##  <a name="format-the-date"></a><a name="bkmk_format_date"></a><span data-ttu-id="8afb8-108">Mettre en forme la date</span><span class="sxs-lookup"><span data-stu-id="8afb8-108">Format the Date</span></span>  
 <span data-ttu-id="8afb8-109">Le champ Date affiche les informations de date et d'heure par défaut.</span><span class="sxs-lookup"><span data-stu-id="8afb8-109">The Date field displays date and time information by default.</span></span> <span data-ttu-id="8afb8-110">Vous pouvez le mettre en forme de sorte qu'il n'affiche que la date.</span><span class="sxs-lookup"><span data-stu-id="8afb8-110">You can format it to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field"></a><span data-ttu-id="8afb8-111">Pour appliquer un format de date</span><span class="sxs-lookup"><span data-stu-id="8afb8-111">To format a date field</span></span>  
  
1.  <span data-ttu-id="8afb8-112">Cliquez sur l'onglet **Conception** .</span><span class="sxs-lookup"><span data-stu-id="8afb8-112">Click the **Design** tab.</span></span>  
  
2.  <span data-ttu-id="8afb8-113">Cliquez avec le bouton droit sur la cellule qui contient l’expression de champ `[Date]` , puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-113">Right-click the cell with the `[Date]` field expression and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="8afb8-114">Cliquez sur **nombre**, puis dans le champ **catégorie** , sélectionnez `Date` .</span><span class="sxs-lookup"><span data-stu-id="8afb8-114">Click **Number**, and then in the **Category** field, select `Date`.</span></span>  
  
4.  <span data-ttu-id="8afb8-115">Dans la zone **Type** , sélectionnez **January 31, 2000**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-115">In the **Type** box, select **January 31, 2000**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8afb8-116">Affichez un aperçu du rapport pour voir la modification apportée au champ `[Date]` , puis repassez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="8afb8-116">Preview the report to see the change to the `[Date]` field and then change back to design view.</span></span>  
  
##  <a name="format-the-currency"></a><a name="bkmk_format_currency"></a><span data-ttu-id="8afb8-117">Mettre en forme la devise</span><span class="sxs-lookup"><span data-stu-id="8afb8-117">Format the Currency</span></span>  
 <span data-ttu-id="8afb8-118">Le champ LineTotal affiche un nombre général.</span><span class="sxs-lookup"><span data-stu-id="8afb8-118">The LineTotal field displays a general number.</span></span> <span data-ttu-id="8afb8-119">Appliquez une mise en forme pour afficher ce nombre dans un format monétaire.</span><span class="sxs-lookup"><span data-stu-id="8afb8-119">Format it to display the number as currency.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="8afb8-120">Pour mettre en forme un champ monétaire</span><span class="sxs-lookup"><span data-stu-id="8afb8-120">To format a currency field</span></span>  
  
1.  <span data-ttu-id="8afb8-121">Cliquez avec le bouton droit sur la cellule qui contient l’expression de champ `[LineTotal]` , puis cliquez sur **Propriétés de la zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-121">Right-click the cell with the `[LineTotal]` field expression and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="8afb8-122">Cliquez sur **Nombre**puis, dans le champ **Catégorie** , sélectionnez **Devise**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-122">Click **Number**, and in the **Category** field, select **Currency**.</span></span>  
  
3.  <span data-ttu-id="8afb8-123">Si votre paramètre régional est Anglais (États-Unis), les valeurs par défaut doivent être :</span><span class="sxs-lookup"><span data-stu-id="8afb8-123">If your regional setting is English (United States), the defaults should be:</span></span>  
  
    -   <span data-ttu-id="8afb8-124">**Nombre de décimales : 2**</span><span class="sxs-lookup"><span data-stu-id="8afb8-124">**Decimal places: 2**</span></span>  
  
    -   <span data-ttu-id="8afb8-125">**Nombres négatifs : ($12345.00)**</span><span class="sxs-lookup"><span data-stu-id="8afb8-125">**Negative numbers: ($12345.00)**</span></span>  
  
    -   <span data-ttu-id="8afb8-126">**Symbole : $ Anglais (États-Unis)**</span><span class="sxs-lookup"><span data-stu-id="8afb8-126">**Symbol: $ English (United States)**</span></span>  
  
4.  <span data-ttu-id="8afb8-127">Sélectionnez **Utiliser le séparateur de milliers (,)**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-127">Select **Use 1000 separator (,)**.</span></span>  
  
     <span data-ttu-id="8afb8-128">Si l'exemple de texte est :**$12,345.00**, vos paramètres sont corrects.</span><span class="sxs-lookup"><span data-stu-id="8afb8-128">If the sample text is:**$12,345.00**, then your settings are correct.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8afb8-129">Affichez un aperçu du rapport pour voir la modification apportée au champ `[LineTotal]` , puis repassez en mode Conception.</span><span class="sxs-lookup"><span data-stu-id="8afb8-129">Preview the report to see the change to the `[LineTotal]` field and then change back to design view.</span></span>  
  
##  <a name="change-text-style-and-column-widths"></a><a name="bkmk_change_textstyle"></a><span data-ttu-id="8afb8-130">Modifier le style de texte et les largeurs de colonne</span><span class="sxs-lookup"><span data-stu-id="8afb8-130">Change Text Style and Column Widths</span></span>  
 <span data-ttu-id="8afb8-131">Vous pouvez également modifier la mise en forme de la ligne d'en-tête afin de la différencier des lignes de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="8afb8-131">You can also change the formatting of the header row to differentiate it from the rows of data in the report.</span></span> <span data-ttu-id="8afb8-132">Enfin, vous pouvez ajuster les largeurs de colonnes.</span><span class="sxs-lookup"><span data-stu-id="8afb8-132">Lastly, you will adjust the widths of the columns.</span></span>  
  
#### <a name="to-format-header-rows-and-table-columns"></a><span data-ttu-id="8afb8-133">Pour mettre en forme les lignes d'en-tête et les colonnes de la table</span><span class="sxs-lookup"><span data-stu-id="8afb8-133">To format header rows and table columns</span></span>  
  
1.  <span data-ttu-id="8afb8-134">Cliquez sur la table pour que les poignées de ligne et de colonne apparaissent au-dessus et à côté de la table.</span><span class="sxs-lookup"><span data-stu-id="8afb8-134">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="8afb8-135">![Conception, table avec ligne d'en-tête et ligne de détails](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Conception, table avec ligne d'en-tête et ligne de détails")</span><span class="sxs-lookup"><span data-stu-id="8afb8-135">![Design, Table with header row and detail row](../../2014/tutorials/media/rs-basictabledetailsdesign.gif "Design, Table with header row and detail row")</span></span>  
  
     <span data-ttu-id="8afb8-136">Les barres grises le long du haut et du côté de la table sont les poignées de colonne et de ligne.</span><span class="sxs-lookup"><span data-stu-id="8afb8-136">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
2.  <span data-ttu-id="8afb8-137">Placez le curseur entre les séparateurs de colonne pour qu'il se transforme en flèche à deux pointes.</span><span class="sxs-lookup"><span data-stu-id="8afb8-137">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="8afb8-138">Faites glisser les colonnes pour les redimensionner.</span><span class="sxs-lookup"><span data-stu-id="8afb8-138">Drag the columns to the size you want.</span></span>  
  
3.  <span data-ttu-id="8afb8-139">Sélectionnez la ligne qui contient les étiquettes d'en-tête de colonne et, dans le menu **Format** , pointez sur **Police** , puis cliquez **Gras**.</span><span class="sxs-lookup"><span data-stu-id="8afb8-139">Select the row containing column header labels and from the **Format** menu, point to **Font** and then click **Bold**.</span></span>  
  
4.  <span data-ttu-id="8afb8-140">Pour afficher un aperçu de votre rapport, cliquez sur l’onglet **Aperçu** . La valeur doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="8afb8-140">To preview your report, click the **Preview** tab. It should look something like this:</span></span>  
  
     <span data-ttu-id="8afb8-141">![Aperçu de table avec en-têtes de colonnes en gras](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Aperçu de table avec en-têtes de colonnes en gras")</span><span class="sxs-lookup"><span data-stu-id="8afb8-141">![Preview of table with bold column headers](../../2014/tutorials/media/rs-basictabledetailsformattedpreview.gif "Preview of table with bold column headers")</span></span>  
  
5.  <span data-ttu-id="8afb8-142">Dans le menu **Fichier** , cliquez sur **Enregistrer tout** pour enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="8afb8-142">On the **File** menu, click **Save All** to save the report.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8afb8-143">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="8afb8-143">Next Steps</span></span>  
 <span data-ttu-id="8afb8-144">Vous avez correctement mis en forme les en-têtes de colonne, ainsi que les valeurs de date et valeurs monétaires.</span><span class="sxs-lookup"><span data-stu-id="8afb8-144">You have successfully formatted column headers and date and currency values.</span></span> <span data-ttu-id="8afb8-145">Vous allez ensuite ajouter un regroupement et des totaux à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="8afb8-145">Next, you will add grouping and totals to your report.</span></span> <span data-ttu-id="8afb8-146">Consultez la [Leçon 6 : ajout d’un regroupement et de totaux &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="8afb8-146">See [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8afb8-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8afb8-147">See Also</span></span>  
 <span data-ttu-id="8afb8-148">[Mise en forme des nombres et des dates &#40;Générateur de rapports et SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="8afb8-148">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="8afb8-149">Comportements de rendu &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8afb8-149">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
