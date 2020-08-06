---
title: Examiner l’utilisation de l’agrégation (Assistant Optimisation basé sur l’utilisation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.reviewaggregationusage.f1
ms.assetid: 49ce2094-c4dc-4e46-8cef-c17c5db084ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5ef9f900e64858515db226d1f9b864874a4ba827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602379"
---
# <a name="review-aggregation-usage-usage-based-optimiation-wizard"></a><span data-ttu-id="bbf3c-102">Passer en revue l'utilisation d'agrégation (Assistant Optimisation de l'utilisation)</span><span class="sxs-lookup"><span data-stu-id="bbf3c-102">Review Aggregation Usage (Usage-Based Optimiation Wizard)</span></span>
  <span data-ttu-id="bbf3c-103">Utilisez la page **Passer en revue l'utilisation d'agrégation** pour configurer des paramètres d'utilisation d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bbf3c-104">Options</span><span class="sxs-lookup"><span data-stu-id="bbf3c-104">Options</span></span>  
 <span data-ttu-id="bbf3c-105">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="bbf3c-105">**Default**</span></span>  
 <span data-ttu-id="bbf3c-106">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut possède la valeur Par défaut.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="bbf3c-107">En utilisant ce paramètre, le concepteur applique une règle par défaut selon le type d'attribut et de dimension.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 <span data-ttu-id="bbf3c-108">**Complète**</span><span class="sxs-lookup"><span data-stu-id="bbf3c-108">**Full**</span></span>  
 <span data-ttu-id="bbf3c-109">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit Full.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-109">Select to set the aggregation usage setting for the attribute to Full.</span></span> <span data-ttu-id="bbf3c-110">En utilisant ce paramètre, chaque agrégation pour le cube doit inclure cet attribut ou un attribut associé qui est inférieur dans la chaîne d'attribut.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-110">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="bbf3c-111">Le paramètre d'utilisation d'agrégation Full doit être évité lorsqu'un attribut contient de nombreux membres.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-111">The Full aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="bbf3c-112">S'il est spécifié pour plusieurs attributs ou pour des attributs qui ont de nombreux membres, ce paramètre peut empêcher la conception d'agrégations en raison d'une taille excessive.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-112">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="bbf3c-113">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="bbf3c-113">**None**</span></span>  
 <span data-ttu-id="bbf3c-114">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit Aucun.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-114">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="bbf3c-115">En utilisant ce paramètre, aucune agrégation pour le cube ne peut inclure cet attribut.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-115">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 <span data-ttu-id="bbf3c-116">**Illimité**</span><span class="sxs-lookup"><span data-stu-id="bbf3c-116">**Unrestricted**</span></span>  
 <span data-ttu-id="bbf3c-117">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-117">Select to set the aggregation usage setting for the attribute to Unrestricted.</span></span> <span data-ttu-id="bbf3c-118">En utilisant ce paramètre, aucune restriction n'est placée sur le concepteur d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-118">By using this setting, no restrictions are put on the aggregation designer.</span></span> <span data-ttu-id="bbf3c-119">Toutefois, l'attribut doit encore être évalué pour déterminer s'il s'agit d'un candidat d'agrégation important.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-119">However, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="bbf3c-120">**Définir tout à la valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="bbf3c-120">**Set All to Default**</span></span>  
 <span data-ttu-id="bbf3c-121">Sélectionnez pour définir les paramètres d'utilisation d'agrégation de tous les attributs avec la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="bbf3c-121">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf3c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbf3c-122">See Also</span></span>  
 <span data-ttu-id="bbf3c-123">[Aide (F1) de l’Assistant conception d’agrégation](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bbf3c-123">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="bbf3c-124">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="bbf3c-124">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
