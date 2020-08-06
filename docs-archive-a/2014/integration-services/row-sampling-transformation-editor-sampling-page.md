---
title: Éditeur de transformation d’échantillonnage de ligne (page échantillonnage) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696940"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="788f4-102">Éditeur de transformation d'échantillonnage de ligne (page Échantillonnage)</span><span class="sxs-lookup"><span data-stu-id="788f4-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="788f4-103">Utilisez la boîte de dialogue **Éditeur de transformation d'échantillonnage de ligne** pour échantillonner une partie d'une entrée à l'aide d'un nombre de lignes spécifié.</span><span class="sxs-lookup"><span data-stu-id="788f4-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="788f4-104">Cette transformation divise l'entrée en deux sorties distinctes.</span><span class="sxs-lookup"><span data-stu-id="788f4-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="788f4-105">Pour en savoir plus sur la transformation d'échantillonnage de lignes, consultez [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="788f4-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="788f4-106">Options</span><span class="sxs-lookup"><span data-stu-id="788f4-106">Options</span></span>  
 <span data-ttu-id="788f4-107">**Nombre de lignes**</span><span class="sxs-lookup"><span data-stu-id="788f4-107">**Number of rows**</span></span>  
 <span data-ttu-id="788f4-108">Définissez le nombre de lignes de l'entrée à utiliser comme échantillon.</span><span class="sxs-lookup"><span data-stu-id="788f4-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="788f4-109">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="788f4-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="788f4-110">**Nom de sortie de l'exemple**</span><span class="sxs-lookup"><span data-stu-id="788f4-110">**Sample output name**</span></span>  
 <span data-ttu-id="788f4-111">Fournissez un nom unique pour la sortie qui contiendra les lignes échantillonnées.</span><span class="sxs-lookup"><span data-stu-id="788f4-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="788f4-112">Le nom fourni sera affiché dans le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="788f4-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="788f4-113">**Nom de sortie non sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="788f4-113">**Unselected output name**</span></span>  
 <span data-ttu-id="788f4-114">Fournissez un nom unique pour la sortie qui contiendra les lignes exclues de l'échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="788f4-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="788f4-115">Le nom fourni sera affiché dans le concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="788f4-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="788f4-116">**Utiliser la valeur de départ aléatoire suivante**</span><span class="sxs-lookup"><span data-stu-id="788f4-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="788f4-117">Définissez la valeur de départ d'échantillonnage du générateur de nombres aléatoires qu'utilise la transformation pour créer un échantillon.</span><span class="sxs-lookup"><span data-stu-id="788f4-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="788f4-118">Ceci est recommandé uniquement pour le développement et les tests.</span><span class="sxs-lookup"><span data-stu-id="788f4-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="788f4-119">La transformation utilise le nombre de cycles Microsoft Windows comme valeur de départ si une valeur de départ aléatoire n'est pas définie.</span><span class="sxs-lookup"><span data-stu-id="788f4-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788f4-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="788f4-120">See Also</span></span>  
 <span data-ttu-id="788f4-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="788f4-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="788f4-122">Transformation d’échantillonnage par pourcentage</span><span class="sxs-lookup"><span data-stu-id="788f4-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
