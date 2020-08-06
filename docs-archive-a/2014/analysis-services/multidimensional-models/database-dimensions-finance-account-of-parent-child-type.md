---
title: Créer un compte finance de dimension de type parent-enfant | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698688"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="69315-102">Créer un compte Finance de la dimension de type parent-enfant</span><span class="sxs-lookup"><span data-stu-id="69315-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="69315-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , une dimension de type compte est une dimension dont les attributs représentent un graphique de comptes à des fins de création de rapports financiers.</span><span class="sxs-lookup"><span data-stu-id="69315-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="69315-104">Une dimension de comptes permet de gérer dans le temps et de manière sélective le comportement de l'agrégation dans les comptes.</span><span class="sxs-lookup"><span data-stu-id="69315-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="69315-105">Un compte de dimensions permet également d'utiliser un mécanisme standard pour résoudre la plupart des problèmes d'agrégation non standard associés généralement aux solutions décisionnelles qui gèrent des données financières.</span><span class="sxs-lookup"><span data-stu-id="69315-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="69315-106">Si vous ne disposiez pas d'un tel mécanisme standard, la résolution des problèmes d'agrégation non standard nécessiterait des formules de cumul personnalisées, des membres calculés ou des scripts d'expression multidimensionnelle (MDX, Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="69315-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="69315-107">Pour définir une dimension sous la forme d'une dimension de comptes, affectez à la propriété `Type` de la dimension la valeur `Accounts`.</span><span class="sxs-lookup"><span data-stu-id="69315-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="69315-108">Structure de la dimension</span><span class="sxs-lookup"><span data-stu-id="69315-108">Dimension Structure</span></span>  
 <span data-ttu-id="69315-109">Une dimension de comptes contient au moins deux attributs :</span><span class="sxs-lookup"><span data-stu-id="69315-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="69315-110">Attribut clé : attribut qui identifie les comptes individuels dans la table de dimension pour la dimension de compte.</span><span class="sxs-lookup"><span data-stu-id="69315-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="69315-111">Attribut de compte : attribut parent qui décrit la façon dont les comptes sont organisés hiérarchiquement dans la dimension Account.</span><span class="sxs-lookup"><span data-stu-id="69315-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="69315-112">Pour définir un attribut comme attribut de compte, affectez à la propriété `Type` de l'attribut la valeur `Account` et à la propriété `Usage`, la valeur `Parent`.</span><span class="sxs-lookup"><span data-stu-id="69315-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="69315-113">Les dimensions de comptes peuvent éventuellement contenir les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="69315-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="69315-114">Attribut de type de compte : attribut qui définit le type de compte pour chaque compte de la dimension.</span><span class="sxs-lookup"><span data-stu-id="69315-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="69315-115">Les noms des membres de l’attribut de type de compte sont associés aux types de comptes définis pour la base de données ou le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , et indiquent la fonction d’agrégation utilisée par [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour ces comptes.</span><span class="sxs-lookup"><span data-stu-id="69315-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="69315-116">Vous pouvez également utiliser des opérateurs unaires ou des formules de cumul personnalisées pour déterminer le comportement d'agrégation des attributs de comptes, mais les types de comptes permettent d'appliquer aisément un comportement cohérent à un graphique de comptes sans avoir à modifier la base de données relationnelle sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="69315-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="69315-117">Pour définir un attribut de type de compte, affectez à la propriété `Type` de l'attribut la valeur `AccountType`.</span><span class="sxs-lookup"><span data-stu-id="69315-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="69315-118">Attribut de nom de compte : attribut utilisé à des fins de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="69315-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="69315-119">Pour définir un attribut de nom de compte, affectez à la propriété `Type` de l'attribut la valeur `AccountName`.</span><span class="sxs-lookup"><span data-stu-id="69315-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="69315-120">Attribut de numéro de compte : attribut utilisé à des fins de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="69315-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="69315-121">Pour définir un attribut de numéro de compte, affectez à la propriété `Type` de l'attribut la valeur `AccountNumber`.</span><span class="sxs-lookup"><span data-stu-id="69315-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="69315-122">Pour plus d’informations sur les types d’attributs, consultez [Configurer des types d’attributs](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="69315-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="69315-123">Ajout de l'intelligence comptable avec l'Assistant Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="69315-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="69315-124">Après avoir défini une dimension de comptes et ajouté la dimension à un cube, vous pouvez utiliser l’Assistant Business Intelligence pour ajouter des fonctions d’intelligence comptable, telles que l’identification et le mappage de types de comptes, à la dimension.</span><span class="sxs-lookup"><span data-stu-id="69315-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="69315-125">Pour plus d’informations, consultez [Ajouter de l’intelligence comptable à une dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="69315-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69315-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69315-126">See Also</span></span>  
 <span data-ttu-id="69315-127">[Attributs et hiérarchies d’attributs](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="69315-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="69315-128">[Aide (F1) de l’Assistant Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="69315-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="69315-129">Types de dimensions</span><span class="sxs-lookup"><span data-stu-id="69315-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
