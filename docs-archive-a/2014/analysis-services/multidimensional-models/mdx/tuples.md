---
title: Tuples | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 35b629ae-b1ef-44b1-b556-96956aeb56e7
author: minewiskan
ms.author: owend
ms.openlocfilehash: c39d03d60cb66f3b2e26b2e660bd85f4e5e9d4ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705572"
---
# <a name="tuples"></a><span data-ttu-id="49b9c-102">Tuples</span><span class="sxs-lookup"><span data-stu-id="49b9c-102">Tuples</span></span>
  <span data-ttu-id="49b9c-103">Un tuple identifie de façon unique une coupe de données d'un cube.</span><span class="sxs-lookup"><span data-stu-id="49b9c-103">A tuple uniquely identifies a slice of data from a cube.</span></span> <span data-ttu-id="49b9c-104">Le tuple est formé par une combinaison de membres de la dimension, à condition qu'il n'y ait pas deux membres ou plus appartenant à la même hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="49b9c-104">The tuple is formed by a combination of dimension members, as long as there are no two or more members that belong to the same hierarchy.</span></span>  
  
## <a name="implicit-or-default-attribute-members-in-a-tuple"></a><span data-ttu-id="49b9c-105">Membres d'attribut implicites ou par défaut dans un tuple</span><span class="sxs-lookup"><span data-stu-id="49b9c-105">Implicit or default attribute members in a tuple</span></span>  
 <span data-ttu-id="49b9c-106">Lorsque vous définissez un tuple dans une requête ou une expression MDX, vous n'avez pas besoin d'inclure le membre d'attribut de chaque hiérarchie d'attribut de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="49b9c-106">When defining a tuple in an MDX query or expression, you do not need to explicitly include the attribute member from every attribute hierarchy.</span></span> <span data-ttu-id="49b9c-107">Si un membre d'une hiérarchie d'attribut n'est pas explicitement intégré dans une requête ou une expression, le membre par défaut de la hiérarchie d'attribut en question correspond au membre d'attribut inclus implicitement dans le tuple.</span><span class="sxs-lookup"><span data-stu-id="49b9c-107">If a member from an attribute hierarchy is not explicitly included in a query or an expression, the default member for that attribute hierarchy is the attribute member implicitly included in the tuple.</span></span> <span data-ttu-id="49b9c-108">À moins d'être explicitement défini dans un cube, le membre par défaut de chaque hiérarchie d'attribut est le membre (All) s'il existe.</span><span class="sxs-lookup"><span data-stu-id="49b9c-108">Unless otherwise explicitly defined in a cube, the default member for every attribute hierarchy is the (All) member, if an (All) member exists.</span></span> <span data-ttu-id="49b9c-109">Si un membre (All) n'existe pas dans une hiérarchie d'attribut, le membre par défaut est un membre au niveau supérieur de la hiérarchie d'attribut.</span><span class="sxs-lookup"><span data-stu-id="49b9c-109">If an (All) member does not exist within an attribute hierarchy, the default member is a member of the attribute hierarchy's top level.</span></span> <span data-ttu-id="49b9c-110">La mesure par défaut correspond à la première mesure précisée dans le cube, sauf si une mesure par défaut est explicitement définie.</span><span class="sxs-lookup"><span data-stu-id="49b9c-110">The default measure is the first measure specified in the cube, unless a default measure is explicitly defined.</span></span> <span data-ttu-id="49b9c-111">Pour plus d’informations, consultez [Définir un membre par défaut](../attribute-properties-define-a-default-member.md) et [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span><span class="sxs-lookup"><span data-stu-id="49b9c-111">For more information, see [Define a Default Member](../attribute-properties-define-a-default-member.md) and [DefaultMember &#40;MDX&#41;](/sql/mdx/defaultmember-mdx).</span></span>  
  
 <span data-ttu-id="49b9c-112">Par exemple, le tuple suivant permet d'identifier une cellule unique dans la base de données Adventure Works en définissant uniquement un membre unique de la dimension de mesures.</span><span class="sxs-lookup"><span data-stu-id="49b9c-112">For example, the following tuple identifies a single cell in the Adventure Works database by explicitly defining only a single member of the Measures dimension.</span></span>  
  
```  
(Measures.[Reseller Sales Amount])  
```  
  
 <span data-ttu-id="49b9c-113">L'exemple ci-dessus identifie de manière unique la cellule composée du membre Reseller Sales Amount (volume de vente du revendeur) de la dimension de mesures et du membre par défaut de chaque hiérarchie d'attribut au sein du cube.</span><span class="sxs-lookup"><span data-stu-id="49b9c-113">The previous example uniquely identifies the cell consisting of the Reseller Sales Amount member from the Measures dimension and the default member from every attribute hierarchy in the cube.</span></span> <span data-ttu-id="49b9c-114">Le membre par défaut est le membre (All) de chaque hiérarchie d'attribut autre que la hiérarchie d'attribut Destination Currency (devise de destination).</span><span class="sxs-lookup"><span data-stu-id="49b9c-114">The default member is the (All) member for every attribute hierarchy other than the Destination Currency attribute hierarchy.</span></span> <span data-ttu-id="49b9c-115">Le membre par défaut de la hiérarchie d'attribut Destination Currency est le membre US Dollar (membre par défaut défini dans le script MDX du cube Adventure Works).</span><span class="sxs-lookup"><span data-stu-id="49b9c-115">The default member for the Destination Currency hierarchy is the US Dollar member (this default member is defined in the MDX script for the Adventure Works cube).</span></span>  
  
 <span data-ttu-id="49b9c-116">La requête suivante retourne la valeur de la cellule référencée par le tuple spécifié dans l'exemple précédent ($80,450.596.98).</span><span class="sxs-lookup"><span data-stu-id="49b9c-116">The following query returns the value for the cell referenced by the tuple specified in the previous example, ($80,450.596.98).</span></span>  
  
```  
SELECT   
Measures.[Reseller Sales Amount] ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="49b9c-117">Lorsque vous spécifiez un axe pour un jeu (composé ici d'un tuple unique) dans une requête, vous devez commencer par spécifier un jeu pour l'axe des colonnes avant de préciser un jeu pour l'axe des lignes.</span><span class="sxs-lookup"><span data-stu-id="49b9c-117">When you specify an axis for a set (in this case composed of a single tuple) in a query, you must begin by specifying a set for the column axis before specifying a set for the row axis.</span></span> <span data-ttu-id="49b9c-118">On peut également utiliser le terme *Axes(0)* ou simplement *0*pour désigner l’axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="49b9c-118">The column axis can also be referred to as *axis(0)* or simply *0*.</span></span> <span data-ttu-id="49b9c-119">Pour plus d’informations sur les requêtes MDX, consultez [Requête MDX de base &#40;MDX&#41;](mdx-query-the-basic-query.md).</span><span class="sxs-lookup"><span data-stu-id="49b9c-119">For more information about MDX queries, see [The Basic MDX Query &#40;MDX&#41;](mdx-query-the-basic-query.md).</span></span>  
  
### <a name="tuples-as-values-or-member-references"></a><span data-ttu-id="49b9c-120">Tuples qui référencent des valeurs ou des membres</span><span class="sxs-lookup"><span data-stu-id="49b9c-120">Tuples as values or member references</span></span>  
 <span data-ttu-id="49b9c-121">Vous pouvez utiliser un tuple dans une requête pour retourner la valeur que référence le tuple dans la cellule, comme dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="49b9c-121">You can use a tuple in a query to return the value in the cell that is referenced by the tuple, as in the previous example.</span></span> <span data-ttu-id="49b9c-122">Vous pouvez aussi recourir à un tuple dans une expression pour désigner de manière explicite les membres spécifiés dans ce tuple.</span><span class="sxs-lookup"><span data-stu-id="49b9c-122">Or you can use a tuple in an expression to explicitly refer to the members specified in the tuple.</span></span> <span data-ttu-id="49b9c-123">La requête ou l'expression peut alors se servir de fonctions qui permettent de retourner ou de consommer des tuples.</span><span class="sxs-lookup"><span data-stu-id="49b9c-123">The query or the expression can utilize functions that either return or consume tuples.</span></span> <span data-ttu-id="49b9c-124">Vous pouvez faire appel à un tuple pour soit désigner la valeur de la cellule que le tuple spécifie, soit spécifier une combinaison de membres à utiliser dans le cadre d'une fonction.</span><span class="sxs-lookup"><span data-stu-id="49b9c-124">A tuple can be used to either refer to the value of the cell that the tuple specifies, or to specify a combination of members when utilized in a function.</span></span>  
  
### <a name="tuple-dimensionality"></a><span data-ttu-id="49b9c-125">Dimensionnalité d'un tuple</span><span class="sxs-lookup"><span data-stu-id="49b9c-125">Tuple dimensionality</span></span>  
 <span data-ttu-id="49b9c-126">La *dimensionnalité* d'un tuple désigne le classement ou l'ordre des membres au sein du tuple.</span><span class="sxs-lookup"><span data-stu-id="49b9c-126">The *dimensionality* of a tuple refers to the sequence or order of the members in the tuple.</span></span> <span data-ttu-id="49b9c-127">Du fait que les membres implicites surviennent toujours dans le même ordre, la dimensionnalité est plus souvent abordée en termes de membres explicitement définis du tuple.</span><span class="sxs-lookup"><span data-stu-id="49b9c-127">Since the implicit members always occur in the same order, dimensionality is most often thought of in terms of the explicitly defined members of the tuple.</span></span> <span data-ttu-id="49b9c-128">Le classement des membres du tuple est primordial lorsque vous définissez un jeu de tuples.</span><span class="sxs-lookup"><span data-stu-id="49b9c-128">The ordering of the members of the tuple is important when you define a set of tuples.</span></span> <span data-ttu-id="49b9c-129">L'exemple ci-dessous présente deux membres dans un tuple sur l'axe des colonnes.</span><span class="sxs-lookup"><span data-stu-id="49b9c-129">The following example includes two members in a tuple on the column axis.</span></span>  
  
```  
SELECT   
([Measures].[Reseller Sales Amount],[Date].[Calendar Year].[CY 2004]) ON COLUMNS   
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="49b9c-130">Lorsque vous précisez de manière explicite un membre dans un tuple issu de plusieurs dimensions, vous devez mettre le tuple tout entier entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="49b9c-130">When you explicitly specify a member in a tuple from more than one dimension, you must include the entire tuple in parentheses.</span></span> <span data-ttu-id="49b9c-131">Lorsque vous spécifiez uniquement un seul membre dans un tuple, l'usage de parenthèses est facultatif.</span><span class="sxs-lookup"><span data-stu-id="49b9c-131">When only specifying a single member in a tuple, parentheses are optional.</span></span>  
  
 <span data-ttu-id="49b9c-132">Le tuple employé dans la requête de l'exemple ci-avant précise le retour de la cellule du cube à l'intersection de la mesure Reseller Sales Amount de la dimension de mesures et du membre CY 2004 de la hiérarchie d'attribut Calendar Year dans la dimension Date.</span><span class="sxs-lookup"><span data-stu-id="49b9c-132">The tuple in the query in the previous example specifies the return of the cube cell at the intersection of the Reseller Sales Amount Measure of the Measures dimension and the CY 2004 member of the Calendar Year attribute hierarchy in the Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49b9c-133">Vous pouvez désigner un membre d'attribut selon son nom ou sa clé de membre.</span><span class="sxs-lookup"><span data-stu-id="49b9c-133">An attribute member can be referred by either its member name or its member key.</span></span> <span data-ttu-id="49b9c-134">Dans l'exemple précédent, vous pouviez remplacer la référence à [CY 2004] par &[2004].</span><span class="sxs-lookup"><span data-stu-id="49b9c-134">In the previous example, you could replace the reference to [CY 2004] with &[2004].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b9c-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49b9c-135">See Also</span></span>  
 <span data-ttu-id="49b9c-136">[Concepts clés dans MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="49b9c-136">[Key Concepts in MDX &#40;Analysis Services&#41;](../key-concepts-in-mdx-analysis-services.md) </span></span>  
 <span data-ttu-id="49b9c-137">[Espace du cube](cube-space.md) </span><span class="sxs-lookup"><span data-stu-id="49b9c-137">[Cube Space](cube-space.md) </span></span>  
 <span data-ttu-id="49b9c-138">[Autoexists](autoexists.md) </span><span class="sxs-lookup"><span data-stu-id="49b9c-138">[Autoexists](autoexists.md) </span></span>  
 [<span data-ttu-id="49b9c-139">Utilisation de membres, de tuples et de jeux &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="49b9c-139">Working with Members, Tuples, and Sets &#40;MDX&#41;</span></span>](working-with-members-tuples-and-sets-mdx.md)  
  
  
