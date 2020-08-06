---
title: Mise en cache XSL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700914"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="b9e8c-102">Mise en cache XSL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b9e8c-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="b9e8c-103">La mise en cache des feuilles de style XSL améliore les performances.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="b9e8c-104">Lors de sa première exécution, une feuille de style XSL reste en mémoire si la mise en cache XSL est définie à ON ; cela permet d'améliorer les performances pour les traitements ultérieurs.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="b9e8c-105">Le paramètre par défaut est ON.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="b9e8c-106">Vous pouvez définir la taille du cache XSL en ajoutant la clé suivante au Registre :</span><span class="sxs-lookup"><span data-stu-id="b9e8c-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="b9e8c-107">La taille du cache XSL doit être définie d'après la mémoire disponible et le nombre de feuilles de style XSL que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="b9e8c-108">La valeur par défaut de **XSLCacheSize** est 31.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="b9e8c-109">Vous pouvez augmenter la taille du cache si l'accès XSL semble lent, ou diminuer la taille du cache si la mémoire est insuffisante.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="b9e8c-110">Pour des performances optimales, il est recommandé de définir **XSLCacheSize** à une valeur plus élevée que le nombre de feuilles de style XSL que vous utilisez généralement.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="b9e8c-111">Si la valeur de **XSLCacheSize** est inférieure au nombre de feuilles de style XSL disponibles, les performances se dégradent avec l'augmentation du nombre de feuilles de style XSL.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="b9e8c-112">La valeur maximale qui peut être définie pour **XSLCacheSize** est 128.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="b9e8c-113">Chaque fois que la feuille de style XSL mise en cache est utilisée, l'heure de modification du fichier XSL est vérifiée pour déterminer s'il doit être actualisé.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="b9e8c-114">En effet, la copie du disque est plus récente que la copie du cache.</span><span class="sxs-lookup"><span data-stu-id="b9e8c-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e8c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9e8c-115">See Also</span></span>  
 <span data-ttu-id="b9e8c-116">[Mise en cache de modèle &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="b9e8c-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="b9e8c-117">Mise en cache de schéma &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="b9e8c-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
