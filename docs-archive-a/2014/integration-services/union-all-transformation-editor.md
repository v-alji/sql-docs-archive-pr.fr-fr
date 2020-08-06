---
title: Éditeur de transformation d’Union totale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602191"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="848b1-102">Éditeur de transformation d'union totale</span><span class="sxs-lookup"><span data-stu-id="848b1-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="848b1-103">La boîte de dialogue **Éditeur de transformation d'union totale** permet de fusionner plusieurs jeux de lignes d'entrée dans un seul jeu de lignes de sortie.</span><span class="sxs-lookup"><span data-stu-id="848b1-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="848b1-104">En incluant la transformation d'union totale dans un flux de données, vous pouvez fusionner les données de plusieurs flux, créer des datasets complexes en imbriquant les transformations d'union totale et en refusionnant les lignes après avoir corrigé les erreurs contenues dans les données.</span><span class="sxs-lookup"><span data-stu-id="848b1-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="848b1-105">Pour en savoir plus sur la transformation d'union totale, consultez [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="848b1-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="848b1-106">Options</span><span class="sxs-lookup"><span data-stu-id="848b1-106">Options</span></span>  
 <span data-ttu-id="848b1-107">**Nom de colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="848b1-107">**Output Column Name**</span></span>  
 <span data-ttu-id="848b1-108">Permet de saisir un alias pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="848b1-108">Type an alias for each column.</span></span> <span data-ttu-id="848b1-109">Par défaut, il s'agit du nom de la colonne d'entrée provenant de la première entrée (de référence). Vous pouvez toutefois choisir un nom unique descriptif.</span><span class="sxs-lookup"><span data-stu-id="848b1-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="848b1-110">**Entrée 1 d'union totale**</span><span class="sxs-lookup"><span data-stu-id="848b1-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="848b1-111">Sélectionnez cette option dans la liste des colonnes d'entrée disponibles dans la première entrée (de référence).</span><span class="sxs-lookup"><span data-stu-id="848b1-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="848b1-112">Les métadonnées des colonnes mappées doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="848b1-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="848b1-113">**Entrée n d'union totale**</span><span class="sxs-lookup"><span data-stu-id="848b1-113">**Union All Input n**</span></span>  
 <span data-ttu-id="848b1-114">Sélectionnez cette option dans la liste des colonnes d'entrée disponibles dans à partir de la deuxième entrée.</span><span class="sxs-lookup"><span data-stu-id="848b1-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="848b1-115">Les métadonnées des colonnes mappées doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="848b1-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848b1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="848b1-116">See Also</span></span>  
 <span data-ttu-id="848b1-117">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="848b1-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="848b1-118">[Fusionner des données à l’aide de la transformation d’Union totale](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="848b1-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="848b1-119">[Transformation de fusion](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="848b1-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="848b1-120">Transformation de jointure de fusion</span><span class="sxs-lookup"><span data-stu-id="848b1-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  
