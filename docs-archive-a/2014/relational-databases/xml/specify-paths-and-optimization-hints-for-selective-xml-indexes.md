---
title: Spécifier les chemins d’accès et les indicateurs d’optimisation des index XML sélectifs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 486ee339-165b-4aeb-b760-d2ba023d7d0a
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a9d683fe57d489fdb9922b53d2c5c6825835216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703967"
---
# <a name="specify-paths-and-optimization-hints-for-selective-xml-indexes"></a><span data-ttu-id="9b29b-102">Spécifier les chemins d'accès et les indicateurs d'optimisation des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="9b29b-102">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>
  <span data-ttu-id="9b29b-103">Cette rubrique explique comment spécifier les chemins d'accès de nœud à indexer et les indicateurs d'optimisation pour l'indexation lorsque vous créez ou modifiez des index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="9b29b-103">This topic describes how to specify node paths to index and optimization hints for indexing when you create or alter selective XML indexes.</span></span>  
  
 <span data-ttu-id="9b29b-104">Vous spécifiez les chemins d'accès de nœud et les indicateurs d'optimisation en même temps dans l'une des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b29b-104">You specify node paths and optimization hints at the same time in one of the following statements:</span></span>  
  
-   <span data-ttu-id="9b29b-105">Dans la clause **FOR** d’une instruction **CREATE** .</span><span class="sxs-lookup"><span data-stu-id="9b29b-105">In the **FOR** clause of a **CREATE** statement.</span></span> <span data-ttu-id="9b29b-106">Pour plus d’informations, consultez [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b29b-106">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
-   <span data-ttu-id="9b29b-107">Dans la clause **ADD** d’une instruction **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="9b29b-107">In the **ADD** clause of an **ALTER** statement.</span></span> <span data-ttu-id="9b29b-108">Pour plus d’informations, consultez [ALTER INDEX &#40;index XML sélectifs&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="9b29b-108">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="9b29b-109">Pour plus d’informations sur les index XML sélectifs, consultez [Index XML sélectifs &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="9b29b-109">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="understanding-xquery-and-sql-server-types-in-untyped-xml"></a><a name="untyped"></a> <span data-ttu-id="9b29b-110">Présentation des types XQuery et SQL Server en XML non typé</span><span class="sxs-lookup"><span data-stu-id="9b29b-110">Understanding XQuery and SQL Server Types in Untyped XML</span></span>  
 <span data-ttu-id="9b29b-111">Les index XML sélectifs prennent en charge deux systèmes de types : les types XQuery et les types [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b29b-111">Selective XML indexes support two type systems: XQuery types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="9b29b-112">Le chemin d'accès indexé peut être utilisé pour correspondre à une expression XQuery, ou pour correspondre au type de retour de la méthode value() de type de données XML.</span><span class="sxs-lookup"><span data-stu-id="9b29b-112">The indexed path can be used either to match an XQuery expression, or to match the return type of the value() method of the XML data type.</span></span>  
  
-   <span data-ttu-id="9b29b-113">Lorsqu'un chemin d'accès à indexer n'est pas annoté, ou est annoté avec le mot clé XQUERY, il correspond à une expression XQuery.</span><span class="sxs-lookup"><span data-stu-id="9b29b-113">When a path to index is not annotated, or is annotated with the XQUERY keyword, the path matches an XQuery expression.</span></span> <span data-ttu-id="9b29b-114">Il existe deux variantes des chemins d'accès de nœud annotés XQUERY :</span><span class="sxs-lookup"><span data-stu-id="9b29b-114">There are two variations for XQUERY-annotated node paths:</span></span>  
  
    -   <span data-ttu-id="9b29b-115">Si vous ne spécifiez pas le mot clé XQUERY et le type de données XQuery, des mappages par défaut sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="9b29b-115">If you do not specify the XQUERY keyword and the XQuery data type, then default mappings are used.</span></span> <span data-ttu-id="9b29b-116">En général, les performances et le stockage ne sont pas optimaux.</span><span class="sxs-lookup"><span data-stu-id="9b29b-116">Typically performance and storage are not optimal.</span></span>  
  
    -   <span data-ttu-id="9b29b-117">Si vous spécifiez le mot clé XQUERY et le type de données XQuery, et éventuellement d'autres indicateurs d'optimisation, vous pouvez obtenir de meilleures performances et le stockage le plus efficace possible.</span><span class="sxs-lookup"><span data-stu-id="9b29b-117">If you specify the XQUERY keyword and the XQuery data type, and optionally other optimization hints, then you can achieve the best possible performance and the most efficient possible storage.</span></span> <span data-ttu-id="9b29b-118">Toutefois, une conversion peut échouer.</span><span class="sxs-lookup"><span data-stu-id="9b29b-118">However, a cast can fail.</span></span>  
  
-   <span data-ttu-id="9b29b-119">Lorsqu'un chemin d'accès à indexer est annoté avec le mot clé SQL, le chemin d'accès correspond au type de retour de la méthode value() de type de données XML.</span><span class="sxs-lookup"><span data-stu-id="9b29b-119">When a path to index is annotated with the SQL keyword, the path matches the return type of the value() method of the XML data type.</span></span> <span data-ttu-id="9b29b-120">Spécifiez le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] approprié, qui est le type de retour attendue de la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-120">Specify the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, which is the return type that you expect from the value() method.</span></span>  
  
 <span data-ttu-id="9b29b-121">Il existe de légères variantes entre le système de type XML d'expressions XQuery et le système de type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appliqués à la méthode value() de type de données XML.</span><span class="sxs-lookup"><span data-stu-id="9b29b-121">There are subtle differences between the XQuery expressions XML type system and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type system applied to the value() method of the XML data type.</span></span> <span data-ttu-id="9b29b-122">Ces différences sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b29b-122">These differences include the following:</span></span>  
  
-   <span data-ttu-id="9b29b-123">Le système de type XQuery tient compte des espaces à droite.</span><span class="sxs-lookup"><span data-stu-id="9b29b-123">The XQuery type system is aware of trailing spaces.</span></span> <span data-ttu-id="9b29b-124">Par exemple, en fonction de la sémantique de type XQuery, les chaînes "abc" et "abc " sont différentes, alors que dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ces chaînes sont équivalentes.</span><span class="sxs-lookup"><span data-stu-id="9b29b-124">For example, according to XQuery type semantics, the strings "abc" and "abc " are not equal, while in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] these strings are equal.</span></span>  
  
-   <span data-ttu-id="9b29b-125">Les types de données à virgule flottante XQuery prennent en charge les valeurs spéciales +/- zéro et +/- infini.</span><span class="sxs-lookup"><span data-stu-id="9b29b-125">XQuery floating point data types support special values of +/- zero and +/- infinity.</span></span> <span data-ttu-id="9b29b-126">Ces valeurs spéciales ne sont pas prises en charge dans les types de données à virgule flottante [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b29b-126">These special values are not supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] floating point data types.</span></span>  
  
### <a name="xquery-types-in-untyped-xml"></a><span data-ttu-id="9b29b-127">Types XQuery en XML non typé</span><span class="sxs-lookup"><span data-stu-id="9b29b-127">XQuery Types in Untyped XML</span></span>  
  
-   <span data-ttu-id="9b29b-128">Les types XQuery correspondent aux expressions XQuery dans toutes les méthodes de type de données XML incluant la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-128">XQuery types match XQuery expressions in all methods of the XML data type including the value() method.</span></span>  
  
-   <span data-ttu-id="9b29b-129">Les types XQuery prennent en charge ces indicateurs d'optimisation : node(), SINGLETON, DATA TYPE et MAXLENGTH.</span><span class="sxs-lookup"><span data-stu-id="9b29b-129">XQuery types support these optimization hints: node(), SINGLETON, DATA TYPE, and MAXLENGTH.</span></span>  
  
 <span data-ttu-id="9b29b-130">Pour les expressions XQuery sur le XML non typé, vous pouvez choisir entre deux modes d'opération :</span><span class="sxs-lookup"><span data-stu-id="9b29b-130">For XQuery expressions over untyped XML, you can choose between two modes of operation:</span></span>  
  
-   <span data-ttu-id="9b29b-131">**Mode de mappage par défaut**.</span><span class="sxs-lookup"><span data-stu-id="9b29b-131">**Default mapping mode**.</span></span> <span data-ttu-id="9b29b-132">Dans ce mode, vous spécifiez uniquement le chemin d'accès lors de la création d'un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="9b29b-132">In this mode, you specify only the path when creating a selective XML index.</span></span>  
  
-   <span data-ttu-id="9b29b-133">**Mode de mappage défini par l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="9b29b-133">**User-specified mapping mode**.</span></span> <span data-ttu-id="9b29b-134">Dans ce mode, vous spécifiez le chemin d'accès et les indicateurs facultatifs d'optimisation.</span><span class="sxs-lookup"><span data-stu-id="9b29b-134">In this mode, you specify both the path and optional optimization hints.</span></span>  
  
 <span data-ttu-id="9b29b-135">Le mode de mappage par défaut utilise une option de stockage pessimiste qui est toujours sécurisée et générale.</span><span class="sxs-lookup"><span data-stu-id="9b29b-135">The default mapping mode uses a conservative storage option which is always safe and general.</span></span> <span data-ttu-id="9b29b-136">Il peut correspondre à n'importe quel type d'expression.</span><span class="sxs-lookup"><span data-stu-id="9b29b-136">It can match any expression type.</span></span> <span data-ttu-id="9b29b-137">Une limitation du mode de mappage par défaut est inférieure aux performances optimales, car un nombre accru de conversions d'exécution sont requis, et les index secondaires sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b29b-137">A limitation of the default mapping mode is less than optimal performance, because an increased number of runtime casts are required, and secondary indexes are not available.</span></span>  
  
 <span data-ttu-id="9b29b-138">Voici un exemple d'index XML sélectif créé avec les mappages par défaut.</span><span class="sxs-lookup"><span data-stu-id="9b29b-138">Here is an example of a selective XML index created with default mappings.</span></span> <span data-ttu-id="9b29b-139">Pour les trois chemins d’accès, le type de nœud par défaut (**xs:untypedAtomic**) et la cardinalité sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="9b29b-139">For all three paths, the default node type (**xs:untypedAtomic**) and cardinality are used.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_default  
ON Tbl(xmlcol)  
FOR  
(  
mypath01 =  '/a/b',  
mypath02 = '/a/b/c',  
mypath03 = '/a/b/d'  
)  
```  
  
 <span data-ttu-id="9b29b-140">Le mode de mappage défini par l'utilisateur vous permet de spécifier un type et une cardinalité du nœud pour obtenir de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="9b29b-140">The user-specified mapping mode lets you specify a type and cardinality for the node to obtain better performance.</span></span> <span data-ttu-id="9b29b-141">Toutefois, ces performances accrues sont obtenues au détriment de la sécurité, car une conversion peut échouer et en général seul le type spécifié est mis en correspondance avec l’index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="9b29b-141">However, this improved performance is achieved by giving up safety - because a cast can fail - and generality - because only the specified type is matched with the selective XML index.</span></span>  
  
 <span data-ttu-id="9b29b-142">Les types XQuery pris en charge pour le XML non typé sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9b29b-142">The XQuery types supported for untyped XML case are:</span></span>  
  
-   <span data-ttu-id="9b29b-143">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="9b29b-143">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="9b29b-144">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="9b29b-144">**xs:double**</span></span>  
  
-   <span data-ttu-id="9b29b-145">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="9b29b-145">**xs:string**</span></span>  
  
-   <span data-ttu-id="9b29b-146">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="9b29b-146">**xs:date**</span></span>  
  
-   <span data-ttu-id="9b29b-147">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="9b29b-147">**xs:time**</span></span>  
  
-   <span data-ttu-id="9b29b-148">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="9b29b-148">**xs:dateTime**</span></span>  
  
 <span data-ttu-id="9b29b-149">Si le type n’est pas spécifié, le nœud est du type de données **xs:untypedAtomic** par défaut.</span><span class="sxs-lookup"><span data-stu-id="9b29b-149">If the type is not specified, the node is assumed to be of the **xs:untypedAtomic** data type.</span></span>  
  
 <span data-ttu-id="9b29b-150">Vous pouvez optimiser l'index XML sélectif affiché de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="9b29b-150">You can optimize the selective XML index shown in the following manner:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_UX_optimized  
ON Tbl(xmlcol)  
FOR  
(  
mypath= '/a/b' as XQUERY 'node()',  
pathX = '/a/b/c' as XQUERY 'xs:double' SINGLETON,  
pathY = '/a/b/d' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
)  
-- mypath - Only the node value is needed; storage is saved.  
-- pathX - Performance is improved; secondary indexes are possible.  
-- pathY - Performance is improved; secondary indexes are possible; storage is saved.  
```  
  
### <a name="sql-server-types-in-untyped-xml"></a><span data-ttu-id="9b29b-151">Types SQL Server en XML non typé</span><span class="sxs-lookup"><span data-stu-id="9b29b-151">SQL Server Types in Untyped XML</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9b29b-152">Les types correspondent à la valeur de retour de la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-152">types match the return value of the value() method.</span></span>  
  
-   <span data-ttu-id="9b29b-153">Les types [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prennent en charge cet indicateur d’optimisation : SINGLETON.</span><span class="sxs-lookup"><span data-stu-id="9b29b-153">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types support this optimization hint: SINGLETON.</span></span>  
  
 <span data-ttu-id="9b29b-154">Spécifier un type est obligatoire pour les chemins d'accès qui retournent des types [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b29b-154">Specifying a type is mandatory for paths that return [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="9b29b-155">Utilisez le même type [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utiliseriez dans la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-155">Use the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type that you would use in the value() method.</span></span>  
  
 <span data-ttu-id="9b29b-156">Considérez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="9b29b-156">Consider the following query:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/d)[1]', 'NVARCHAR(200)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="9b29b-157">La requête spécifiée retourne une valeur du chemin d'accès `/a/b/d` compressé dans un type de données NVARCHAR(200). Ainsi, le type de données à spécifier pour le nœud est évident.</span><span class="sxs-lookup"><span data-stu-id="9b29b-157">The specified query returns a value from the path `/a/b/d` packed into an NVARCHAR(200) data type, so the data type to specify for the node is obvious.</span></span> <span data-ttu-id="9b29b-158">Néanmoins, il n'existe aucun schéma pour spécifier la cardinalité du nœud en XML non typé.</span><span class="sxs-lookup"><span data-stu-id="9b29b-158">However there is no schema to specify the cardinality of the node in untyped XML.</span></span> <span data-ttu-id="9b29b-159">Pour spécifier que le nœud `d` apparaît au plus une fois sous son nœud parent `b`, créez un index XML sélectif qui utilise l'indicateur d'optimisation de SINGLETON comme suit :</span><span class="sxs-lookup"><span data-stu-id="9b29b-159">To specify that node `d` appears at most once under its parent node `b`, create a selective XML index that uses the SINGLETON optimization hint as follows:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX example_sxi_US  
ON Tbl(xmlcol)  
FOR  
(  
node1223 = '/a/b/d' as SQL NVARCHAR(200) SINGLETON  
)  
```  
  

  
##  <a name="understanding-selective-xml-index-support-for-typed-xml"></a><a name="typed"></a> <span data-ttu-id="9b29b-160">Présentation de la prise en charge des index XML sélectifs pour le XML typé</span><span class="sxs-lookup"><span data-stu-id="9b29b-160">Understanding Selective XML Index support for typed XML</span></span>  
 <span data-ttu-id="9b29b-161">Le XML typé de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est un schéma associé à un document XML donné.</span><span class="sxs-lookup"><span data-stu-id="9b29b-161">Typed XML in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is a schema associated with a given XML document.</span></span> <span data-ttu-id="9b29b-162">Ce schéma définit la structure globale du document et les types de nœuds.</span><span class="sxs-lookup"><span data-stu-id="9b29b-162">The schema defines overall document structure and types of nodes.</span></span> <span data-ttu-id="9b29b-163">S'il existe un schéma, l'index XML sélectif applique la structure de schéma lorsque l'utilisateur promeut les chemins d'accès. Il est donc inutile de spécifier les types XQUERY pour les chemins d'accès.</span><span class="sxs-lookup"><span data-stu-id="9b29b-163">If a schema exists, Selective XML Index applies the schema structure when the user promotes paths, so there is no need to specify the XQUERY types for paths.</span></span>  
  
 <span data-ttu-id="9b29b-164">Les index XML sélectifs prennent en charge les types XSD suivants :</span><span class="sxs-lookup"><span data-stu-id="9b29b-164">Selective XML Index supports following XSD types:</span></span>  
  
-   <span data-ttu-id="9b29b-165">**xs:anyUri**</span><span class="sxs-lookup"><span data-stu-id="9b29b-165">**xs:anyUri**</span></span>  
  
-   <span data-ttu-id="9b29b-166">**xs:boolean**</span><span class="sxs-lookup"><span data-stu-id="9b29b-166">**xs:boolean**</span></span>  
  
-   <span data-ttu-id="9b29b-167">**xs:date**</span><span class="sxs-lookup"><span data-stu-id="9b29b-167">**xs:date**</span></span>  
  
-   <span data-ttu-id="9b29b-168">**xs:dateTime**</span><span class="sxs-lookup"><span data-stu-id="9b29b-168">**xs:dateTime**</span></span>  
  
-   <span data-ttu-id="9b29b-169">**xs:day**</span><span class="sxs-lookup"><span data-stu-id="9b29b-169">**xs:day**</span></span>  
  
-   <span data-ttu-id="9b29b-170">**xs:decimal**</span><span class="sxs-lookup"><span data-stu-id="9b29b-170">**xs:decimal**</span></span>  
  
-   <span data-ttu-id="9b29b-171">**xs:double**</span><span class="sxs-lookup"><span data-stu-id="9b29b-171">**xs:double**</span></span>  
  
-   <span data-ttu-id="9b29b-172">**xs:float**</span><span class="sxs-lookup"><span data-stu-id="9b29b-172">**xs:float**</span></span>  
  
-   <span data-ttu-id="9b29b-173">**xs:int**</span><span class="sxs-lookup"><span data-stu-id="9b29b-173">**xs:int**</span></span>  
  
-   <span data-ttu-id="9b29b-174">**xs:integer**</span><span class="sxs-lookup"><span data-stu-id="9b29b-174">**xs:integer**</span></span>  
  
-   <span data-ttu-id="9b29b-175">**xs:language**</span><span class="sxs-lookup"><span data-stu-id="9b29b-175">**xs:language**</span></span>  
  
-   <span data-ttu-id="9b29b-176">**xs:long**</span><span class="sxs-lookup"><span data-stu-id="9b29b-176">**xs:long**</span></span>  
  
-   <span data-ttu-id="9b29b-177">**xs:name**</span><span class="sxs-lookup"><span data-stu-id="9b29b-177">**xs:name**</span></span>  
  
-   <span data-ttu-id="9b29b-178">**xs:NCName**</span><span class="sxs-lookup"><span data-stu-id="9b29b-178">**xs:NCName**</span></span>  
  
-   <span data-ttu-id="9b29b-179">**xs:negativeInteger**</span><span class="sxs-lookup"><span data-stu-id="9b29b-179">**xs:negativeInteger**</span></span>  
  
-   <span data-ttu-id="9b29b-180">**xs:nmtoken**</span><span class="sxs-lookup"><span data-stu-id="9b29b-180">**xs:nmtoken**</span></span>  
  
-   <span data-ttu-id="9b29b-181">**xs:nonNegativeInteger**</span><span class="sxs-lookup"><span data-stu-id="9b29b-181">**xs:nonNegativeInteger**</span></span>  
  
-   <span data-ttu-id="9b29b-182">**xs:nonPositiveInteger**</span><span class="sxs-lookup"><span data-stu-id="9b29b-182">**xs:nonPositiveInteger**</span></span>  
  
-   <span data-ttu-id="9b29b-183">**xs:positiveInteger**</span><span class="sxs-lookup"><span data-stu-id="9b29b-183">**xs:positiveInteger**</span></span>  
  
-   <span data-ttu-id="9b29b-184">**xs:qname**</span><span class="sxs-lookup"><span data-stu-id="9b29b-184">**xs:qname**</span></span>  
  
-   <span data-ttu-id="9b29b-185">**xs:short**</span><span class="sxs-lookup"><span data-stu-id="9b29b-185">**xs:short**</span></span>  
  
-   <span data-ttu-id="9b29b-186">**xs:string**</span><span class="sxs-lookup"><span data-stu-id="9b29b-186">**xs:string**</span></span>  
  
-   <span data-ttu-id="9b29b-187">**xs:time**</span><span class="sxs-lookup"><span data-stu-id="9b29b-187">**xs:time**</span></span>  
  
-   <span data-ttu-id="9b29b-188">**xs:token**</span><span class="sxs-lookup"><span data-stu-id="9b29b-188">**xs:token**</span></span>  
  
-   <span data-ttu-id="9b29b-189">**xs:unsignedByte**</span><span class="sxs-lookup"><span data-stu-id="9b29b-189">**xs:unsignedByte**</span></span>  
  
-   <span data-ttu-id="9b29b-190">**xs:unsignedInt**</span><span class="sxs-lookup"><span data-stu-id="9b29b-190">**xs:unsignedInt**</span></span>  
  
-   <span data-ttu-id="9b29b-191">**xs:unsignedLong**</span><span class="sxs-lookup"><span data-stu-id="9b29b-191">**xs:unsignedLong**</span></span>  
  
-   <span data-ttu-id="9b29b-192">**xs:unsignedShort**</span><span class="sxs-lookup"><span data-stu-id="9b29b-192">**xs:unsignedShort**</span></span>  
  
 <span data-ttu-id="9b29b-193">Lorsque l'index XML sélectif est créé sur un document contenant le schéma qui lui est associé, la spécification d'un type XQUERY lors de la création ou de la modification d'un index retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="9b29b-193">When Selective XML Index is created over a document that has schema associated with it, specifying a XQUERY type at index creation or altering returns an error.</span></span> <span data-ttu-id="9b29b-194">L'utilisateur peut utiliser des annotations de type SQL dans le cadre de la promotion de chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="9b29b-194">The user can use SQL type annotations in the path promotion part.</span></span> <span data-ttu-id="9b29b-195">Le type SQL doit être une conversion valide du type XSD défini dans le schéma, sinon une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="9b29b-195">The SQL type must be a valid conversion from the XSD type defined in the schema, or an error is thrown.</span></span> <span data-ttu-id="9b29b-196">Tous les types SQL disposant des performances adéquates dans le schéma XSD sont pris en charge, sauf les types date/heure.</span><span class="sxs-lookup"><span data-stu-id="9b29b-196">All SQL types that have adequate representation in XSD are supported, with an exception of date/time types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b29b-197">L'index sélectif est utilisé si le type spécifié dans la promotion de chemin d'accès d'index XML sélectif est identique à la valeur retournée par la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-197">The selective index is used if the type specified in the Selective XML Index path promotion is the same as the value() method return value.</span></span>  
  
 <span data-ttu-id="9b29b-198">Les indicateurs d'optimisation suivants peuvent être utilisés avec des documents XML typés :</span><span class="sxs-lookup"><span data-stu-id="9b29b-198">The following optimization hints can be used with typed XML documents:</span></span>  
  
-   <span data-ttu-id="9b29b-199">indicateur d'optimisation node().</span><span class="sxs-lookup"><span data-stu-id="9b29b-199">node() optimization hint.</span></span>  
  
-   <span data-ttu-id="9b29b-200">L'indicateur d'optimisation MAXLENGTH peut être utilisé avec types xs:string pour raccourcir la valeur indexée.</span><span class="sxs-lookup"><span data-stu-id="9b29b-200">MAXLENGTH optimization hint can be used with xs:string types to shorten the indexed value.</span></span>  
  
 <span data-ttu-id="9b29b-201">Pour plus d’informations sur les indicateurs d’optimisation, consultez [Spécification des indicateurs d’optimisation](#hints).</span><span class="sxs-lookup"><span data-stu-id="9b29b-201">For more information about optimization hints, see [Specifying Optimization Hints](#hints).</span></span>  
  
##  <a name="specifying-paths"></a><a name="paths"></a> <span data-ttu-id="9b29b-202">Spécification des chemins d'accès</span><span class="sxs-lookup"><span data-stu-id="9b29b-202">Specifying Paths</span></span>  
 <span data-ttu-id="9b29b-203">Un index XML sélectif vous permet d'indexer uniquement un sous-ensemble de nœuds de données XML stockées en rapport avec les requêtes que vous comptez exécuter.</span><span class="sxs-lookup"><span data-stu-id="9b29b-203">A selective XML index lets you index only a subset of nodes from the stored XML data that are relevant for the queries that you expect to run.</span></span> <span data-ttu-id="9b29b-204">Lorsque le sous-ensemble de nœuds appropriés est beaucoup plus petit que le nombre total de nœuds dans le document XML, l'index XML sélectif stocke uniquement les nœuds appropriés.</span><span class="sxs-lookup"><span data-stu-id="9b29b-204">When the subset of relevant nodes is much smaller than the total number of nodes in the XML document, the selective XML index stores only the relevant nodes.</span></span> <span data-ttu-id="9b29b-205">Pour bénéficier d'un index XML sélectif, identifiez le sous-ensemble correct de nœuds à indexer.</span><span class="sxs-lookup"><span data-stu-id="9b29b-205">To benefit from a selective XML index, identify the correct subset of nodes to index.</span></span>  
  
### <a name="choosing-the-nodes-to-index"></a><span data-ttu-id="9b29b-206">Sélection des nœuds à indexer</span><span class="sxs-lookup"><span data-stu-id="9b29b-206">Choosing the nodes to index</span></span>  
 <span data-ttu-id="9b29b-207">Vous pouvez utiliser les deux principes simples suivants pour identifier le sous-ensemble correct de nœuds à ajouter à un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="9b29b-207">You can use the following two simple principles to identify the correct subset of nodes to add to a selective XML index.</span></span>  
  
1.  <span data-ttu-id="9b29b-208">**Principe 1** : pour évaluer une expression XQuery donnée, indexez tous les nœuds que vous devez examiner.</span><span class="sxs-lookup"><span data-stu-id="9b29b-208">**Principle 1**: To evaluate a given XQuery expression, index all nodes that you need to examine.</span></span>  
  
    -   <span data-ttu-id="9b29b-209">Indexez tous les nœuds dont l'existence ou la valeur est utilisée dans l'expression XQuery.</span><span class="sxs-lookup"><span data-stu-id="9b29b-209">Index all nodes whose existence or value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="9b29b-210">Indexez tous les nœuds de l'expression XQuery sur laquelle les prédicats XQuery sont appliqués.</span><span class="sxs-lookup"><span data-stu-id="9b29b-210">Index all nodes in the XQuery expression on which XQuery predicates are applied.</span></span>  
  
     <span data-ttu-id="9b29b-211">Considérez la requête simple suivante sur [l’exemple de document XML](#sample) dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="9b29b-211">Consider the following simple query over the [sample XML document](#sample) in this topic:</span></span>  
  
    ```sql  
    SELECT T.record FROM myXMLTable T  
    WHERE T.xmldata.exist('/a/b[./c = "43"]') = 1  
    ```  
  
     <span data-ttu-id="9b29b-212">Pour retourner des instances XML qui satisfont cette requête, un index XML sélectif doit examiner deux nœuds dans chaque instance XML :</span><span class="sxs-lookup"><span data-stu-id="9b29b-212">In order to return the XML instances that satisfy this query, a selective XML index needs to examine two nodes in every XML instance:</span></span>  
  
    -   <span data-ttu-id="9b29b-213">Le nœud `c`, car sa valeur est utilisée dans l'expression XQuery.</span><span class="sxs-lookup"><span data-stu-id="9b29b-213">Node `c`, because its value is used in the XQuery expression.</span></span>  
  
    -   <span data-ttu-id="9b29b-214">Le nœud `b`, car un prédicat est appliqué sur le nœud`b` dans l'expression XQuery.</span><span class="sxs-lookup"><span data-stu-id="9b29b-214">Node `b`, because a predicate is applied over node`b` in the XQuery expression.</span></span>  
  
2.  <span data-ttu-id="9b29b-215">**Principe 2** : pour obtenir de meilleures performances, indexez tous les nœuds nécessaires pour évaluer une expression XQuery donnée.</span><span class="sxs-lookup"><span data-stu-id="9b29b-215">**Principle 2**: For best performance, index all nodes that are required to evaluate a given XQuery expression.</span></span> <span data-ttu-id="9b29b-216">Si vous indexez uniquement certains nœuds, l'index XML sélectif améliore l'évaluation des sous-expressions qui incluent uniquement les nœuds indexés.</span><span class="sxs-lookup"><span data-stu-id="9b29b-216">If you index only some of the nodes, then the selective XML index improves the evaluation of sub-expressions that include only indexed nodes.</span></span>  
  
 <span data-ttu-id="9b29b-217">Pour améliorer les performances de l'instruction SELECT ci-dessus, créez l'index XML sélectif suivant :</span><span class="sxs-lookup"><span data-stu-id="9b29b-217">To improve the performance of the SELECT statement shown above, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX simple_sxi  
ON Tbl(xmlcol)  
FOR  
(  
    path123 =  '/a/b',  
    path124 =  '/a/b/c'  
)  
```  
  
### <a name="indexing-identical-paths"></a><span data-ttu-id="9b29b-218">Indexation de chemins d'accès identiques</span><span class="sxs-lookup"><span data-stu-id="9b29b-218">Indexing identical paths</span></span>  
 <span data-ttu-id="9b29b-219">Vous ne pouvez pas promouvoir des chemins d'accès identiques de même type de données sous des noms de chemins d'accès différents.</span><span class="sxs-lookup"><span data-stu-id="9b29b-219">You cannot promote identical paths as the same data type under different path names.</span></span> <span data-ttu-id="9b29b-220">Par exemple, la requête suivante génère une erreur, car `pathOne` et `pathTwo` sont identiques :</span><span class="sxs-lookup"><span data-stu-id="9b29b-220">For example, the following query raises an error, because `pathOne` and `pathTwo` are identical:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:string',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
 <span data-ttu-id="9b29b-221">Toutefois, vous pouvez promouvoir des chemins d'accès de types de données différents avec des noms différents.</span><span class="sxs-lookup"><span data-stu-id="9b29b-221">However, you can promote identical paths as different data types with different names.</span></span> <span data-ttu-id="9b29b-222">Par exemple, la requête suivante est maintenant acceptable, car les types de données sont différents :</span><span class="sxs-lookup"><span data-stu-id="9b29b-222">For example, the following query is now acceptable, because the data types are different:</span></span>  
  
```sql  
CREATE SELECTIVE INDEX test_simple_sxi ON T1(xmlCol)  
FOR  
(  
    pathOne = 'book/authors/authorID' AS XQUERY 'xs:double',  
    pathTwo = 'book/authors/authorID' AS XQUERY 'xs:string'  
)  
```  
  
### <a name="examples"></a><span data-ttu-id="9b29b-223">Exemples</span><span class="sxs-lookup"><span data-stu-id="9b29b-223">Examples</span></span>  
 <span data-ttu-id="9b29b-224">Voici quelques exemples supplémentaires de sélection des nœuds appropriés pour indexer des types XQuery différents.</span><span class="sxs-lookup"><span data-stu-id="9b29b-224">Here are some additional examples of selecting the correct nodes to index for different XQuery types.</span></span>  
  
 <span data-ttu-id="9b29b-225">**Exemple 1**</span><span class="sxs-lookup"><span data-stu-id="9b29b-225">**Example 1**</span></span>  
  
 <span data-ttu-id="9b29b-226">Voici une requête XQuery simple qui utilise la méthode exist() :</span><span class="sxs-lookup"><span data-stu-id="9b29b-226">Here is a simple XQuery that uses the exist() method:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e/h') = 1  
```  
  
 <span data-ttu-id="9b29b-227">Le tableau suivant indique les nœuds qui doivent être indexés pour laisser cette requête utiliser les index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="9b29b-227">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="9b29b-228">Nœd à inclure dans l'index</span><span class="sxs-lookup"><span data-stu-id="9b29b-228">Node to include in the index</span></span>|<span data-ttu-id="9b29b-229">Raison de l'indexation de ce nœud</span><span class="sxs-lookup"><span data-stu-id="9b29b-229">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="9b29b-230">**/a/b/c/d/e/h**</span><span class="sxs-lookup"><span data-stu-id="9b29b-230">**/a/b/c/d/e/h**</span></span>|<span data-ttu-id="9b29b-231">L'existence du nœud `h` est évaluée dans la méthode exist().</span><span class="sxs-lookup"><span data-stu-id="9b29b-231">The existence of node `h` is evaluated in the exist() method.</span></span>|  
  
 <span data-ttu-id="9b29b-232">**Exemple 2**</span><span class="sxs-lookup"><span data-stu-id="9b29b-232">**Example 2**</span></span>  
  
 <span data-ttu-id="9b29b-233">Voici une variation plus complexe de la requête XQuery précédente, avec un prédicat appliqué :</span><span class="sxs-lookup"><span data-stu-id="9b29b-233">Here is a more complex variation of the previous XQuery, with a predicate applied:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b/c/d/e[./f = "SQL"]') = 1  
```  
  
 <span data-ttu-id="9b29b-234">Le tableau suivant indique les nœuds qui doivent être indexés pour laisser cette requête utiliser les index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="9b29b-234">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="9b29b-235">Nœd à inclure dans l'index</span><span class="sxs-lookup"><span data-stu-id="9b29b-235">Node to include in the index</span></span>|<span data-ttu-id="9b29b-236">Raison de l'indexation de ce nœud</span><span class="sxs-lookup"><span data-stu-id="9b29b-236">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="9b29b-237">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="9b29b-237">**/a/b/c/d/e**</span></span>|<span data-ttu-id="9b29b-238">Un prédicat est appliqué sur le nœud `e`.</span><span class="sxs-lookup"><span data-stu-id="9b29b-238">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="9b29b-239">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="9b29b-239">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="9b29b-240">La valeur du nœud `f` est évaluée au sein du prédicat.</span><span class="sxs-lookup"><span data-stu-id="9b29b-240">The value of node `f` is evaluated inside the predicate.</span></span>|  
  
 <span data-ttu-id="9b29b-241">**Exemple 3**</span><span class="sxs-lookup"><span data-stu-id="9b29b-241">**Example 3**</span></span>  
  
 <span data-ttu-id="9b29b-242">Voici une requête plus complexe avec une clause value() :</span><span class="sxs-lookup"><span data-stu-id="9b29b-242">Here is a more complex query with a value() clause:</span></span>  
  
```sql  
SELECT T.record,  
    T.xmldata.value('(/a/b/c/d/e[./f = "SQL"]/g)[1]', 'nvarchar(100)')  
FROM myXMLTable T  
```  
  
 <span data-ttu-id="9b29b-243">Le tableau suivant indique les nœuds qui doivent être indexés pour laisser cette requête utiliser les index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="9b29b-243">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="9b29b-244">Nœd à inclure dans l'index</span><span class="sxs-lookup"><span data-stu-id="9b29b-244">Node to include in the index</span></span>|<span data-ttu-id="9b29b-245">Raison de l'indexation de ce nœud</span><span class="sxs-lookup"><span data-stu-id="9b29b-245">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="9b29b-246">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="9b29b-246">**/a/b/c/d/e**</span></span>|<span data-ttu-id="9b29b-247">Un prédicat est appliqué sur le nœud `e`.</span><span class="sxs-lookup"><span data-stu-id="9b29b-247">A predicate is applied over node `e`.</span></span>|  
|<span data-ttu-id="9b29b-248">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="9b29b-248">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="9b29b-249">La valeur du nœud `f` est évaluée au sein du prédicat.</span><span class="sxs-lookup"><span data-stu-id="9b29b-249">The value of node `f` is evaluated inside the predicate.</span></span>|  
|<span data-ttu-id="9b29b-250">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="9b29b-250">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="9b29b-251">La valeur du nœud `g` est retournée par la méthode value().</span><span class="sxs-lookup"><span data-stu-id="9b29b-251">The value of node `g` is returned by the value() method.</span></span>|  
  
 <span data-ttu-id="9b29b-252">**Exemple 4**</span><span class="sxs-lookup"><span data-stu-id="9b29b-252">**Example 4**</span></span>  
  
 <span data-ttu-id="9b29b-253">Voici une requête qui utilise une clause FLWOR dans une clause exist().</span><span class="sxs-lookup"><span data-stu-id="9b29b-253">Here is a query that uses a FLWOR clause inside an exist() clause.</span></span> <span data-ttu-id="9b29b-254">(Le nom FLWOR provient des cinq clauses qui peuvent composer une expression XQuery FLWOR : FOR, LET, WHERE, ORDER BY et RETURN.)</span><span class="sxs-lookup"><span data-stu-id="9b29b-254">(The name FLWOR comes from the five clauses that can make up an XQuery FLWOR expression: for, let, where, order by, and return.)</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('  
  For $x in /a/b/c/d/e  
  Where $x/f = "SQL"  
  Return $x/g  
') = 1  
```  
  
 <span data-ttu-id="9b29b-255">Le tableau suivant indique les nœuds qui doivent être indexés pour laisser cette requête utiliser les index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="9b29b-255">The following table shows the nodes that should be indexed to let this query use the selective XML index.</span></span>  
  
|<span data-ttu-id="9b29b-256">Nœd à inclure dans l'index</span><span class="sxs-lookup"><span data-stu-id="9b29b-256">Node to include in the index</span></span>|<span data-ttu-id="9b29b-257">Raison de l'indexation de ce nœud</span><span class="sxs-lookup"><span data-stu-id="9b29b-257">Reason for indexing this node</span></span>|  
|----------------------------------|-----------------------------------|  
|<span data-ttu-id="9b29b-258">**/a/b/c/d/e**</span><span class="sxs-lookup"><span data-stu-id="9b29b-258">**/a/b/c/d/e**</span></span>|<span data-ttu-id="9b29b-259">L'existence du nœud `e` est évaluée dans la clause FLWOR.</span><span class="sxs-lookup"><span data-stu-id="9b29b-259">The existence of node `e` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="9b29b-260">**/a/b/c/d/e/f**</span><span class="sxs-lookup"><span data-stu-id="9b29b-260">**/a/b/c/d/e/f**</span></span>|<span data-ttu-id="9b29b-261">La valeur du nœud `f` est évaluée dans la clause FLWOR.</span><span class="sxs-lookup"><span data-stu-id="9b29b-261">The value of node `f` is evaluated in the FLWOR clause.</span></span>|  
|<span data-ttu-id="9b29b-262">**/a/b/c/d/e/g**</span><span class="sxs-lookup"><span data-stu-id="9b29b-262">**/a/b/c/d/e/g**</span></span>|<span data-ttu-id="9b29b-263">L'existence du nœud `g` est évaluée par la méthode exist().</span><span class="sxs-lookup"><span data-stu-id="9b29b-263">The existence of node `g` is evaluated by the exist() method.</span></span>|  
  

  
##  <a name="specifying-optimization-hints"></a><a name="hints"></a> <span data-ttu-id="9b29b-264">Spécification des indicateurs d’optimisation</span><span class="sxs-lookup"><span data-stu-id="9b29b-264">Specifying Optimization Hints</span></span>  
 <span data-ttu-id="9b29b-265">Vous pouvez utiliser des indicateurs facultatifs d'optimisation pour spécifier des détails supplémentaires de mappage pour un nœud indexé par un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="9b29b-265">You can use optional optimization hints to specify additional mapping details for a node indexed by a selective XML index.</span></span> <span data-ttu-id="9b29b-266">Par exemple, vous pouvez spécifier le type de données et la cardinalité du nœud, ainsi que certaines informations sur la structure des données.</span><span class="sxs-lookup"><span data-stu-id="9b29b-266">For example, you can specify the data type and cardinality of the node, and certain information about the structure of the data.</span></span> <span data-ttu-id="9b29b-267">Ces informations permettent un meilleur mappage.</span><span class="sxs-lookup"><span data-stu-id="9b29b-267">This additional information supports better mapping.</span></span> <span data-ttu-id="9b29b-268">Elles entraînent également des améliorations des performances ou des économies en termes de stockage, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="9b29b-268">It also results in improvements in performance or savings in storage, or both.</span></span>  
  
 <span data-ttu-id="9b29b-269">L'utilisation des indicateurs d'optimisation est facultative.</span><span class="sxs-lookup"><span data-stu-id="9b29b-269">The use of optimization hints is optional.</span></span> <span data-ttu-id="9b29b-270">Vous pouvez toujours accepter les mappages par défaut, qui sont fiables mais ne permettent pas des performances et un stockage optimaux.</span><span class="sxs-lookup"><span data-stu-id="9b29b-270">You can always accept the default mappings, which are reliable but may not provide optimal performance and storage.</span></span>  
  
 <span data-ttu-id="9b29b-271">Certains indicateurs d’optimisation (par exemple, l’indicateur SINGLETON) introduisent des contraintes sur vos données.</span><span class="sxs-lookup"><span data-stu-id="9b29b-271">Some optimization hints - for example, the SINGLETON hint - introduce constraints over your data.</span></span> <span data-ttu-id="9b29b-272">Dans certains cas, des erreurs peuvent être générées lorsque ces contraintes ne sont pas satisfaites.</span><span class="sxs-lookup"><span data-stu-id="9b29b-272">In some cases, errors may be raised when those constraints are not met.</span></span>  
  
### <a name="benefits-of-optimization-hints"></a><span data-ttu-id="9b29b-273">Avantages des indicateurs d'optimisation</span><span class="sxs-lookup"><span data-stu-id="9b29b-273">Benefits of Optimization Hints</span></span>  
 <span data-ttu-id="9b29b-274">Le tableau suivant identifie les indicateurs d'optimisation qui prennent en charge un stockage plus efficace ou de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="9b29b-274">The following table identifies the optimization hints that support more efficient storage or improved performance.</span></span>  
  
|<span data-ttu-id="9b29b-275">indicateur d'optimisation</span><span class="sxs-lookup"><span data-stu-id="9b29b-275">Optimization hint</span></span>|<span data-ttu-id="9b29b-276">Stockage plus efficace</span><span class="sxs-lookup"><span data-stu-id="9b29b-276">More efficient storage</span></span>|<span data-ttu-id="9b29b-277">performances améliorées</span><span class="sxs-lookup"><span data-stu-id="9b29b-277">Improved performance</span></span>|  
|-----------------------|----------------------------|--------------------------|  
|<span data-ttu-id="9b29b-278">**node()**</span><span class="sxs-lookup"><span data-stu-id="9b29b-278">**node()**</span></span>|<span data-ttu-id="9b29b-279">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-279">Yes</span></span>|<span data-ttu-id="9b29b-280">Non</span><span class="sxs-lookup"><span data-stu-id="9b29b-280">No</span></span>|  
|<span data-ttu-id="9b29b-281">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="9b29b-281">**SINGLETON**</span></span>|<span data-ttu-id="9b29b-282">Non</span><span class="sxs-lookup"><span data-stu-id="9b29b-282">No</span></span>|<span data-ttu-id="9b29b-283">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-283">Yes</span></span>|  
|<span data-ttu-id="9b29b-284">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="9b29b-284">**DATA TYPE**</span></span>|<span data-ttu-id="9b29b-285">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-285">Yes</span></span>|<span data-ttu-id="9b29b-286">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-286">Yes</span></span>|  
|<span data-ttu-id="9b29b-287">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="9b29b-287">**MAXLENGTH**</span></span>|<span data-ttu-id="9b29b-288">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-288">Yes</span></span>|<span data-ttu-id="9b29b-289">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-289">Yes</span></span>|  
  
### <a name="optimization-hints-and-data-types"></a><span data-ttu-id="9b29b-290">Indicateurs d'optimisation et types de données</span><span class="sxs-lookup"><span data-stu-id="9b29b-290">Optimization Hints and Data Types</span></span>  
 <span data-ttu-id="9b29b-291">Vous pouvez indexer des nœuds en tant que types de données XQuery ou en tant que types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b29b-291">You can index nodes as XQuery data types or as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="9b29b-292">Le tableau suivant illustre les indicateurs d'optimisation pris en charge avec chaque type de données.</span><span class="sxs-lookup"><span data-stu-id="9b29b-292">The following table shows which optimization hints are supported with each data type.</span></span>  
  
|<span data-ttu-id="9b29b-293">indicateur d'optimisation</span><span class="sxs-lookup"><span data-stu-id="9b29b-293">Optimization hint</span></span>|<span data-ttu-id="9b29b-294">Types de données XQuery</span><span class="sxs-lookup"><span data-stu-id="9b29b-294">XQuery data types</span></span>|<span data-ttu-id="9b29b-295">Types de données SQL</span><span class="sxs-lookup"><span data-stu-id="9b29b-295">SQL data types</span></span>|  
|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="9b29b-296">**node()**</span><span class="sxs-lookup"><span data-stu-id="9b29b-296">**node()**</span></span>|<span data-ttu-id="9b29b-297">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-297">Yes</span></span>|<span data-ttu-id="9b29b-298">Non</span><span class="sxs-lookup"><span data-stu-id="9b29b-298">No</span></span>|  
|<span data-ttu-id="9b29b-299">**SINGLETON**</span><span class="sxs-lookup"><span data-stu-id="9b29b-299">**SINGLETON**</span></span>|<span data-ttu-id="9b29b-300">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-300">Yes</span></span>|<span data-ttu-id="9b29b-301">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-301">Yes</span></span>|  
|<span data-ttu-id="9b29b-302">**DATA TYPE**</span><span class="sxs-lookup"><span data-stu-id="9b29b-302">**DATA TYPE**</span></span>|<span data-ttu-id="9b29b-303">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-303">Yes</span></span>|<span data-ttu-id="9b29b-304">Non</span><span class="sxs-lookup"><span data-stu-id="9b29b-304">No</span></span>|  
|<span data-ttu-id="9b29b-305">**MAXLENGTH**</span><span class="sxs-lookup"><span data-stu-id="9b29b-305">**MAXLENGTH**</span></span>|<span data-ttu-id="9b29b-306">Oui</span><span class="sxs-lookup"><span data-stu-id="9b29b-306">Yes</span></span>|<span data-ttu-id="9b29b-307">Non</span><span class="sxs-lookup"><span data-stu-id="9b29b-307">No</span></span>|  
  
### <a name="node-optimization-hint"></a><span data-ttu-id="9b29b-308">Indicateur d'optimisation node()</span><span class="sxs-lookup"><span data-stu-id="9b29b-308">node() optimization hint</span></span>  
 <span data-ttu-id="9b29b-309">S’applique à : Types de données XQuery</span><span class="sxs-lookup"><span data-stu-id="9b29b-309">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="9b29b-310">Vous pouvez utiliser l'optimisation node() pour spécifier un nœud dont la valeur n'est pas requise pour évaluer la requête classique.</span><span class="sxs-lookup"><span data-stu-id="9b29b-310">You can use the node() optimization to specify a node whose value is not required to evaluate the typical query.</span></span> <span data-ttu-id="9b29b-311">Cet indicateur réduit les besoins de stockage lorsque la requête classique doit uniquement évaluer l'existence du nœud.</span><span class="sxs-lookup"><span data-stu-id="9b29b-311">This hint reduces storage requirements when the typical query only has to evaluate the existence of the node.</span></span> <span data-ttu-id="9b29b-312">(Par défaut, un index XML sélectif stocke la valeur de tous les nœuds promus, à l'exception des types de nœuds complexes.)</span><span class="sxs-lookup"><span data-stu-id="9b29b-312">(By default, a selective XML index stores the value for all promoted nodes, except complex node types.)</span></span>  
  
 <span data-ttu-id="9b29b-313">Prenons l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="9b29b-313">Consider the following example:</span></span>  
  
```sql  
SELECT T.record FROM myXMLTable T  
WHERE T.xmldata.exist('/a/b[./c=5]') = 1  
```  
  
 <span data-ttu-id="9b29b-314">Pour utiliser un index XML sélectif pour évaluer cette requête, effectuez la promotion des nœuds `b` et `c`.</span><span class="sxs-lookup"><span data-stu-id="9b29b-314">To use a selective XML index to evaluate this query, promote nodes `b` and `c`.</span></span> <span data-ttu-id="9b29b-315">Toutefois, étant donné que la valeur du nœud `b` n'est pas obligatoire, vous pouvez utiliser l'indicateur node() avec la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9b29b-315">However, since the value of node `b` is not required, you can use the node() hint with the following syntax:</span></span>  
  
 `/a/b/ as node()`  
  
 <span data-ttu-id="9b29b-316">Si une requête requiert la valeur d'un nœud qui a été indexé avec l'indicateur node(), l'index XML sélectif ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="9b29b-316">If a query requires the value of a node that has been indexed with the node() hint, then the selective XML index cannot be used.</span></span>  
  
### <a name="singleton-optimization-hint"></a><span data-ttu-id="9b29b-317">Indicateur d'optimisation SINGLETON</span><span class="sxs-lookup"><span data-stu-id="9b29b-317">SINGLETON optimization hint</span></span>  
 <span data-ttu-id="9b29b-318">S’applique à : Types de données XQuery ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b29b-318">Applies to: XQuery or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types</span></span>  
  
 <span data-ttu-id="9b29b-319">L'indicateur d'optimisation SINGLETON spécifie la cardinalité d'un nœud.</span><span class="sxs-lookup"><span data-stu-id="9b29b-319">The SINGLETON optimization hint specifies the cardinality of a node.</span></span> <span data-ttu-id="9b29b-320">Cet indicateur améliore les performances des requêtes, car il sait à l'avance qu'un nœud apparaît au plus une fois dans son parent ou ancêtre.</span><span class="sxs-lookup"><span data-stu-id="9b29b-320">This hint improves query performance since it is known in advance that a node appears at most one time within its parent or ancestor.</span></span>  
  
 <span data-ttu-id="9b29b-321">Examinez [l’exemple de document XML](#sample) dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9b29b-321">Consider the [sample XML document](#sample) in this topic.</span></span>  
  
 <span data-ttu-id="9b29b-322">Pour utiliser un index XML sélectif pour interroger ce document, spécifiez l'indicateur SINGLETON du nœud `d` , car il apparaît au plus une fois dans son parent.</span><span class="sxs-lookup"><span data-stu-id="9b29b-322">To use a selective XML index to query this document, you can specify the SINGLETON hint for node `d` since it appears at most one time within its parent.</span></span>  
  
 <span data-ttu-id="9b29b-323">Si l'indicateur SINGLETON a été spécifié, mais un nœud apparaît plusieurs fois dans son parent ou ancêtre, une erreur est générée lorsque vous créez l'index (pour les données existantes) ou lorsque vous exécutez une requête (pour les nouvelles données).</span><span class="sxs-lookup"><span data-stu-id="9b29b-323">If the SINGLETON hint has been specified, but a node appears more than one time within its parent or ancestor, then an error is raised when you create the index (for existing data) or when you run a query (for new data).</span></span>  
  
### <a name="data-type-optimization-hint"></a><span data-ttu-id="9b29b-324">Indicateur d'optimisation DATA TYPE</span><span class="sxs-lookup"><span data-stu-id="9b29b-324">DATA TYPE optimization hint</span></span>  
 <span data-ttu-id="9b29b-325">S’applique à : Types de données XQuery</span><span class="sxs-lookup"><span data-stu-id="9b29b-325">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="9b29b-326">L'indicateur d'optimisation DATA TYPE vous permet de spécifier un type de données XQuery ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du nœud indexé.</span><span class="sxs-lookup"><span data-stu-id="9b29b-326">The DATA TYPE optimization hint lets you specify an XQuery or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for the indexed node.</span></span> <span data-ttu-id="9b29b-327">Le type de données est utilisé pour la colonne dans la table de données de l'index XML sélectif qui correspond au nœud indexé.</span><span class="sxs-lookup"><span data-stu-id="9b29b-327">The data type is used for the column in the data table of the selective XML index that corresponds to the indexed node.</span></span>  
  
 <span data-ttu-id="9b29b-328">Lors de la conversion d'une valeur existante dans le type de données spécifié échoue, l'opération d'insertion (dans l'index) réussit ; toutefois, une valeur NULL est insérée dans la table de données de l'index.</span><span class="sxs-lookup"><span data-stu-id="9b29b-328">When casting an existing value to the specified data type fails, the insert operation (into the index) does not fail; however, a null value is inserted into the data table of the index.</span></span>  
  
### <a name="maxlength-optimization-hint"></a><span data-ttu-id="9b29b-329">Indicateur d'optimisation MAXLENGTH</span><span class="sxs-lookup"><span data-stu-id="9b29b-329">MAXLENGTH optimization hint</span></span>  
 <span data-ttu-id="9b29b-330">S’applique à : Types de données XQuery</span><span class="sxs-lookup"><span data-stu-id="9b29b-330">Applies to: XQuery data types</span></span>  
  
 <span data-ttu-id="9b29b-331">L'indicateur d'optimisation MAXLENGTH vous permet de limiter la longueur de données xs:string.</span><span class="sxs-lookup"><span data-stu-id="9b29b-331">The MAXLENGTH optimization hint lets you limit the length of xs:string data.</span></span> <span data-ttu-id="9b29b-332">MAXLENGTH n'est pas pertinente pour les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étant donné que vous spécifiez la longueur lorsque vous spécifiez les types de dates VARCHAR ou NVARCHAR.</span><span class="sxs-lookup"><span data-stu-id="9b29b-332">MAXLENGTH is not relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types since you specify the length when you specify the VARCHAR or NVARCHAR date types.</span></span>  
  
 <span data-ttu-id="9b29b-333">Lorsqu'une chaîne existante est plus longue que l'indicateur MAXLENGTH spécifié, l'insertion de cette valeur dans l'index échoue.</span><span class="sxs-lookup"><span data-stu-id="9b29b-333">When an existing string is longer than the specified MAXLENGTH, then inserting that value into the index fails.</span></span>  
  

  
##  <a name="sample-xml-document-for-examples"></a><a name="sample"></a> <span data-ttu-id="9b29b-334">Document XML des exemples</span><span class="sxs-lookup"><span data-stu-id="9b29b-334">Sample XML Document for Examples</span></span>  
 <span data-ttu-id="9b29b-335">Le document XML suivant est référencé dans les exemples de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="9b29b-335">The following sample XML document is referenced in the examples in this topic:</span></span>  
  
```xml  
<a>  
    <b>  
         <c atc="aa">10</c>  
         <c atc="bb">15</c>  
         <d atd1="dd" atd2="ddd">md </d>  
    </b>  
     <b>  
        <c></c>  
        <c atc="">117</c>  
     </b>  
</a>  
```  
  

  
## <a name="see-also"></a><span data-ttu-id="9b29b-336">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b29b-336">See Also</span></span>  
 <span data-ttu-id="9b29b-337">[Index XML sélectifs &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span><span class="sxs-lookup"><span data-stu-id="9b29b-337">[Selective XML Indexes &#40;SXI&#41;](../xml/selective-xml-indexes-sxi.md) </span></span>  
 [<span data-ttu-id="9b29b-338">Créer, modifier ou supprimer des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="9b29b-338">Create, Alter, and Drop Selective XML Indexes</span></span>](../xml/create-alter-and-drop-selective-xml-indexes.md)  
  
  
