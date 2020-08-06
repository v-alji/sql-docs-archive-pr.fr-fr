---
title: xs:QName, type | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xs:QName type
ms.assetid: 72c5bfde-b0b2-4372-bf36-97ba930dea06
author: rothja
ms.author: jroth
ms.openlocfilehash: 79aaf992243e665738f97c7ee1858528d6fb867c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703964"
---
# <a name="the-xsqname-type"></a><span data-ttu-id="95ad8-102">The xs:QName Type</span><span class="sxs-lookup"><span data-stu-id="95ad8-102">The xs:QName Type</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95ad8-103">ne prend pas en charge les types dérivés de **xs:QName** utilisant un élément de restriction de schéma XML.</span><span class="sxs-lookup"><span data-stu-id="95ad8-103">does not support types derived from **xs:QName** by the use of an XML Schema restriction element.</span></span> <span data-ttu-id="95ad8-104">De plus, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne prend pas en charge actuellement les types union avec **QName** en tant que type de membre.</span><span class="sxs-lookup"><span data-stu-id="95ad8-104">Also, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] currently does not support union types with **QName** as a member type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95ad8-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="95ad8-105">Example</span></span>  
 <span data-ttu-id="95ad8-106">Les instructions `CREATE XML SCHEMA COLLECTION` suivantes ne peuvent pas charger le schéma XML, car elles spécifient le type `xs:QName` en tant que type de membre de l'union :</span><span class="sxs-lookup"><span data-stu-id="95ad8-106">The following `CREATE XML SCHEMA COLLECTION` statements cannot load the XML schema, because they specify the `xs:QName` type as a member type of the union:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION QNameLimitation1 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:int xs:QName"/>  
    </xs:simpleType>  
</xs:schema>'  
GO  
  
CREATE XML SCHEMA COLLECTION QNameLimitation2 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:integer">  
   <xs:simpleType>  
    <xs:list itemType="xs:QName"/>  
   </xs:simpleType>  
  </xs:union>  
    </xs:simpleType>  
</xs:schema>'  
GO  
```  
  
 <span data-ttu-id="95ad8-107">Ces deux instructions échouent avec une erreur.</span><span class="sxs-lookup"><span data-stu-id="95ad8-107">Both statements fail with an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ad8-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95ad8-108">See Also</span></span>  
 [<span data-ttu-id="95ad8-109">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="95ad8-109">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
