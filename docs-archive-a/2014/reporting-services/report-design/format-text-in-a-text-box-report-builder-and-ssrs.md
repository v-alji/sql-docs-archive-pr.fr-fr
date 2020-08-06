---
title: Mettre en forme du texte dans une zone de texte (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: df0794b5-96b0-4034-bd17-1be7f31e29db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 522bc420f77b2e5e9d2163c28d3d688b7c47883c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603835"
---
# <a name="format-text-in-a-text-box-report-builder-and-ssrs"></a><span data-ttu-id="50dd7-102">Mettre en forme du texte dans une zone de texte (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="50dd7-102">Format Text in a Text Box (Report Builder and SSRS)</span></span>
  <span data-ttu-id="50dd7-103">Vous pouvez mettre en forme indépendamment toute partie du texte dans une zone de texte, et mélanger le texte de l'espace réservé à du texte statique dans une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="50dd7-103">You can format any part of the text within a text box independently, and mix placeholder text and static text in one text box.</span></span> <span data-ttu-id="50dd7-104">Cette possibilité de mélanger les formats et d'ajouter le texte d'espace réservé vous permet de créer des publipostages ou des modèles de texte dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="50dd7-104">This ability to mix formats and add placeholder text enables you to create mail merges or templates for text in your report.</span></span> <span data-ttu-id="50dd7-105">Toute expression peut être définie et mise en forme séparément à l'aide d'un espace réservé.</span><span class="sxs-lookup"><span data-stu-id="50dd7-105">Any expression can be defined and formatted separately using a placeholder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-combine-multiple-formats-in-a-text-box"></a><span data-ttu-id="50dd7-106">Pour associer plusieurs formats dans une zone de texte</span><span class="sxs-lookup"><span data-stu-id="50dd7-106">To combine multiple formats in a text box</span></span>  
  
1.  <span data-ttu-id="50dd7-107">Sous l'onglet **Insérer** , cliquez sur **Zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-107">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="50dd7-108">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue.</span><span class="sxs-lookup"><span data-stu-id="50dd7-108">Click the design surface, and then drag to create a box that is the size you want.</span></span>  
  
2.  <span data-ttu-id="50dd7-109">Dans la zone de texte, sélectionnez le texte à mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="50dd7-109">Inside the text box, select the text you want to format.</span></span>  
  
3.  <span data-ttu-id="50dd7-110">Cliquez avec le bouton droit sur le texte sélectionné, puis cliquez sur **Propriétés du texte**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-110">Right-click the selected text, and click **Text Properties**.</span></span>  
  
4.  <span data-ttu-id="50dd7-111">Définissez les options de mise en forme.</span><span class="sxs-lookup"><span data-stu-id="50dd7-111">Set formatting options.</span></span> <span data-ttu-id="50dd7-112">Par exemple, sous l’onglet **Général** :</span><span class="sxs-lookup"><span data-stu-id="50dd7-112">For example, on the **General** tab:</span></span>  
  
    -   <span data-ttu-id="50dd7-113">**Info-bulle** Tapez du texte ou une expression qui se transforme en info-bulle.</span><span class="sxs-lookup"><span data-stu-id="50dd7-113">**Tooltip** Type text or an expression that evaluates to a ToolTip.</span></span> <span data-ttu-id="50dd7-114">L'info-bulle apparaît lorsque l'utilisateur place le pointeur sur l'élément dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="50dd7-114">The ToolTip appears when the user pauses the pointer over the item in a report</span></span>  
  
    -   <span data-ttu-id="50dd7-115">**Type de balise** Sélectionnez une option pour indiquer de quelle façon rendre le texte sélectionné :</span><span class="sxs-lookup"><span data-stu-id="50dd7-115">**Markup type** Select an option to indicate how the selected text will be rendered:</span></span>  
  
         <span data-ttu-id="50dd7-116">**Texte brut** Affichez le texte sélectionné au format texte simple.</span><span class="sxs-lookup"><span data-stu-id="50dd7-116">**Plain Text** Display the selected text as simple text.</span></span> <span data-ttu-id="50dd7-117">Le format HTML sera traité comme texte littéral.</span><span class="sxs-lookup"><span data-stu-id="50dd7-117">HTML will be treated as literal text.</span></span>  
  
         <span data-ttu-id="50dd7-118">**HTML**  Affichez le texte sélectionné au format HTML.</span><span class="sxs-lookup"><span data-stu-id="50dd7-118">**HTML**  Display the selected text as HTML.</span></span> <span data-ttu-id="50dd7-119">Si la valeur d'expression de l'espace réservé contient des balises HTML valides, ces balises seront rendues au format HTML.</span><span class="sxs-lookup"><span data-stu-id="50dd7-119">If the expression value of the placeholder contains valid HTML tags, these tags will be rendered as HTML.</span></span> <span data-ttu-id="50dd7-120">Pour plus d’informations, consultez [Importation de données HTML dans un rapport &#40;Générateur de rapports et SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="50dd7-120">For more information, see [Importing HTML into a Report &#40;Report Builder and SSRS&#41;](importing-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
5.  <span data-ttu-id="50dd7-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-121">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="50dd7-122">Répétez les étapes 2 à 5 pour tout texte supplémentaire que vous souhaitez mettre en forme.</span><span class="sxs-lookup"><span data-stu-id="50dd7-122">Repeat steps 2 through 5 for the remaining text you want to format.</span></span>  
  
### <a name="to-format-text-and-placeholders-differently-in-the-same-text-box"></a><span data-ttu-id="50dd7-123">Pour mettre en forme différemment texte et espaces réservés dans la même zone de texte</span><span class="sxs-lookup"><span data-stu-id="50dd7-123">To format text and placeholders differently in the same text box</span></span>  
  
1.  <span data-ttu-id="50dd7-124">Sous l’onglet **Insérer** , cliquez sur **Liste**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-124">On the **Insert** tab, click **List**.</span></span> <span data-ttu-id="50dd7-125">Cliquez sur l'aire de conception, puis faites glisser la souris pour créer une zone de la taille voulue.</span><span class="sxs-lookup"><span data-stu-id="50dd7-125">Click the design surface, and then drag to create a box that is the size you want.</span></span> <span data-ttu-id="50dd7-126">La boîte de dialogue **Propriétés du dataset** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="50dd7-126">The **Dataset Properties** dialog box opens.</span></span> <span data-ttu-id="50dd7-127">Vous pouvez utiliser un dataset partagé ou un dataset incorporé dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="50dd7-127">You can use a shared dataset or a dataset embedded in your report.</span></span> <span data-ttu-id="50dd7-128">Pour plus d’informations, cliquez sur [Boîte de dialogue Propriétés du dataset, Requête &#40;Générateur de rapports&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) ou [Boîte de dialogue Propriétés du dataset, Requête](../dataset-properties-dialog-box-query.md).</span><span class="sxs-lookup"><span data-stu-id="50dd7-128">For more information, click [Dataset Properties Dialog Box, Query &#40;Report Builder&#41;](../report-data/dataset-properties-dialog-box-query-report-builder.md) or [Dataset Properties Dialog Box, Query](../dataset-properties-dialog-box-query.md).</span></span>  
  
2.  <span data-ttu-id="50dd7-129">Sous l'onglet **Insérer** , cliquez sur **Zone de texte**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-129">On the **Insert** tab, click **Text Box**.</span></span> <span data-ttu-id="50dd7-130">Cliquez dans la liste, puis faites glisser la souris pour créer une zone de la taille voulue.</span><span class="sxs-lookup"><span data-stu-id="50dd7-130">Click in the list, and then drag to create a box that is the size you want.</span></span>  
  
3.  <span data-ttu-id="50dd7-131">Tapez une étiquette dans la zone de texte, par exemple, **Mon champ** :.</span><span class="sxs-lookup"><span data-stu-id="50dd7-131">Type a label in the text box - for example, **My Field**:.</span></span>  
  
4.  <span data-ttu-id="50dd7-132">Faites glisser un champ de votre dataset dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="50dd7-132">Drag a field from your dataset into the text box.</span></span> <span data-ttu-id="50dd7-133">Un espace réservé est créé pour votre champ.</span><span class="sxs-lookup"><span data-stu-id="50dd7-133">A placeholder is created for your field.</span></span>  
  
5.  <span data-ttu-id="50dd7-134">Pour appliquer une mise en forme simple, sélectionnez le texte de l’espace réservé, puis cliquez sur l’une des options de mise en forme dans le groupe **Police** sous l’onglet **Accueil** . Par exemple, cliquez sur le bouton **Gras**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-134">For basic formatting, select the placeholder text and then click one of the formatting options in the **Font** group on the **Home** tab. For example, click the **Bold** button.</span></span>  
  
     <span data-ttu-id="50dd7-135">Pour afficher davantage d’options de mise en forme, cliquez avec le bouton droit sur le texte de l’espace réservé, puis cliquez sur **Propriétés de l’espace réservé**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-135">For more formatting options, right-click the placeholder text, and then click **Placeholder Properties**.</span></span>  
  
6.  <span data-ttu-id="50dd7-136">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-136">Click **OK**.</span></span> <span data-ttu-id="50dd7-137">En mode création de rapport, la zone de texte doit contenir «**Mon champ**: [*NomChamp*] », *NomChamp* étant le nom de votre champ.</span><span class="sxs-lookup"><span data-stu-id="50dd7-137">In report design view, the text box should contain "**My Field**: [*FieldName*]", where *FieldName* is the name of your field.</span></span>  
  
7.  <span data-ttu-id="50dd7-138">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="50dd7-138">Click **Run**.</span></span>  
  
 <span data-ttu-id="50dd7-139">La liste se répète une fois pour chaque valeur du champ, et l’espace réservé *NomChamp* est automatiquement remplacé par la valeur de ce champ dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="50dd7-139">The list repeats one time for every value in the field, and the *FieldName* placeholder is replaced each time by the value of that field in the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50dd7-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50dd7-140">See Also</span></span>  
 <span data-ttu-id="50dd7-141">[Zones de texte &#40;Générateur de rapport et SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-141">[Text Boxes &#40;Report Builder and SSRS&#41;](text-boxes-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-142">[Mise en forme du texte et des espaces réservés &#40;Générateur de rapports et SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-142">[Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-143">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-143">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-144">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-144">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-145">[Ajouter du code HTML à un rapport &#40;Générateur de rapports et SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-145">[Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-146">[Répertorie &#40;Générateur de rapports et SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-146">[Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="50dd7-147">[Mise en forme des nombres et des dates &#40;Générateur de rapports et SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50dd7-147">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="50dd7-148">Boîte de dialogue Propriétés de l’espace réservé, Général &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="50dd7-148">Placeholder Properties Dialog Box, General &#40;Report Builder and SSRS&#41;</span></span>](../placeholder-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  
