---
title: Index XML sélectifs (SXI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 598ecdcd-084b-4032-81b2-eed6ae9f5d44
author: rothja
ms.author: jroth
ms.openlocfilehash: 37dd72c5de2892672dc9f63066075ab5e770d758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614408"
---
# <a name="selective-xml-indexes-sxi"></a><span data-ttu-id="585e7-102">Index XML sélectifs (SXI)</span><span class="sxs-lookup"><span data-stu-id="585e7-102">Selective XML Indexes (SXI)</span></span>
  <span data-ttu-id="585e7-103">Les index XML sélectifs sont un autre type d'index XML disponible en plus des index XML ordinaires.</span><span class="sxs-lookup"><span data-stu-id="585e7-103">Selective XML indexes are another type of XML index that is available to you in addition to ordinary XML indexes.</span></span> <span data-ttu-id="585e7-104">Les objectifs de la fonctionnalité d'index XML sélectif sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="585e7-104">The goals of the selective XML index feature are the following:</span></span>  
  
-   <span data-ttu-id="585e7-105">Améliorer les performances des requêtes sur les données XML stockées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="585e7-105">To improve the performance of queries over XML data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="585e7-106">Prendre en charge une indexation plus rapide des charges de travail importantes de données XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-106">To support faster indexing of large XML data workloads.</span></span>  
  
-   <span data-ttu-id="585e7-107">Améliorer l'évolutivité en réduisant les coûts de stockage des index XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-107">To improve scalability by reducing the storage costs of XML indexes.</span></span>  
  
 <span data-ttu-id="585e7-108">La principale limitation avec des index XML ordinaires est qu'ils indexent le document XML entier.</span><span class="sxs-lookup"><span data-stu-id="585e7-108">The main limitation with ordinary XML indexes is that they index the entire XML document.</span></span> <span data-ttu-id="585e7-109">Cela entraîne plusieurs inconvénients significatifs, tels que la réduction des performances des requêtes et la hausee du coût de maintenance de l'index, principalement liés aux coûts de stockage de l'index.</span><span class="sxs-lookup"><span data-stu-id="585e7-109">This leads to several significant drawbacks, such as decreased query performance and increased index maintenance cost, mostly related to the storage costs of the index.</span></span>  
  
 <span data-ttu-id="585e7-110">La fonctionnalité d'index XML sélectif vous permet de promouvoir uniquement certains chemins d'accès des documents XML à indexer.</span><span class="sxs-lookup"><span data-stu-id="585e7-110">The selective XML index feature lets you promote only certain paths from the XML documents to index.</span></span> <span data-ttu-id="585e7-111">Lors de la création d'index, les chemins d'accès sont évalués et les nœuds vers lesquels ils pointent sont fragmentés et stockés dans une table relationnelle dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="585e7-111">At index creation time, these paths are evaluated, and the nodes that they point to are shredded and stored inside a relational table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="585e7-112">Cette fonctionnalité utilise un algorithme efficace de mappage développé par [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research en collaboration avec l'équipe de produit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="585e7-112">This feature uses an efficient mapping algorithm developed by [!INCLUDE[msCoName](../../includes/msconame-md.md)] Research in collaboration with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product team.</span></span> <span data-ttu-id="585e7-113">Cet algorithme associe les nœuds XML à une table relationnelle, et permet d'obtenir des performances exceptionnelles tout en exigeant qu'un espace de stockage modeste.</span><span class="sxs-lookup"><span data-stu-id="585e7-113">This algorithm maps the XML nodes to a single relational table, and achieves exceptional performance while requiring only modest storage space.</span></span>  
  
 <span data-ttu-id="585e7-114">La fonctionnalité d'index XML sélectif prend également en charge les index XML secondaires sélectifs sur les nœuds qui ont été indexés par un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-114">The selective XML index feature also supports secondary selective XML indexes over nodes that have been indexed by a selective XML index.</span></span> <span data-ttu-id="585e7-115">Ces index sélectifs secondaires sont efficaces et améliorent encore les performances des requêtes.</span><span class="sxs-lookup"><span data-stu-id="585e7-115">These secondary selective indexes are efficient and further improve the performance of queries.</span></span>  
  
##  <a name="benefits-of-selective-xml-indexes"></a><a name="benefits"></a> <span data-ttu-id="585e7-116">Avantages des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="585e7-116">Benefits of Selective XML Indexes</span></span>  
 <span data-ttu-id="585e7-117">Les index XML sélectif présentent les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="585e7-117">Selective XML indexes provide the following benefits:</span></span>  
  
1.  <span data-ttu-id="585e7-118">Les performances des requêtes sont considérablement améliorées sur le type de données XML pour les charges de requête classique.</span><span class="sxs-lookup"><span data-stu-id="585e7-118">Greatly improved query performance over the XML data type for typical query loads.</span></span>  
  
2.  <span data-ttu-id="585e7-119">Capacité de stockage réduite comparée aux index XML ordinaires.</span><span class="sxs-lookup"><span data-stu-id="585e7-119">Reduced storage requirements compared to ordinary XML indexes.</span></span>  
  
3.  <span data-ttu-id="585e7-120">Coûts réduits de maintenance des index par rapport aux index XML ordinaires.</span><span class="sxs-lookup"><span data-stu-id="585e7-120">Reduced index maintenance costs compared to ordinary XML indexes.</span></span>  
  
4.  <span data-ttu-id="585e7-121">Aucun besoin de mettre à jour des applications pour tirer parti des index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="585e7-121">No need to update applications to benefit from selective XML indexes.</span></span>  
  

  
##  <a name="selective-xml-indexes-and-primary-xml-indexes"></a><a name="compare"></a> <span data-ttu-id="585e7-122">Index XML sélectifs et index XML primaires sélectifs</span><span class="sxs-lookup"><span data-stu-id="585e7-122">Selective XML Indexes and Primary XML Indexes</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="585e7-123">Créez un index XML sélectif au lieu d'un index XML ordinaire dans la plupart des cas pour obtenir de meilleures performances et un stockage plus efficace.</span><span class="sxs-lookup"><span data-stu-id="585e7-123">Create a selective XML index instead of an ordinary XML index in most cases for better performance and more efficient storage.</span></span>  
  
 <span data-ttu-id="585e7-124">Toutefois, un index XML sélectif n'est pas recommandé lorsque l'une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="585e7-124">However, a selective XML index is not recommended when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="585e7-125">Vous mappez un grand nombre de chemins d'accès de nœud.</span><span class="sxs-lookup"><span data-stu-id="585e7-125">You map a large number of node paths.</span></span>  
  
-   <span data-ttu-id="585e7-126">Vous devez prendre en charge des requêtes d'éléments inconnus ou des éléments d'un emplacement inconnu dans la structure du document.</span><span class="sxs-lookup"><span data-stu-id="585e7-126">You support queries for unknown elements or elements in an unknown location in the document structure.</span></span>  
  

  
##  <a name="simple-example-of-a-selective-xml-index"></a><a name="example"></a> <span data-ttu-id="585e7-127">Exemple simple d'un index XML sélectif</span><span class="sxs-lookup"><span data-stu-id="585e7-127">Simple Example of a Selective XML Index</span></span>  
 <span data-ttu-id="585e7-128">Examinons le fragment de code XML suivant sous la forme d'un document XML dans une table d'environ 500 000 lignes :</span><span class="sxs-lookup"><span data-stu-id="585e7-128">Consider the following XML fragment as an XML document in a table of approximately 500,000 rows:</span></span>  
  
```xml  
<book>  
    <created>2004-03-01</created>   
    <authors>Various</authors>  
    <subjects>  
        <subject>English wit and humor -- Periodicals</subject>  
        <subject>AP</subject>   
    </subjects>  
    <title>Punch, or the London Charivari, Volume 156, April 2, 1919</title>  
    <id>etext11617</id>  
</book>  
```  
  
 <span data-ttu-id="585e7-129">La création d'un index XML primaire sur un aussi grand nombre de lignes de ce schéma simple prend beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="585e7-129">Creating a primary XML index over so many rows of this simple schema takes a long time.</span></span> <span data-ttu-id="585e7-130">L'interrogation de ces données souffre également du fait qu'un index XML primaire ne prend pas en charge l'indexation sélective.</span><span class="sxs-lookup"><span data-stu-id="585e7-130">Querying this data also suffers from the fact that a primary XML index does not support selective indexing.</span></span>  
  
 <span data-ttu-id="585e7-131">Si vous devez uniquement interroger ces données sur le chemin d'accès `/book/title` et le chemin d'accès `/book/subjects` , créez l'index XML sélectif suivant :</span><span class="sxs-lookup"><span data-stu-id="585e7-131">If you only need to query this data over the `/book/title` path and the `/book/subjects` path, you can create the following selective XML index:</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX SXI_index  
ON Tbl(xmlcol)  
FOR   
(  
    pathTitle = '/book/title/text()' AS XQUERY 'xs:string',   
    pathAuthors = '/book/authors' AS XQUERY 'node()',  
    pathId = '/book/id' AS SQL NVARCHAR(100)  
)  
```  
  
 <span data-ttu-id="585e7-132">L'instruction précédente est un bon exemple de syntaxe CREATE que vous utilisez lorsque vous créez un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-132">The preceding statement is a good example of the CREATE syntax that you use when you create a selective XML index.</span></span> <span data-ttu-id="585e7-133">Dans l'instruction CREATE, vous spécifiez d'abord un nom pour l'index et vous identifiez la table et la colonne XML à indexer.</span><span class="sxs-lookup"><span data-stu-id="585e7-133">In the CREATE statement, first you provide a name for the index and identify the table and the XML column to index.</span></span> <span data-ttu-id="585e7-134">Vous spécifiez ensuite les chemins d'accès à indexer.</span><span class="sxs-lookup"><span data-stu-id="585e7-134">Then you provide the paths to index.</span></span> <span data-ttu-id="585e7-135">Un chemin d'accès possède trois parties :</span><span class="sxs-lookup"><span data-stu-id="585e7-135">A path has three parts:</span></span>  
  
1.  <span data-ttu-id="585e7-136">Un nom qui identifie de façon unique le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="585e7-136">A name that uniquely identifies the path.</span></span>  
  
2.  <span data-ttu-id="585e7-137">Une expression XQuery qui décrit le chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="585e7-137">An XQuery expression that describes the path.</span></span>  
  
3.  <span data-ttu-id="585e7-138">Des indicateurs d'optimisation facultatifs.</span><span class="sxs-lookup"><span data-stu-id="585e7-138">Optional optimization hints.</span></span>  
  
 <span data-ttu-id="585e7-139">Pour plus d'informations sur ces éléments, consultez [Tâches associées](#reltasks).</span><span class="sxs-lookup"><span data-stu-id="585e7-139">For more information about these elements, see [Related Tasks](#reltasks).</span></span>  
  

  
## <a name="supported-features-prerequisites-and-limitations"></a><span data-ttu-id="585e7-140">Fonctionnalités prises en charge, configuration requise et limitations</span><span class="sxs-lookup"><span data-stu-id="585e7-140">Supported Features, Prerequisites, and Limitations</span></span>  
  
###  <a name="supported-xml-features"></a><a name="features"></a> <span data-ttu-id="585e7-141">Fonctionnalités XML prises en charge</span><span class="sxs-lookup"><span data-stu-id="585e7-141">Supported XML Features</span></span>  
 <span data-ttu-id="585e7-142">Les index XML sélectifs prennent en charge la syntaxe XQuery prise en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans les méthodes exist(), value() et nodes().</span><span class="sxs-lookup"><span data-stu-id="585e7-142">Selective XML indexes support the XQuery supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inside the exist(), value() and nodes() methods.</span></span>  
  
-   <span data-ttu-id="585e7-143">Pour les méthodes exist(), value() et nodes(), les index XML sélectifs contiennent suffisamment d'informations pour convertir l'expression entière.</span><span class="sxs-lookup"><span data-stu-id="585e7-143">For the exist(), value() and nodes() methods, selective XML indexes contain enough information to transform the entire expression.</span></span>  
  
-   <span data-ttu-id="585e7-144">Pour les méthodes query() et modify(), les index XML sélectifs ne peuvent être utilisés que pour le filtrage de nœud.</span><span class="sxs-lookup"><span data-stu-id="585e7-144">For the query() and modify() methods, selective XML indexes may be used for node filtering only.</span></span>  
  
-   <span data-ttu-id="585e7-145">Pour la méthode query(), les index XML sélectifs ne sont pas utilisés pour récupérer les résultats.</span><span class="sxs-lookup"><span data-stu-id="585e7-145">For the query() method, selective XML indexes are not used to retrieve results.</span></span>  
  
-   <span data-ttu-id="585e7-146">Pour la méthode modify(), les index XML sélectifs ne sont pas utilisés pour mettre à jour les documents XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-146">For the modify() method, selective XML indexes are not used to update XML documents.</span></span>  
  

  
###  <a name="unsupported-xml-features"></a><a name="unsupported"></a> <span data-ttu-id="585e7-147">Fonctionnalités XML non prises en charge</span><span class="sxs-lookup"><span data-stu-id="585e7-147">Unsupported XML Features</span></span>  
 <span data-ttu-id="585e7-148">Les index XML sélectifs ne prennent pas en charge les fonctionnalités suivantes qui sont prises en charge dans l'implémentation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du XML :</span><span class="sxs-lookup"><span data-stu-id="585e7-148">Selective XML indexes do not support the following features that are supported in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementation of XML:</span></span>  
  
-   <span data-ttu-id="585e7-149">Indexation des nœuds avec des types complexes XS : types d'unions, types de séquences et types de listes.</span><span class="sxs-lookup"><span data-stu-id="585e7-149">Indexing of nodes with complex XS types: union types, sequence types, and list types.</span></span>  
  
-   <span data-ttu-id="585e7-150">Indexation des nœuds avec des types de données binaires XS : par exemple, base64Binary et hexBinary.</span><span class="sxs-lookup"><span data-stu-id="585e7-150">Indexing of nodes with binary XS types: for example, base64Binary and hexBinary.</span></span>  
  
-   <span data-ttu-id="585e7-151">Spécification des nœuds à indexer avec des expressions XPath qui se terminent par le caractère générique `*` : Par exemple, `/a/b/c/*`, `/a//b/*` ou `/a/b/*:c`.</span><span class="sxs-lookup"><span data-stu-id="585e7-151">Specifying the nodes to index with XPath expressions that contain the wildcard character `*` at the end: For example,  `/a/b/c/*`, `/a//b/*`, or `/a/b/*:c`.</span></span>  
  
-   <span data-ttu-id="585e7-152">Indexation d'un axe autre que l'enfant, l'attribut ou le descendant.</span><span class="sxs-lookup"><span data-stu-id="585e7-152">Indexing any axis other than child, attribute, or descendant.</span></span> <span data-ttu-id="585e7-153">`//<step>` est autorisé comme un cas particulier.</span><span class="sxs-lookup"><span data-stu-id="585e7-153">The `//<step>` case is allowed as a special case.</span></span>  
  
-   <span data-ttu-id="585e7-154">Indexation d'instructions de traitement XML et de commentaires.</span><span class="sxs-lookup"><span data-stu-id="585e7-154">Indexing of XML processing instructions and comments.</span></span>  
  
-   <span data-ttu-id="585e7-155">Spécification et récupération de l'identificateur d'un nœud en utilisant la fonction id().</span><span class="sxs-lookup"><span data-stu-id="585e7-155">Specifying and retrieving the identifier for a node by using the id() function.</span></span>  
  

  
###  <a name="prerequisites"></a><a name="prereq"></a> <span data-ttu-id="585e7-156">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="585e7-156">Prerequisites</span></span>  
 <span data-ttu-id="585e7-157">Les conditions suivantes doivent être réunies avant de pouvoir créer un index XML sélectif sur une colonne XML dans une table utilisateur :</span><span class="sxs-lookup"><span data-stu-id="585e7-157">The following prerequisites must exist before you can create a selective XML index over an XML column in a user table:</span></span>  
  
-   <span data-ttu-id="585e7-158">Un index cluster doit exister dans la clé primaire de la table utilisateur.</span><span class="sxs-lookup"><span data-stu-id="585e7-158">A clustered index must exist on the primary key of the user table.</span></span>  
  
-   <span data-ttu-id="585e7-159">La clé primaire de la table d'utilisateur est limitée à une taille de 128 octets si elle est utilisée avec des index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="585e7-159">The primary key of the user table is limited to a size of 128 bytes when used with selective XML indexes.</span></span>  
  
-   <span data-ttu-id="585e7-160">La clé de clustering de la table utilisateur est limitée à 15 colonnes si elle est utilisée avec des index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="585e7-160">The clustering key of the user table is limited to 15 columns when used with selective XML indexes.</span></span>  
  

  
###  <a name="limitations"></a><a name="limits"></a> <span data-ttu-id="585e7-161">Limitations</span><span class="sxs-lookup"><span data-stu-id="585e7-161">Limitations</span></span>  
 <span data-ttu-id="585e7-162">**Limitations et exigences générales**</span><span class="sxs-lookup"><span data-stu-id="585e7-162">**General requirements and limitations**</span></span>  
  
-   <span data-ttu-id="585e7-163">Un index XML sélectif ne peut être créé que sur une colonne XML unique.</span><span class="sxs-lookup"><span data-stu-id="585e7-163">Each selective XML index can only be created on a single XML column.</span></span>  
  
-   <span data-ttu-id="585e7-164">Vous ne pouvez pas créer un index XML sélectif sur une colonne autre qu'une colonne XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-164">You cannot create a selective XML index on a non-XML column.</span></span>  
  
-   <span data-ttu-id="585e7-165">Chaque colonne XML d'une table peut présenter un seul index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-165">Each XML column in a table can have only one selective XML index.</span></span>  
  
-   <span data-ttu-id="585e7-166">Chaque table peut comporter jusqu'à 249 index XML sélectifs.</span><span class="sxs-lookup"><span data-stu-id="585e7-166">Each table can have up to 249 selective XML indexes.</span></span>  
  
 <span data-ttu-id="585e7-167">**Limitations des objets pris en charge**</span><span class="sxs-lookup"><span data-stu-id="585e7-167">**Limitations on supported objects**</span></span>  
  
 <span data-ttu-id="585e7-168">Vous ne pouvez pas créer d'index XML sélectifs sur les objets suivants :</span><span class="sxs-lookup"><span data-stu-id="585e7-168">You cannot create selective XML indexes on the following objects:</span></span>  
  
1.  <span data-ttu-id="585e7-169">Colonnes XML dans une vue.</span><span class="sxs-lookup"><span data-stu-id="585e7-169">XML columns in a view.</span></span>  
  
2.  <span data-ttu-id="585e7-170">Variable table avec des colonnes XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-170">Table-valued variable with XML columns.</span></span>  
  
3.  <span data-ttu-id="585e7-171">Variables de type XML.</span><span class="sxs-lookup"><span data-stu-id="585e7-171">XML type variables.</span></span>  
  
4.  <span data-ttu-id="585e7-172">Colonnes XML calculées.</span><span class="sxs-lookup"><span data-stu-id="585e7-172">Computed XML columns.</span></span>  
  
5.  <span data-ttu-id="585e7-173">Colonnes XML avec une profondeur de plus de 128 nœuds imbriqués.</span><span class="sxs-lookup"><span data-stu-id="585e7-173">XML columns with a depth of more than 128 nested nodes.</span></span>  
  
 <span data-ttu-id="585e7-174">**Limitations relatives au stockage**</span><span class="sxs-lookup"><span data-stu-id="585e7-174">**Limitations related to storage**</span></span>  
  
 <span data-ttu-id="585e7-175">Il existe une limite finie sur le nombre de nœuds du document XML pouvant être ajoutés à l'index.</span><span class="sxs-lookup"><span data-stu-id="585e7-175">There is a finite limit on the number of nodes from the XML document that can be added to the index.</span></span> <span data-ttu-id="585e7-176">Un index XML sélectif mappe des documents XML à une table relationnelle.</span><span class="sxs-lookup"><span data-stu-id="585e7-176">A selective XML index maps XML documents to a single relational table.</span></span> <span data-ttu-id="585e7-177">Par conséquent, il ne peut pas y avoir plus de 1 024 colonnes non Null dans une ligne donnée de la table.</span><span class="sxs-lookup"><span data-stu-id="585e7-177">Therefore it cannot have more than 1024 non-null columns in any given row of the table.</span></span> <span data-ttu-id="585e7-178">En outre, la plupart des limitations des colonnes éparses s'appliquent également aux index XML sélectifs, car les index utilisent des colonnes éparses pour le stockage.</span><span class="sxs-lookup"><span data-stu-id="585e7-178">Furthermore, many of the limitations of sparse columns also apply to selective XML indexes, because the indexes use sparse columns for storage.</span></span>  
  
 <span data-ttu-id="585e7-179">Le nombre maximal de colonnes non Null prises en charge dans toute ligne donnée dépend de la taille des données dans les colonnes :</span><span class="sxs-lookup"><span data-stu-id="585e7-179">The maximum number of non-null columns supported in any given row depends on the size of the data in the columns:</span></span>  
  
-   <span data-ttu-id="585e7-180">Dans le meilleur des cas, 1024 colonnes non NULL sont prises en charge quand toutes les colonnes sont de type **bit**.</span><span class="sxs-lookup"><span data-stu-id="585e7-180">In the best case, 1024 non-null columns are supported when all columns are of type **bit**.</span></span>  
  
-   <span data-ttu-id="585e7-181">Dans le pire des cas, seules 236 colonnes non NULL sont prises en charge quand toutes les colonnes sont de grands objets de type **varchar**.</span><span class="sxs-lookup"><span data-stu-id="585e7-181">In the worst case, only 236 non-null columns are supported when all columns are large objects of type **varchar**.</span></span>  
  
 <span data-ttu-id="585e7-182">Les index XML sélectifs utilisent une à quatre colonnes en interne pour chaque chemin d'accès du nœud qui est indexé.</span><span class="sxs-lookup"><span data-stu-id="585e7-182">Selective XML indexes use from one to four columns internally for every node path that is indexed.</span></span> <span data-ttu-id="585e7-183">Le nombre total de nœuds qui peuvent être indexés s'étend de 60 à plusieurs centaines de nœuds, selon la taille réelle des données dans les chemins d'accès indexés.</span><span class="sxs-lookup"><span data-stu-id="585e7-183">The total number of nodes that can be indexed ranges from 60 to several hundred nodes, depending on the actual size of the data in the indexed paths.</span></span>  
  
-   <span data-ttu-id="585e7-184">Dans le pire des cas, si certains ou tous les nœuds sont mappés en utilisant `//` dans la définition du chemin d'accès du nœud, le nombre maximal de nœuds indexés est 60.</span><span class="sxs-lookup"><span data-stu-id="585e7-184">In the worst case, when some or all nodes are mapped using `//` in the node path definition, the maximum number of indexed nodes is 60.</span></span>  
  
-   <span data-ttu-id="585e7-185">Dans le meilleur des cas, si des nœuds sont mappés sans utiliser `//` dans la définition du chemin d'accès du nœud, le nombre maximal de nœuds indexés est 200.</span><span class="sxs-lookup"><span data-stu-id="585e7-185">In the best case, when nodes are mapped without using `//` in the node path definition, the maximum number of indexed nodes is 200.</span></span>  
  
 <span data-ttu-id="585e7-186">**Les index XML sélectifs sont régénérés lorsque vous créez (CREATE) ou modifiez (ALTER) l'index.**</span><span class="sxs-lookup"><span data-stu-id="585e7-186">**Selective XML indexes are rebuilt when you CREATE or ALTER the index.**</span></span>  
  
 <span data-ttu-id="585e7-187">Lorsque vous créez ou modifiez un index XML sélectif, il est reconstruit en mode hors connexion monothread.</span><span class="sxs-lookup"><span data-stu-id="585e7-187">When you CREATE or ALTER a selective XML index, it is rebuilt in a single-threaded, offline mode.</span></span> <span data-ttu-id="585e7-188">L'utilisation fréquente d'instructions ALTER a un impact négatif sur les performances des requêtes exécutées sur des documents XML indexés.</span><span class="sxs-lookup"><span data-stu-id="585e7-188">Frequently ALTER statements negatively affect the performance of queries over the indexed XML documents.</span></span>  
  
 <span data-ttu-id="585e7-189">**Autres limitations**</span><span class="sxs-lookup"><span data-stu-id="585e7-189">**Other limitations**</span></span>  
  
-   <span data-ttu-id="585e7-190">Les index XML sélectifs ne sont pas pris en charge dans les indicateurs de requête.</span><span class="sxs-lookup"><span data-stu-id="585e7-190">Selective XML indexes are not supported in query hints.</span></span>  
  
-   <span data-ttu-id="585e7-191">Les index XML sélectifs et les index XML secondaires sélectifs ne sont pas pris en charge par l'Assistant Paramétrage de base de données.</span><span class="sxs-lookup"><span data-stu-id="585e7-191">Selective XML indexes and secondary selective XML indexes are not supported in Database Tuning Advisor.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="585e7-192">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="585e7-192">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="585e7-193">**Tâche**</span><span class="sxs-lookup"><span data-stu-id="585e7-193">**Task**</span></span>|<span data-ttu-id="585e7-194">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="585e7-194">**Topic**</span></span>|  
|<span data-ttu-id="585e7-195">Spécifiez les chemins d'accès du nœud que vous souhaitez indexer et les indicateurs facultatifs d'optimisation lorsque vous créez ou modifiez un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-195">Specify the node paths that you want to index and optional optimization hints when you create or alter a selective XML index.</span></span>|[<span data-ttu-id="585e7-196">Spécifier les chemins d’accès et les indicateurs d’optimisation des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="585e7-196">Specify Paths and Optimization Hints for Selective XML Indexes</span></span>](specify-paths-and-optimization-hints-for-selective-xml-indexes.md)|  
|<span data-ttu-id="585e7-197">Créez, modifiez ou supprimez un index XML sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-197">Create, alter, or drop a selective XML index.</span></span>|[<span data-ttu-id="585e7-198">Créer, modifier ou supprimer des index XML sélectifs</span><span class="sxs-lookup"><span data-stu-id="585e7-198">Create, Alter, and Drop Selective XML Indexes</span></span>](create-alter-and-drop-selective-xml-indexes.md)|  
|<span data-ttu-id="585e7-199">Créez, modifiez ou supprimez un index XML secondaire sélectif.</span><span class="sxs-lookup"><span data-stu-id="585e7-199">Create, alter, or drop a secondary selective XML index.</span></span>|[<span data-ttu-id="585e7-200">Créer, modifier ou supprimer des index XML secondaires sélectifs</span><span class="sxs-lookup"><span data-stu-id="585e7-200">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>](create-alter-and-drop-secondary-selective-xml-indexes.md)|  
  

  
  
