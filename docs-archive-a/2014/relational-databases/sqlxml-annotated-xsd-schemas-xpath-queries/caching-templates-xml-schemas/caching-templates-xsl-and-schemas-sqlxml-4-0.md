---
title: Mise en cache des modèles, XSL et schémas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, caching
- cache [SQLXML]
- memory [SQLXML]
ms.assetid: 80b4fa79-243f-442c-9f22-74ad66186501
author: rothja
ms.author: jroth
ms.openlocfilehash: 4df25909cf156957908abf0691964fd66a76343a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610992"
---
# <a name="caching-templates-xsl-and-schemas-sqlxml-40"></a><span data-ttu-id="f9a8d-102">Mise en cache des modèles, XSL et schémas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f9a8d-102">Caching Templates, XSL, and Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="f9a8d-103">Pour améliorer les performances, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 prend en charge la mise en cache des modèles, des fichiers XSL et des schémas.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-103">To improve performance, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 supports caching templates, XSL, and schemas.</span></span>  
  
 <span data-ttu-id="f9a8d-104">Tous les schémas, modèles et fichiers XSL (sauf les fichiers provenant d'un emplacement http:// ou ftp://) sont mis en cache.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-104">All schemas, templates, and XSL files (except the files from an http:// or ftp:// location) are cached.</span></span> <span data-ttu-id="f9a8d-105">Les fichiers mis en cache demeurent en mémoire pendant que le processus est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-105">The cached files remain in memory while the process is running.</span></span> <span data-ttu-id="f9a8d-106">Lorsque le processus s'arrête, la totalité du cache est perdue.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-106">As the process exits, all the cache is lost.</span></span> <span data-ttu-id="f9a8d-107">Par conséquent, si vous exécutez un processus par requête, l'avantage de la mise en cache peut ne pas être perceptible.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-107">Therefore, if you run one process per query, the caching benefit may not be noticeable.</span></span>  
  
 <span data-ttu-id="f9a8d-108">Les rubriques de cette section fournissent plus d'informations sur la mise en cache.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-108">The topics in this section provide more information about caching.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9a8d-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="f9a8d-109">In This Section</span></span>  
 [<span data-ttu-id="f9a8d-110">Mise en cache de modèle &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9a8d-110">Template Caching &#40;SQLXML 4.0&#41;</span></span>](template-caching-sqlxml-4-0.md)  
 <span data-ttu-id="f9a8d-111">Décrit et fournit une clé de Registre pour la mise en cache des modèles.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-111">Describes and provides a registry key for template caching.</span></span>  
  
 [<span data-ttu-id="f9a8d-112">Mise en cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9a8d-112">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
 <span data-ttu-id="f9a8d-113">Décrit et fournit une clé de Registre pour la mise en cache des fichiers XSL.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-113">Describes and provides a registry key for XSL caching.</span></span>  
  
 [<span data-ttu-id="f9a8d-114">Mise en cache de schéma &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9a8d-114">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
 <span data-ttu-id="f9a8d-115">Explique les installations SQLXML côte à côte en rapport avec la mise en cache de schémas, et fournit les clés de Registre pour la mise en cache des schémas.</span><span class="sxs-lookup"><span data-stu-id="f9a8d-115">Discusses SQLXML side-by-side installation issues related to schema caching, and provides registry keys for schema caching.</span></span>  
  
  
