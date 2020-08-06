---
title: Importation de code HTML dans un rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dd0410ea-8839-4e8c-9944-8cdfe5465591
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f978e67c67556184012db6b809e4f5754f2374c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697535"
---
# <a name="importing-html-into-a-report-report-builder-and-ssrs"></a><span data-ttu-id="04d42-102">Importation de données HTML dans un rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="04d42-102">Importing HTML into a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="04d42-103">Vous pouvez utiliser une zone de texte pour insérer dans un rapport du texte au format HTML récupéré à partir de l'un des champs de votre dataset.</span><span class="sxs-lookup"><span data-stu-id="04d42-103">You can use a text box to insert HTML-formatted text that you have retrieved from a field in your dataset into a report.</span></span> <span data-ttu-id="04d42-104">Ce texte au format HTML peut être issu de toute expression simple ou complexe capable de transformer correctement des données au format HTML.</span><span class="sxs-lookup"><span data-stu-id="04d42-104">The text can come from any simple or complex expression that evaluates to correctly formatted HTML.</span></span> <span data-ttu-id="04d42-105">Le texte ainsi mis en forme peut être converti dans tous les formats de sortie pris en charge, y compris au format PDF.</span><span class="sxs-lookup"><span data-stu-id="04d42-105">Formatted text can be rendered to all supported output formats, including PDF.</span></span>  
  
 <span data-ttu-id="04d42-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span><span class="sxs-lookup"><span data-stu-id="04d42-106">![rs_HTMLFormatting](../media/rs-htmlformatting.gif "rs_HTMLFormatting")</span></span>  
  
 <span data-ttu-id="04d42-107">Cette illustration montre le texte au format HTML en mode création de rapport, ainsi que le rendu de ce même texte lors de l'exécution du rapport.</span><span class="sxs-lookup"><span data-stu-id="04d42-107">This illustration shows text with HTML formatting in report design view, and the same text as it is rendered when the report is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04d42-108">Lorsque vous importez du texte qui contient des balises HTML, les données de ce texte doivent toujours être analysées en premier par la zone de texte où elles sont importées.</span><span class="sxs-lookup"><span data-stu-id="04d42-108">When you import text that contains HTML markup, the data must always be parsed by the text box first.</span></span> <span data-ttu-id="04d42-109">Seul un sous-ensemble de balises HTML étant pris en charge, les données HTML affichées dans le rapport rendu peuvent différer des données HTML d'origine.</span><span class="sxs-lookup"><span data-stu-id="04d42-109">Because only a subset of HTML tags is supported, the HTML that is shown in the rendered report may differ from your original HTML.</span></span>  
  
 <span data-ttu-id="04d42-110">Pour une prise en main rapide, consultez [Didacticiel : mettre en forme du texte &#40;Générateur de rapports&#41;](../tutorial-format-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="04d42-110">To quickly get started, see [Tutorial: Format Text &#40;Report Builder&#41;](../tutorial-format-text-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="supported-html-tags"></a><span data-ttu-id="04d42-111">Balises HTML prises en charge</span><span class="sxs-lookup"><span data-stu-id="04d42-111">Supported HTML Tags</span></span>  
 <span data-ttu-id="04d42-112">La liste suivante répertorie toutes les balises qui seront restituées sous forme de balises HTML lorsque définies comme texte de l'espace réservé :</span><span class="sxs-lookup"><span data-stu-id="04d42-112">The following is a complete list of tags that will render as HTML when defined as placeholder text:</span></span>  
  
-   <span data-ttu-id="04d42-113">Éléments d’en-tête, de style et de bloc : \<H{n}> , \<DIV> ,, \<SPAN> \<P> ,\<LI></span><span class="sxs-lookup"><span data-stu-id="04d42-113">Header, style and block elements: \<H{n}>, \<DIV>, \<SPAN>,\<P>, \<LI></span></span>  
  
 <span data-ttu-id="04d42-114">Toutes les autres balises HTML ne seront pas prises en compte lorsque le rapport sera généré.</span><span class="sxs-lookup"><span data-stu-id="04d42-114">Any other HTML markup tags will be ignored during report processing.</span></span> <span data-ttu-id="04d42-115">Si le texte au format HTML de l'espace réservé représenté par son expression comporte des erreurs de langage, il apparaîtra au format texte simple.</span><span class="sxs-lookup"><span data-stu-id="04d42-115">If the HTML represented by the expression in the placeholder text is not well formed, the placeholder is rendered as plain text.</span></span> <span data-ttu-id="04d42-116">Aucune des balises HTML n'est sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="04d42-116">All HTML tags are case-insensitive.</span></span>  
  
 <span data-ttu-id="04d42-117">Si le texte de votre zone de texte contient uniquement un bloc de texte, toutes les données HTML de l'espace réservé définissant des éléments de bloc seront correctement restituées.</span><span class="sxs-lookup"><span data-stu-id="04d42-117">If the text in your text box contains only one block of text, any HTML in the placeholder that defines block elements will render correctly.</span></span> <span data-ttu-id="04d42-118">Toutefois, si cette zone de texte contient plusieurs blocs de texte, les balises HTML seront ignorées et la structure du texte sera définie en fonction des blocs de texte.</span><span class="sxs-lookup"><span data-stu-id="04d42-118">However, if the text box has multiple blocks of text, the HTML tags are ignored and the structure of the text is defined by the blocks of text.</span></span>  
  
 <span data-ttu-id="04d42-119">Si plusieurs balises HTML sont définies pour le texte et que [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] détecte un conflit entre ces balises et les contraintes actuellement définies pour les rapports, seule la balise HTML la plus intérieure est traitée comme du code HTML.</span><span class="sxs-lookup"><span data-stu-id="04d42-119">If more than one tag is defined for text, and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] detects a conflict between the HTML and existing report constraints, only the innermost HTML tag will be treated as HTML.</span></span>  
  
 <span data-ttu-id="04d42-120">Quand vous utilisez les balises de gestion de liste, la police et le style de toutes les puces et les préfixes de numéro sont définis sur Arial noir.</span><span class="sxs-lookup"><span data-stu-id="04d42-120">When using the list handling tags, the font and style of all bullets and number prefixes will be fixed to Arial black.</span></span>  
  
 <span data-ttu-id="04d42-121">Pour plus d’informations, consultez [Ajouter du code HTML à un rapport &#40;Générateur de rapports et SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="04d42-121">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
## <a name="limitations-of-cascading-style-sheet-attributes"></a><span data-ttu-id="04d42-122">Limites des attributs de feuille de style en cascade</span><span class="sxs-lookup"><span data-stu-id="04d42-122">Limitations of Cascading Style Sheet Attributes</span></span>  
 <span data-ttu-id="04d42-123">Lors de l'utilisation d'attributs de feuille de style en cascade (CSS), seul un jeu principal de balises est défini.</span><span class="sxs-lookup"><span data-stu-id="04d42-123">When using cascading style sheet (CSS) attributes, only a basic set of tags are defined.</span></span> <span data-ttu-id="04d42-124">La liste suivante répertorie les attributs pris en charge :</span><span class="sxs-lookup"><span data-stu-id="04d42-124">The following is a list of attributes that are supported:</span></span>  
  
-   <span data-ttu-id="04d42-125">text-align, text-indent</span><span class="sxs-lookup"><span data-stu-id="04d42-125">text-align, text-indent</span></span>  
  
-   <span data-ttu-id="04d42-126">font-family</span><span class="sxs-lookup"><span data-stu-id="04d42-126">font-family</span></span>  
  
-   <span data-ttu-id="04d42-127">font-size</span><span class="sxs-lookup"><span data-stu-id="04d42-127">font-size</span></span>  
  
    -   <span data-ttu-id="04d42-128">Seules les valeurs de taille RDL valides, en unités de longueur CSS absolues sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="04d42-128">Only valid RDL size values, in absolute CSS length units are supported.</span></span> <span data-ttu-id="04d42-129">Les unités prises en charge sont in, cm, mm, pt et pc.</span><span class="sxs-lookup"><span data-stu-id="04d42-129">Supported units are: in, cm, mm, pt, pc.</span></span>  
  
    -   <span data-ttu-id="04d42-130">Les unités de longueur CSS relatives sont ignorées et ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="04d42-130">Relative CSS length units are ignored and not supported.</span></span> <span data-ttu-id="04d42-131">Les unités non prises en charge sont em, ex, px, %, rem.</span><span class="sxs-lookup"><span data-stu-id="04d42-131">Unsupported units include em, ex, px,%,rem.</span></span>  
  
-   <span data-ttu-id="04d42-132">color</span><span class="sxs-lookup"><span data-stu-id="04d42-132">color</span></span>  
  
-   <span data-ttu-id="04d42-133">padding, padding-bottom, padding-top, padding-right, padding-left</span><span class="sxs-lookup"><span data-stu-id="04d42-133">padding, padding-bottom, padding-top, padding-right, padding-left</span></span>  
  
-   <span data-ttu-id="04d42-134">font-weight</span><span class="sxs-lookup"><span data-stu-id="04d42-134">font-weight</span></span>  
  
 <span data-ttu-id="04d42-135">Voici quelques-uns des points à considérer lorsque vous utilisez des feuilles de style CSS :</span><span class="sxs-lookup"><span data-stu-id="04d42-135">Here are some considerations for using CSS:</span></span>  
  
-   <span data-ttu-id="04d42-136">À l'instar des balises HTML erronées, les valeurs CSS incorrectes sont également ignorées.</span><span class="sxs-lookup"><span data-stu-id="04d42-136">Malformed CSS values are ignored in the same way as malformed HTML.</span></span>  
  
-   <span data-ttu-id="04d42-137">Lorsque des attributs de style CSS coexistent avec un attribut standard dans une même balise, la propriété CSS est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="04d42-137">When both attribute and CSS style attributes exist in the same tag, the CSS property has a higher precedence.</span></span> <span data-ttu-id="04d42-138">Par exemple, si votre texte est **\<p style="text-align: right" align="left">** , seul l’attribut text-align est appliqué et le texte est aligné à droite.</span><span class="sxs-lookup"><span data-stu-id="04d42-138">For example, if your text is **\<p style="text-align: right" align="left">**, only the text-align attribute will be applied and the text will be right-aligned.</span></span>  
  
-   <span data-ttu-id="04d42-139">Dans le cadre des styles CSS et des attributs, lorsqu'une propriété est spécifiée à plusieurs reprises, seule la dernière instance spécifiée est prise en compte et appliquée.</span><span class="sxs-lookup"><span data-stu-id="04d42-139">For attributes and CSS styles, if a property is specified more than once, only the last instance of the property is applied.</span></span> <span data-ttu-id="04d42-140">Par exemple, si votre texte est **\<p align="left" align="right">** , le texte sera aligné à droite.</span><span class="sxs-lookup"><span data-stu-id="04d42-140">For example, if your text is **\<p align="left" align="right">**, the text will be right-aligned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d42-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04d42-141">See Also</span></span>  
 [<span data-ttu-id="04d42-142">Rendu au format HTML &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="04d42-142">Rendering to HTML &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/rendering-to-html-report-builder-and-ssrs.md)  
  
  
