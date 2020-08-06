---
title: Éditeur de destination ADO NET (page Mappages) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetdest.mappings.f1
ms.assetid: 842d075f-8b7a-457c-a1a1-a7acbe10e9b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7e7a2397e4e2d16e6eeca93d41f5127dfde4c35e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600199"
---
# <a name="ado-net-destination-editor-mappings-page"></a><span data-ttu-id="0a2d2-102">Éditeur de destination ADO NET (page Mappages)</span><span class="sxs-lookup"><span data-stu-id="0a2d2-102">ADO NET Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="0a2d2-103">Utilisez la page **Mappages** de la boîte de dialogue **Éditeur de destination ADO NET** pour mapper des colonnes d’entrée à des colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-103">Use the **Mappings** page of the **ADO NET Destination Editor** dialog box to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="0a2d2-104">Pour en savoir plus sur la destination ADO NET, consultez [ADO NET Destination](data-flow/ado-net-destination.md).</span><span class="sxs-lookup"><span data-stu-id="0a2d2-104">To learn more about the ADO NET destination, see [ADO NET Destination](data-flow/ado-net-destination.md).</span></span>  
  
 <span data-ttu-id="0a2d2-105">**Pour ouvrir la page Mappages**</span><span class="sxs-lookup"><span data-stu-id="0a2d2-105">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="0a2d2-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui possède la destination ADO NET.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET destination.</span></span>  
  
2.  <span data-ttu-id="0a2d2-107">Sous l’onglet **Flux de données** , double-cliquez sur la destination ADO NET.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-107">On the **Data Flow** tab, double-click the ADO NET destination.</span></span>  
  
3.  <span data-ttu-id="0a2d2-108">Dans **l’Éditeur de destination ADO NET**, cliquez sur **Mappages**.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-108">In the **ADO NET Destination Editor**, click **Mappings**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a2d2-109">Options</span><span class="sxs-lookup"><span data-stu-id="0a2d2-109">Options</span></span>  
 <span data-ttu-id="0a2d2-110">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="0a2d2-110">**Available Input Columns**</span></span>  
 <span data-ttu-id="0a2d2-111">Affichez la liste des colonnes d'entrée disponibles.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-111">View the list of available input columns.</span></span> <span data-ttu-id="0a2d2-112">Au moyen du glisser-déplacer, mappez les colonnes d'entrée disponibles dans la table sur des colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-112">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="0a2d2-113">**Colonnes de destination disponibles**</span><span class="sxs-lookup"><span data-stu-id="0a2d2-113">**Available Destination Columns**</span></span>  
 <span data-ttu-id="0a2d2-114">Affichez la liste des colonnes de destination disponibles.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-114">View the list of available destination columns.</span></span> <span data-ttu-id="0a2d2-115">Utilisez une opération de glisser-déplacer pour mapper les colonnes de destination disponibles dans la table aux colonnes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-115">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="0a2d2-116">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="0a2d2-116">**Input Column**</span></span>  
 <span data-ttu-id="0a2d2-117">Affichez les colonnes d’entrée que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-117">View the input columns that you selected.</span></span> <span data-ttu-id="0a2d2-118">Vous pouvez supprimer des mappages en sélectionnant **\<ignore>** pour exclure des colonnes de la sortie.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-118">You can remove mappings by selecting **\<ignore>** to exclude columns from the output.</span></span>  
  
 <span data-ttu-id="0a2d2-119">**Colonne de destination**</span><span class="sxs-lookup"><span data-stu-id="0a2d2-119">**Destination Column**</span></span>  
 <span data-ttu-id="0a2d2-120">Indique chaque colonne de destination disponible, qu'elle soit mappée ou non.</span><span class="sxs-lookup"><span data-stu-id="0a2d2-120">View each available destination column, regardless of whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2d2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a2d2-121">See Also</span></span>  
 <span data-ttu-id="0a2d2-122">[Éditeur de destination ADO NET &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="0a2d2-122">[ADO NET Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="0a2d2-123">Éditeur de destination ADO NET &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="0a2d2-123">ADO NET Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/ado-net-destination-editor-error-output-page.md)  
  
  
