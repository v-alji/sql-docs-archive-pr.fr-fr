---
title: Colonnes de dimensions à variation lente (Assistant Dimension à variation lente) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.scdsupport.f1
ms.assetid: 36de99d5-5368-48e0-b876-17e9c6862c6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6283887cbddb9844e0ac769281184f588dc2a94d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695868"
---
# <a name="slowly-changing-dimension-columns-slowly-changing-dimension-wizard"></a><span data-ttu-id="cb131-102">Colonnes de dimensions à variation lente (Assistant Dimension à variation lente)</span><span class="sxs-lookup"><span data-stu-id="cb131-102">Slowly Changing Dimension Columns (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="cb131-103">Utilisez la boîte de dialogue **Colonnes de dimensions à variation lente** pour sélectionner un type de modification pour chaque colonne de dimension à variation lente.</span><span class="sxs-lookup"><span data-stu-id="cb131-103">Use the **Slowly Changing Dimensions Columns** dialog box to select a change type for each slowly changing dimension column.</span></span>  
  
 <span data-ttu-id="cb131-104">Pour en savoir plus sur cet Assistant, consultez [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cb131-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb131-105">Options</span><span class="sxs-lookup"><span data-stu-id="cb131-105">Options</span></span>  
 <span data-ttu-id="cb131-106">**Colonnes de dimension**</span><span class="sxs-lookup"><span data-stu-id="cb131-106">**Dimension Columns**</span></span>  
 <span data-ttu-id="cb131-107">Sélectionnez une colonne de dimension dans la liste.</span><span class="sxs-lookup"><span data-stu-id="cb131-107">Select a dimension column from the list.</span></span>  
  
 <span data-ttu-id="cb131-108">**Modifier de type**</span><span class="sxs-lookup"><span data-stu-id="cb131-108">**Change Type**</span></span>  
 <span data-ttu-id="cb131-109">Sélectionnez un **Attribut fixe**ou sélectionnez l’un des deux types d’attributs variables.</span><span class="sxs-lookup"><span data-stu-id="cb131-109">Select a **Fixed Attribute**, or select one of the two types of changing attributes.</span></span> <span data-ttu-id="cb131-110">Utilisez **Attribut fixe** lorsque la valeur d'une colonne ne doit pas changer ; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] traite alors les modifications comme des erreurs.</span><span class="sxs-lookup"><span data-stu-id="cb131-110">Use **Fixed Attribute** when the value in a column should not change; [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] then treats changes as errors.</span></span> <span data-ttu-id="cb131-111">Utilisez **Modification d'attribut** pour remplacer les valeurs existantes par des valeurs modifiées.</span><span class="sxs-lookup"><span data-stu-id="cb131-111">Use **Changing Attribute** to overwrite existing values with changed values.</span></span> <span data-ttu-id="cb131-112">Utilisez **Attribut d'historique** pour enregistrer les valeurs modifiées dans de nouveaux enregistrements tout en marquant comme obsolètes les anciens enregistrements.</span><span class="sxs-lookup"><span data-stu-id="cb131-112">Use **Historical Attribute** to save changed values in new records, while marking previous records as outdated.</span></span>  
  
 <span data-ttu-id="cb131-113">**Remove**</span><span class="sxs-lookup"><span data-stu-id="cb131-113">**Remove**</span></span>  
 <span data-ttu-id="cb131-114">Sélectionnez une colonne de dimension et supprimez-la de la liste des colonnes mappées en cliquant sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cb131-114">Select a dimension column, and remove it from the list of mapped columns by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb131-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb131-115">See Also</span></span>  
 [<span data-ttu-id="cb131-116">Configurer les sorties à l'aide de l'Assistant Dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="cb131-116">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
