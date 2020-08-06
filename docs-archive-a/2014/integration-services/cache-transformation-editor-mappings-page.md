---
title: Éditeur de transformation du cache (page Mappages) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetransmap.f1
ms.assetid: ffd53f18-9646-458a-a84a-f2467d601ea5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bb31e479ea98133da34dcbf257d59e70f4ffe8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613106"
---
# <a name="cache-transformation-editor-mappings-page"></a><span data-ttu-id="2d8ab-102">Éditeur de transformation du cache (page Mappages)</span><span class="sxs-lookup"><span data-stu-id="2d8ab-102">Cache Transformation Editor (Mappings Page)</span></span>
  <span data-ttu-id="2d8ab-103">Utilisez la page **Mappages** de l' **Éditeur de transformation du cache** pour mapper les colonnes d'entrée de la transformation du cache aux colonnes de destination du gestionnaire de connexions du cache.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-103">Use the **Mappings** page of the **Cache Transformation Editor** to map the input columns in the Cache Transform transformation to destination columns in the Cache connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d8ab-104">Chaque colonne d'entrée doit être mappée à une colonne de destination et les types de données de colonne doivent correspondre.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-104">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="2d8ab-105">Sinon, le Concepteur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] affiche un message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-105">Otherwise, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
 <span data-ttu-id="2d8ab-106">Pour en savoir plus sur la transformation du cache, consultez [Cache Transform](data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="2d8ab-106">To learn more about the Cache Transform, see [Cache Transform](data-flow/transformations/cache-transform.md).</span></span>  
  
 <span data-ttu-id="2d8ab-107">Pour en savoir plus sur le gestionnaire de connexions du cache, consultez [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2d8ab-107">To learn more about the Cache connection manager, see [Cache Connection Manager](connection-manager/cache-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d8ab-108">Options</span><span class="sxs-lookup"><span data-stu-id="2d8ab-108">Options</span></span>  
 <span data-ttu-id="2d8ab-109">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="2d8ab-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="2d8ab-110">Affichez la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-110">View the list of available input columns.</span></span> <span data-ttu-id="2d8ab-111">Au moyen d'une opération glisser-déplacer, mappez les colonnes d'entrée disponibles aux colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-111">Use a drag-and-drop operation to map available input columns to destination columns.</span></span>  
  
 <span data-ttu-id="2d8ab-112">Vous pouvez également mapper des colonnes d'entrée aux colonnes de destination à l'aide du clavier. Pour ce faire, mettez en surbrillance une colonne dans la table **Colonnes d'entrée disponibles** , appuyez sur la touche de menu, puis sélectionnez **Mapper les éléments par noms correspondants**.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-112">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="2d8ab-113">**Colonnes de destination disponibles**</span><span class="sxs-lookup"><span data-stu-id="2d8ab-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="2d8ab-114">Affichez la liste des colonnes de destination disponibles.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-114">View the list of available destination columns.</span></span> <span data-ttu-id="2d8ab-115">Au moyen d'une opération glisser-déplacer, mappez les colonnes de destination disponibles aux colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-115">Use a drag-and-drop operation to map available destination columns to input columns.</span></span>  
  
 <span data-ttu-id="2d8ab-116">Vous pouvez également mapper des colonnes d'entrée aux colonnes de destination à l'aide du clavier. Pour ce faire, mettez en surbrillance une colonne dans la table **Colonnes de destination disponibles** , appuyez sur la touche de menu, puis sélectionnez **Mapper les éléments par noms correspondants**.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-116">You can also map input columns to destination columns using the keyboard, by highlighting a column in the **Available Destination Columns** table, pressing the menu key, and then selecting **Map Items By Matching Names**.</span></span>  
  
 <span data-ttu-id="2d8ab-117">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="2d8ab-117">**Input Column**</span></span>  
 <span data-ttu-id="2d8ab-118">Affichez les colonnes d'entrée sélectionnées précédemment.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-118">View input columns selected earlier in this topic.</span></span> <span data-ttu-id="2d8ab-119">Vous pouvez modifier les mappages au moyen de la liste **Colonnes d'entrée disponibles**.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-119">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="2d8ab-120">**Colonne de destination**</span><span class="sxs-lookup"><span data-stu-id="2d8ab-120">**Destination Column**</span></span>  
 <span data-ttu-id="2d8ab-121">Affichez les colonnes de destination disponibles.</span><span class="sxs-lookup"><span data-stu-id="2d8ab-121">View each available destination column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8ab-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d8ab-122">See Also</span></span>  
 [<span data-ttu-id="2d8ab-123">Éditeur de transformation du cache &#40;Page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="2d8ab-123">Cache Transformation Editor &#40;Connection Manager Page&#41;</span></span>](../../2014/integration-services/cache-transformation-editor-connection-manager-page.md)  
  
  
