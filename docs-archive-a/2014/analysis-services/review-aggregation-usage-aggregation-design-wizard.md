---
title: Examiner l’utilisation de l’agrégation (Assistant conception d’agrégation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
author: minewiskan
ms.author: owend
ms.openlocfilehash: afbb02dae64f3f7ebd57065c3ff8a7d1e202dcf2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602380"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a><span data-ttu-id="85d46-102">Passer en revue l'utilisation d'agrégation (Assistant Conception d'agrégation)</span><span class="sxs-lookup"><span data-stu-id="85d46-102">Review Aggregation Usage (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="85d46-103">Utilisez la page **Passer en revue l'utilisation d'agrégation** pour configurer des paramètres d'utilisation d'agrégation.</span><span class="sxs-lookup"><span data-stu-id="85d46-103">Use the **Review Aggregation Usage** page to configure aggregation usage settings.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85d46-104">Options</span><span class="sxs-lookup"><span data-stu-id="85d46-104">Options</span></span>  
 <span data-ttu-id="85d46-105">**Par défaut**</span><span class="sxs-lookup"><span data-stu-id="85d46-105">**Default**</span></span>  
 <span data-ttu-id="85d46-106">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut possède la valeur Par défaut.</span><span class="sxs-lookup"><span data-stu-id="85d46-106">Select to set the aggregation usage setting for the attribute to Default.</span></span> <span data-ttu-id="85d46-107">En utilisant ce paramètre, le concepteur applique une règle par défaut selon le type d'attribut et de dimension.</span><span class="sxs-lookup"><span data-stu-id="85d46-107">By using this setting, the designer applies a default rule based on the type of attribute and dimension.</span></span>  
  
 `Full`  
 <span data-ttu-id="85d46-108">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit `Full`.</span><span class="sxs-lookup"><span data-stu-id="85d46-108">Select to set the aggregation usage setting for the attribute to `Full`.</span></span> <span data-ttu-id="85d46-109">En utilisant ce paramètre, chaque agrégation pour le cube doit inclure cet attribut ou un attribut associé qui est inférieur dans la chaîne d'attribut.</span><span class="sxs-lookup"><span data-stu-id="85d46-109">By using this setting, every aggregation for the cube must include this attribute or a related attribute that is lower in the attribute chain.</span></span> <span data-ttu-id="85d46-110">Le paramètre d'utilisation d'agrégation `Full` doit être évité lorsqu'un attribut contient de nombreux membres.</span><span class="sxs-lookup"><span data-stu-id="85d46-110">The `Full` aggregation usage setting should be avoided when an attribute contains many members.</span></span> <span data-ttu-id="85d46-111">S'il est spécifié pour plusieurs attributs ou pour des attributs qui ont de nombreux membres, ce paramètre peut empêcher la conception d'agrégations en raison d'une taille excessive.</span><span class="sxs-lookup"><span data-stu-id="85d46-111">If specified for multiple attributes or attributes that have many members, this setting might prevent aggregations from being designed because of excessive size.</span></span>  
  
 <span data-ttu-id="85d46-112">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="85d46-112">**None**</span></span>  
 <span data-ttu-id="85d46-113">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit Aucun.</span><span class="sxs-lookup"><span data-stu-id="85d46-113">Select to set the aggregation usage setting for the attribute to None.</span></span> <span data-ttu-id="85d46-114">En utilisant ce paramètre, aucune agrégation pour le cube ne peut inclure cet attribut.</span><span class="sxs-lookup"><span data-stu-id="85d46-114">By using this setting, no aggregation for the cube can include this attribute.</span></span>  
  
 `Unrestricted`  
 <span data-ttu-id="85d46-115">Sélectionnez pour que le paramètre d'utilisation d'agrégation de l'attribut soit `Unrestricted`.</span><span class="sxs-lookup"><span data-stu-id="85d46-115">Select to set the aggregation usage setting for the attribute to `Unrestricted`.</span></span> <span data-ttu-id="85d46-116">En utilisant ce paramètre, aucune restriction n'est placée sur le concepteur d'agrégations ; toutefois, l'attribut doit encore être évalué pour déterminer s'il constitue un candidat d'agrégation important.</span><span class="sxs-lookup"><span data-stu-id="85d46-116">By using this setting, no restrictions are put on the aggregation designer; however, the attribute must still be evaluated to determine whether it is a valuable aggregation candidate.</span></span>  
  
 <span data-ttu-id="85d46-117">**Définir tout à la valeur par défaut**</span><span class="sxs-lookup"><span data-stu-id="85d46-117">**Set All to Default**</span></span>  
 <span data-ttu-id="85d46-118">Sélectionnez pour définir les paramètres d'utilisation d'agrégation de tous les attributs avec la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="85d46-118">Select to set the aggregation usage settings for all attributes to Default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d46-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85d46-119">See Also</span></span>  
 <span data-ttu-id="85d46-120">[Aide (F1) de l’Assistant conception d’agrégation](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="85d46-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="85d46-121">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="85d46-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
