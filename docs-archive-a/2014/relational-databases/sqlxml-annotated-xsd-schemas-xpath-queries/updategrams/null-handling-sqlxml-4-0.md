---
title: Gestion des valeurs NULL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611700"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="2a1bc-102">gestion NULL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2a1bc-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="2a1bc-103">La syntaxe XML assimile la valeur NULL à une absence.</span><span class="sxs-lookup"><span data-stu-id="2a1bc-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="2a1bc-104">(Par exemple, si une valeur d’attribut ou d’élément est NULL, cet attribut ou cet élément est absent du document XML.) Dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, l' `updg:nullvalue` attribut permet de spécifier null pour une valeur d’élément ou d’attribut.</span><span class="sxs-lookup"><span data-stu-id="2a1bc-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="2a1bc-105">Par exemple, la mise à jour suivante garantit que la valeur de **titre** pour un contact avec **ContactID** de 64 est null, puis met à jour la valeur de **titre** en « Mr ».</span><span class="sxs-lookup"><span data-stu-id="2a1bc-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="2a1bc-106">pour ce contact.</span><span class="sxs-lookup"><span data-stu-id="2a1bc-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="2a1bc-107">Lorsque les paramètres sont transmis à un code de mise à jour (updategram), la valeur NULL peut être passée comme valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="2a1bc-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="2a1bc-108">Pour cela, spécifiez l'attribut `nullvalue` dans le bloc `<updg:header>`.</span><span class="sxs-lookup"><span data-stu-id="2a1bc-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="2a1bc-109">Pour obtenir un exemple, consultez [transmission de paramètres à codes &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2a1bc-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1bc-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a1bc-110">See Also</span></span>  
 [<span data-ttu-id="2a1bc-111">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="2a1bc-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
