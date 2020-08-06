---
title: Éditeur de source ADO NET (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.columns.f1
ms.assetid: fbc205b9-2001-4737-a76b-1ba777344bd9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d89f8c926761b9149f19269bc2519c12bcf130e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605684"
---
# <a name="ado-net-source-editor-columns-page"></a><span data-ttu-id="8e706-102">Éditeur de source ADO NET (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="8e706-102">ADO NET Source Editor (Columns Page)</span></span>
  <span data-ttu-id="8e706-103">Utilisez la page **Colonnes** de la boîte de dialogue **Éditeur de source ADO NET** pour mapper une colonne de sortie à chaque colonne externe (source).</span><span class="sxs-lookup"><span data-stu-id="8e706-103">Use the **Columns** page of the **ADO NET Source Editor** dialog box to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="8e706-104">Pour en savoir plus sur la source ADO NET, consultez [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="8e706-104">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="8e706-105">**Pour ouvrir la page Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8e706-105">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="8e706-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui possède la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="8e706-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="8e706-107">Sous l’onglet **Flux de données** , double-cliquez sur la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="8e706-107">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="8e706-108">Dans l' **Éditeur de source ADO NET**, cliquez sur **Colonnes**.</span><span class="sxs-lookup"><span data-stu-id="8e706-108">In the **ADO NET Source Editor**, click **Columns**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e706-109">Options</span><span class="sxs-lookup"><span data-stu-id="8e706-109">Options</span></span>  
 <span data-ttu-id="8e706-110">**Colonnes externes disponibles**</span><span class="sxs-lookup"><span data-stu-id="8e706-110">**Available External Columns**</span></span>  
 <span data-ttu-id="8e706-111">Affiche la liste des colonnes externes disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="8e706-111">View the list of available external columns in the data source.</span></span> <span data-ttu-id="8e706-112">Vous ne pouvez pas ajouter ou supprimer des colonnes à l'aide de cette table.</span><span class="sxs-lookup"><span data-stu-id="8e706-112">You cannot use this table to add or delete columns.</span></span>  
  
 <span data-ttu-id="8e706-113">**Colonne externe**</span><span class="sxs-lookup"><span data-stu-id="8e706-113">**External Column**</span></span>  
 <span data-ttu-id="8e706-114">Affiche les colonnes externes (sources) selon l'ordre dans lequel vous les visualisez lorsque vous configurez des composants qui consomment des données à partir de cette source.</span><span class="sxs-lookup"><span data-stu-id="8e706-114">View external (source) columns in the order in which you will see them when configuring components that consume data from this source.</span></span>  
  
 <span data-ttu-id="8e706-115">**Colonne de sortie**</span><span class="sxs-lookup"><span data-stu-id="8e706-115">**Output Column**</span></span>  
 <span data-ttu-id="8e706-116">Spécifiez un nom unique pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="8e706-116">Provide a unique name for each output column.</span></span> <span data-ttu-id="8e706-117">Le nom par défaut est celui de la colonne externe (source) sélectionnée ; vous pouvez néanmoins choisir n'importe quel nom unique et significatif.</span><span class="sxs-lookup"><span data-stu-id="8e706-117">The default is the name of the selected external (source) column; however, you can choose any unique, descriptive name.</span></span> <span data-ttu-id="8e706-118">Le nom fourni s'affichera dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8e706-118">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e706-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e706-119">See Also</span></span>  
 <span data-ttu-id="8e706-120">[Éditeur de source ADO NET &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="8e706-120">[ADO NET Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/ado-net-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="8e706-121">[Éditeur de source ADO NET &#40;page sortie d’erreur&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="8e706-121">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="8e706-122">Gestionnaire de connexions ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8e706-122">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
