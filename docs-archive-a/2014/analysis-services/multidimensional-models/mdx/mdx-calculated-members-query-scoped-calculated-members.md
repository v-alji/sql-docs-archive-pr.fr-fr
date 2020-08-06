---
title: Création de membres calculés d’étendue de requête (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- query-scoped calculated members [MDX]
ms.assetid: c4507149-e67b-4e5d-9192-cc911acd9adc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9c0b3e7184f3cc6abd189344bbce1b6e1f948ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604188"
---
# <a name="creating-query-scoped-calculated-members-mdx"></a><span data-ttu-id="7c145-102">Création de membres calculés d'étendue de requête (MDX)</span><span class="sxs-lookup"><span data-stu-id="7c145-102">Creating Query-Scoped Calculated Members (MDX)</span></span>
  <span data-ttu-id="7c145-103">Si un membre calculé n'est nécessaire que pour une seule requête MDX (Multidimensional Expressions), vous pouvez le définir à l'aide du mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="7c145-103">If a calculated member is only required for a single Multidimensional Expressions (MDX) query, you can define that calculated member by using the WITH keyword.</span></span> <span data-ttu-id="7c145-104">Un membre calculé créé à l'aide du mot clé WITH n'existe plus une fois que l'exécution de la requête est terminée.</span><span class="sxs-lookup"><span data-stu-id="7c145-104">A calculated member that is created by using the WITH keyword no longer exists after the query has finished running.</span></span>  
  
 <span data-ttu-id="7c145-105">Comme l'explique cette rubrique, la syntaxe du mot clé WITH est très souple, et accepte même qu'un membre calculé soit basé sur un autre membre calculé.</span><span class="sxs-lookup"><span data-stu-id="7c145-105">As discussed in this topic, the syntax of the WITH keyword is quite flexible, even allowing a calculated member to be based on another calculated member.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c145-106">Pour plus d’informations sur les membres calculés, consultez [Création de membres calculés dans MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="7c145-106">For more information about calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="with-keyword-syntax"></a><span data-ttu-id="7c145-107">Syntaxe du mot clé WITH</span><span class="sxs-lookup"><span data-stu-id="7c145-107">WITH Keyword Syntax</span></span>  
 <span data-ttu-id="7c145-108">Utilisez la syntaxe suivante pour ajouter le mot clé WITH à une instruction MDX SELECT :</span><span class="sxs-lookup"><span data-stu-id="7c145-108">Use the following syntax to add the WITH keyword to an MDX SELECT statement:</span></span>  
  
```  
[ WITH <SELECT WITH clause> [ , <SELECT WITH clause> ... ] ] SELECT [ * | ( <SELECT query axis clause> [ , <SELECT query axis clause> ... ] ) ]FROM <SELECT subcube clause> [ <SELECT slicer axis clause> ][ <SELECT cell property list clause> ]  
<SELECT WITH clause> ::=  
   ( [ CALCULATED ] MEMBER <CREATE MEMBER body clause>) | <CREATE MEMBER body clause> ::= Member_Identifier AS 'MDX_Expression'  
   [ <CREATE MEMBER property clause> [ , <CREATE MEMBER property clause> ... ] ]  
<CREATE MEMBER property clause> ::=  
   ( MemberProperty_Identifier = Scalar_Expression )  
  
```  
  
 <span data-ttu-id="7c145-109">Dans la syntaxe du mot clé WITH, la valeur de `Member_Identifier` est le nom complet du membre calculé.</span><span class="sxs-lookup"><span data-stu-id="7c145-109">In the syntax for the WITH keyword, the `Member_Identifier` value is the fully qualified name of the calculated member.</span></span> <span data-ttu-id="7c145-110">Ce nom complet comprend la dimension ou le niveau auquel le membre calculé est associé.</span><span class="sxs-lookup"><span data-stu-id="7c145-110">This fully qualified name includes the dimension or level to which the calculated member is associated.</span></span> <span data-ttu-id="7c145-111">La valeur `MDX_Expression` retourne la valeur du membre calculé après l'évaluation de l'expression.</span><span class="sxs-lookup"><span data-stu-id="7c145-111">The `MDX_Expression` value returns the value of the calculated member after the expression value has been evaluated.</span></span> <span data-ttu-id="7c145-112">Vous pouvez également, si vous le souhaitez, spécifier les valeurs des propriétés de cellules intrinsèques d'un membre calculé en fournissant le nom de la propriété de cellule dans la valeur `MemberProperty_Identifier` et la valeur de la propriété de cellule dans la valeur `Scalar_Expression` .</span><span class="sxs-lookup"><span data-stu-id="7c145-112">The values of intrinsic cell properties for a calculated member can be optionally specified by supplying the name of the cell property in the `MemberProperty_Identifier` value and the value of the cell property in the `Scalar_Expression` value.</span></span>  
  
## <a name="with-keyword-examples"></a><span data-ttu-id="7c145-113">Exemple de mot clé WITH</span><span class="sxs-lookup"><span data-stu-id="7c145-113">WITH Keyword Examples</span></span>  
 <span data-ttu-id="7c145-114">La requête MDX ci-dessous définit un membre calculé, `[Measures].[Special Discount]`, en calculant une remise spéciale basée sur le montant de la remise d'origine.</span><span class="sxs-lookup"><span data-stu-id="7c145-114">The following MDX query defines a calculated member, `[Measures].[Special Discount]`, calculating a special discount based on the original discount amount.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Amount] * 1.5  
SELECT   
   [Measures].[Special Discount] on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
```  
  
 <span data-ttu-id="7c145-115">Vous pouvez également créer des membres calculés en n'importe quel point d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="7c145-115">You can also create calculated members at any point within a hierarchy.</span></span> <span data-ttu-id="7c145-116">L'exemple de requête MDX ci-dessous définit le membre calculé `[BigSeller]` pour un cube Sales hypothétique.</span><span class="sxs-lookup"><span data-stu-id="7c145-116">For example, the following MDX query defines the `[BigSeller]` calculated member for a hypothetical Sales cube.</span></span> <span data-ttu-id="7c145-117">Ce membre calculé détermine si un magasin spécifié dispose d'au moins 100 unités de vente dans le domaine des vins et bières.</span><span class="sxs-lookup"><span data-stu-id="7c145-117">This calculated member determines whether a specified store has at least 100.00 in unit sales for beer and wine.</span></span> <span data-ttu-id="7c145-118">Cependant, la requête crée le membre calculé `[BigSeller]` non comme un membre enfant de la dimension `[Product]` , mais comme un enfant du membre `[Beer and Wine]` .</span><span class="sxs-lookup"><span data-stu-id="7c145-118">However, the query creates the `[BigSeller]` calculated member not as a child member of the `[Product]` dimension, but instead as a child member of the `[Beer and Wine]` member.</span></span>  
  
```  
WITH   
   MEMBER [Product].[Beer and Wine].[BigSeller] AS  
  IIf([Product].[Beer and Wine] > 100, "Yes","No")  
SELECT  
   {[Product].[BigSeller]} ON COLUMNS,  
   Store.[Store Name].Members ON ROWS  
FROM Sales  
  
```  
  
 <span data-ttu-id="7c145-119">Les membres calculés ne doivent pas forcément dépendre uniquement des membres existants dans un cube.</span><span class="sxs-lookup"><span data-stu-id="7c145-119">Calculated members do not have to depend only on existing members in a cube.</span></span> <span data-ttu-id="7c145-120">Un membre calculé peut également être basé sur d'autres membres calculés définis dans la même expression MDX.</span><span class="sxs-lookup"><span data-stu-id="7c145-120">Calculated member can also be based on other calculated members defined in the same MDX expression.</span></span> <span data-ttu-id="7c145-121">Par exemple, la requête MDX ci-dessous utilise la valeur créée dans le premier membre calculé, `[Measures].[Special Discount]`, pour générer la valeur du second membre calculé, `[Measures].[Special Discounted Amount]`.</span><span class="sxs-lookup"><span data-stu-id="7c145-121">For example, the following MDX query uses the value created in the first calculated member, `[Measures].[Special Discount]`, to generate the value of the second calculated member, `[Measures].[Special Discounted Amount]`.</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Special Discount] AS  
   [Measures].[Discount Percentage] * 1.5,   
   FORMAT_STRING = 'Percent'  
  
   MEMBER [Measures].[Special Discounted Amount] AS  
   [Measures].[Reseller Average Unit Price] * [Measures].[Special Discount],   
   FORMAT_STRING = 'Currency'  
  
SELECT   
   {[Measures].[Special Discount], [Measures].[Special Discounted Amount]} on COLUMNS,  
   NON EMPTY [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
WHERE [Product].[Category].[Bikes]  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c145-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c145-122">See Also</span></span>  
 <span data-ttu-id="7c145-123">[Référence des fonctions MDX &#40;&#41;MDX](/sql/mdx/mdx-function-reference-mdx) </span><span class="sxs-lookup"><span data-stu-id="7c145-123">[MDX Function Reference &#40;MDX&#41;](/sql/mdx/mdx-function-reference-mdx) </span></span>  
 <span data-ttu-id="7c145-124">[Instruction SELECT &#40;&#41;MDX](/sql/mdx/mdx-data-manipulation-select) </span><span class="sxs-lookup"><span data-stu-id="7c145-124">[SELECT Statement &#40;MDX&#41;](/sql/mdx/mdx-data-manipulation-select) </span></span>  
 [<span data-ttu-id="7c145-125">Création de membres calculés au niveau de la session &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="7c145-125">Creating Session-Scoped Calculated Members &#40;MDX&#41;</span></span>](mdx-calculated-members-session-scoped-calculated-members.md)  
  
  
