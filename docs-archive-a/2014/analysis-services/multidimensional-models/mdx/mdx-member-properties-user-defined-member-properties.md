---
title: Propriétés de membre définies par l’utilisateur (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698622"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="07a60-102">Propriétés de membre définies par l'utilisateur (MDX)</span><span class="sxs-lookup"><span data-stu-id="07a60-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="07a60-103">Les propriétés de membre définies par l'utilisateur peuvent être ajoutées à un niveau spécifique dans une dimension en tant que relations d'attributs.</span><span class="sxs-lookup"><span data-stu-id="07a60-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="07a60-104">Elles ne peuvent pas être ajoutées au niveau `(All)` d'une hiérarchie ou à la hiérarchie proprement dite.</span><span class="sxs-lookup"><span data-stu-id="07a60-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="07a60-105">Création de propriétés de membre définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="07a60-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="07a60-106">Les propriétés de membre définies par l'utilisateur peuvent être ajoutées à des dimensions ou à des cubes basés sur le serveur par l'intermédiaire de l'interface utilisateur ou par programmation :</span><span class="sxs-lookup"><span data-stu-id="07a60-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="07a60-107">Pour ajouter des propriétés de membre définies par l’utilisateur à l'aide de l’interface utilisateur, utilisez le Concepteur de dimensions disponible dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07a60-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="07a60-108">Pour plus d’informations, consultez [Définir des relations d’attributs](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="07a60-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="07a60-109">Pour ajouter des propriétés de membre définies par l'utilisateur par programmation, votre application peut utiliser des objets AMO (Analysis Manager Object) ou une combinaison du langage XMLA (XML for Analysis) et du langage ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="07a60-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="07a60-110">Pour plus d’informations, consultez [Relations d’attributs](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="07a60-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="07a60-111">Récupération de propriétés de membre définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="07a60-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="07a60-112">Vous pouvez récupérer des propriétés de membre définies par l’utilisateur à l’aide du `PROPERTIES` mot clé ou de la fonction [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="07a60-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="07a60-113">Utilisation du mot clé PROPERTIES pour récupérer des propriétés de membre définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="07a60-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="07a60-114">La syntaxe permettant de récupérer des propriétés de membre définies par l'utilisateur ressemble à celle utilisée pour faire référence aux propriétés de membre intrinsèques relatives à un niveau, comme le montre la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="07a60-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="07a60-115">Le mot clé `PROPERTIES` s'affiche après l'expression de jeu de la spécification de l'axe.</span><span class="sxs-lookup"><span data-stu-id="07a60-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="07a60-116">Par exemple, la requête MDX suivante utilise le mot clé `PROPERTIES`, récupère les propriétés de membre définies par l'utilisateur `List Price` et `Dealer Price`, puis apparaît après l'expression de jeu qui identifie les produits vendus en janvier :</span><span class="sxs-lookup"><span data-stu-id="07a60-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="07a60-117">Utilisation de la fonction Properties pour récupérer des propriétés de membre définies par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="07a60-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="07a60-118">Vous pouvez également accéder à des propriétés de membre définies par l'utilisateur à l'aide de la fonction `Properties`.</span><span class="sxs-lookup"><span data-stu-id="07a60-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="07a60-119">Par exemple, la requête MDX suivante utilise le mot clé `WITH` pour créer un membre calculé composé de la propriété de membre `List Price` :</span><span class="sxs-lookup"><span data-stu-id="07a60-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="07a60-120">Pour plus d’informations sur la création de membres calculés, consultez [Création de membres calculés dans MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="07a60-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a60-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07a60-121">See Also</span></span>  
 <span data-ttu-id="07a60-122">[Utilisation des propriétés de membre &#40;MDX&#41;](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="07a60-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="07a60-123">Propriétés &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="07a60-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
