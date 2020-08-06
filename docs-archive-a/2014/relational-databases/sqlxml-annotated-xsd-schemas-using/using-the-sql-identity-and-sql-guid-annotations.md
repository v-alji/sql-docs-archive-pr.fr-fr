---
title: 'Utilisation des annotations SQL : Identity et SQL : GUID | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:guid
- annotated XSD schemas, IDENTITY-type columns
- annotated XSD schemas, GUID values
- DiffGrams [SQLXML], annotations
- identity annotation
- XSD schemas [SQLXML], GUID values
- GUIDs [SQLXML]
- guid annotation
- sql:identity
- IDENTITY-type column
- XSD schemas [SQLXML], IDENTITY-type columns
- updategrams [SQLXML], GUID values
ms.assetid: 7661dfd0-6573-4692-a8f1-3597adcd33c4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc5c08f158911edb0a1a0638fc4bcee1e05a248c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605354"
---
# <a name="using-the-sqlidentity-and-sqlguid-annotations"></a><span data-ttu-id="2a978-102">Utilisation des annotations sql:identity et sql:guid</span><span class="sxs-lookup"><span data-stu-id="2a978-102">Using the sql:identity and sql:guid Annotations</span></span>
  <span data-ttu-id="2a978-103">Vous pouvez spécifier les `sql:identity` `sql:guid` annotations et dans un schéma XSD sur tout nœud qui est mappé à une colonne de base de données dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a978-103">You can specify the `sql:identity` and `sql:guid` annotations in an XSD schema on any node that maps to a database column in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2a978-104">Le format de code de mise à jour (updategram) prend en charge les attributs `updg:at-identity` et `updg:guid`, contrairement au format de DiffGram.</span><span class="sxs-lookup"><span data-stu-id="2a978-104">Whereas the updategram format supports the `updg:at-identity` and `updg:guid` attributes, the DiffGram format does not.</span></span> <span data-ttu-id="2a978-105">L'attribut `updg:at-identity` définit le comportement de mise à jour d'une colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="2a978-105">The `updg:at-identity` attribute defines the behavior in updating an IDENTITY-type column.</span></span> <span data-ttu-id="2a978-106">L'attribut `updg:guid` permet d'obtenir une valeur GUID à partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et de l'utiliser dans le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="2a978-106">The `updg:guid` attribute allows you to obtain a GUID value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and use it in the updategram.</span></span> <span data-ttu-id="2a978-107">Pour plus d’informations et pour obtenir des exemples fonctionnels, consultez [insertion de données à l’aide de XML codes &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2a978-107">For more information and working samples, see [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="2a978-108">Les annotations `sql:identity` et `sql:guid` étendent ces fonctionnalités aux DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="2a978-108">The `sql:identity` and `sql:guid` annotations extend this functionality to DiffGrams.</span></span>  
  
 <span data-ttu-id="2a978-109">Lorsque vous exécutez un DiffGram, il est d'abord converti en un code de mise à jour (updategram), puis le code de mise à jour (updategram) est exécuté.</span><span class="sxs-lookup"><span data-stu-id="2a978-109">When you execute a DiffGram, it is first converted to an updategram, and then the updategram is executed.</span></span> <span data-ttu-id="2a978-110">En spécifiant les annotations `sql:identity` et `sql:guid` dans le schéma XSD, vous définissez en fait le comportement d'un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="2a978-110">By specifying the `sql:identity` and `sql:guid` annotations in the XSD schema, you are in fact defining the behavior of an updategram.</span></span> <span data-ttu-id="2a978-111">Par conséquent, toutes les annotations sont décrites dans le contexte d'un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="2a978-111">Therefore, all the annotations are described in the context of an updategram.</span></span> <span data-ttu-id="2a978-112">Les annotations peuvent être utilisées à la fois pour les DiffGrams et les codes de mise à jour (updategram) ; toutefois, les codes de mise à jour (updategram) offrent déjà un moyen plus puissant pour gérer l'identité et les valeurs GUID.</span><span class="sxs-lookup"><span data-stu-id="2a978-112">The annotations can be used both for DiffGrams and updategrams; however, updategrams already provide a more powerful way of handling identity and GUID values.</span></span>  
  
 <span data-ttu-id="2a978-113">Les annotations `sql:identity` et `sql:guid` peuvent être définies sur un élément de contenu complexe.</span><span class="sxs-lookup"><span data-stu-id="2a978-113">The `sql:identity` and `sql:guid` annotations can be defined on a complex content element.</span></span>  
  
## <a name="sqlidentity-annotation"></a><span data-ttu-id="2a978-114">Annotation sql:identity</span><span class="sxs-lookup"><span data-stu-id="2a978-114">sql:identity Annotation</span></span>  
 <span data-ttu-id="2a978-115">Vous pouvez spécifier l'annotation `sql:identity` dans le schéma XSD de n'importe quel nœud mappé sur une colonne de base de données de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="2a978-115">You can specify the `sql:identity` annotation in the XSD schema on any node that maps to an IDENTITY-type database column.</span></span> <span data-ttu-id="2a978-116">La valeur spécifiée pour cette annotation définit le mode de mise à jour de la colonne de type IDENTity (à l’aide de la valeur fournie dans mise à jour pour modifier la colonne ou en ignorant la valeur, auquel cas une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valeur générée est utilisée pour cette colonne).</span><span class="sxs-lookup"><span data-stu-id="2a978-116">The value specified for this annotation defines how the IDENTITY-type column is updated (either by using the value provided in the updategram to modify the column or by ignoring the value, in which case a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-generated value is used for this column).</span></span>  
  
 <span data-ttu-id="2a978-117">Deux valeurs peuvent être assignées à l'annotation `sql:identity` :</span><span class="sxs-lookup"><span data-stu-id="2a978-117">The `sql:identity` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="2a978-118">ignore</span><span class="sxs-lookup"><span data-stu-id="2a978-118">ignore</span></span>  
 <span data-ttu-id="2a978-119">Ordonne au code de mise à jour (updategram) d'ignorer toute valeur fournie dans le code de mise à jour (updategram) pour cette colonne et de compter sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour générer la valeur d'identité.</span><span class="sxs-lookup"><span data-stu-id="2a978-119">Directs the updategram to ignore any value that is provided in the updategram for that column and to rely on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to generate the identity value.</span></span>  
  
 <span data-ttu-id="2a978-120">useValue</span><span class="sxs-lookup"><span data-stu-id="2a978-120">useValue</span></span>  
 <span data-ttu-id="2a978-121">Ordonne au code de mise à jour (updategram) d'utiliser la valeur fournie dans le code de mise à jour (updategram) pour mettre à jour la colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="2a978-121">Directs the updategram to use the value that is provided in the updategram to update the IDENTITY-type column.</span></span> <span data-ttu-id="2a978-122">Un code de mise à jour (updategram) ne vérifie pas si la colonne est une valeur d'identité ou pas.</span><span class="sxs-lookup"><span data-stu-id="2a978-122">An updategram does not check whether the column is an identity value or not.</span></span>  
  
 <span data-ttu-id="2a978-123">Si le code de mise à jour (updategram) spécifie une valeur pour la colonne de type IDENTITY, l'annotation `sql:identity="useValue"` doit être spécifiée dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="2a978-123">If the updategram specifies a value for the IDENTITY-type column, the `sql:identity="useValue"` must be specified in the schema.</span></span>  
  
## <a name="sqlguid-annotation"></a><span data-ttu-id="2a978-124">Annotation sql:guid</span><span class="sxs-lookup"><span data-stu-id="2a978-124">sql:guid Annotation</span></span>  
 <span data-ttu-id="2a978-125">Un code de mise à jour (updategram) peut faire en sorte que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] génère une valeur GUID, puis utiliser cette valeur dans le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="2a978-125">An updategram can have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generate a GUID value and then use this value in the updategram.</span></span> <span data-ttu-id="2a978-126">Dans le contexte de DiffGrams, vous pouvez utiliser l'annotation `sql:guid` pour spécifier s'il faut utiliser une valeur GUID générée par SQL Server ou utiliser la valeur fournie dans le code de mise à jour (updategram) pour cette colonne.</span><span class="sxs-lookup"><span data-stu-id="2a978-126">In the context of DiffGrams, you can use the `sql:guid` annotation to specify whether to use a GUID value that is generated by SQL Server or use the value that is provided in the updategram for that column.</span></span>  
  
 <span data-ttu-id="2a978-127">Deux valeurs peuvent être assignées à l'annotation `sql:guid` :</span><span class="sxs-lookup"><span data-stu-id="2a978-127">The `sql:guid` annotation can be assigned two values:</span></span>  
  
 <span data-ttu-id="2a978-128">générer</span><span class="sxs-lookup"><span data-stu-id="2a978-128">generate</span></span>  
 <span data-ttu-id="2a978-129">Spécifie que le GUID généré par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être utilisé pour cette colonne de l'opération de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="2a978-129">Specifies that the GUID generated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] be used for that column in the update operation.</span></span>  
  
 <span data-ttu-id="2a978-130">useValue</span><span class="sxs-lookup"><span data-stu-id="2a978-130">useValue</span></span>  
 <span data-ttu-id="2a978-131">Spécifie que la valeur spécifiée dans le code de mise à jour (updategram) doit être utilisée pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="2a978-131">Specifies that the value specified in the updategram be used for the column.</span></span> <span data-ttu-id="2a978-132">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2a978-132">This is the default value.</span></span>  
  
  
