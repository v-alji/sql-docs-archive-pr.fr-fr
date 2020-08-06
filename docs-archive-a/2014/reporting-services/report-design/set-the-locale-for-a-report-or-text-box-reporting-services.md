---
title: Définir les paramètres régionaux d’un rapport ou d’une zone de texte (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601887"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="b2fb4-102">Définir les paramètres régionaux d'un rapport ou d'une zone de texte (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="b2fb4-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="b2fb4-103">La propriété **Language** d'un rapport ou d'une zone de texte contient les paramètres régionaux, qui déterminent les formats par défaut d'affichage des données de rapport qui varient selon la langue et la région géographique, comme la date, la monnaie ou les valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="b2fb4-104">La propriété **Language** d'une zone de texte substitue la propriété **Language** du rapport.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="b2fb4-105">Si aucune valeur n'est spécifiée pour **Language**, Reporting Services utilise les paramètres régionaux du système d'exploitation du serveur de rapports pour les rapports publiés ou de l'ordinateur qui a servi à créer les rapports pour en afficher l'aperçu.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="b2fb4-106">Pour les rapports HTML, vous pouvez remplacer la valeur **Language** par défaut par la langue spécifiée dans l’en-tête HTTP du client du navigateur en utilisant le champ prédéfini User!Language dans une expression pour la propriété **Language** d’un rapport ou d’une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="b2fb4-107">Vous pouvez également spécifier la propriété **Language** d'un rapport dans une URL.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="b2fb4-108">Pour plus d’informations, consultez [Définir la langue des paramètres de rapport dans une URL](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="b2fb4-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="b2fb4-109">Pour définir les paramètres régionaux d'un rapport</span><span class="sxs-lookup"><span data-stu-id="b2fb4-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="b2fb4-110">En mode Conception, cliquez à l'extérieur de l'aire de conception du rapport pour sélectionner le rapport.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="b2fb4-111">Dans le volet Propriétés, pour la propriété **Language** , tapez ou sélectionnez la langue à utiliser pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="b2fb4-112">Pour définir les paramètres régionaux d'une zone de texte</span><span class="sxs-lookup"><span data-stu-id="b2fb4-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="b2fb4-113">En mode Conception, sélectionnez la zone de texte à laquelle vous souhaitez appliquer les paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="b2fb4-114">Dans le volet Propriétés, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2fb4-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="b2fb4-115">Pour la propriété **Calendar** , tapez ou sélectionnez le calendrier que vous souhaitez utiliser pour les dates.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="b2fb4-116">Pour la propriété **Direction** , tapez ou sélectionnez la direction dans laquelle le texte doit être écrit.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="b2fb4-117">Pour la propriété **Language** , tapez ou sélectionnez la langue que vous souhaitez affecter à la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="b2fb4-118">Cette valeur substitue la propriété **Language** du rapport.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="b2fb4-119">Pour la propriété **NumeralLanguage** , tapez ou sélectionnez le format à utiliser pour les nombres dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="b2fb4-120">Pour la propriété **NumeralVariant** , tapez ou sélectionnez la variante du format à utiliser pour les nombres dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="b2fb4-121">Pour la propriété **UnicodeBiDi** , sélectionnez le niveau d'incorporation bidirectionnelle à appliquer à la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="b2fb4-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fb4-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2fb4-122">See Also</span></span>  
 [<span data-ttu-id="b2fb4-123">Utilisation d’expressions dans les rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b2fb4-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
