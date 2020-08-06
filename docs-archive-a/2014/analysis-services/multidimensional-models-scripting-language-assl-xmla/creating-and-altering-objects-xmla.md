---
title: Création et modification d’objets (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613191"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="4a848-102">Création et modification d'objets (XMLA)</span><span class="sxs-lookup"><span data-stu-id="4a848-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="4a848-103">Les objets principaux peuvent être créés, modifiés et supprimés de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="4a848-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="4a848-104">Les objets principaux se composent notamment des objets suivants :</span><span class="sxs-lookup"><span data-stu-id="4a848-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="4a848-105">Serveurs</span><span class="sxs-lookup"><span data-stu-id="4a848-105">Servers</span></span>  
  
-   <span data-ttu-id="4a848-106">Bases de données</span><span class="sxs-lookup"><span data-stu-id="4a848-106">Databases</span></span>  
  
-   <span data-ttu-id="4a848-107">Dimensions</span><span class="sxs-lookup"><span data-stu-id="4a848-107">Dimensions</span></span>  
  
-   <span data-ttu-id="4a848-108">Cubes</span><span class="sxs-lookup"><span data-stu-id="4a848-108">Cubes</span></span>  
  
-   <span data-ttu-id="4a848-109">les groupes de mesures ;</span><span class="sxs-lookup"><span data-stu-id="4a848-109">Measure groups</span></span>  
  
-   <span data-ttu-id="4a848-110">Partitions</span><span class="sxs-lookup"><span data-stu-id="4a848-110">Partitions</span></span>  
  
-   <span data-ttu-id="4a848-111">Perspectives</span><span class="sxs-lookup"><span data-stu-id="4a848-111">Perspectives</span></span>  
  
-   <span data-ttu-id="4a848-112">Modèles d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="4a848-112">Mining models</span></span>  
  
-   <span data-ttu-id="4a848-113">Rôles</span><span class="sxs-lookup"><span data-stu-id="4a848-113">Roles</span></span>  
  
-   <span data-ttu-id="4a848-114">Commandes associées à un serveur ou à une base de données</span><span class="sxs-lookup"><span data-stu-id="4a848-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="4a848-115">Sources de données</span><span class="sxs-lookup"><span data-stu-id="4a848-115">Data sources</span></span>  
  
 <span data-ttu-id="4a848-116">Vous utilisez la commande [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) pour créer un objet principal sur une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , et la commande [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) pour modifier un objet principal existant sur une instance.</span><span class="sxs-lookup"><span data-stu-id="4a848-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="4a848-117">Les deux commandes sont exécutées à l’aide de la méthode [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="4a848-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="4a848-118">Création d'objets</span><span class="sxs-lookup"><span data-stu-id="4a848-118">Creating Objects</span></span>  
 <span data-ttu-id="4a848-119">Lorsque vous créez des objets à l'aide de la méthode `Create`, vous devez tout d'abord identifier l'objet parent qui contient l'objet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à créer.</span><span class="sxs-lookup"><span data-stu-id="4a848-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="4a848-120">Vous identifiez l’objet parent en fournissant une référence d’objet dans la propriété [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) de la `Create` commande.</span><span class="sxs-lookup"><span data-stu-id="4a848-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="4a848-121">Chaque référence d'objet contient les identificateurs d'objet nécessaires pour identifier de manière unique l'objet parent pour la commande `Create`.</span><span class="sxs-lookup"><span data-stu-id="4a848-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="4a848-122">Pour plus d’informations sur les références d’objets, consultez [définition et identification d’objets &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="4a848-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="4a848-123">Par exemple, vous devez fournir une référence d'objet à un cube pour créer un groupe de mesures pour le cube.</span><span class="sxs-lookup"><span data-stu-id="4a848-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="4a848-124">La référence d'objet pour le cube dans la propriété `ParentObject` contient à la fois un identificateur de base de données et un identificateur de cube, car le même identificateur de cube peut très bien être utilisé dans une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="4a848-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="4a848-125">L’élément [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) contient des éléments ASSL (Analysis Services Scripting Language) qui définissent l’objet principal à créer.</span><span class="sxs-lookup"><span data-stu-id="4a848-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="4a848-126">Pour plus d’informations sur ASSL, consultez [développement avec le langage de script Analysis Services &#40;&#41;ASSL ](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="4a848-127">Si vous définissez l'attribut `AllowOverwrite` de la commande `Create` à true, vous pouvez remplacer un objet principal existant associé à l'identificateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="4a848-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="4a848-128">Sinon, une erreur se produit si un objet principal associé à l'identificateur spécifié existe déjà dans l'objet parent.</span><span class="sxs-lookup"><span data-stu-id="4a848-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="4a848-129">Pour plus d’informations sur la `Create` commande, consultez [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="4a848-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="4a848-130">Création d'objets de session</span><span class="sxs-lookup"><span data-stu-id="4a848-130">Creating Session Objects</span></span>  
 <span data-ttu-id="4a848-131">Les objets de session sont des objets temporaires disponibles uniquement pour la session explicite ou implicite utilisée par une application cliente et qui sont supprimés à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="4a848-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="4a848-132">Vous pouvez créer des objets de session en affectant `Scope` à l’attribut de la commande la valeur `Create` *session*.</span><span class="sxs-lookup"><span data-stu-id="4a848-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a848-133">Lors de l’utilisation du paramètre de *session* , l' `ObjectDefinition` élément peut contenir uniquement des éléments [dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)ou [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL.</span><span class="sxs-lookup"><span data-stu-id="4a848-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="4a848-134">Modification d'objets</span><span class="sxs-lookup"><span data-stu-id="4a848-134">Altering Objects</span></span>  
 <span data-ttu-id="4a848-135">Lorsque vous modifiez des objets à l’aide de la `Alter` méthode, vous devez d’abord identifier l’objet à modifier en fournissant une référence d’objet dans la propriété d' [objet](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) de la `Alter` commande.</span><span class="sxs-lookup"><span data-stu-id="4a848-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="4a848-136">Chaque référence d'objet contient les identificateurs d'objet nécessaires pour identifier de manière unique l'objet pour la commande `Alter`.</span><span class="sxs-lookup"><span data-stu-id="4a848-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="4a848-137">Pour plus d’informations sur les références d’objets, consultez [définition et identification d’objets &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="4a848-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="4a848-138">Par exemple, vous devez fournir une référence d'objet à un cube pour modifier la structure de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="4a848-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="4a848-139">La référence d'objet pour le cube dans la propriété `Object` contient à la fois un identificateur de base de données et un identificateur de cube, car le même identificateur de cube peut très bien être utilisé dans une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="4a848-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="4a848-140">L'élément `ObjectDefinition` contient des éléments ASSL qui définissent l'objet principal à modifier.</span><span class="sxs-lookup"><span data-stu-id="4a848-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="4a848-141">Pour plus d’informations sur ASSL, consultez [développement avec le langage de script Analysis Services &#40;&#41;ASSL ](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="4a848-142">Si vous définissez l'attribut `AllowCreate` de la commande `Alter` à true, vous pouvez créer l'objet principal spécifié si l'objet n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="4a848-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="4a848-143">Sinon, une erreur se produit si un objet principal spécifié n'existe pas déjà.</span><span class="sxs-lookup"><span data-stu-id="4a848-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="4a848-144">Utilisation de l'attribut ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="4a848-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="4a848-145">Si vous modifiez uniquement les propriétés de l’objet principal et que vous ne redéfinissez pas les objets secondaires contenus dans l’objet principal, vous pouvez définir l' `ObjectExpansion` attribut de la `Alter` commande sur *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="4a848-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="4a848-146">La propriété `ObjectDefinition` ne doit donc contenir que les éléments relatifs aux propriétés de l'objet principal, et la commande `Alter` laisse les objets secondaires associés à l'objet principal inchangés.</span><span class="sxs-lookup"><span data-stu-id="4a848-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="4a848-147">Pour redéfinir des objets mineurs pour un objet principal, vous devez affecter à l’attribut la valeur `ObjectExpansion` *ExpandFull* et la définition de l’objet doit inclure tous les objets secondaires contenus dans l’objet principal.</span><span class="sxs-lookup"><span data-stu-id="4a848-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="4a848-148">Si la propriété `ObjectDefinition` de la commande `Alter` n'inclut pas explicitement un objet secondaire contenu dans l'objet principal, cet objet secondaire est supprimé.</span><span class="sxs-lookup"><span data-stu-id="4a848-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="4a848-149">Modification d'objets de session</span><span class="sxs-lookup"><span data-stu-id="4a848-149">Altering Session Objects</span></span>  
 <span data-ttu-id="4a848-150">Pour modifier les objets de session créés par la `Create` commande, affectez `Scope` à l’attribut de la commande la valeur `Alter` *session*.</span><span class="sxs-lookup"><span data-stu-id="4a848-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a848-151">Lors de l’utilisation du paramètre de *session* , l' `ObjectDefinition` élément peut contenir uniquement des éléments [dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)ou [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL.</span><span class="sxs-lookup"><span data-stu-id="4a848-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="4a848-152">Création ou modification d'objets subordonnés</span><span class="sxs-lookup"><span data-stu-id="4a848-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="4a848-153">Bien qu'une commande `Create` ou `Alter` ne crée ou ne modifie qu'un seul objet principal de niveau supérieur, l'objet principal ainsi créé ou modifié peut contenir des définitions dans la propriété `ObjectDefinition` englobante pour les autres objets principaux ou secondaires qui lui sont subordonnés.</span><span class="sxs-lookup"><span data-stu-id="4a848-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="4a848-154">Par exemple, si vous définissez un cube, vous spécifiez la base de données parente dans `ParentObject`. Ensuite, dans la propriété de la définition du cube `ObjectDefinition`, vous pouvez définir des groupes de mesures pour le cube et, dans chaque groupe de mesures, vous pouvez définir des partitions.</span><span class="sxs-lookup"><span data-stu-id="4a848-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="4a848-155">Un objet secondaire ne peut être défini que sous l'objet principal qui le contient.</span><span class="sxs-lookup"><span data-stu-id="4a848-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="4a848-156">Pour plus d’informations sur les objets principaux et secondaires, consultez [objets de base de données &#40;Analysis Services-&#41;de données multidimensionnelles ](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="4a848-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4a848-157">Exemples</span><span class="sxs-lookup"><span data-stu-id="4a848-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="4a848-158">Description</span><span class="sxs-lookup"><span data-stu-id="4a848-158">Description</span></span>  
 <span data-ttu-id="4a848-159">L’exemple suivant crée une source de données relationnelle qui fait référence à l' [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] exemple [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de base de données.</span><span class="sxs-lookup"><span data-stu-id="4a848-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4a848-160">Code</span><span class="sxs-lookup"><span data-stu-id="4a848-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="4a848-161">Description</span><span class="sxs-lookup"><span data-stu-id="4a848-161">Description</span></span>  
 <span data-ttu-id="4a848-162">L'exemple suivant modifie la source de données relationnelle créée dans l'exemple précédent pour définir le délai d'expiration de requête de la source de données à 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="4a848-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4a848-163">Code</span><span class="sxs-lookup"><span data-stu-id="4a848-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="4a848-164">Commentaires</span><span class="sxs-lookup"><span data-stu-id="4a848-164">Comments</span></span>  
 <span data-ttu-id="4a848-165">L' `ObjectExpansion` attribut de la `Alter` commande a été défini sur *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="4a848-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="4a848-166">Ce paramètre permet à l’élément [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) , un objet mineur, d’être exclu de la source de données définie dans `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="4a848-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="4a848-167">Par conséquent, les informations d'emprunt d'identité de cette source de données restent définies sur le compte de service, comme spécifié dans le premier exemple.</span><span class="sxs-lookup"><span data-stu-id="4a848-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a848-168">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a848-168">See Also</span></span>  
 <span data-ttu-id="4a848-169">[Méthode Execute &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="4a848-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="4a848-170">[Développement avec le langage de script Analysis Services &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="4a848-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="4a848-171">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4a848-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
