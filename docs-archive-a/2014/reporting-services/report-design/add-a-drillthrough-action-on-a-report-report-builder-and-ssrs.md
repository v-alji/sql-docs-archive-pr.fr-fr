---
title: Ajouter une action d’extraction à un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a429380f677a309e4e1437a2e3c5036bb4e8a455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603255"
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a><span data-ttu-id="e258b-102">Ajouter une action d'extraction à un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="e258b-102">Add a Drillthrough Action on a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e258b-103">Le rapport qui s’ouvre quand vous cliquez sur le lien dans le rapport principal est appelé *rapport d’extraction*.</span><span class="sxs-lookup"><span data-stu-id="e258b-103">The report that opens when you click the link in the main report is known as a *drillthrough report*.</span></span> <span data-ttu-id="e258b-104">Ce lien d'extraction autorise une action d'extraction.</span><span class="sxs-lookup"><span data-stu-id="e258b-104">This drillthrough link enables a drillthrough action.</span></span>  
  
 <span data-ttu-id="e258b-105">Les rapports d'extraction doivent être publiés sur le même serveur de rapports que le rapport principal, mais pas nécessairement dans le même dossier.</span><span class="sxs-lookup"><span data-stu-id="e258b-105">Drillthrough reports must be published to the same report server as the main report, but they can be in different folders.</span></span> <span data-ttu-id="e258b-106">Vous pouvez ajouter un lien d’extraction à tout élément disposant d’une propriété **Action** , tel qu’une zone de texte, une image ou des points de données dans un graphique.</span><span class="sxs-lookup"><span data-stu-id="e258b-106">You can add a drillthrough link to any item that has an **Action** property, such as a text box, an image, or data points on a chart.</span></span>  
  
 <span data-ttu-id="e258b-107">Pour ajouter un lien d'extraction à un rapport, vous devez d'abord créer le rapport d'extraction auquel le rapport principal sera lié.</span><span class="sxs-lookup"><span data-stu-id="e258b-107">To add a drillthrough link to a report, you must first create the drillthrough report that the main report will link to.</span></span> <span data-ttu-id="e258b-108">Un rapport d'extraction comporte généralement les détails relatifs à un élément contenu dans le rapport de synthèse d'origine ; en outre, il comporte souvent des paramètres qui filtrent le rapport d'extraction en fonction de paramètres qui lui sont passés à partir du rapport principal.</span><span class="sxs-lookup"><span data-stu-id="e258b-108">A drillthrough report commonly contains details about an item that is contained in the original summary report, and often contains parameters that filter the drillthrough report based on parameters passed to it from the main report.</span></span> <span data-ttu-id="e258b-109">Pour plus d’informations sur la création du rapport d’extraction, consultez [Rapports d’extraction &#40;Générateur de rapports et SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e258b-109">For more information on creating the drillthrough report, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a><span data-ttu-id="e258b-110">Pour ajouter une action d'extraction</span><span class="sxs-lookup"><span data-stu-id="e258b-110">To add a drillthrough action</span></span>  
  
1.  <span data-ttu-id="e258b-111">En mode Conception, cliquez avec le bouton droit sur la zone de texte, l’image ou le graphique auquel vous voulez ajouter un lien, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e258b-111">In Design view, right-click the text box, image, or chart to which you want to add a link and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e258b-112">Dans la boîte de dialogue **Propriétés** de l’élément, cliquez sur **Action**.</span><span class="sxs-lookup"><span data-stu-id="e258b-112">In the item's **Properties** dialog box, click **Action**.</span></span>  
  
3.  <span data-ttu-id="e258b-113">Sélectionnez **Atteindre le rapport**.</span><span class="sxs-lookup"><span data-stu-id="e258b-113">Select **Go to report**.</span></span> <span data-ttu-id="e258b-114">Des sections supplémentaires apparaissent dans la boîte de dialogue pour cette option.</span><span class="sxs-lookup"><span data-stu-id="e258b-114">Additional sections appear in the dialog box for this option.</span></span>  
  
4.  <span data-ttu-id="e258b-115">Dans **Spécifier un rapport**, cliquez sur **Parcourir** pour localiser le rapport auquel vous souhaitez accéder, ou tapez le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="e258b-115">In **Specify a report**, click **Browse** to locate the report that you want to jump to, or type the name of the report.</span></span> <span data-ttu-id="e258b-116">Vous pouvez également cliquer sur le bouton d’expression (**fx**) pour créer une expression pour le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="e258b-116">Alternatively, click the expression (**fx**) button to create an expression for the report name.</span></span>  
  
     <span data-ttu-id="e258b-117">Le chemin d'accès au rapport d'extraction présente un format différent selon que vous êtes en mode natif ou en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e258b-117">The format of the path to the drillthrough report differs for native and SharePoint integrated mode.</span></span> <span data-ttu-id="e258b-118">Si vous utilisez la fonctionnalité Parcourir pour accéder au rapport, un chemin d'accès au format approprié est fourni.</span><span class="sxs-lookup"><span data-stu-id="e258b-118">If you browse to the report, a path of the correct format is provided.</span></span> <span data-ttu-id="e258b-119">Pour plus d’informations, consultez [Spécification de chemins d’accès à des éléments externes &#40;Générateur de rapports et SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e258b-119">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
     <span data-ttu-id="e258b-120">Si vous devez spécifier des paramètres pour le rapport d'extraction, effectuez l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="e258b-120">If you have to specify parameters for the drillthrough report, follow the next step.</span></span>  
  
5.  <span data-ttu-id="e258b-121">Dans **Utiliser ces paramètres pour exécuter le rapport**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e258b-121">In **Use these parameters to run the report**, click **Add**.</span></span> <span data-ttu-id="e258b-122">Une nouvelle ligne est ajoutée à la grille des paramètres.</span><span class="sxs-lookup"><span data-stu-id="e258b-122">A new row is added to the parameter grid.</span></span>  
  
    -   <span data-ttu-id="e258b-123">Dans la zone de texte **Nom** , cliquez sur la liste déroulante ou tapez le nom du paramètre de rapport dans le rapport d’extraction.</span><span class="sxs-lookup"><span data-stu-id="e258b-123">In the **Name** text box, click the drop-down list or type the name of the report parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e258b-124">Les noms dans la liste des paramètres doivent correspondre de façon exacte aux paramètres du rapport cible.</span><span class="sxs-lookup"><span data-stu-id="e258b-124">The names in the parameter list must match the expected parameters in the target report exactly.</span></span> <span data-ttu-id="e258b-125">Par exemple, les noms de paramètres doivent avoir une casse identique.</span><span class="sxs-lookup"><span data-stu-id="e258b-125">For example, parameter names must match by case.</span></span> <span data-ttu-id="e258b-126">Si les noms ne correspondent pas ou si un paramètre attendu ne figure pas dans la liste, la génération du rapport d'extraction échoue.</span><span class="sxs-lookup"><span data-stu-id="e258b-126">If the names do not match, or if an expected parameter is not listed, the drillthrough report fails.</span></span>  
  
    -   <span data-ttu-id="e258b-127">Dans **Valeur**, tapez ou sélectionnez la valeur à transmettre au paramètre dans le rapport d’extraction.</span><span class="sxs-lookup"><span data-stu-id="e258b-127">In **Value**, type or select the value to pass to the parameter in the drillthrough report.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="e258b-128">Ces valeurs peuvent contenir une expression qui correspond à une valeur à passer au paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="e258b-128">Values can contain an expression that evaluates to a value to pass to the report parameter.</span></span> <span data-ttu-id="e258b-129">Les expressions de la liste de valeurs incluent la liste des champs du rapport en cours.</span><span class="sxs-lookup"><span data-stu-id="e258b-129">The expressions in the value list include the field list for the current report.</span></span>  
  
     <span data-ttu-id="e258b-130">Pour plus d’informations sur la façon de masquer des paramètres dans les rapports, consultez [Ajouter, modifier ou supprimer un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e258b-130">For information on how to hide parameters in reports, see [Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="e258b-131">(Facultatif) Pour les zones de texte, il est judicieux d’indiquer à l’utilisateur que le texte est un lien en changeant la couleur et l’effet du texte sous l’onglet **Accueil** du ruban.</span><span class="sxs-lookup"><span data-stu-id="e258b-131">(Optional) For text boxes, it is helpful to indicate to the user that the text is a link by changing the color and effect of the text on the **Home** tab of the Ribbon.</span></span>  
  
7.  <span data-ttu-id="e258b-132">Pour tester le lien, exécutez le rapport et cliquez sur l'élément de rapport sur lequel vous avez défini ce lien.</span><span class="sxs-lookup"><span data-stu-id="e258b-132">To test the link, run the report and click the report item that you set this link on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e258b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e258b-133">See Also</span></span>  
 <span data-ttu-id="e258b-134">[Boîte de dialogue Propriétés relatives aux actions &#40;Générateur de rapports et SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e258b-134">[Action Properties Dialog Box &#40;Report Builder and SSRS&#41;](../action-properties-dialog-box-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e258b-135">[Mise en forme des points de données sur un graphique &#40;Générateur de rapports et SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e258b-135">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e258b-136">Afficher des info-bulles dans une série &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e258b-136">Show ToolTips on a Series &#40;Report Builder and SSRS&#41;</span></span>](show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
