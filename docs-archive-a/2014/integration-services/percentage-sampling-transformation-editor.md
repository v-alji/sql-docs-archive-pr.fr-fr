---
title: Éditeur de transformation d’échantillonnage par pourcentage | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601542"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="7f792-102">Éditeur de transformation de l'échantillonnage du pourcentage</span><span class="sxs-lookup"><span data-stu-id="7f792-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="7f792-103">La boîte de dialogue **Éditeur de transformation de l'échantillonnage du pourcentage** permet de fractionner une partie d'une entrée en un exemple par le biais d'un certain pourcentage de lignes.</span><span class="sxs-lookup"><span data-stu-id="7f792-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="7f792-104">Cette transformation divise l'entrée en deux sorties distinctes.</span><span class="sxs-lookup"><span data-stu-id="7f792-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="7f792-105">Pour en savoir plus sur la transformation d'échantillonnage par pourcentage, consultez [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="7f792-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f792-106">Options</span><span class="sxs-lookup"><span data-stu-id="7f792-106">Options</span></span>  
 <span data-ttu-id="7f792-107">**Pourcentage de lignes**</span><span class="sxs-lookup"><span data-stu-id="7f792-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="7f792-108">Permet d'indiquer le pourcentage de lignes de l'entrée à utiliser comme exemple.</span><span class="sxs-lookup"><span data-stu-id="7f792-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="7f792-109">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="7f792-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="7f792-110">**Nom de sortie de l'exemple**</span><span class="sxs-lookup"><span data-stu-id="7f792-110">**Sample output name**</span></span>  
 <span data-ttu-id="7f792-111">Fournissez un nom unique pour la sortie qui contiendra les lignes échantillonnées.</span><span class="sxs-lookup"><span data-stu-id="7f792-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="7f792-112">Le nom fourni s'affichera dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f792-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7f792-113">**Nom de sortie non sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="7f792-113">**Unselected output name**</span></span>  
 <span data-ttu-id="7f792-114">Fournissez un nom unique pour la sortie qui contiendra les lignes exclues de l'échantillonnage.</span><span class="sxs-lookup"><span data-stu-id="7f792-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="7f792-115">Le nom fourni s'affichera dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7f792-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="7f792-116">**Utiliser la valeur de départ aléatoire suivante**</span><span class="sxs-lookup"><span data-stu-id="7f792-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="7f792-117">Définissez la valeur de départ d'échantillonnage du générateur de nombres aléatoires qu'utilise la transformation pour créer un échantillon.</span><span class="sxs-lookup"><span data-stu-id="7f792-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="7f792-118">Ceci est recommandé uniquement pour le développement et les tests.</span><span class="sxs-lookup"><span data-stu-id="7f792-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="7f792-119">La fonctionnalité de transformation utilise le nombre de cycles de Microsoft Windows si aucune valeur de départ aléatoire n'est mentionnée.</span><span class="sxs-lookup"><span data-stu-id="7f792-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f792-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f792-120">See Also</span></span>  
 <span data-ttu-id="7f792-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7f792-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="7f792-122">Transformation d'échantillonnage de lignes</span><span class="sxs-lookup"><span data-stu-id="7f792-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
