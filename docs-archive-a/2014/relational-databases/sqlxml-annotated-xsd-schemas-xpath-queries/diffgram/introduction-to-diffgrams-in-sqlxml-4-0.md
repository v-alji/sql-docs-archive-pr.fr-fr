---
title: Présentation des DiffGrams dans SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotations [SQLXML]
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: 1902d67f-baf3-46e6-a36c-b24b5ba6f8ea
author: rothja
ms.author: jroth
ms.openlocfilehash: e57d87d064ace47247f342ed002b162b920e627f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610545"
---
# <a name="introduction-to-diffgrams-in-sqlxml-40"></a><span data-ttu-id="1111f-102">Introduction aux DiffGrams dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="1111f-102">Introduction to DiffGrams in SQLXML 4.0</span></span>
  <span data-ttu-id="1111f-103">Cette rubrique fournit une brève introduction aux DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="1111f-103">This topic provides a brief introduction to DiffGrams.</span></span>  
  
## <a name="diffgram-format"></a><span data-ttu-id="1111f-104">Format DiffGram</span><span class="sxs-lookup"><span data-stu-id="1111f-104">DiffGram Format</span></span>  
 <span data-ttu-id="1111f-105">Voici le format DiffGram général :</span><span class="sxs-lookup"><span data-stu-id="1111f-105">This is the general DiffGram format:</span></span>  
  
```  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
   <DataInstance>  
      ...  
   </DataInstance>  
   [<diffgr:before>  
        ...  
   </diffgr:before>]  
  
   [<diffgr:errors>  
        ...  
   </diffgr:errors>]  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="1111f-106">Le format DiffGram est constitué des blocs suivants :</span><span class="sxs-lookup"><span data-stu-id="1111f-106">The DiffGram format consists of these blocks:</span></span>  
  
 **\<DataInstance>**  
 <span data-ttu-id="1111f-107">Le nom de cet élément, **DataInstance**, est utilisé à des fins d’explication dans cette documentation.</span><span class="sxs-lookup"><span data-stu-id="1111f-107">The name of this element, **DataInstance**, is used for explanation purposes in this documentation.</span></span> <span data-ttu-id="1111f-108">Par exemple, si le DiffGram a été généré à partir d’un DataSet dans le .NET Framework, la valeur de la propriété **Name** du DataSet est utilisée comme nom de cet élément.</span><span class="sxs-lookup"><span data-stu-id="1111f-108">For example, if the DiffGram were generated from a dataset in the .NET Framework, the value of the **Name** property of the dataset would be used as the name of this element.</span></span> <span data-ttu-id="1111f-109">Ce bloc contient toutes les données pertinentes après la modification, y compris éventuellement les données qui n'ont pas été modifiées.</span><span class="sxs-lookup"><span data-stu-id="1111f-109">This block contains all relevant data after the change, possibly including data that has not been modified.</span></span> <span data-ttu-id="1111f-110">La logique de traitement DiffGram ignore les éléments de ce bloc pour lesquels l’attribut **diffgr : hasChanges** n’est pas spécifié.</span><span class="sxs-lookup"><span data-stu-id="1111f-110">The DiffGram processing logic ignores the elements in this block for which the **diffgr:hasChanges** attribute is not specified.</span></span>  
  
 **\<diffgr:before>**  
 <span data-ttu-id="1111f-111">Ce bloc facultatif contient les instances (éléments) de l'enregistrement d'origine qui doivent être mises à jour ou supprimées.</span><span class="sxs-lookup"><span data-stu-id="1111f-111">This optional block contains the original record instances (elements) that must be updated or deleted.</span></span> <span data-ttu-id="1111f-112">Toutes les tables de base de données qui sont modifiées (mises à jour ou supprimées) par le DiffGram doivent apparaître en tant qu’éléments de niveau supérieur dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="1111f-112">All the database tables being modified (updated or deleted) by the DiffGram must appear as top-level elements in the **\<before>** block.</span></span>  
  
 **\<diffgr:errors>**  
 <span data-ttu-id="1111f-113">Ce bloc facultatif est ignoré par la logique de traitement DiffGram.</span><span class="sxs-lookup"><span data-stu-id="1111f-113">This optional block is ignored by the DiffGram processing logic.</span></span>  
  
## <a name="diffgram-annotations"></a><span data-ttu-id="1111f-114">Annotations DiffGram</span><span class="sxs-lookup"><span data-stu-id="1111f-114">DiffGram Annotations</span></span>  
 <span data-ttu-id="1111f-115">Ces annotations sont définies dans l’espace de noms DiffGram **« urn : schemas-microsoft-com : XML-DiffGram-01 »**:</span><span class="sxs-lookup"><span data-stu-id="1111f-115">These annotations are defined in the DiffGram namespace **"urn:schemas-microsoft-com:xml-diffgram-01"**:</span></span>  
  
 <span data-ttu-id="1111f-116">**id**</span><span class="sxs-lookup"><span data-stu-id="1111f-116">**id**</span></span>  
 <span data-ttu-id="1111f-117">Cet attribut est utilisé pour coupler les éléments dans les **\<before>** **\<DataInstance>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="1111f-117">This attribute is used to pair the elements in the **\<before>** and the **\<DataInstance>** blocks.</span></span>  
  
 <span data-ttu-id="1111f-118">**hasChanges**</span><span class="sxs-lookup"><span data-stu-id="1111f-118">**hasChanges**</span></span>  
 <span data-ttu-id="1111f-119">Pour une opération d’insertion ou de mise à jour, le DiffGram doit spécifier cet attribut avec la valeur **insérée** ou **modifiée**.</span><span class="sxs-lookup"><span data-stu-id="1111f-119">For an insert or an update operation, the DiffGram must specify this attribute with the value **inserted** or **modified**.</span></span> <span data-ttu-id="1111f-120">Si cet attribut n’est pas présent, l’élément correspondant dans **\<DataInstance>** est ignoré par la logique de traitement et aucune mise à jour n’est effectuée.</span><span class="sxs-lookup"><span data-stu-id="1111f-120">If this attribute is not present, the corresponding element in the **\<DataInstance>** is ignored by the processing logic and no updates are performed.</span></span> <span data-ttu-id="1111f-121">Pour obtenir des exemples fonctionnels, consultez [exemples DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1111f-121">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="1111f-122">**ID**</span><span class="sxs-lookup"><span data-stu-id="1111f-122">**parentID**</span></span>  
 <span data-ttu-id="1111f-123">Cet attribut est utilisé pour spécifier les relations parent-enfant parmi les éléments du DiffGram.</span><span class="sxs-lookup"><span data-stu-id="1111f-123">This attribute is used to specify parent-child relationships among the elements in the DiffGram.</span></span> <span data-ttu-id="1111f-124">Cet attribut apparaît uniquement dans le \<before> bloc.</span><span class="sxs-lookup"><span data-stu-id="1111f-124">This attribute appears only in the \<before> block.</span></span> <span data-ttu-id="1111f-125">Il est utilisé par SQLXML lors de l'application de mises à jour.</span><span class="sxs-lookup"><span data-stu-id="1111f-125">It is used by SQLXML when applying updates.</span></span> <span data-ttu-id="1111f-126">La relation parent-enfant est utilisée pour déterminer l'ordre dans lequel les éléments du DiffGram sont traités.</span><span class="sxs-lookup"><span data-stu-id="1111f-126">The parent-child relationship is used in determining the order in which the elements in the DiffGram are processed.</span></span>  
  
## <a name="understanding-the-diffgram-processing-logic"></a><span data-ttu-id="1111f-127">Fonctionnement de la logique de traitement DiffGram</span><span class="sxs-lookup"><span data-stu-id="1111f-127">Understanding the DiffGram Processing Logic</span></span>  
 <span data-ttu-id="1111f-128">La logique de traitement DiffGram utilise certaines règles pour déterminer si une opération est une opération d'insertion, de mise à jour ou de suppression.</span><span class="sxs-lookup"><span data-stu-id="1111f-128">The DiffGram processing logic uses certain rules to determine whether an operation is an insert, update, or delete operation.</span></span> <span data-ttu-id="1111f-129">Ces règles sont décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="1111f-129">These rules are described in the following table.</span></span>  
  
|<span data-ttu-id="1111f-130">Opération</span><span class="sxs-lookup"><span data-stu-id="1111f-130">Operation</span></span>|<span data-ttu-id="1111f-131">Description</span><span class="sxs-lookup"><span data-stu-id="1111f-131">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1111f-132">Insert</span><span class="sxs-lookup"><span data-stu-id="1111f-132">Insert</span></span>|<span data-ttu-id="1111f-133">Un DiffGram indique une opération d’insertion lorsqu’un élément apparaît dans le **\<DataInstance>** bloc mais pas dans le **\<before>** bloc correspondant, et l’attribut **diffgr : hasChanges** est spécifié (**diffgr : hasChanges = inserted**) sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="1111f-133">A DiffGram indicates an insert operation when an element appears in the **\<DataInstance>** block but not in the corresponding **\<before>** block, and the **diffgr:hasChanges** attribute is specified (**diffgr:hasChanges=inserted**) on the element.</span></span> <span data-ttu-id="1111f-134">Dans ce cas, le DiffGram insère l’instance d’enregistrement spécifiée dans le **\<DataInstance>** bloc dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1111f-134">In this case, the DiffGram inserts the record instance that is specified in the **\<DataInstance>** block into the database.</span></span><br /><br /> <span data-ttu-id="1111f-135">Si l’attribut **diffgr : hasChanges** n’est pas spécifié, l’élément est ignoré par la logique de traitement et aucune insertion n’est effectuée.</span><span class="sxs-lookup"><span data-stu-id="1111f-135">If the **diffgr:hasChanges** attribute is not specified, the element is ignored by the processing logic and no insert is performed.</span></span> <span data-ttu-id="1111f-136">Pour obtenir des exemples fonctionnels, consultez [exemples DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1111f-136">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span>|  
|<span data-ttu-id="1111f-137">Update</span><span class="sxs-lookup"><span data-stu-id="1111f-137">Update</span></span>|<span data-ttu-id="1111f-138">Le DiffGram indique une opération de mise à jour lorsqu’il existe un élément dans le \<before> bloc pour lequel il existe un élément correspondant dans le **\<DataInstance>** bloc (autrement dit, les deux éléments ont un attribut **diffgr : ID** avec la même valeur) et l’attribut **diffgr : hasChanges** est spécifié avec la valeur **modifiée** sur l’élément dans le **\<DataInstance>** bloc.</span><span class="sxs-lookup"><span data-stu-id="1111f-138">The DiffGram indicates an update operation when there is an element in the \<before> block for which there is a corresponding element in the **\<DataInstance>** block (that is, both elements have a **diffgr:id** attribute with same value) and the **diffgr:hasChanges** attribute is specified with the value **modified** on the element in the **\<DataInstance>** block.</span></span><br /><br /> <span data-ttu-id="1111f-139">Si l’attribut **diffgr : hasChanges** n’est pas spécifié sur l’élément du **\<DataInstance>** bloc, une erreur est retournée par la logique de traitement.</span><span class="sxs-lookup"><span data-stu-id="1111f-139">If the **diffgr:hasChanges** attribute is not specified on the element in the **\<DataInstance>** block, an error is returned by the processing logic.</span></span> <span data-ttu-id="1111f-140">Pour obtenir des exemples fonctionnels, consultez [exemples DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1111f-140">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="1111f-141">Si **diffgr : ParentId** est spécifié dans le **\<before>** bloc, la relation parent-enfant des éléments spécifiés par **ParentId** est utilisée pour déterminer l’ordre dans lequel les enregistrements sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="1111f-141">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are updated.</span></span>|  
|<span data-ttu-id="1111f-142">Supprimer</span><span class="sxs-lookup"><span data-stu-id="1111f-142">Delete</span></span>|<span data-ttu-id="1111f-143">Un DiffGram indique une opération de suppression lorsqu’un élément apparaît dans le **\<before>** bloc mais pas dans le **\<DataInstance>** bloc correspondant.</span><span class="sxs-lookup"><span data-stu-id="1111f-143">A DiffGram indicates a delete operation when an element appears in the **\<before>** block but not in the corresponding **\<DataInstance>** block.</span></span> <span data-ttu-id="1111f-144">Dans ce cas, le DiffGram supprime de la base de données l’instance d’enregistrement spécifiée dans le **\<before>** bloc.</span><span class="sxs-lookup"><span data-stu-id="1111f-144">In this case, the DiffGram deletes the record instance that is specified in the **\<before>** block from the database.</span></span> <span data-ttu-id="1111f-145">Pour obtenir des exemples fonctionnels, consultez [exemples DiffGram &#40;SQLXML 4,0&#41;](diffgram-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1111f-145">For working samples, see [DiffGram Examples &#40;SQLXML 4.0&#41;](diffgram-examples-sqlxml-4-0.md).</span></span><br /><br /> <span data-ttu-id="1111f-146">Si **diffgr : ParentId** est spécifié dans le **\<before>** bloc, la relation parent-enfant des éléments spécifiés par **ParentId** est utilisée pour déterminer l’ordre dans lequel les enregistrements sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="1111f-146">If **diffgr:parentID** is specified in the **\<before>** block, the parent-child relationship of elements that are specified by **parentID** are used in determining the order in which records are deleted.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1111f-147">Les paramètres ne peuvent pas être passés aux DiffGrams.</span><span class="sxs-lookup"><span data-stu-id="1111f-147">Parameters cannot be passed to DiffGrams.</span></span>  
  
  
