---
title: Gestion des problèmes de concurrence de base de données dans codes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611701"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="35c62-102">Gestion des problèmes d'accès concurrentiel aux bases de données dans les codes de mise à jour (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="35c62-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="35c62-103">Comme d'autres mécanismes de mise à jour de base de données, les codes de mise à jour doivent faire face à des mises à jour simultanées de données dans un environnement multi-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35c62-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="35c62-104">Les codes de mise à jour utilisent le contrôle d'accès concurrentiel optimiste, qui utilise la comparaison des données de champ sélectionnées comme instantanés pour garantir que les données à mettre à jour n'ont pas été altérées par une autre application utilisateur depuis qu'elles ont été lues à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="35c62-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="35c62-105">Codes inclut ces valeurs d’instantané dans le **\<before>** bloc du codes.</span><span class="sxs-lookup"><span data-stu-id="35c62-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="35c62-106">Avant de mettre à jour la base de données, le mise à jour vérifie les valeurs spécifiées dans le **\<before>** bloc par rapport aux valeurs actuellement présentes dans la base de données pour s’assurer que la mise à jour est valide.</span><span class="sxs-lookup"><span data-stu-id="35c62-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="35c62-107">Le contrôle d'accès concurrentiel optimiste offre trois niveaux de protection dans un code de mise à jour : bas (aucune), intermédiaire et haut.</span><span class="sxs-lookup"><span data-stu-id="35c62-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="35c62-108">Vous pouvez décider de quel niveau de protection vous avez besoin en spécifiant le code de mise à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="35c62-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="35c62-109">Niveau de protection le plus bas</span><span class="sxs-lookup"><span data-stu-id="35c62-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="35c62-110">Ce niveau correspond à une mise à jour aveugle, dans laquelle la mise à jour est traitée sans se référer aux autres mises à jour effectuées depuis la dernière lecture de la base de données.</span><span class="sxs-lookup"><span data-stu-id="35c62-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="35c62-111">Dans ce cas, vous spécifiez uniquement la ou les colonnes de clé primaire dans le **\<before>** bloc pour identifier l’enregistrement et vous spécifiez les informations mises à jour dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="35c62-112">Par exemple, le nouveau numéro de téléphone du contact dans le code de mise à jour suivant est correct, indépendamment de ce que le numéro de téléphone était précédemment.</span><span class="sxs-lookup"><span data-stu-id="35c62-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="35c62-113">Notez que le **\<before>** bloc spécifie uniquement la colonne de clé primaire (ContactID).</span><span class="sxs-lookup"><span data-stu-id="35c62-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="35c62-114">Niveau de protection intermédiaire</span><span class="sxs-lookup"><span data-stu-id="35c62-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="35c62-115">Dans ce niveau de protection, le code de mise à jour compare la ou les valeurs actuelles des données qui sont mises à jour avec la ou les valeurs présentes dans la ou les colonnes de la base de données pour garantir que les valeurs n'ont pas été modifiées par quelque autre transaction depuis que l'enregistrement a été lu par votre transaction.</span><span class="sxs-lookup"><span data-stu-id="35c62-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="35c62-116">Vous pouvez bénéficier de ce niveau de protection en spécifiant la ou les colonnes de clé primaire et la ou les colonnes que vous mettez à jour dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="35c62-117">Par exemple, ce code de mise à jour modifie la valeur dans la colonne Phone de la table Person.Contact pour le contact dont ContactID a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="35c62-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="35c62-118">Le **\<before>** bloc spécifie l’attribut **Phone** pour garantir que cette valeur d’attribut correspond à la valeur de la colonne correspondante dans la base de données avant d’appliquer la valeur mise à jour.</span><span class="sxs-lookup"><span data-stu-id="35c62-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="35c62-119">Niveau de protection élevé</span><span class="sxs-lookup"><span data-stu-id="35c62-119">High Level of Protection</span></span>  
 <span data-ttu-id="35c62-120">Un niveau de protection élevé garantit qu'un enregistrement reste le même depuis que votre application a lu pour la dernière fois cet enregistrement (autrement dit, depuis que votre application a lu l'enregistrement, celui-ci n'a été modifié par aucune autre transaction).</span><span class="sxs-lookup"><span data-stu-id="35c62-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="35c62-121">Il existe deux façons d'obtenir ce niveau de protection élevé contre les mises à jour simultanées :</span><span class="sxs-lookup"><span data-stu-id="35c62-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="35c62-122">Spécifiez des colonnes supplémentaires dans la table du **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="35c62-123">Si vous spécifiez des colonnes supplémentaires dans le **\<before>** bloc, mise à jour compare les valeurs spécifiées pour ces colonnes aux valeurs qui se trouvaient dans la base de données avant d’appliquer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="35c62-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="35c62-124">Si l'une quelconque des colonnes d'enregistrement a changé depuis que votre transaction a lu l'enregistrement, le code de mise à jour n'effectue pas la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="35c62-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="35c62-125">Par exemple, le mise à jour suivant met à jour le nom de l’équipe, mais spécifie des colonnes supplémentaires (StartTime, EndTime) dans le **\<before>** bloc, ce qui demande un niveau de protection supérieur contre les mises à jour simultanées.</span><span class="sxs-lookup"><span data-stu-id="35c62-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="35c62-126">Cet exemple spécifie le niveau de protection le plus élevé en spécifiant toutes les valeurs de colonne de l’enregistrement dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="35c62-127">Spécifiez la colonne timestamp (si disponible) dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="35c62-128">Au lieu de spécifier toutes les colonnes d’enregistrement dans le `<before` bloc>, vous pouvez simplement spécifier la colonne timestamp (si la table en a une) avec la ou les colonnes de clé primaire dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="35c62-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="35c62-129">La base de données met à jour la colonne timestamp en spécifiant une valeur unique après chaque mise à jour de l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="35c62-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="35c62-130">Dans ce cas, le code de mise à jour compare la valeur de l'horodateur avec la valeur correspondante dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="35c62-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="35c62-131">La valeur d'horodateur stockée dans la base de données est une valeur binaire.</span><span class="sxs-lookup"><span data-stu-id="35c62-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="35c62-132">Par conséquent, la colonne timestamp doit être spécifiée dans le schéma en tant que `dt:type="bin.hex"`, `dt:type="bin.base64"` ou `sql:datatype="timestamp"`.</span><span class="sxs-lookup"><span data-stu-id="35c62-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="35c62-133">(Vous pouvez spécifier le `xml` type de données ou le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] type de données.)</span><span class="sxs-lookup"><span data-stu-id="35c62-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="35c62-134">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="35c62-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="35c62-135">Créez cette table dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="35c62-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="35c62-136">Ajoutez cet exemple d'enregistrement :</span><span class="sxs-lookup"><span data-stu-id="35c62-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="35c62-137">Copiez le schéma XSD suivant et collez-le dans le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="35c62-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="35c62-138">Enregistrez-le sous le nom ConcurrencySampleSchema.xml :</span><span class="sxs-lookup"><span data-stu-id="35c62-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="35c62-139">Copiez le code de mise à jour ci-dessous dans le Bloc-notes et enregistrez-le sous le nom ConcurrencySampleTemplate.xml dans le répertoire où vous avez enregistré le schéma créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="35c62-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="35c62-140">(Notez que la valeur d'horodateur ci-dessous pour LastUpdated différera dans votre exemple de table Customer et copiez donc la valeur réelle pour LastUpdated à partir de la table et collez-la dans le code de mise à jour.)</span><span class="sxs-lookup"><span data-stu-id="35c62-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="35c62-141">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="35c62-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="35c62-142">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="35c62-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="35c62-143">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="35c62-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35c62-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35c62-144">See Also</span></span>  
 [<span data-ttu-id="35c62-145">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="35c62-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
