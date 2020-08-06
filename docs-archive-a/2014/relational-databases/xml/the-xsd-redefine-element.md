---
title: '&lt;xsd:redefine&gt;, élément | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703963"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="2b1fa-102">Élément &lt;xsd:redefine&gt;</span><span class="sxs-lookup"><span data-stu-id="2b1fa-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="2b1fa-103">L’élément W3C XSD **redefine** assure la prise en charge de la redéfinition des composants de schéma.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="2b1fa-104">Toutefois, la prise en charge de cette directive est potentiellement coûteuse pour les performances et requiert également que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalide toutes les instances du `xml` type de données associées au schéma redéfini.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="2b1fa-105">Par conséquent, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne prend pas en charge cet élément.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="2b1fa-106">Les schémas XML incluant l'élément **\<xsd:redefine>** sont rejetés par le serveur.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="2b1fa-107">Au lieu d'utiliser cet élément, vous pouvez mettre à jour un schéma ou ses composants en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="2b1fa-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="2b1fa-108">Créez une nouvelle collection de schémas XML en y incluant les composants de schéma modifiés.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="2b1fa-109">Retapez tous les `xml` types de données (XML DT) qui utilisent la collection de schémas XML à redéfinir pour utiliser la nouvelle collection de schémas XML à la place.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="2b1fa-110">Pour cela, utilisez l'option ALTER COLUMN de la commande ALTER TABLE pour retaper les colonnes ou modifiez les contraintes de collection de schémas XML sur les variables ou les paramètres.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="2b1fa-111">Supprimez l'ancienne version de la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2b1fa-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1fa-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b1fa-112">See Also</span></span>  
 [<span data-ttu-id="2b1fa-113">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="2b1fa-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
