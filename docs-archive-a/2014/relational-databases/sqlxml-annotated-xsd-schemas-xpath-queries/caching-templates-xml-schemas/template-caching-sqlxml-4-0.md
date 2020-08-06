---
title: Mise en cache de modèle (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- templates [SQLXML], caching
ms.assetid: 73e151c6-b24e-4422-a116-51e0846bc6f5
author: rothja
ms.author: jroth
ms.openlocfilehash: b2ea8a539086ada1b15abbb9cff4f838af45818c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605329"
---
# <a name="template-caching-sqlxml-40"></a><span data-ttu-id="27446-102">Mise en cache de modèle (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="27446-102">Template Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="27446-103">La mise en cache de modèle améliore considérablement les performances.</span><span class="sxs-lookup"><span data-stu-id="27446-103">Template caching significantly improves performance.</span></span> <span data-ttu-id="27446-104">Si la mise en cache de modèle est définie, le modèle reste en mémoire lors de sa première exécution.</span><span class="sxs-lookup"><span data-stu-id="27446-104">If template caching is set, the template remains in memory upon its first execution.</span></span> <span data-ttu-id="27446-105">Il s'ensuit une amélioration des performances de la prochaine exécution du modèle.</span><span class="sxs-lookup"><span data-stu-id="27446-105">This improves the performance for the subsequent execution of the template.</span></span>  
  
 <span data-ttu-id="27446-106">Vous pouvez définir la taille du cache du modèle en ajoutant la clé suivante au Registre :</span><span class="sxs-lookup"><span data-stu-id="27446-106">You can set the template cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\TemplateCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="27446-107">La taille du modèle doit être définie d'après la mémoire disponible et le nombre de modèles que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="27446-107">The template size should be set on the basis of the available memory and the number of templates you are using.</span></span> <span data-ttu-id="27446-108">La valeur par défaut de **TemplateCacheSize** Size est 31.</span><span class="sxs-lookup"><span data-stu-id="27446-108">The default of **TemplateCacheSize** size is 31.</span></span> <span data-ttu-id="27446-109">Vous pouvez augmenter la taille du cache si l'accès au modèle semble lent ou diminuer la taille du cache si la mémoire est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="27446-109">You can increase the cache size if template access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="27446-110">Pour de meilleures performances, il est recommandé de définir **TemplateCacheSize** à une valeur supérieure au nombre de modèles que vous utilisez généralement.</span><span class="sxs-lookup"><span data-stu-id="27446-110">For better performance, it is recommended that you set **TemplateCacheSize** higher than the number of templates you usually use.</span></span> <span data-ttu-id="27446-111">Si **TemlateCacheSize** est inférieur au nombre de modèles dont vous disposez, les performances se dégradent à mesure que le nombre de modèles augmente.</span><span class="sxs-lookup"><span data-stu-id="27446-111">If **TemlateCacheSize** is less than the number of templates you have, performance degrades as the number of templates increase.</span></span> <span data-ttu-id="27446-112">Le **TemplateCacheSize** peut être défini sur un maximum de 128.</span><span class="sxs-lookup"><span data-stu-id="27446-112">The **TemplateCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="27446-113">Chaque fois qu'un modèle mis en cache est utilisé, l'heure de modification du fichier modèle est vérifiée pour déterminer s'il doit être actualisé.</span><span class="sxs-lookup"><span data-stu-id="27446-113">Every time a cached template is used, the modification time of the template file is checked to see whether it needs to be refreshed.</span></span> <span data-ttu-id="27446-114">En effet, la copie du disque est plus récente que la copie du cache.</span><span class="sxs-lookup"><span data-stu-id="27446-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27446-115">Les paramètres de modèle et les propriétés de commande ne sont pas mis en cache.</span><span class="sxs-lookup"><span data-stu-id="27446-115">Template parameters and command properties are not cached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27446-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27446-116">See Also</span></span>  
 <span data-ttu-id="27446-117">[Mise en cache de schéma &#40;SQLXML 4,0&#41;](schema-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="27446-117">[Schema Caching &#40;SQLXML 4.0&#41;](schema-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="27446-118">Mise en cache XSL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="27446-118">XSL Caching &#40;SQLXML 4.0&#41;</span></span>](xsl-caching-sqlxml-4-0.md)  
  
  
