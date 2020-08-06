---
title: Boîte de dialogue Vue détaillée des résultats | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.results.f1
- sql12.swb.dmf.policy.resultdetails.f1
ms.assetid: 366f0ff8-722a-40a9-934f-854147e4933d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1c4d669fb1546d27eb8b6ae78e0de8dea5975f24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708223"
---
# <a name="results-detailed-view-dialog-box"></a><span data-ttu-id="5a4bc-102">Boîte de dialogue Vue détaillée des résultats</span><span class="sxs-lookup"><span data-stu-id="5a4bc-102">Results Detailed View Dialog Box</span></span>
  <span data-ttu-id="5a4bc-103">Cette boîte de dialogue affiche les résultats d'évaluation de stratégie après l'exécution d'une stratégie lorsque vous ouvrez la boîte de dialogue **Évaluer les stratégies** et que vous cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-103">This dialog box shows the results of policy evaluation after you have run a policy by using the **Evaluate Policies** dialog box and clicked **Evaluate**.</span></span> <span data-ttu-id="5a4bc-104">Cette boîte de dialogue est en lecture seule et vous aide à comprendre quelle partie d'une expression de propriété peut échouer.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-104">This dialog box is read-only, and helps you understand which part of a property expression might be failing.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a4bc-105">Options</span><span class="sxs-lookup"><span data-stu-id="5a4bc-105">Options</span></span>  
 <span data-ttu-id="5a4bc-106">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-106">**AndOr**</span></span>  
 <span data-ttu-id="5a4bc-107">Lorsque plusieurs expressions de propriété sont présentes, indique si les expressions de propriété sont cumulatives ou autres.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-107">When more than one property expression is present, indicates whether the property expressions are cumulative or alternative.</span></span>  
  
 <span data-ttu-id="5a4bc-108">**Résultat**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-108">**Result**</span></span>  
 <span data-ttu-id="5a4bc-109">Icône qui représente le succès ou l'échec de l'expression de propriété.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-109">Icon that represents the success or failure of the property expression.</span></span>  
  
 <span data-ttu-id="5a4bc-110">**Champ**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-110">**Field**</span></span>  
 <span data-ttu-id="5a4bc-111">Propriété de la facette qui est modelée.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-111">The property of the facet that is being modeled.</span></span>  
  
 <span data-ttu-id="5a4bc-112">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-112">**Operator**</span></span>  
 <span data-ttu-id="5a4bc-113">Opérateur pour l’expression, par exemple **=** ou **Comme**.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-113">The operator for the expression, for example **=** or **Like**.</span></span>  
  
 <span data-ttu-id="5a4bc-114">**Valeur attendue**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-114">**Expected Value**</span></span>  
 <span data-ttu-id="5a4bc-115">Valeur du champ qui entraîne le succès de l'expression de propriété.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-115">The value for the field that will cause the property expression to be successful.</span></span>  
  
 <span data-ttu-id="5a4bc-116">**Valeur réelle**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-116">**Actual Value**</span></span>  
 <span data-ttu-id="5a4bc-117">Valeur du champ détectée par la stratégie.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-117">The value for the field that was detected by the policy.</span></span>  
  
 <span data-ttu-id="5a4bc-118">**Description de stratégie**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-118">**Policy description**</span></span>  
 <span data-ttu-id="5a4bc-119">Description de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-119">The description of the policy.</span></span>  
  
 <span data-ttu-id="5a4bc-120">**Aide supplémentaire**</span><span class="sxs-lookup"><span data-stu-id="5a4bc-120">**Additional help**</span></span>  
 <span data-ttu-id="5a4bc-121">Cliquez sur le lien hypertexte pour ouvrir une page Web en rapport avec cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-121">Click the hyperlink to open a Web page that is related to this policy.</span></span> <span data-ttu-id="5a4bc-122">Le lien hypertexte d'aide supplémentaire est configuré lors de la création de la stratégie et il peut être vide ou non disponible.</span><span class="sxs-lookup"><span data-stu-id="5a4bc-122">The Additional Help hyperlink is configured when the policy is created and might be blank or unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4bc-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a4bc-123">See Also</span></span>  
 <span data-ttu-id="5a4bc-124">[Nœud Gestion de la stratégie &#40;Explorateur d’objets&#41;](../../ssms/object/object-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="5a4bc-124">[Policy Management Node &#40;Object Explorer&#41;](../../ssms/object/object-explorer.md) </span></span>  
 [<span data-ttu-id="5a4bc-125">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="5a4bc-125">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
