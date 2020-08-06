---
title: Définir l’option max degree of parallelism pour des performances optimales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708208"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="7cc9e-102">Définir l'option max degree of parallelism pour des performances optimales</span><span class="sxs-lookup"><span data-stu-id="7cc9e-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="7cc9e-103">Cette règle détermine si l'option max degree of parallelism (MAXDOP) (degré maximum de parallélisme) est définie sur une valeur supérieure à 8.</span><span class="sxs-lookup"><span data-stu-id="7cc9e-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="7cc9e-104">La définition d'une valeur supérieure à 8 conduit souvent à la consommation inutile de ressources et à la dégradation des performances.</span><span class="sxs-lookup"><span data-stu-id="7cc9e-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7cc9e-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="7cc9e-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7cc9e-106">Définissez l'option max degree of parallelism sur 8 ou une valeur supérieure à l'aide de sp_configure.</span><span class="sxs-lookup"><span data-stu-id="7cc9e-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7cc9e-107">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="7cc9e-107">For More Information</span></span>  
 [<span data-ttu-id="7cc9e-108">Article 329204 de la Base de connaissances Microsoft</span><span class="sxs-lookup"><span data-stu-id="7cc9e-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="7cc9e-109">Configurer l'option de configuration de serveur max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="7cc9e-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="7cc9e-110">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7cc9e-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
