---
title: Exemples d’expressions de groupe (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695336"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="cb39a-102">Exemples d'expressions de groupe (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="cb39a-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cb39a-103">Dans une région de données, vous pouvez regrouper des données selon un champ unique ou créer des expressions plus complexes qui identifient les données sur lesquelles effectuer le regroupement.</span><span class="sxs-lookup"><span data-stu-id="cb39a-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="cb39a-104">Les expressions complexes incluent des références à plusieurs champs ou paramètres et instructions conditionnelles, ou à du code personnalisé.</span><span class="sxs-lookup"><span data-stu-id="cb39a-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="cb39a-105">Quand vous définissez un groupe pour une région de données, vous ajoutez ces expressions aux propriétés du **groupe** .</span><span class="sxs-lookup"><span data-stu-id="cb39a-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="cb39a-106">Pour plus d’informations, consultez [Ajouter ou supprimer un groupe dans une région de données &#40;Générateur de rapports et SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cb39a-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="cb39a-107">Pour fusionner plusieurs groupes basés sur des expressions de champ simples, ajoutez chaque champ à la liste d'expressions de groupe dans la définition de groupe.</span><span class="sxs-lookup"><span data-stu-id="cb39a-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="cb39a-108">Exemples d'expressions de groupe</span><span class="sxs-lookup"><span data-stu-id="cb39a-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="cb39a-109">Le tableau suivant fournit des exemples d'expressions de groupe qu'il est possible d'utiliser pour définir un groupe.</span><span class="sxs-lookup"><span data-stu-id="cb39a-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="cb39a-110">Description</span><span class="sxs-lookup"><span data-stu-id="cb39a-110">Description</span></span>|<span data-ttu-id="cb39a-111">Expression</span><span class="sxs-lookup"><span data-stu-id="cb39a-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="cb39a-112">Regroupement selon le champ `Region` .</span><span class="sxs-lookup"><span data-stu-id="cb39a-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="cb39a-113">Regroupement selon le nom et le prénom.</span><span class="sxs-lookup"><span data-stu-id="cb39a-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="cb39a-114">Regroupement selon la première lettre du nom.</span><span class="sxs-lookup"><span data-stu-id="cb39a-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="cb39a-115">Regroupement selon un paramètre, en fonction de la sélection de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb39a-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="cb39a-116">Dans cet exemple, le paramètre `GroupBy` doit être basé sur une liste de valeurs disponibles qui fournit un choix valide de regroupements.</span><span class="sxs-lookup"><span data-stu-id="cb39a-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="cb39a-117">Regroupement selon trois tranches d'âge distinctes :</span><span class="sxs-lookup"><span data-stu-id="cb39a-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="cb39a-118">Moins de 21 ans, Entre 21 et 50, et Plus de 50.</span><span class="sxs-lookup"><span data-stu-id="cb39a-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="cb39a-119">Regroupement selon de nombreuses tranches d'âge.</span><span class="sxs-lookup"><span data-stu-id="cb39a-119">Group by many age ranges.</span></span> <span data-ttu-id="cb39a-120">Cet exemple illustre un code personnalisé, écrit en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, qui retourne une chaîne pour les tranches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cb39a-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="cb39a-121">25 ou moins</span><span class="sxs-lookup"><span data-stu-id="cb39a-121">25 or Under</span></span><br /><br /> <span data-ttu-id="cb39a-122">26 à 50</span><span class="sxs-lookup"><span data-stu-id="cb39a-122">26 to 50</span></span><br /><br /> <span data-ttu-id="cb39a-123">51 à 75</span><span class="sxs-lookup"><span data-stu-id="cb39a-123">51 to 75</span></span><br /><br /> <span data-ttu-id="cb39a-124">Plus de 75</span><span class="sxs-lookup"><span data-stu-id="cb39a-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="cb39a-125">Code personnalisé :</span><span class="sxs-lookup"><span data-stu-id="cb39a-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="cb39a-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb39a-126">See Also</span></span>  
 <span data-ttu-id="cb39a-127">[Filtrer, regrouper et trier des données &#40;Générateur de rapports et SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cb39a-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="cb39a-128">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="cb39a-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="cb39a-129">Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb39a-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
