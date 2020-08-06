---
title: Facettes d’énumération | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- enumeration facets
ms.assetid: dec23a79-ddd6-4701-9721-55a2c435a34d
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e06598890d9b652879327e0351db5113cc17e6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600680"
---
# <a name="enumeration-facets"></a><span data-ttu-id="83050-102">facettes d'énumération</span><span class="sxs-lookup"><span data-stu-id="83050-102">Enumeration Facets</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83050-103">rejette les schémas XML avec des types présentant des facettes de modèles ou des énumérations enfreignant ces facettes.</span><span class="sxs-lookup"><span data-stu-id="83050-103">rejects XML schemas with types that have pattern facets or enumerations that violate those facets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83050-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="83050-104">Example</span></span>  
 <span data-ttu-id="83050-105">Le schéma serait rejeté car d'une part, la valeur d'énumération comprend une valeur à casse mixte et que,</span><span class="sxs-lookup"><span data-stu-id="83050-105">The following schema would be rejected, because the featured enumeration value includes a mixed-case value.</span></span> <span data-ttu-id="83050-106">d'autre part, cette valeur enfreint le modèle limitant les valeurs à des lettres minuscules.</span><span class="sxs-lookup"><span data-stu-id="83050-106">It would also be rejected because this value violates the pattern value that limits values to only lowercase letters.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MySampleCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" xmlns:ns="http://ns">  
    <simpleType name="MyST">  
       <restriction base="string">  
          <pattern value="[a-z]*"/>  
       </restriction>  
    </simpleType>  
  
    <simpleType name="MyST2">  
       <restriction base="ns:MyST">  
           <enumeration value="mYstring"/>  
       </restriction>  
    </simpleType>  
</schema>'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="83050-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83050-107">See Also</span></span>  
 [<span data-ttu-id="83050-108">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="83050-108">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
