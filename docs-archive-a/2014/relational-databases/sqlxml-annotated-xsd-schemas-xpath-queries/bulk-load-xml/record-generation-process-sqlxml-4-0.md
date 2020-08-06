---
title: Processus de génération d’enregistrements (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], record generation process
- node scopes [SQLXML]
- record subsets [SQLXML]
- scope [SQLXML]
- key ordering rules [SQLXML]
- record generation process for bulk loads [SQLXML]
- entering node scope [SQLXML]
- bulk load [SQLXML], record generation process
- leaving node scope [SQLXML]
- schema mapping [SQLXML]
ms.assetid: d8885bbe-6f15-4fb9-9684-ca7883cfe9ac
author: rothja
ms.author: jroth
ms.openlocfilehash: 5734776864aecbda7adaf0b9b16180b5ebd55ce3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695499"
---
# <a name="record-generation-process-sqlxml-40"></a><span data-ttu-id="2ee33-102">Processus de génération d'enregistrements (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2ee33-102">Record Generation Process (SQLXML 4.0)</span></span>
  <span data-ttu-id="2ee33-103">Le chargement en masse XML traite les données d'entrée XML et prépare des enregistrements pour les tables appropriées dans Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee33-103">XML Bulk Load processes the XML input data and prepares records for the appropriate tables in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ee33-104">La logique de la fonctionnalité de chargement en masse XML détermine quand générer un nouvel enregistrement, quelles valeurs d'attributs ou d'éléments enfants copier dans les champs de l'enregistrement et quand l'enregistrement est terminé et prêt à être envoyé à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour insertion.</span><span class="sxs-lookup"><span data-stu-id="2ee33-104">The logic in XML Bulk Load determines when to generate a new record, what child element or attribute values to copy into the fields of the record, and when the record is complete and ready to be sent to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="2ee33-105">Le chargement en masse XML ne charge pas toutes les données d'entrée XML dans la mémoire et ne produit pas de jeux d'enregistrements complets avant d'envoyer les données à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee33-105">XML Bulk Load does not load the entire XML input data into memory, and does not produce complete record sets before sending data to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ee33-106">Cela tient au fait que les données d'entrée XML peuvent correspondre à un document volumineux et que le chargement du document entier en mémoire peut s'avérer onéreux.</span><span class="sxs-lookup"><span data-stu-id="2ee33-106">This is because XML input data can be a large document and loading the entire document in memory can be expensive.</span></span> <span data-ttu-id="2ee33-107">À la place, le chargement en masse XML effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ee33-107">Instead, XML Bulk Load does the following:</span></span>  
  
1.  <span data-ttu-id="2ee33-108">Il analyse le schéma de mappage et prépare le plan d'exécution nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2ee33-108">Analyzes the mapping schema and prepares the necessary execution plan.</span></span>  
  
2.  <span data-ttu-id="2ee33-109">Il applique le plan d'exécution aux données dans le flux d'entrée.</span><span class="sxs-lookup"><span data-stu-id="2ee33-109">Applies the execution plan to the data in the input stream.</span></span>  
  
 <span data-ttu-id="2ee33-110">Ce traitement séquentiel fait qu'il est important de fournir les données d'entrée XML d'une manière spécifique.</span><span class="sxs-lookup"><span data-stu-id="2ee33-110">This sequential processing makes it important to provide the XML input data in a specific way.</span></span> <span data-ttu-id="2ee33-111">Vous devez comprendre comment le chargement en masse XML analyse le schéma de mappage et comment le processus de génération d'enregistrements se produit.</span><span class="sxs-lookup"><span data-stu-id="2ee33-111">You must understand how XML Bulk Load analyzes the mapping schema and how the record generation process occurs.</span></span> <span data-ttu-id="2ee33-112">Comprendre cela vous permet de fournir un schéma de mappage au chargement en masse XML qui produit les résultats que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="2ee33-112">With this understanding, you can provide a mapping schema to XML Bulk Load that produces the results you want.</span></span>  
  
 <span data-ttu-id="2ee33-113">Le chargement en masse XML gère les annotations de schéma de mappage courantes, y compris les mappages de colonne et de table (spécifiés explicitement à l'aide d'annotations ou implicitement par le biais du mappage par défaut), ainsi que les relations de jointure.</span><span class="sxs-lookup"><span data-stu-id="2ee33-113">XML Bulk Load handles common mapping schema annotations, including column and table mappings (specified explicitly by using annotations or implicitly through the default mapping), and join relationships.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ee33-114">Cette rubrique suppose que vous connaissez bien les schémas de mappage XDR ou XSD annotés.</span><span class="sxs-lookup"><span data-stu-id="2ee33-114">It is assumed that you are familiar with annotated XSD or XDR mapping schemas.</span></span> <span data-ttu-id="2ee33-115">Pour plus d’informations sur les schémas, consultez [Présentation des schémas XSD Annotés &#40;sqlxml 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) ou [schémas XDR annotés &#40;dépréciés dans SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2ee33-115">For more information about schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) or [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="2ee33-116">Pour comprendre la génération d'enregistrements, vous devez comprendre les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="2ee33-116">Understanding record generation requires understanding the following concepts:</span></span>  
  
-   <span data-ttu-id="2ee33-117">Étendue d'un nœud</span><span class="sxs-lookup"><span data-stu-id="2ee33-117">Scope of a node</span></span>  
  
-   <span data-ttu-id="2ee33-118">Règle de génération d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="2ee33-118">Record Generation Rule</span></span>  
  
-   <span data-ttu-id="2ee33-119">Sous-ensemble d'enregistrements et règle de tri par clé</span><span class="sxs-lookup"><span data-stu-id="2ee33-119">Record subset and the Key Ordering Rule</span></span>  
  
-   <span data-ttu-id="2ee33-120">Exceptions à la règle de génération d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="2ee33-120">Exceptions to the Record Generation Rule</span></span>  
  
## <a name="scope-of-a-node"></a><span data-ttu-id="2ee33-121">Étendue d’un nœud</span><span class="sxs-lookup"><span data-stu-id="2ee33-121">Scope of a Node</span></span>  
 <span data-ttu-id="2ee33-122">Un nœud (un élément ou un attribut) dans un document XML entre dans l' *étendue* lorsque le chargement en masse XML le rencontre dans le flux de données d’entrée XML.</span><span class="sxs-lookup"><span data-stu-id="2ee33-122">A node (an element or an attribute) in an XML document enters *into scope* when XML Bulk Load encounters it in the XML input data stream.</span></span> <span data-ttu-id="2ee33-123">Pour un nœud d'élément, la balise de début de l'élément place l'élément dans l'étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-123">For an element node, the start tag of the element brings the element in scope.</span></span> <span data-ttu-id="2ee33-124">Pour un nœud d'attribut, le nom d'attribut place l'attribut dans l'étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-124">For an attribute node, the attribute name brings the attribute in scope.</span></span>  
  
 <span data-ttu-id="2ee33-125">Un nœud quitte l'étendue lorsqu'il ne reste plus de données pour lui : soit au niveau de la balise de fin (dans le cas d'un nœud d'élément), soit à la fin d'une valeur d'attribut (dans le cas d'un nœud d'attribut).</span><span class="sxs-lookup"><span data-stu-id="2ee33-125">A node leaves scope when there is no more data for it: either at the end tag (in the case of an element node) or at the end of an attribute value (in the case of an attribute node).</span></span>  
  
## <a name="record-generation-rule"></a><span data-ttu-id="2ee33-126">Règle de génération d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="2ee33-126">Record Generation Rule</span></span>  
 <span data-ttu-id="2ee33-127">Lorsqu'un nœud (élément ou attribut) entre dans l'étendue, il est possible de générer un enregistrement à partir de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="2ee33-127">When a node (element or attribute) enters into scope, there is a potential for generating a record from that node.</span></span> <span data-ttu-id="2ee33-128">L'enregistrement dure tant que le nœud associé est dans l'étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-128">The record lives as long as the associated node is in scope.</span></span> <span data-ttu-id="2ee33-129">Lorsque le nœud sort de l'étendue, le chargement en masse XML considère l'enregistrement généré comme complet (avec les données) et l'envoie à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour insertion.</span><span class="sxs-lookup"><span data-stu-id="2ee33-129">When the node goes out of scope, XML Bulk Load considers the generated record complete (with data) and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for insertion.</span></span>  
  
 <span data-ttu-id="2ee33-130">Considérons, par exemple, le fragment de schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="2ee33-130">For example, consider the following XSD schema fragment:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Customers" >  
   <xsd:complexType>  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
     <xsd:attribute name="CompanyName" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="2ee33-131">Le schéma spécifie un **\<Customer>** élément avec les attributs **CustomerID** et **CompanyName** .</span><span class="sxs-lookup"><span data-stu-id="2ee33-131">The schema specifies a **\<Customer>** element with **CustomerID** and **CompanyName** attributes.</span></span> <span data-ttu-id="2ee33-132">L' `sql:relation` annotation mappe l' **\<Customer>** élément à la table Customers.</span><span class="sxs-lookup"><span data-stu-id="2ee33-132">The `sql:relation` annotation maps the **\<Customer>** element to the Customers table.</span></span>  
  
 <span data-ttu-id="2ee33-133">Considérez ce fragment d'un document XML :</span><span class="sxs-lookup"><span data-stu-id="2ee33-133">Consider this fragment of an XML document:</span></span>  
  
```  
<Customer CustomerID="1" CompanyName="xyz" />  
<Customer CustomerID="2" CompanyName="abc" />  
...  
```  
  
 <span data-ttu-id="2ee33-134">Lorsque le chargement en masse XML est fourni avec le schéma décrit dans les paragraphes précédents et les données XML comme entrée, il traite les nœuds (éléments et attributs) dans les données sources comme suit :</span><span class="sxs-lookup"><span data-stu-id="2ee33-134">When XML Bulk Load is provided with the schema described in the preceding paragraphs and XML data as input, it processes the nodes (elements and attributes) in the source data as follows:</span></span>  
  
-   <span data-ttu-id="2ee33-135">La balise de début du premier **\<Customer>** élément amène cet élément dans la portée.</span><span class="sxs-lookup"><span data-stu-id="2ee33-135">The start tag of the first **\<Customer>** element brings that element in scope.</span></span> <span data-ttu-id="2ee33-136">Ce nœud est mappé à la table Customers.</span><span class="sxs-lookup"><span data-stu-id="2ee33-136">This node maps to the Customers table.</span></span> <span data-ttu-id="2ee33-137">Par conséquent, le chargement en masse XML génère un enregistrement pour la table Customers.</span><span class="sxs-lookup"><span data-stu-id="2ee33-137">Therefore, XML Bulk Load generates a record for the Customers table.</span></span>  
  
-   <span data-ttu-id="2ee33-138">Dans le schéma, tous les attributs de l' **\<Customer>** élément sont mappés à des colonnes de la table Customers.</span><span class="sxs-lookup"><span data-stu-id="2ee33-138">In the schema, all attributes of the **\<Customer>** element map to columns of the Customers table.</span></span> <span data-ttu-id="2ee33-139">Lorsque ces attributs entrent dans l'étendue, le chargement en masse XML copie leurs valeurs dans l'enregistrement de client qui est déjà généré par l'étendue parente.</span><span class="sxs-lookup"><span data-stu-id="2ee33-139">As these attributes enter into scope, XML Bulk Load copies their values to the customer record that is already generated by the parent scope.</span></span>  
  
-   <span data-ttu-id="2ee33-140">Lorsque le chargement en masse XML atteint la balise de fin de l' **\<Customer>** élément, l’élément est hors de portée.</span><span class="sxs-lookup"><span data-stu-id="2ee33-140">When XML Bulk Load reaches the end tag for the **\<Customer>** element, the element goes out of scope.</span></span> <span data-ttu-id="2ee33-141">Cela conduit le chargement en masse XML à considérer l'enregistrement comme complet et à l'envoyer à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee33-141">This causes XML Bulk Load to consider the record complete and send it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2ee33-142">Le chargement en masse XML suit ce processus pour chaque **\<Customer>** élément suivant.</span><span class="sxs-lookup"><span data-stu-id="2ee33-142">XML Bulk Load follows this process for each subsequent **\<Customer>** element.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2ee33-143">Dans ce modèle, comme un enregistrement est inséré lorsque la balise de fin est atteinte (ou lorsque le nœud est hors de portée), vous devez définir toutes les données associées à l'enregistrement dans l'étendue du nœud.</span><span class="sxs-lookup"><span data-stu-id="2ee33-143">In this model, because a record is inserted when the end tag is reached (or the node is out of scope), you must define all of the data that is associated with the record within the scope of the node.</span></span>  
  
## <a name="record-subset-and-the-key-ordering-rule"></a><span data-ttu-id="2ee33-144">Sous-ensemble d’enregistrements et règle de classement des clés</span><span class="sxs-lookup"><span data-stu-id="2ee33-144">Record Subset and the Key Ordering Rule</span></span>  
 <span data-ttu-id="2ee33-145">Lorsque vous spécifiez un schéma de mappage qui utilise `<sql:relationship>`, le terme de sous-ensemble fait référence au jeu d'enregistrements qui est généré sur le côté étranger de la relation.</span><span class="sxs-lookup"><span data-stu-id="2ee33-145">When you specify a mapping schema that uses `<sql:relationship>`, the subset term refers to the set of records that is generated on the foreign side of the relationship.</span></span> <span data-ttu-id="2ee33-146">Dans l'exemple suivant, les enregistrements CustOrder sont sur le côté étranger, `<sql:relationship>`.</span><span class="sxs-lookup"><span data-stu-id="2ee33-146">In the following example, the CustOrder records are on the foreign side, `<sql:relationship>`.</span></span>  
  
 <span data-ttu-id="2ee33-147">Prenons l'exemple d'une base de données contenant les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ee33-147">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="2ee33-148">Cust (CustomerID, CompanyName, City)</span><span class="sxs-lookup"><span data-stu-id="2ee33-148">Cust (CustomerID, CompanyName, City)</span></span>  
  
-   <span data-ttu-id="2ee33-149">CustOrder (CustomerID, OrderID)</span><span class="sxs-lookup"><span data-stu-id="2ee33-149">CustOrder (CustomerID, OrderID)</span></span>  
  
 <span data-ttu-id="2ee33-150">CustomerID dans la table CustOrder est une clé étrangère qui fait référence à la clé primaire CustomerID dans la table Cust.</span><span class="sxs-lookup"><span data-stu-id="2ee33-150">The CustomerID in the CustOrder table is a foreign key that refers to the CustomerID primary key in the Cust table.</span></span>  
  
 <span data-ttu-id="2ee33-151">À présent, considérez la vue XML telle qu'elle est spécifiée dans le schéma XSD annoté ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2ee33-151">Now, consider the XML view as specified in the following annotated XSD schema.</span></span> <span data-ttu-id="2ee33-152">Ce schéma utilise `<sql:relationship>` pour spécifier la relation entre les tables Cust et CustOrder.</span><span class="sxs-lookup"><span data-stu-id="2ee33-152">This schema uses `<sql:relationship>` to specify the relationship between the Cust and CustOrder tables.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="2ee33-153">L'exemple de données XML et les étapes de création d'un exemple fonctionnel sont fournis ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2ee33-153">The sample XML data and the steps to create a working sample are given below.</span></span>  
  
-   <span data-ttu-id="2ee33-154">Lorsqu’un **\<Customer>** nœud d’élément dans le fichier de données XML entre dans l’étendue, le chargement en masse XML génère un enregistrement pour la table Cust.</span><span class="sxs-lookup"><span data-stu-id="2ee33-154">When a **\<Customer>** element node in the XML data file enters into scope, XML Bulk Load generates a record for the Cust table.</span></span> <span data-ttu-id="2ee33-155">Le chargement en masse XML copie ensuite les valeurs de colonne nécessaires (CustomerID, CompanyName et City) à partir du **\<CustomerID>** , de **\<CompanyName>** et des **\<City>** éléments enfants, car ces éléments entrent dans la portée.</span><span class="sxs-lookup"><span data-stu-id="2ee33-155">XML Bulk Load then copies the necessary column values (CustomerID, CompanyName, and City) from the **\<CustomerID>**, **\<CompanyName>**, and the **\<City>** child elements as these elements enter into scope.</span></span>  
  
-   <span data-ttu-id="2ee33-156">Quand un **\<Order>** nœud d’élément entre dans l’étendue, le chargement en masse XML génère un enregistrement pour la table CustOrder.</span><span class="sxs-lookup"><span data-stu-id="2ee33-156">When an **\<Order>** element node enters into scope, XML Bulk Load generates a record for the CustOrder table.</span></span> <span data-ttu-id="2ee33-157">Le chargement en masse XML copie la valeur de l’attribut **OrderID** dans cet enregistrement.</span><span class="sxs-lookup"><span data-stu-id="2ee33-157">XML Bulk Load copies the value of the **OrderID** attribute to this record.</span></span> <span data-ttu-id="2ee33-158">La valeur requise pour la colonne CustomerID est obtenue à partir de l' **\<CustomerID>** élément enfant de l' **\<Customer>** élément.</span><span class="sxs-lookup"><span data-stu-id="2ee33-158">The value required for the CustomerID column is obtained from the **\<CustomerID>** child element of the **\<Customer>** element.</span></span> <span data-ttu-id="2ee33-159">Le chargement en masse XML utilise les informations spécifiées dans `<sql:relationship>` pour obtenir la valeur de clé étrangère CustomerID pour cet enregistrement, à moins que l’attribut **CustomerID** ait été spécifié dans l' **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="2ee33-159">XML Bulk Load uses the information that is specified in `<sql:relationship>` to obtain the CustomerID foreign key value for this record, unless the **CustomerID** attribute was specified in the **\<Order>** element.</span></span> <span data-ttu-id="2ee33-160">La règle générale est que si l'élément enfant spécifie explicitement une valeur pour l'attribut de clé étrangère, le chargement en masse XML utilise cette valeur et n'obtient pas la valeur à partir de l'élément parent en utilisant le `<sql:relationship>` spécifié.</span><span class="sxs-lookup"><span data-stu-id="2ee33-160">The general rule is that if the child element explicitly specifies a value for the foreign key attribute, XML Bulk Load uses that value and does not obtain the value from the parent element by using the specified `<sql:relationship>`.</span></span> <span data-ttu-id="2ee33-161">Comme ce **\<Order>** nœud d’élément sort de l’étendue, le chargement en masse XML envoie l’enregistrement à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et traite ensuite tous les **\<Order>** nœuds d’élément suivants de la même manière.</span><span class="sxs-lookup"><span data-stu-id="2ee33-161">As this **\<Order>** element node goes out of scope, XML Bulk Load sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and then processes all the subsequent **\<Order>** element nodes in the same manner.</span></span>  
  
-   <span data-ttu-id="2ee33-162">Enfin, le **\<Customer>** nœud d’élément est hors de portée.</span><span class="sxs-lookup"><span data-stu-id="2ee33-162">Finally, the **\<Customer>** element node goes out of scope.</span></span> <span data-ttu-id="2ee33-163">À ce stade, le chargement en masse XML envoie l'enregistrement de client à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee33-163">At that time, XML Bulk Load sends the customer record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ee33-164">Le chargement en masse XML suit ce processus pour tous les clients suivants dans le flux de données XML.</span><span class="sxs-lookup"><span data-stu-id="2ee33-164">XML Bulk Load follows this process for all the subsequent customers in the XML data stream.</span></span>  
  
 <span data-ttu-id="2ee33-165">Voici deux observations à propos du schéma de mappage :</span><span class="sxs-lookup"><span data-stu-id="2ee33-165">Here are two observations about the mapping schema:</span></span>  
  
-   <span data-ttu-id="2ee33-166">Lorsque le schéma répond à la règle de « relation contenant-contenu » (par exemple, toutes les données associées au client et à la commande sont définies dans l’étendue des **\<Customer>** **\<Order>** nœuds d’élément et associés), le chargement en masse réussit.</span><span class="sxs-lookup"><span data-stu-id="2ee33-166">When the schema satisfies the "containment" rule (for example, all data that is associated with the customer and the order is defined within the scope of the associated **\<Customer>** and **\<Order>** element nodes), the bulk load succeeds.</span></span>  
  
-   <span data-ttu-id="2ee33-167">Lors de la description de l' **\<Customer>** élément, ses éléments enfants sont spécifiés dans l’ordre approprié.</span><span class="sxs-lookup"><span data-stu-id="2ee33-167">In describing the **\<Customer>** element, its child elements are specified in the appropriate order.</span></span> <span data-ttu-id="2ee33-168">Dans ce cas, l' **\<CustomerID>** élément enfant est spécifié avant l' **\<Order>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="2ee33-168">In this case, the **\<CustomerID>** child element is specified before the **\<Order>** child element.</span></span> <span data-ttu-id="2ee33-169">Cela signifie que, dans le fichier de données XML d’entrée, la valeur de l' **\<CustomerID>** élément est disponible en tant que valeur de clé étrangère lorsque l' **\<Order>** élément entre dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-169">This means that in the input XML data file, the **\<CustomerID>** element value is available as the foreign key value when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="2ee33-170">Les attributs de clé sont spécifiés en premier ; ceci est la « règle de tri par clé ».</span><span class="sxs-lookup"><span data-stu-id="2ee33-170">The key attributes are specified first; this is the "Key Ordering Rule."</span></span>  
  
     <span data-ttu-id="2ee33-171">Si vous spécifiez l' **\<CustomerID>** élément enfant après l' **\<Order>** élément enfant, la valeur n’est pas disponible lorsque l' **\<Order>** élément entre dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-171">If you specify the **\<CustomerID>** child element after the **\<Order>** child element, the value is not available when the **\<Order>** element enters into scope.</span></span> <span data-ttu-id="2ee33-172">Lorsque la **\</Order>** balise de fin est ensuite lue, l’enregistrement de la table CustOrder est considéré comme complet et est inséré dans la table CustOrder avec une valeur null pour la colonne CustomerID, ce qui n’est pas le résultat souhaité.</span><span class="sxs-lookup"><span data-stu-id="2ee33-172">When the **\</Order>** end tag is then read, the record for CustOrder table is considered complete and is inserted in the CustOrder table with a NULL value for the CustomerID column, which is not the desired result.</span></span>  
  
#### <a name="to-create-a-working-sample"></a><span data-ttu-id="2ee33-173">Pour créer un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="2ee33-173">To create a working sample</span></span>  
  
1.  <span data-ttu-id="2ee33-174">Enregistrez le schéma fourni dans cet exemple sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="2ee33-174">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="2ee33-175">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ee33-175">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                 OrderID        int         PRIMARY KEY,  
                 CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
3.  <span data-ttu-id="2ee33-176">Enregistrez l'exemple de données d'entrée XML ci-après sous le nom SampleXMLData.xml :</span><span class="sxs-lookup"><span data-stu-id="2ee33-176">Save the following sample XML input data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>   
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
        <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="2ee33-177">Pour effectuer le chargement en masse XML, enregistrez et exécutez l'exemple [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) suivant (BulkLoad.vbs) :</span><span class="sxs-lookup"><span data-stu-id="2ee33-177">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example (BulkLoad.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
## <a name="exceptions-to-the-record-generation-rule"></a><span data-ttu-id="2ee33-178">Exceptions à la règle de génération d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="2ee33-178">Exceptions to the Record Generation Rule</span></span>  
 <span data-ttu-id="2ee33-179">Le chargement en masse XML ne génère pas d'enregistrement pour un nœud lorsqu'il entre dans l'étendue si ce nœud est de type IDREF ou IDREFS.</span><span class="sxs-lookup"><span data-stu-id="2ee33-179">XML Bulk Load does not generate a record for a node when it enters into scope if that node is either an IDREF or IDREFS type.</span></span> <span data-ttu-id="2ee33-180">Vous devez vous assurer qu'une description complète de l'enregistrement se produit à un point quelconque dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="2ee33-180">You must make sure that a complete description of the record occurs at some place in the schema.</span></span> <span data-ttu-id="2ee33-181">Les annotations `dt:type="nmtokens"` sont ignorées tout comme le type IDREFS est ignoré.</span><span class="sxs-lookup"><span data-stu-id="2ee33-181">The `dt:type="nmtokens"` annotations are ignored just as the IDREFS type is ignored.</span></span>  
  
 <span data-ttu-id="2ee33-182">Par exemple, considérez le schéma XSD suivant qui décrit les **\<Customer>** **\<Order>** éléments et.</span><span class="sxs-lookup"><span data-stu-id="2ee33-182">For example, consider the following XSD schema that describes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="2ee33-183">L' **\<Customer>** élément comprend un attribut **OrderList** du type IDREFS.</span><span class="sxs-lookup"><span data-stu-id="2ee33-183">The **\<Customer>** element includes an **OrderList** attribute of the IDREFS type.</span></span> <span data-ttu-id="2ee33-184">La balise `<sql:relationship>` spécifie la relation un-à-plusieurs entre le client et la liste des commandes.</span><span class="sxs-lookup"><span data-stu-id="2ee33-184">The `<sql:relationship>` tag specifies the one-to-many relationship between the customer and list of orders.</span></span>  
  
 <span data-ttu-id="2ee33-185">Voici le schéma :</span><span class="sxs-lookup"><span data-stu-id="2ee33-185">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
                 parent="Cust"  
                 parent-key="CustomerID"  
                 child="CustOrder"  
                 child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="CompanyName" type="xsd:string" />  
    <xsd:attribute name="City" type="xsd:string" />  
    <xsd:attribute name="OrderList"   
                       type="xsd:IDREFS"   
                       sql:relation="CustOrder"   
                       sql:field="OrderID"  
                       sql:relationship="CustCustOrder" >  
    </xsd:attribute>  
  </xsd:complexType>  
 </xsd:element>  
  
  <xsd:element name="Order" sql:relation="CustOrder" >  
   <xsd:complexType>  
    <xsd:attribute name="OrderID" type="xsd:string" />  
    <xsd:attribute name="CustomerID" type="xsd:integer" />  
    <xsd:attribute name="OrderDate" type="xsd:date" />  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="2ee33-186">Étant donné que le chargement en masse ignore les nœuds de type IDREFS, aucune génération d’enregistrement n’est générée lorsque le nœud d’attribut **OrderList** entre dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="2ee33-186">Because Bulk Load ignores the nodes of IDREFS type, there is no record generation when the **OrderList** attribute node enters into scope.</span></span> <span data-ttu-id="2ee33-187">Par conséquent, si vous souhaitez que les enregistrements de commandes soient ajoutés à la table Orders, vous devez décrire ces commandes quelque part dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="2ee33-187">Therefore, if you want the order records added to the Orders table, you must describe those orders somewhere in the schema.</span></span> <span data-ttu-id="2ee33-188">Dans ce schéma, la spécification de l' **\<Order>** élément garantit que le chargement en masse XML ajoute les enregistrements de commande à la table Orders.</span><span class="sxs-lookup"><span data-stu-id="2ee33-188">In this schema, specifying the **\<Order>** element ensures that XML Bulk Load adds the order records to the Orders table.</span></span> <span data-ttu-id="2ee33-189">L' **\<Order>** élément décrit tous les attributs requis pour remplir l’enregistrement de la table CustOrder.</span><span class="sxs-lookup"><span data-stu-id="2ee33-189">The **\<Order>** element describes all the attributes that are required to fill the record for the CustOrder table.</span></span>  
  
 <span data-ttu-id="2ee33-190">Vous devez vous assurer que les valeurs **CustomerID** et **OrderID** de l' **\<Customer>** élément correspondent aux valeurs de l' **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="2ee33-190">You must ensure that the **CustomerID** and **OrderID** values in the **\<Customer>** element match the values in the **\<Order>** element.</span></span> <span data-ttu-id="2ee33-191">Vous êtes chargé de maintenir l'intégrité référentielle.</span><span class="sxs-lookup"><span data-stu-id="2ee33-191">You are responsible for maintaining referential integrity.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="2ee33-192">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="2ee33-192">To test a working sample</span></span>  
  
1.  <span data-ttu-id="2ee33-193">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="2ee33-193">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
                  CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
                  CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID),  
                  OrderDate      datetime DEFAULT '2000-01-01')  
    GO  
    ```  
  
2.  <span data-ttu-id="2ee33-194">Enregistrez le schéma de mappage fourni dans cet exemple sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="2ee33-194">Save the mapping schema provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="2ee33-195">Enregistrez l'exemple de données XML ci-après sous le nom SampleXMLData.xml :</span><span class="sxs-lookup"><span data-stu-id="2ee33-195">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai" City="NY"  
                 OrderList="Ord1 Ord2" />  
      <Customers CustomerID="1112" CompanyName="Dont Know" City="LA"  
                 OrderList="Ord3 Ord4" />  
      <Order OrderID="Ord1" CustomerID="1111" OrderDate="1999-01-01" />  
      <Order OrderID="Ord2" CustomerID="1111" OrderDate="1999-02-01" />  
      <Order OrderID="Ord3" CustomerID="1112" OrderDate="1999-03-01" />  
      <Order OrderID="Ord4" CustomerID="1112" OrderDate="1999-04-01" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="2ee33-196">Pour exécuter le chargement en masse XML, enregistrez et exécutez cet exemple VBScript (SampleVB.vbs) :</span><span class="sxs-lookup"><span data-stu-id="2ee33-196">To execute XML Bulk Load, save and execute this VBScript example (SampleVB.vbs):</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
