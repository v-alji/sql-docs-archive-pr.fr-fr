---
title: Éditeur de transformation de regroupement probable (onglet Avancé) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602890"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="556de-102">Éditeur de transformation de regroupement probable (onglet Avancé).</span><span class="sxs-lookup"><span data-stu-id="556de-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="556de-103">Utilisez l'onglet **Avancé** de la boîte de dialogue **Éditeur de transformation de regroupement probable** pour spécifier les colonnes d'entrée et de sortie, définir des seuils de similarité et des séparateurs.</span><span class="sxs-lookup"><span data-stu-id="556de-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="556de-104">Les `Exhaustive` Propriétés et `MaxMemoryUsage` de la transformation de regroupement approximatif ne sont pas disponibles dans l **'éditeur de transformation de regroupement probable**, mais elles peuvent être définies à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="556de-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="556de-105">Pour plus d'informations sur ces propriétés, consultez la section Transformation de regroupement approximatif dans [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="556de-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="556de-106">Pour en savoir plus sur la transformation de regroupement approximatif, consultez [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="556de-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="556de-107">Options</span><span class="sxs-lookup"><span data-stu-id="556de-107">Options</span></span>  
 <span data-ttu-id="556de-108">**Nom de la colonne clé d'entrée**</span><span class="sxs-lookup"><span data-stu-id="556de-108">**Input key column name**</span></span>  
 <span data-ttu-id="556de-109">Spécifiez le nom d'une colonne de sortie qui contient l'identificateur unique de chaque ligne d'entée.</span><span class="sxs-lookup"><span data-stu-id="556de-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="556de-110">La colonne `_key_in` a un nom qui identifie chaque ligne de manière unique.</span><span class="sxs-lookup"><span data-stu-id="556de-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="556de-111">**Nom de la colonne clé de sortie**</span><span class="sxs-lookup"><span data-stu-id="556de-111">**Output key column name**</span></span>  
 <span data-ttu-id="556de-112">Spécifiez le nom d'une colonne de sortie qui contient l'identificateur unique de la ligne canonique d'un groupe de lignes dupliquées.</span><span class="sxs-lookup"><span data-stu-id="556de-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="556de-113">La colonne `_key_out` correspond à la valeur `_key_in` de la ligne de données canonique.</span><span class="sxs-lookup"><span data-stu-id="556de-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="556de-114">**Nom de colonne du score de similarité**</span><span class="sxs-lookup"><span data-stu-id="556de-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="556de-115">Spécifiez un nom qui contient le score de similarité.</span><span class="sxs-lookup"><span data-stu-id="556de-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="556de-116">Le score de similarité est une valeur comprise entre 0 et 1 qui indique le niveau de similarité avec la ligne canonique.</span><span class="sxs-lookup"><span data-stu-id="556de-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="556de-117">Plus le score se rapproche de 1, plus la ligne correspond à la ligne canonique.</span><span class="sxs-lookup"><span data-stu-id="556de-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="556de-118">**Seuil de similarité**</span><span class="sxs-lookup"><span data-stu-id="556de-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="556de-119">Définissez le seuil de similarité au moyen du curseur.</span><span class="sxs-lookup"><span data-stu-id="556de-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="556de-120">Plus le seuil est proche de 1, plus la similarité entre les lignes est grande pour se qualifier comme lignes dupliquées.</span><span class="sxs-lookup"><span data-stu-id="556de-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="556de-121">L'augmentation du seuil peut accélérer les recherches du fait que moins de candidats doivent être évalués.</span><span class="sxs-lookup"><span data-stu-id="556de-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="556de-122">**Séparateurs de jetons**</span><span class="sxs-lookup"><span data-stu-id="556de-122">**Token delimiters**</span></span>  
 <span data-ttu-id="556de-123">La transformation fournit un ensemble de séparateurs par défaut pour marquer des données, mais vous devez ajouter ou supprimer des séparateurs en modifiant la liste en fonction des besoins.</span><span class="sxs-lookup"><span data-stu-id="556de-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="556de-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="556de-124">See Also</span></span>  
 <span data-ttu-id="556de-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="556de-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="556de-126">Identifier des lignes de données semblables à l'aide de la transformation de regroupement probable</span><span class="sxs-lookup"><span data-stu-id="556de-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
