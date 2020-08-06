---
title: Mise à jour de données à l’aide de codes XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611692"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="5d6c7-102">Mise à jour de données à l'aide de codes de mise à jour (updategrams) XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="5d6c7-103">Lorsque vous mettez à jour des données existantes, vous devez spécifier à la fois les **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="5d6c7-104">Les éléments spécifiés dans **\<before>** les **\<after>** blocs et décrivent la modification souhaitée.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="5d6c7-105">Le mise à jour utilise le ou les éléments spécifiés dans le **\<before>** bloc pour identifier les enregistrements existants dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="5d6c7-106">Le ou les éléments correspondants dans le **\<after>** bloc indiquent la manière dont les enregistrements doivent s’afficher après l’exécution de l’opération de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="5d6c7-107">À partir de ces informations, mise à jour crée une instruction SQL qui correspond au **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="5d6c7-108">Le code de mise à jour (updategram) utilise ensuite cette instruction pour mettre à jour la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="5d6c7-109">Voici le format du code de mise à jour (updategram) pour une opération de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="5d6c7-110">Les éléments du **\<before>** bloc identifient les enregistrements existants dans les tables de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="5d6c7-111">Les éléments du **\<after>** bloc décrivent comment les enregistrements spécifiés dans le **\<before>** bloc doivent apparaître après l’application des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="5d6c7-112">L'attribut `mapping-schema` identifie le schéma de mappage à utiliser par le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="5d6c7-113">Si le mise à jour spécifie un schéma de mappage, les noms d’élément et d’attribut spécifiés dans les **\<before>** **\<after>** blocs et doivent correspondre aux noms du schéma.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="5d6c7-114">Le schéma de mappage mappe ces noms d'éléments ou d'attributs aux noms de tables et de colonnes de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="5d6c7-115">Si le code de mise à jour (updategram) ne spécifie pas de schéma, le mappage par défaut est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="5d6c7-116">Dans le mappage par défaut, le **\<ElementName>** spécifié dans le mise à jour est mappé à la table de base de données et les éléments ou attributs enfants sont mappés aux colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="5d6c7-117">Un élément du **\<before>** bloc doit correspondre à une seule ligne de table dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="5d6c7-118">Si l’élément correspond à plusieurs lignes de table ou ne correspond à aucune ligne de table, le mise à jour retourne une erreur et annule l’intégralité du **\<sync>** bloc.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="5d6c7-119">Un mise à jour peut inclure plusieurs **\<sync>** blocs.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="5d6c7-120">Chaque **\<sync>** bloc est traité comme une transaction.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="5d6c7-121">Chaque **\<sync>** bloc peut avoir plusieurs **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="5d6c7-122">Par exemple, si vous mettez à jour deux des enregistrements existants, vous pouvez spécifier deux **\<before>** paires et **\<after>** , une pour chaque enregistrement en cours de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="5d6c7-123">Utilisation de l'attribut updg:id</span><span class="sxs-lookup"><span data-stu-id="5d6c7-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="5d6c7-124">Quand plusieurs éléments sont spécifiés dans **\<before>** les **\<after>** blocs et, utilisez l' `updg:id` attribut pour marquer les lignes dans les **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="5d6c7-125">La logique de traitement utilise ces informations pour déterminer quel enregistrement dans les **\<before>** paires de blocs avec quel enregistrement dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="5d6c7-126">L'attribut `updg:id` n'est pas nécessaire (bien qu'il soit recommandé) si l'un ou l'autre des cas de figure se présente :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="5d6c7-127">L'attribut `sql:key-fields` est défini sur les éléments du schéma de mappage spécifié.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="5d6c7-128">Il existe une ou plusieurs valeurs spécifiques fournies pour le ou les champs clés dans le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="5d6c7-129">Si l’un ou l’autre est le cas, le mise à jour utilise les colonnes clés spécifiées dans le `sql:key-fields` pour coupler les éléments dans les **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="5d6c7-130">Si le schéma de mappage n'identifie pas de colonnes clés (via `sql:key-fields`) ou si le code de mise à jour (updategram) met à jour une valeur de colonne clé, vous devez spécifier `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="5d6c7-131">Les enregistrements qui sont identifiés dans les **\<before>** **\<after>** blocs et n’ont pas besoin d’être dans le même ordre.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="5d6c7-132">L' `updg:id` attribut force l’association entre les éléments spécifiés dans les **\<before>** blocs et **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="5d6c7-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="5d6c7-133">Si vous spécifiez un élément dans le **\<before>** bloc et un seul élément correspondant dans le **\<after>** bloc, l’utilisation de `updg:id` n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="5d6c7-134">Toutefois, il est recommandé de spécifier quand même `updg:id` pour éviter toute ambiguïté.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5d6c7-135">Exemples</span><span class="sxs-lookup"><span data-stu-id="5d6c7-135">Examples</span></span>  
 <span data-ttu-id="5d6c7-136">Avant d'utiliser les exemples de code de mise à jour (updategram), notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="5d6c7-137">La plupart des exemples utilisent le mappage par défaut (en d'autres termes, aucun schéma de mappage n'est spécifié dans le code de mise à jour (updategram)).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="5d6c7-138">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="5d6c7-139">La plupart des exemples sont basés sur l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="5d6c7-140">Toutes les mises à jour sont appliquées aux tables de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="5d6c7-141">Vous pouvez restaurer la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="5d6c7-142">R.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-142">A.</span></span> <span data-ttu-id="5d6c7-143">Mise à jour d'un enregistrement</span><span class="sxs-lookup"><span data-stu-id="5d6c7-143">Updating a record</span></span>  
 <span data-ttu-id="5d6c7-144">Le code de mise à jour (updategram) suivant met à jour le nom de famille d'un employé en le remplaçant par Fuller dans la table Person.Contact de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="5d6c7-145">Le code de mise à jour (updategram) ne spécifie pas de schéma de mappage ; par conséquent, le mappage par défaut est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="5d6c7-146">L’enregistrement décrit dans le **\<before>** bloc représente l’enregistrement actif dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="5d6c7-147">Mise à jour utilise toutes les valeurs de colonne spécifiées dans le **\<before>** bloc pour Rechercher l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="5d6c7-148">Dans ce mise à jour, le **\<before>** bloc fournit uniquement la colonne ContactID ; par conséquent, mise à jour utilise uniquement la valeur pour Rechercher l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="5d6c7-149">Si vous deviez ajouter la valeur de LastName à ce bloc, le code de mise à jour (updategram) utiliserait à la fois les valeurs de ContactID et de LastName pour effectuer la recherche.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="5d6c7-150">Dans ce mise à jour, le **\<after>** bloc fournit uniquement la valeur de la colonne LastName, car il s’agit de la seule valeur en cours de modification.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-151">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-152">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-153">Enregistrez le fichier sous le nom UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="5d6c7-154">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-155">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="5d6c7-156">B.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-156">B.</span></span> <span data-ttu-id="5d6c7-157">Mise à jour de plusieurs enregistrements à l'aide de l'attribut updg:id</span><span class="sxs-lookup"><span data-stu-id="5d6c7-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="5d6c7-158">Dans cet exemple, le code de mise à jour (updategram) effectue deux mises à jour sur la table HumanResources.Shift de la base de données AdventureWorks :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="5d6c7-159">Il modifie le nom de l'équipe de jour d'origine qui commence à 7 h 09 en remplaçant « Day » par « Early Morning ».</span><span class="sxs-lookup"><span data-stu-id="5d6c7-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="5d6c7-160">Il insère une nouvelle équipe nommée « Late Morning » qui commence à 10 h 00.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="5d6c7-161">Dans mise à jour, l' `updg:id` attribut crée des associations entre les éléments des **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="5d6c7-162">Notez que l' `updg:id` attribut couple la première instance de l' \<HumanResources.Shift> élément dans le **\<before>** bloc à la deuxième instance de l' \<HumanResources.Shift> élément dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-163">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-164">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-165">Enregistrez le fichier sous le nom UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="5d6c7-166">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-167">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="5d6c7-168">C.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-168">C.</span></span> <span data-ttu-id="5d6c7-169">Spécification \<before> de plusieurs \<after> blocs et</span><span class="sxs-lookup"><span data-stu-id="5d6c7-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="5d6c7-170">Pour éviter toute ambiguïté, vous pouvez écrire le mise à jour dans l’exemple B à l’aide de plusieurs **\<before>** **\<after>** paires de blocs et.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="5d6c7-171">La spécification de **\<before>** **\<after>** paires et est un moyen de spécifier plusieurs mises à jour avec un minimum de confusion.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="5d6c7-172">En outre, si chacun des **\<before>** **\<after>** blocs et spécifie au plus un élément, vous n’êtes pas obligé d’utiliser l' `updg:id` attribut.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5d6c7-173">Pour former une paire, la **\<after>** balise doit suivre immédiatement la **\<before>** balise correspondante.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="5d6c7-174">Dans le mise à jour suivant, la première **\<before>** et la **\<after>** paire met à jour le nom du décalage pour l’équipe de jour.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="5d6c7-175">La seconde paire insère un nouvel enregistrement d'équipe.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-176">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-177">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-178">Enregistrez le fichier sous le nom UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="5d6c7-179">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-180">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="5d6c7-181">D.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-181">D.</span></span> <span data-ttu-id="5d6c7-182">Spécification de plusieurs \<sync> blocs</span><span class="sxs-lookup"><span data-stu-id="5d6c7-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="5d6c7-183">Vous pouvez spécifier plusieurs **\<sync>** blocs dans un mise à jour.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="5d6c7-184">Chaque **\<sync>** bloc spécifié est une transaction indépendante.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="5d6c7-185">Dans le mise à jour suivant, le premier **\<sync>** bloc met à jour un enregistrement dans la table Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="5d6c7-186">Pour des raisons de simplicité, le code de mise à jour (updategram) spécifie uniquement les valeurs de colonne requises, la valeur d'identité (CustomerID) et la valeur mise à jour (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="5d6c7-187">Le deuxième **\<sync>** bloc ajoute deux enregistrements à la table Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="5d6c7-188">Pour cette table, SalesOrderID est une colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="5d6c7-189">Par conséquent, mise à jour ne spécifie pas la valeur de SalesOrderID dans chacun des \<Sales.SalesOrderHeader> éléments.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="5d6c7-190">La spécification de plusieurs **\<sync>** blocs est utile, car si le deuxième **\<sync>** bloc (une transaction) ne parvient pas à ajouter des enregistrements à la table Sales. SalesOrderHeader, le premier **\<sync>** bloc peut toujours mettre à jour l’enregistrement du client dans la table Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-191">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-192">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-193">Enregistrez le fichier sous le nom UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="5d6c7-194">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-195">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="5d6c7-196">E.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-196">E.</span></span> <span data-ttu-id="5d6c7-197">Utilisation d'un schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="5d6c7-197">Using a mapping schema</span></span>  
 <span data-ttu-id="5d6c7-198">Dans cet exemple, le code de mise à jour (updategram) spécifie un schéma de mappage à l'aide de l'attribut `mapping-schema`.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="5d6c7-199">(Il n'y a aucun mappage par défaut ; en d'autres termes, le schéma de mappage fournit le mappage nécessaire des éléments et attributs du code de mise à jour (updategram) aux tables et colonnes de la base de données.)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="5d6c7-200">Les éléments et attributs spécifiés dans le code de mise à jour (updategram) font référence aux éléments et attributs du schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="5d6c7-201">Le schéma de mappage XSD suivant contient les **\<Customer>** **\<Order>** éléments, et **\<OD>** qui mappent aux tables Sales. Customer, sales. SalesOrderHeader et Sales. SalesOrderDetail dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5d6c7-202">Ce schéma de mappage (UpdategramMappingSchema.xml) est spécifié dans le code de mise à jour (updategram) suivant.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="5d6c7-203">Le code de mise à jour (updategram) ajoute un article dans la table Sales.SalesOrderDetail pour une commande spécifique.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="5d6c7-204">Mise à jour comprend des éléments imbriqués : un **\<OD>** élément imbriqué à l’intérieur d’un **\<Order>** élément.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="5d6c7-205">La relation clé primaire/clé étrangère entre ces deux éléments est spécifiée dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-206">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-207">Copiez le schéma de mappage ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-208">Enregistrez le fichier sous le nom UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="5d6c7-209">Copiez le modèle de code de mise à jour (updategram) ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-210">Enregistrez le fichier sous le nom UpdateWithMappingSchema.xml dans le même dossier que celui utilisé pour l'enregistrement du schéma de mappage (UpdategramMappingSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="5d6c7-211">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-212">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="5d6c7-213">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="5d6c7-214">F.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-214">F.</span></span> <span data-ttu-id="5d6c7-215">Utilisation d'un schéma de mappage avec les attributs IDREFS</span><span class="sxs-lookup"><span data-stu-id="5d6c7-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="5d6c7-216">Cet exemple montre comment les codes de mise à jour (updategrams) utilisent les attributs IDREFS du schéma de mappage pour mettre à jour des enregistrements dans plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="5d6c7-217">Pour cet exemple, supposez que la base de données comporte les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="5d6c7-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="5d6c7-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="5d6c7-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="5d6c7-221">Dans la mesure où un étudiant peut s'inscrire à de nombreux cours et comme un cours peut avoir de nombreux étudiants, la troisième table, la table Enrollment, est requise pour représenter cette relation M:N.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="5d6c7-222">Le schéma de mappage XSD suivant fournit une vue XML des tables à l’aide **\<Student>** des **\<Course>** éléments, et **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="5d6c7-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="5d6c7-223">Les attributs **IDREFS** dans le schéma de mappage spécifient la relation entre ces éléments.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="5d6c7-224">L’attribut **StudentIDList** de l' **\<Course>** élément est un attribut de type **IDREFS** qui fait référence à la colonne StudentID de la table d’inscription.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="5d6c7-225">De même, l’attribut **EnrolledIn** sur l' **\<Student>** élément est un attribut de type **IDREFS** qui fait référence à la colonne CourseID dans la table d’inscription.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5d6c7-226">Chaque fois que vous spécifiez ce schéma dans un code de mise à jour (updategram) et que vous insérez un enregistrement dans la table Course, le code de mise à jour (updategram) insère un nouvel enregistrement de cours dans la table Course.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="5d6c7-227">Si vous spécifiez un ou plusieurs nouveaux ID d'étudiants pour l'attribut StudentIDList, le code de mise à jour (updategram) insère également un enregistrement dans la table Enrollment pour chaque nouvel étudiant.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="5d6c7-228">Le code de mise à jour (updategram) s'assure qu'aucun doublon n'est ajouté à la table Enrollment.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5d6c7-229">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="5d6c7-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5d6c7-230">Créez ces tables dans la base de données spécifiée dans la racine virtuelle :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="5d6c7-231">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="5d6c7-232">Copiez le schéma de mappage ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="5d6c7-233">Enregistrez le fichier sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="5d6c7-234">Enregistrez le code de mise à jour (SampleUpdategram) dans le même dossier que celui utilisé pour l'enregistrement du schéma de mappage à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="5d6c7-235">(Ce code de mise à jour (updategram) supprime un étudiant pour lequel StudentID="1" dans le cours CS102.)</span><span class="sxs-lookup"><span data-stu-id="5d6c7-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="5d6c7-236">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="5d6c7-237">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="5d6c7-238">Enregistrez et exécutez le code de mise à jour (updategram) suivant, comme décrit dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="5d6c7-239">Le code de mise à jour (updategram) rajoute l'étudiant pour lequel StudentID="1" dans le cours CS102 en insérant un enregistrement dans la table Enrollment.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="5d6c7-240">Enregistrez et exécutez le mise à jour suivant comme décrit dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="5d6c7-241">Ce code de mise à jour (updategram) insère trois nouveaux étudiants et les inscrit au cours CS101.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="5d6c7-242">À nouveau, la relation IDREFS insère des enregistrements dans la table Enrollment.</span><span class="sxs-lookup"><span data-stu-id="5d6c7-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="5d6c7-243">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="5d6c7-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="5d6c7-244">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5d6c7-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6c7-245">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d6c7-245">See Also</span></span>  
 [<span data-ttu-id="5d6c7-246">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5d6c7-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
