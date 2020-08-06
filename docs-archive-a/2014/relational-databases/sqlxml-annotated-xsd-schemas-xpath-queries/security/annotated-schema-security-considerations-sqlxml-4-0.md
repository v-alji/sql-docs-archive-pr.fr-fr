---
title: Considérations sur la sécurité des schémas annotés (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping schema [SQLXML], security
- annotated XDR schemas, security
- XDR schemas [SQLXML], security
- annotations [SQLXML]
- annotated XSD schemas, security
- SQLXML, annotated XSD schemas
- SQLXML, annotated XDR schemas
- security [SQLXML], annotated schemas
- XSD schemas [SQLXML], security
ms.assetid: 7d7e44dc-b6d3-4e0f-95c7-8f99930c94f2
author: rothja
ms.author: jroth
ms.openlocfilehash: 098f554410a846ed0223d17117b51025dfcf7897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600722"
---
# <a name="annotated-schema-security-considerations-sqlxml-40"></a><span data-ttu-id="72ac4-102">Considérations sur la sécurité des schémas annotés (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="72ac4-102">Annotated Schema Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="72ac4-103">Les éléments suivants constituent les indications de sécurité relatives à l'utilisation des schémas annotés :</span><span class="sxs-lookup"><span data-stu-id="72ac4-103">The following are security guidelines for using annotated schemas:</span></span>  
  
-   <span data-ttu-id="72ac4-104">Évitez d'utiliser le mappage par défaut dans les schémas de mappage.</span><span class="sxs-lookup"><span data-stu-id="72ac4-104">Avoid using default mapping in the mapping schemas.</span></span> <span data-ttu-id="72ac4-105">Le mappage par défaut expose les informations sur la base de données (noms de table et noms de colonne) dans le document XML obtenu parce que, par défaut, les noms d'élément sont mappés avec les noms de table et les noms d'attribut avec les noms de colonne.</span><span class="sxs-lookup"><span data-stu-id="72ac4-105">The default mapping exposes the database information (table and column names) in the resulting XML document because, by default, the element names map to table names and attribute names map to column names.</span></span> <span data-ttu-id="72ac4-106">Par conséquent, tout utilisateur qui consulte le document XML a accès aux informations sur les tables et les colonnes de la base de données, d'où un problème de sécurité potentiel.</span><span class="sxs-lookup"><span data-stu-id="72ac4-106">Therefore, any user who sees the XML document has access to the table and column information in the database, presenting a potential security risk.</span></span> <span data-ttu-id="72ac4-107">Pour éviter ce risque, spécifiez des noms d'élément et d'attribut arbitraires dans le schéma et utilisez les annotations pour les mapper explicitement avec les tables et les colonnes.</span><span class="sxs-lookup"><span data-stu-id="72ac4-107">To avoid this risk, specify arbitrary element and attribute names in the schema and use annotations to explicitly map them to the tables and columns.</span></span> <span data-ttu-id="72ac4-108">Pour plus d’informations sur l’utilisation du mappage par défaut lorsque vous créez des schémas XSD, consultez [mappage par défaut d’éléments et d’attributs XSD à des tables et des colonnes &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="72ac4-108">For more information about using default mapping when you create XSD schemas, see [Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="72ac4-109">Le mappage explicite spécifié à l'aide d'annotations expose les informations sur la base de données (telles que les noms de table et les noms de colonne).</span><span class="sxs-lookup"><span data-stu-id="72ac4-109">The explicit mapping specified using the annotations exposes the database information (such as table names and column names).</span></span> <span data-ttu-id="72ac4-110">Par conséquent, il se peut que vous ne souhaitiez pas rendre ces schémas disponibles publiquement.</span><span class="sxs-lookup"><span data-stu-id="72ac4-110">Therefore, you may not want to make these schemas available publicly.</span></span>  
  
-   <span data-ttu-id="72ac4-111">Certaines requêtes telles que celles spécifiées sur le schéma de mappage avec récurrence (spécifiée à l'aide de l'annotation `max-depth` définie avec une valeur supérieure) peuvent nécessiter plus de temps pour s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="72ac4-111">Certain queries such as those specified against mapping schema with recursion (specified using `max-depth` annotation set to a higher value) may take longer to execute.</span></span> <span data-ttu-id="72ac4-112">Vous pouvez éventuellement spécifier une limite de délai d’attente en définissant la propriété délai d’expiration de la commande (en secondes).</span><span class="sxs-lookup"><span data-stu-id="72ac4-112">You can optionally specify a time-out limit by setting the Command Time Out property (in seconds).</span></span> <span data-ttu-id="72ac4-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="72ac4-113">For example:</span></span>  
  
    ```  
    cn.Open "Provider=SQLOLEDB;Server=localhost;Database=tempdb;Integrated Security=SSPI;Command Properties='Command Time Out=50';"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="72ac4-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72ac4-114">See Also</span></span>  
 [<span data-ttu-id="72ac4-115">Schémas XSD annotés dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="72ac4-115">Annotated XSD Schemas in SQLXML 4.0</span></span>](../../sqlxml/annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
  
  
