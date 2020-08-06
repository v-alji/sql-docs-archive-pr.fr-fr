---
title: Mise en cache de schéma (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- schemas [SQLXML]
ms.assetid: 7e5fda21-b435-41fd-b637-8b616560a93f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e36711955fa28bafd3b0996b1a02f6cd71f3c4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613374"
---
# <a name="schema-caching-sqlxml-40"></a><span data-ttu-id="ae89b-102">Mise en cache des schémas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ae89b-102">Schema Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="ae89b-103">Avec une installation côte à côte de XML pour Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0 et SQLXML 3.0, vous pouvez contrôler explicitement la mise en cache des schémas dans toutes les versions à l'aide des clés de Registre suivantes :</span><span class="sxs-lookup"><span data-stu-id="ae89b-103">With a side-by-side installation of XML for Microsoft SQL Server 2000 Web Release 1, Microsoft SQLXML 2.0, and SQLXML 3.0, you can explicitly control the schema caching in all versions by using the following registry keys:</span></span>  
  
 <span data-ttu-id="ae89b-104">Web Release 1 :</span><span class="sxs-lookup"><span data-stu-id="ae89b-104">Web Release 1:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX\SchemaCacheSize  
```  
  
 <span data-ttu-id="ae89b-105">SQLXML 2,0 :</span><span class="sxs-lookup"><span data-stu-id="ae89b-105">SQLXML 2.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML2\SchemaCacheSize  
```  
  
 <span data-ttu-id="ae89b-106">SQLXML 3.0 :</span><span class="sxs-lookup"><span data-stu-id="ae89b-106">SQLXML 3.0:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML3\SchemaCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="ae89b-107">Pour plus d’informations sur l’installation côte à côte, consultez [What’s New in SQLXML 4,0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span><span class="sxs-lookup"><span data-stu-id="ae89b-107">For more information about side-by-side installation, see [What's New in SQLXML 4.0 SP1](../../sqlxml/what-s-new-in-sqlxml-4-0-sp1.md).</span></span>  
  
 <span data-ttu-id="ae89b-108">La mise en cache des schémas améliore considérablement les performances d'une requête XPath.</span><span class="sxs-lookup"><span data-stu-id="ae89b-108">Schema caching significantly improves the performance of an XPath query.</span></span> <span data-ttu-id="ae89b-109">Quand une requête XPath est exécutée sur un schéma de mappage, le schéma est stocké en mémoire et les structures de données nécessaires sont construites en mémoire.</span><span class="sxs-lookup"><span data-stu-id="ae89b-109">When an XPath query is executed against a mapping schema, the schema is stored in memory, and the necessary data structures are built in memory.</span></span> <span data-ttu-id="ae89b-110">Si la mise en cache des schémas est définie, le schéma demeure en mémoire, en améliorant de cette façon les requêtes XPath suivantes.</span><span class="sxs-lookup"><span data-stu-id="ae89b-110">If schema caching is set, the schema remains in memory, thereby improving performance for subsequent XPath queries.</span></span>  
  
 <span data-ttu-id="ae89b-111">Vous pouvez définir la taille du cache des schémas en ajoutant la clé précitée au Registre.</span><span class="sxs-lookup"><span data-stu-id="ae89b-111">You can set the schema cache size by adding the above key in the registry</span></span>  
  
 <span data-ttu-id="ae89b-112">La taille du schéma est fonction de la mémoire disponible et du nombre de schémas que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="ae89b-112">The schema size is set based on the available memory and the number of schemas you are using.</span></span> <span data-ttu-id="ae89b-113">La taille de **SchemaCacheSize** par défaut est 31.</span><span class="sxs-lookup"><span data-stu-id="ae89b-113">The default **SchemaCacheSize** size is 31.</span></span> <span data-ttu-id="ae89b-114">Si vous définissez **SchemaCacheSize** à un niveau supérieur, davantage de mémoire est utilisée.</span><span class="sxs-lookup"><span data-stu-id="ae89b-114">If you set **SchemaCacheSize** higher, more memory is used.</span></span> <span data-ttu-id="ae89b-115">Par conséquent, vous pouvez augmenter la taille du cache en cas d'accès lent au schéma ou diminuer la taille du cache si la mémoire est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="ae89b-115">Therefore, you can increase the cache size if schema access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="ae89b-116">Pour des raisons de performances, il est recommandé de définir **SchemaCacheSize** à une valeur supérieure au nombre de schémas de mappage que vous utilisez généralement.</span><span class="sxs-lookup"><span data-stu-id="ae89b-116">For performance reasons, it is recommended that you set **SchemaCacheSize** higher than the number of mapping schemas you usually use.</span></span> <span data-ttu-id="ae89b-117">À mesure que le nombre de schémas augmente, si **SchemaCacheSize** est inférieur au nombre de schémas dont vous disposez, les performances se dégradent.</span><span class="sxs-lookup"><span data-stu-id="ae89b-117">As the number of schemas increase, if **SchemaCacheSize** is less than the number of schemas you have, the performance degrades.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae89b-118">Pendant le développement, il est recommandé de ne pas mettre en cache les schémas, car les modifications apportées aux schémas ne sont pas répercutées dans le cache pendant deux minutes environ.</span><span class="sxs-lookup"><span data-stu-id="ae89b-118">During development, it is recommended that you do not cache the schemas, because the changes to the schemas are not reflected in the cache for about two minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae89b-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae89b-119">See Also</span></span>  
 <span data-ttu-id="ae89b-120">[Mise en cache de modèle &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="ae89b-120">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="ae89b-121">Mise en cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ae89b-121">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
