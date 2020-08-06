---
title: Éditeur de transformation de recherche floue (onglet Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696991"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a><span data-ttu-id="5bd24-102">Éditeur de transformation de recherche floue (onglet Avancé)</span><span class="sxs-lookup"><span data-stu-id="5bd24-102">Fuzzy Lookup Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="5bd24-103">Utilisez l’onglet **Avancé** de la boîte de dialogue **Éditeur de transformation de recherche floue** pour définir les paramètres relatifs à une recherche floue.</span><span class="sxs-lookup"><span data-stu-id="5bd24-103">Use the **Advanced** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set parameters for the fuzzy lookup.</span></span>  
  
 <span data-ttu-id="5bd24-104">Pour en savoir plus sur la transformation de recherche floue, consultez [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="5bd24-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5bd24-105">Options</span><span class="sxs-lookup"><span data-stu-id="5bd24-105">Options</span></span>  
 <span data-ttu-id="5bd24-106">**Correspondances maximales à afficher par recherche**</span><span class="sxs-lookup"><span data-stu-id="5bd24-106">**Maximum number of matches to output per lookup**</span></span>  
 <span data-ttu-id="5bd24-107">Indiquez le nombre maximal de correspondances que la transformation peut retourner pour chaque ligne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="5bd24-107">Specify the maximum number of matches the transformation can return for each input row.</span></span> <span data-ttu-id="5bd24-108">La valeur par défaut est **1**.</span><span class="sxs-lookup"><span data-stu-id="5bd24-108">The default is **1**.</span></span>  
  
 <span data-ttu-id="5bd24-109">**Seuil de similarité**</span><span class="sxs-lookup"><span data-stu-id="5bd24-109">**Similarity threshold**</span></span>  
 <span data-ttu-id="5bd24-110">Définissez le seuil de similarité au niveau du composant à l'aide du curseur.</span><span class="sxs-lookup"><span data-stu-id="5bd24-110">Set the similarity threshold at the component level by using the slider.</span></span> <span data-ttu-id="5bd24-111">Plus la valeur est proche de 1, plus la valeur de recherche doit être proche de la valeur source pour constituer une correspondance.</span><span class="sxs-lookup"><span data-stu-id="5bd24-111">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="5bd24-112">Si vous augmentez le seuil, vous pouvez améliorer la vitesse de correspondance étant donné qu'un plus petit nombre d'enregistrements candidats doit être pris en compte.</span><span class="sxs-lookup"><span data-stu-id="5bd24-112">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="5bd24-113">**Séparateurs de jetons**</span><span class="sxs-lookup"><span data-stu-id="5bd24-113">**Token delimiters**</span></span>  
 <span data-ttu-id="5bd24-114">Indiquez les séparateurs utilisés par la transformation pour marquer les valeurs de colonne.</span><span class="sxs-lookup"><span data-stu-id="5bd24-114">Specify the delimiters that the transformation uses to tokenize column values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd24-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5bd24-115">See Also</span></span>  
 <span data-ttu-id="5bd24-116">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5bd24-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5bd24-117">[Éditeur de transformation de recherche floue &#40;onglet de la table de référence&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="5bd24-117">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="5bd24-118">Éditeur de transformation de recherche floue &#40;onglet Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="5bd24-118">Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
