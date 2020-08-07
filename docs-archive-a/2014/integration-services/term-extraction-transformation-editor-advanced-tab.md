---
title: Éditeur de transformation d’extraction de terme (onglet Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703120"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="2ef2f-102">Éditeur de transformation d'extraction de terme (onglet Avancé)</span><span class="sxs-lookup"><span data-stu-id="2ef2f-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="2ef2f-103">Utilisez l’onglet **Avancé** de la boîte de dialogue **Éditeur de transformation d’extraction de terme** pour définir les propriétés de l’extraction, telles que la fréquence et la longueur, et indiquer si les mots ou les phrases doivent être extraits.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="2ef2f-104">Pour en savoir plus sur la transformation d'extraction de terme, consultez [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2ef2f-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ef2f-105">Options</span><span class="sxs-lookup"><span data-stu-id="2ef2f-105">Options</span></span>  
 <span data-ttu-id="2ef2f-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-106">**Noun**</span></span>  
 <span data-ttu-id="2ef2f-107">Indique que la transformation extrait uniquement des noms individuels.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="2ef2f-108">**Expression nominale**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-108">**Noun phrase**</span></span>  
 <span data-ttu-id="2ef2f-109">Indique que la transformation extrait uniquement des expressions nominales.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="2ef2f-110">**Nom et expression nominale**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="2ef2f-111">Indique que la transformation extrait des noms et des expressions nominales.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="2ef2f-112">**Fréquence**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-112">**Frequency**</span></span>  
 <span data-ttu-id="2ef2f-113">Indique que le score correspond à la fréquence du terme.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="2ef2f-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-114">**TFIDF**</span></span>  
 <span data-ttu-id="2ef2f-115">Indique que le score correspond à la valeur TFIDF du terme.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="2ef2f-116">Le score TFIDF est le produit de la fréquence des termes (TF, Term Frequency) et de la fréquence inverse de documents (IDF, Inverse Document Frequency), défini comme suit : TFIDF d’un terme T = (fréquence de T) \* log((#lignes en entrée) / (#lignes ayant T))</span><span class="sxs-lookup"><span data-stu-id="2ef2f-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="2ef2f-117">**Seuil de fréquence**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="2ef2f-118">Définissez le nombre d'occurrences d'un mot ou d'une expression avant son extraction.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="2ef2f-119">La valeur par défaut est 2.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="2ef2f-120">**Longueur maximale du terme**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="2ef2f-121">Définissez la longueur maximale d'une expression en nombre de mots.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="2ef2f-122">Cette option affecte uniquement les expressions nominales.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-122">This option affects noun phrases only.</span></span> <span data-ttu-id="2ef2f-123">La valeur par défaut est 12.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="2ef2f-124">**Utiliser l'extraction de terme respectant la casse**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="2ef2f-125">Indiquez si l'extraction doit respecter la casse.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="2ef2f-126">Par défaut, il s’agit de `False`.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="2ef2f-127">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="2ef2f-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="2ef2f-128">Utilisez la boîte de dialogue [Configurer l’affichage des erreurs](../../2014/integration-services/configure-error-output.md) pour spécifier la gestion des erreurs dans les lignes qui provoquent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="2ef2f-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef2f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ef2f-129">See Also</span></span>  
 <span data-ttu-id="2ef2f-130">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2ef2f-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2ef2f-131">[Éditeur de transformation d’extraction de terme &#40;onglet extraction de terme&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2ef2f-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="2ef2f-132">[Éditeur de transformation d’extraction de terme &#40;onglet exclusion&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2ef2f-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="2ef2f-133">Transformation de recherche de terme</span><span class="sxs-lookup"><span data-stu-id="2ef2f-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
