---
title: Suppression de données à l’aide de codes XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612725"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="f3b8b-102">Suppression de données à l'aide de codes de mise à jour (updategrams) XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f3b8b-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="f3b8b-103">Un mise à jour indique une opération de suppression lorsqu’une instance d’enregistrement apparaît dans le **\<before>** bloc sans enregistrements correspondants dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="f3b8b-104">Dans ce cas, le mise à jour supprime l’enregistrement du bloc de **\<before>** la base de données.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="f3b8b-105">Voici le format du code de mise à jour pour une opération de suppression :</span><span class="sxs-lookup"><span data-stu-id="f3b8b-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="f3b8b-106">Vous pouvez omettre la **\<after>** balise si le mise à jour exécute uniquement une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="f3b8b-107">Si vous ne spécifiez pas l' `mapping-schema` attribut facultatif, le **\<ElementName>** spécifié dans le mise à jour est mappé à une table de base de données et les éléments ou attributs enfants sont mappés aux colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="f3b8b-108">Si un élément spécifié dans le mise à jour correspond à plusieurs lignes de la table ou qu’il ne correspond à aucune ligne, mise à jour retourne une erreur et annule l’intégralité du **\<sync>** bloc.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="f3b8b-109">Un seul enregistrement peut être supprimé à la fois par un élément dans le code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f3b8b-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="f3b8b-110">Examples</span></span>  
 <span data-ttu-id="f3b8b-111">Les exemples dans cette section utilisent le mappage par défaut (en d'autres termes, aucun schéma de mappage n'est spécifié dans le code de mise à jour).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="f3b8b-112">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="f3b8b-113">Pour créer des exemples fonctionnels à l’aide des exemples suivants, vous devez respecter les exigences spécifiées dans la [Configuration requise pour l’exécution d’exemples SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="f3b8b-114">R.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-114">A.</span></span> <span data-ttu-id="f3b8b-115">Suppression d'un enregistrement à l'aide d'un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="f3b8b-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="f3b8b-116">Les codes de mise à jour suivants suppriment deux enregistrements de la table HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="f3b8b-117">Dans ces exemples, le code de mise à jour ne spécifie pas de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="f3b8b-118">Par conséquent, le code de mise à jour utilise le mappage par défaut, dans lequel le nom d'élément est mappé à un nom de table et les attributs ou sous-éléments sont mappés aux colonnes.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="f3b8b-119">Ce premier mise à jour est centré sur les attributs et identifie deux décalages (jour-soirée et soir-nuit) dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="f3b8b-120">Étant donné qu’il n’y a aucun enregistrement correspondant dans le **\<after>** bloc, il s’agit d’une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="f3b8b-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="f3b8b-121">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="f3b8b-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="f3b8b-122">Complétez l’exemple B (« insertion de plusieurs enregistrements à l’aide d’un mise à jour ») lors de l' [insertion de données à l’aide de XML codes &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="f3b8b-123">Copiez le mise à jour ci-dessus dans le bloc-notes et enregistrez-le en tant que Updategram-RemoveShifts.xml dans le même dossier que celui utilisé pour la finalisation (« insertion de plusieurs enregistrements à l’aide d’un mise à jour ») lors de l' [insertion de données à l’aide de XML codes &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="f3b8b-124">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="f3b8b-125">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="f3b8b-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b8b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3b8b-126">See Also</span></span>  
 [<span data-ttu-id="f3b8b-127">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f3b8b-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
