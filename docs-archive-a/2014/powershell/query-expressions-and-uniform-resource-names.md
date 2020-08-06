---
title: Expressions de requête et noms URN | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604605"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="c29c8-102">Expressions de requête et noms URN</span><span class="sxs-lookup"><span data-stu-id="c29c8-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="c29c8-103">Les modèles SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Objects) et les composants logiciels enfichables [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell utilisent deux types de chaînes d’expression semblables aux expressions XPath.</span><span class="sxs-lookup"><span data-stu-id="c29c8-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="c29c8-104">Les expressions de requête sont des chaînes qui spécifient un jeu de critères permettant d'énumérer un ou plusieurs objets dans une hiérarchie de modèle objet.</span><span class="sxs-lookup"><span data-stu-id="c29c8-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="c29c8-105">Un nom de ressource unique (URN) est un type spécifique de chaîne d'expression de requête qui identifie de façon unique un objet particulier.</span><span class="sxs-lookup"><span data-stu-id="c29c8-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29c8-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c29c8-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c29c8-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="c29c8-107">Arguments</span></span>  
 <span data-ttu-id="c29c8-108">*Object*</span><span class="sxs-lookup"><span data-stu-id="c29c8-108">*Object*</span></span>  
 <span data-ttu-id="c29c8-109">Spécifie le type d'objet qui est représenté au niveau de ce nœud par la chaîne d'expression.</span><span class="sxs-lookup"><span data-stu-id="c29c8-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="c29c8-110">Chaque objet représente une classe de collection à partir de ces espaces de noms du modèle objet SMO :</span><span class="sxs-lookup"><span data-stu-id="c29c8-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="c29c8-111">Par exemple, spécifiez Server pour la classe **ServerCollection** et Database pour la classe **DatabaseCollection** .</span><span class="sxs-lookup"><span data-stu-id="c29c8-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="c29c8-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="c29c8-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="c29c8-113">Spécifie le nom de l’une des propriétés de la classe associée à l’objet spécifié dans *Object*.</span><span class="sxs-lookup"><span data-stu-id="c29c8-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="c29c8-114">Le nom de la propriété doit avoir pour préfixe le caractère \@.</span><span class="sxs-lookup"><span data-stu-id="c29c8-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="c29c8-115">Par exemple, spécifiez \@IsAnsiNull pour la propriété de classe **Database\*\*\*\*IsAnsiNull**.</span><span class="sxs-lookup"><span data-stu-id="c29c8-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="c29c8-116">\@*BooleanPropertyName*=true()</span><span class="sxs-lookup"><span data-stu-id="c29c8-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="c29c8-117">Énumère tous les objets où la propriété booléenne spécifiée a la valeur TRUE.</span><span class="sxs-lookup"><span data-stu-id="c29c8-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="c29c8-118">\@*BooleanPropertyName*=false()</span><span class="sxs-lookup"><span data-stu-id="c29c8-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="c29c8-119">Énumère tous les objets où la propriété booléenne spécifiée a la valeur FALSE.</span><span class="sxs-lookup"><span data-stu-id="c29c8-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="c29c8-120">contains(\@*StringPropertyName*, '*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="c29c8-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="c29c8-121">Énumère tous les objets où la propriété de chaîne spécifiée contient au moins une occurrence du jeu de caractères spécifié dans '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="c29c8-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="c29c8-122">\@*StringPropertyName*='*PatternString*'</span><span class="sxs-lookup"><span data-stu-id="c29c8-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="c29c8-123">Énumère tous les objets où la valeur de la propriété de chaîne spécifiée est identique au modèle de caractère spécifié dans '*PatternString*'.</span><span class="sxs-lookup"><span data-stu-id="c29c8-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="c29c8-124">\@*DatePropertyName*= datetime('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="c29c8-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="c29c8-125">Énumère tous les objets où la valeur de la propriété de date spécifiée correspond à la date spécifiée dans '*DateString*'.</span><span class="sxs-lookup"><span data-stu-id="c29c8-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="c29c8-126">*DateString* doit être au format aaaa-mm-jj hh:mi:ss.mmm.</span><span class="sxs-lookup"><span data-stu-id="c29c8-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c29c8-127">aaaa</span><span class="sxs-lookup"><span data-stu-id="c29c8-127">yyyy</span></span>|<span data-ttu-id="c29c8-128">Année à quatre chiffres.</span><span class="sxs-lookup"><span data-stu-id="c29c8-128">Four digit year.</span></span>|  
|<span data-ttu-id="c29c8-129">MM</span><span class="sxs-lookup"><span data-stu-id="c29c8-129">mm</span></span>|<span data-ttu-id="c29c8-130">Mois à deux chiffres (01 à 12).</span><span class="sxs-lookup"><span data-stu-id="c29c8-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="c29c8-131">jj</span><span class="sxs-lookup"><span data-stu-id="c29c8-131">dd</span></span>|<span data-ttu-id="c29c8-132">Date à deux chiffres (01 à 31).</span><span class="sxs-lookup"><span data-stu-id="c29c8-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="c29c8-133">hh</span><span class="sxs-lookup"><span data-stu-id="c29c8-133">hh</span></span>|<span data-ttu-id="c29c8-134">Heure à deux chiffres au format 24 heures (01 à 23).</span><span class="sxs-lookup"><span data-stu-id="c29c8-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="c29c8-135">mi</span><span class="sxs-lookup"><span data-stu-id="c29c8-135">mi</span></span>|<span data-ttu-id="c29c8-136">Minutes à deux chiffres (01 à 59).</span><span class="sxs-lookup"><span data-stu-id="c29c8-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="c29c8-137">ss</span><span class="sxs-lookup"><span data-stu-id="c29c8-137">ss</span></span>|<span data-ttu-id="c29c8-138">Secondes à deux chiffres (01 à 59).</span><span class="sxs-lookup"><span data-stu-id="c29c8-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="c29c8-139">mmm</span><span class="sxs-lookup"><span data-stu-id="c29c8-139">mmm</span></span>|<span data-ttu-id="c29c8-140">Nombre de millisecondes (001 à 999).</span><span class="sxs-lookup"><span data-stu-id="c29c8-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="c29c8-141">Les dates spécifiées dans ce format peuvent être évaluées par rapport à tout format de date stocké dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c29c8-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c29c8-142">is_null(\@*PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="c29c8-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="c29c8-143">Énumère tous les objets où la propriété spécifiée a la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="c29c8-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="c29c8-144">Not ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="c29c8-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="c29c8-145">Inverse la valeur d’évaluation de *PropertyExpression*, énumérant tous les objets qui ne correspondent pas à la condition spécifiée dans *PropertyExpression*.</span><span class="sxs-lookup"><span data-stu-id="c29c8-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="c29c8-146">Par exemple, not(contains(\@Name, 'xyz')) énumère tous les objets dont le nom ne contient pas la chaîne xyz.</span><span class="sxs-lookup"><span data-stu-id="c29c8-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c29c8-147">Notes</span><span class="sxs-lookup"><span data-stu-id="c29c8-147">Remarks</span></span>  
 <span data-ttu-id="c29c8-148">Les expressions de requête sont des chaînes qui énumèrent les nœuds dans une hiérarchie de modèle SMO.</span><span class="sxs-lookup"><span data-stu-id="c29c8-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="c29c8-149">Chaque nœud possède une expression de filtre qui spécifie les critères pour déterminer les objets qui sont énumérés au niveau de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="c29c8-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="c29c8-150">Les expressions de requête sont modélisées sur le langage d'expression XPath.</span><span class="sxs-lookup"><span data-stu-id="c29c8-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="c29c8-151">Les expressions de requête implémentent un petit sous-ensemble des expressions qui sont prises en charge par XPath, et possèdent également quelques extensions qui ne sont pas présentes dans XPath.</span><span class="sxs-lookup"><span data-stu-id="c29c8-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="c29c8-152">Les expressions XPath sont des chaînes qui spécifient un jeu de critères utilisé pour énumérer une ou plusieurs balises dans un document XML.</span><span class="sxs-lookup"><span data-stu-id="c29c8-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="c29c8-153">Pour plus d'informations sur XPath, consultez [W3C XPath Language](http://www.w3.org/TR/xpath20/)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="c29c8-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="c29c8-154">Les expressions de requête doivent commencer par une référence absolue à l'objet serveur.</span><span class="sxs-lookup"><span data-stu-id="c29c8-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="c29c8-155">Les expressions relatives avec une barre oblique (/) de début ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="c29c8-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="c29c8-156">La séquence des objets spécifiés dans une expression de requête doit respecter la hiérarchie des objets de collection dans le modèle objet associé.</span><span class="sxs-lookup"><span data-stu-id="c29c8-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="c29c8-157">Par exemple, une expression de requête qui fait référence à des objets dans l'espace de noms Microsoft.SqlServer.Management.Smo doit commencer par un nœud Server, suivi d'un nœud Database, etc.</span><span class="sxs-lookup"><span data-stu-id="c29c8-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="c29c8-158">Si un *\<FilterExpression>* n’est pas spécifié pour un objet, tous les objets au niveau de ce nœud sont énumérés.</span><span class="sxs-lookup"><span data-stu-id="c29c8-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="c29c8-159">URN (Uniform Resource Name)</span><span class="sxs-lookup"><span data-stu-id="c29c8-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="c29c8-160">Les noms URN sont un sous-ensemble d'expressions de requête.</span><span class="sxs-lookup"><span data-stu-id="c29c8-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="c29c8-161">Chaque nom URN forme une référence complète à un objet unique.</span><span class="sxs-lookup"><span data-stu-id="c29c8-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="c29c8-162">Un nom URN type utilise la propriété Name pour identifier un objet unique au niveau de chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="c29c8-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="c29c8-163">Par exemple, ce nom URN fait référence à une colonne spécifique :</span><span class="sxs-lookup"><span data-stu-id="c29c8-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="c29c8-164">Exemples</span><span class="sxs-lookup"><span data-stu-id="c29c8-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="c29c8-165">R.</span><span class="sxs-lookup"><span data-stu-id="c29c8-165">A.</span></span> <span data-ttu-id="c29c8-166">Énumération d'objets à l'aide de false()</span><span class="sxs-lookup"><span data-stu-id="c29c8-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="c29c8-167">Cette expression de requête énumère toutes les bases de données dont l’attribut **AutoClose** a la valeur false dans l’instance par défaut sur **MyComputer**.</span><span class="sxs-lookup"><span data-stu-id="c29c8-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="c29c8-168">B.</span><span class="sxs-lookup"><span data-stu-id="c29c8-168">B.</span></span> <span data-ttu-id="c29c8-169">Énumération d'objets à l'aide de contains</span><span class="sxs-lookup"><span data-stu-id="c29c8-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="c29c8-170">Cette expression de requête énumère toutes les bases de données qui ne respectent pas la casse et dont le nom comporte le caractère « m ».</span><span class="sxs-lookup"><span data-stu-id="c29c8-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="c29c8-171">C.</span><span class="sxs-lookup"><span data-stu-id="c29c8-171">C.</span></span> <span data-ttu-id="c29c8-172">Énumération d'objets à l'aide de not</span><span class="sxs-lookup"><span data-stu-id="c29c8-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="c29c8-173">Cette expression de requête énumère toutes les tables [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] qui ne figurent pas dans le schéma **Production** et qui contiennent le mot History dans le nom de la table :</span><span class="sxs-lookup"><span data-stu-id="c29c8-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="c29c8-174">D.</span><span class="sxs-lookup"><span data-stu-id="c29c8-174">D.</span></span> <span data-ttu-id="c29c8-175">Non-spécification d'une expression de filtre pour le dernier nœud</span><span class="sxs-lookup"><span data-stu-id="c29c8-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="c29c8-176">Cette expression de requête énumère toutes les colonnes dans la table **AdventureWorks2012.Sales.SalesPerson** :</span><span class="sxs-lookup"><span data-stu-id="c29c8-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="c29c8-177">E.</span><span class="sxs-lookup"><span data-stu-id="c29c8-177">E.</span></span> <span data-ttu-id="c29c8-178">Énumération d'objets à l'aide de datetime</span><span class="sxs-lookup"><span data-stu-id="c29c8-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="c29c8-179">Cette expression de requête énumère toutes les tables créées dans la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] à une heure spécifique :</span><span class="sxs-lookup"><span data-stu-id="c29c8-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="c29c8-180">F.</span><span class="sxs-lookup"><span data-stu-id="c29c8-180">F.</span></span> <span data-ttu-id="c29c8-181">Énumération d'objets à l'aide de is_null</span><span class="sxs-lookup"><span data-stu-id="c29c8-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="c29c8-182">Cette expression de requête énumère toutes les tables dans la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] dont la propriété de date de dernière modification n'a pas la valeur NULL :</span><span class="sxs-lookup"><span data-stu-id="c29c8-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="c29c8-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c29c8-183">See Also</span></span>  
 <span data-ttu-id="c29c8-184">[Applet de commande Invoke-PolicyEvaluation](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="c29c8-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="c29c8-185">SQL Server Audit &#40moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="c29c8-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
