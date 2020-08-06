---
title: Modèles de contenu non déterministes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696511"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="e08e6-102">modèles de contenu non déterministes</span><span class="sxs-lookup"><span data-stu-id="e08e6-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="e08e6-103">Avant [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejetait les schémas XML qui avaient des modèles de contenu non déterministes.</span><span class="sxs-lookup"><span data-stu-id="e08e6-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="e08e6-104">À compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, toutefois, les modèles de contenu non déterministes sont acceptés si les contraintes d’occurrence sont 0,1, ou non liées.</span><span class="sxs-lookup"><span data-stu-id="e08e6-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="e08e6-105">Exemple : modèle de contenu non déterministe rejeté</span><span class="sxs-lookup"><span data-stu-id="e08e6-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="e08e6-106">L'exemple suivant tente de créer un schéma XML dont le modèle de contenu est non déterministe.</span><span class="sxs-lookup"><span data-stu-id="e08e6-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="e08e6-107">Le code échoue car il n'est pas certain si l'élément `<root>` doit avoir une séquence de deux éléments `<a>` ou si l'élément `<root>` doit avoir deux séquences, chacune possédant un élément `<a>` .</span><span class="sxs-lookup"><span data-stu-id="e08e6-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="e08e6-108">Il est possible de corriger le schéma en déplaçant la contrainte d'occurrence vers un emplacement unique.</span><span class="sxs-lookup"><span data-stu-id="e08e6-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="e08e6-109">Par exemple, vous pouvez déplacer la contrainte vers la particule Sequence conteneur :</span><span class="sxs-lookup"><span data-stu-id="e08e6-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="e08e6-110">Ou vous pouvez la déplacer vers l'élément contenu :</span><span class="sxs-lookup"><span data-stu-id="e08e6-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="e08e6-111">Exemple : modèle de contenu non déterministe accepté</span><span class="sxs-lookup"><span data-stu-id="e08e6-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="e08e6-112">Le schéma suivant serait rejeté dans les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="e08e6-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e08e6-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e08e6-113">See Also</span></span>  
 [<span data-ttu-id="e08e6-114">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="e08e6-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
