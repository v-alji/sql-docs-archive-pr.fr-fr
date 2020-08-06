---
title: Créer une dimension de type monétaire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698682"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="79d20-102">Créer une dimension de type monétaire</span><span class="sxs-lookup"><span data-stu-id="79d20-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="79d20-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , une dimension de type monétaire est une dimension dont les attributs représentent une liste de devises pour les rapports financiers.</span><span class="sxs-lookup"><span data-stu-id="79d20-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="79d20-104">Une dimension monétaire permet d'ajouter des fonctions de conversion monétaire à un cube dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79d20-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="79d20-105">Pour ajouter une conversion monétaire à un cube, utilisez l'Assistant Business Intelligence pour définir une commande de script MDX (Multidimensional Expressions) qui convertit les mesures monétaires en valeurs correspondant aux paramètres régionaux de l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="79d20-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="79d20-106">Pour créer ce script MDX, vous devez fournir les informations suivantes à l'Assistant Business Intelligence :</span><span class="sxs-lookup"><span data-stu-id="79d20-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="79d20-107">Une dimension monétaire qui représente les devises sources.</span><span class="sxs-lookup"><span data-stu-id="79d20-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="79d20-108">(Cette dimension est la dimension monétaire source.)</span><span class="sxs-lookup"><span data-stu-id="79d20-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="79d20-109">Un groupe de mesures qui représente les taux de change à utiliser.</span><span class="sxs-lookup"><span data-stu-id="79d20-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="79d20-110">À partir de ces informations, l'Assistant Business Intelligence crée un processus de conversion monétaire qui identifie la dimension monétaire de destination appropriée (la dimension monétaire qui représente les devises de destination).</span><span class="sxs-lookup"><span data-stu-id="79d20-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="79d20-111">Selon le nombre de conversions monétaires nécessaires à la solution décisionnelle, l'Assistant Business Intelligence peut définir plusieurs dimensions monétaires de destination.</span><span class="sxs-lookup"><span data-stu-id="79d20-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="79d20-112">Pour plus d’informations sur la définition de conversions monétaires, consultez [Conversions monétaires &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="79d20-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="79d20-113">Pour définir une dimension comme dimension monétaire, affectez à la propriété `Type` de la dimension la valeur `Currency`.</span><span class="sxs-lookup"><span data-stu-id="79d20-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="79d20-114">Structure de la dimension</span><span class="sxs-lookup"><span data-stu-id="79d20-114">Dimension Structure</span></span>  
 <span data-ttu-id="79d20-115">Une dimension monétaire contient au moins un attribut clé qui identifie les devises dans la table de la dimension monétaire.</span><span class="sxs-lookup"><span data-stu-id="79d20-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="79d20-116">La valeur de l'attribut clé est différente dans les dimensions monétaires source et de destination :</span><span class="sxs-lookup"><span data-stu-id="79d20-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="79d20-117">Pour définir un attribut comme attribut clé d'une dimension monétaire source, affectez à la propriété `Type` de l'attribut la valeur `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="79d20-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="79d20-118">Pour définir un attribut comme dimension monétaire de destination, affectez à la propriété `Type` de l'attribut la valeur `CurrencyDestination`.</span><span class="sxs-lookup"><span data-stu-id="79d20-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="79d20-119">Pour les rapports, les dimensions monétaires source et de destination peuvent contenir éventuellement les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="79d20-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="79d20-120">Un attribut de nom de devise</span><span class="sxs-lookup"><span data-stu-id="79d20-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="79d20-121">Pour définir un attribut comme attribut de nom de devise, affectez à la propriété `Type` de l'attribut la valeur `CurrencyName`.</span><span class="sxs-lookup"><span data-stu-id="79d20-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="79d20-122">Un attribut de source de devise</span><span class="sxs-lookup"><span data-stu-id="79d20-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="79d20-123">Pour définir un attribut comme attribut de source de devise, affectez à la propriété `Type` de l'attribut la valeur `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="79d20-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="79d20-124">Un code ISO (International Standards Organization) de devise</span><span class="sxs-lookup"><span data-stu-id="79d20-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="79d20-125">Pour définir un attribut comme attribut de code ISO de devise, affectez à la propriété `Type` de l'attribut la valeur `CurrencyIsoCode`.</span><span class="sxs-lookup"><span data-stu-id="79d20-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="79d20-126">Pour plus d’informations sur les types d’attributs, consultez [Configurer des types d’attributs](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="79d20-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="79d20-127">Définition de l'intelligence comptable avec l'Assistant Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="79d20-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="79d20-128">Après avoir défini une dimension de comptes et ajouté la dimension à un cube, vous pouvez utiliser l'Assistant Business Intelligence pour ajouter des fonctions d'intelligence comptable, telles que l'identification et le mappage de types de comptes, à la dimension.</span><span class="sxs-lookup"><span data-stu-id="79d20-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="79d20-129">Pour plus d’informations, consultez [Ajouter de l’intelligence comptable à une dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="79d20-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d20-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79d20-130">See Also</span></span>  
 <span data-ttu-id="79d20-131">[Attributs et hiérarchies d’attributs](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="79d20-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="79d20-132">[Aide (F1) de l’Assistant Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="79d20-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="79d20-133">Types de dimensions</span><span class="sxs-lookup"><span data-stu-id="79d20-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
