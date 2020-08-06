---
title: Boîte de dialogue Créer une nouvelle condition ou Ouvrir une condition, page Général | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614557"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="db7dd-102">Boîte de dialogue Créer une nouvelle condition ou Ouvrir une condition, page Général</span><span class="sxs-lookup"><span data-stu-id="db7dd-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="db7dd-103">Utilisez cette boîte de dialogue pour créer ou modifier une condition de la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="db7dd-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="db7dd-104">Une condition est une expression booléenne qui spécifie un jeu d'états autorisés d'une cible gérée de la Gestion basée sur des stratégies en ce qui concerne des facettes.</span><span class="sxs-lookup"><span data-stu-id="db7dd-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="db7dd-105">Les propriétés qui peuvent être sélectionnées dans la zone **Expression/Champ** dépendent de la facette utilisée.</span><span class="sxs-lookup"><span data-stu-id="db7dd-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="db7dd-106">Pour plus d’informations sur le rapport entre les conditions et les facettes et stratégies, consultez [Administrer des serveurs à l’aide de la Gestion basée sur des stratégies](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="db7dd-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="db7dd-107">Options</span><span class="sxs-lookup"><span data-stu-id="db7dd-107">Options</span></span>  
 <span data-ttu-id="db7dd-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="db7dd-108">**Name**</span></span>  
 <span data-ttu-id="db7dd-109">Pour une nouvelle condition, tapez le nom de la nouvelle condition.</span><span class="sxs-lookup"><span data-stu-id="db7dd-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="db7dd-110">Pour une condition existante, le nom est affiché.</span><span class="sxs-lookup"><span data-stu-id="db7dd-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="db7dd-111">**Facette**</span><span class="sxs-lookup"><span data-stu-id="db7dd-111">**Facet**</span></span>  
 <span data-ttu-id="db7dd-112">Facette utilisée par cette condition.</span><span class="sxs-lookup"><span data-stu-id="db7dd-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="db7dd-113">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="db7dd-113">**AndOr**</span></span>  
 <span data-ttu-id="db7dd-114">Quand vous ajoutez plusieurs expressions, indique si les expressions doivent être jointes à l’aide de **Et** ou **Ou**.</span><span class="sxs-lookup"><span data-stu-id="db7dd-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="db7dd-115">Reste vierge lorsqu'il n'y a qu'une seule expression.</span><span class="sxs-lookup"><span data-stu-id="db7dd-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="db7dd-116">**Champ**</span><span class="sxs-lookup"><span data-stu-id="db7dd-116">**Field**</span></span>  
 <span data-ttu-id="db7dd-117">Chaque facette expose une ou plusieurs propriétés qui peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="db7dd-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="db7dd-118">Dans la zone de champ, sélectionnez une propriété dans la liste de propriétés disponibles afin de créer une expression pour cette condition.</span><span class="sxs-lookup"><span data-stu-id="db7dd-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="db7dd-119">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="db7dd-119">**Operator**</span></span>  
 <span data-ttu-id="db7dd-120">Sélectionnez un opérateur de comparaison pour cette expression.</span><span class="sxs-lookup"><span data-stu-id="db7dd-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="db7dd-121">Les opérateurs sont les suivants : =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="db7dd-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="db7dd-122">Les opérateurs ne sont pas tous disponibles pour certaines propriétés.</span><span class="sxs-lookup"><span data-stu-id="db7dd-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="db7dd-123">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="db7dd-123">**Value**</span></span>  
 <span data-ttu-id="db7dd-124">Paramètre de valeur pour cette expression.</span><span class="sxs-lookup"><span data-stu-id="db7dd-124">The value setting for this expression.</span></span> <span data-ttu-id="db7dd-125">Les valeurs autorisées dépendent de la facette.</span><span class="sxs-lookup"><span data-stu-id="db7dd-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="db7dd-126">Les valeurs peuvent être VRAI/FAUX, chaîne ou numérique.</span><span class="sxs-lookup"><span data-stu-id="db7dd-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="db7dd-127">Les valeurs de chaîne doivent être placées entre guillemets simples, par exemple **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="db7dd-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="db7dd-128">Les opérateurs ne sont pas tous disponibles pour certaines propriétés.</span><span class="sxs-lookup"><span data-stu-id="db7dd-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="db7dd-129">Regroupement de clauses</span><span class="sxs-lookup"><span data-stu-id="db7dd-129">Group Clauses</span></span>  
 <span data-ttu-id="db7dd-130">Les clauses peuvent être regroupées pour fonctionner comme une unité unique, distincte du reste de la requête, à l'instar de la mise entre parenthèses d'une expression dans une équation mathématique ou une instruction logique.</span><span class="sxs-lookup"><span data-stu-id="db7dd-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="db7dd-131">Le regroupement de clauses est utile pour générer des requêtes complexes.</span><span class="sxs-lookup"><span data-stu-id="db7dd-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="db7dd-132">**Pour regrouper des clauses**</span><span class="sxs-lookup"><span data-stu-id="db7dd-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="db7dd-133">Appuyez sur la touche MAJ ou CTRL, puis cliquez sur deux clauses (ou plus) pour sélectionner une plage.</span><span class="sxs-lookup"><span data-stu-id="db7dd-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="db7dd-134">Cliquez avec le bouton droit sur la zone sélectionnée, puis cliquez sur **Regrouper des clauses**.</span><span class="sxs-lookup"><span data-stu-id="db7dd-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7dd-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db7dd-135">See Also</span></span>  
 [<span data-ttu-id="db7dd-136">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="db7dd-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
