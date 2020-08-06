---
title: Après la mise à niveau, les nouveaux mots clés réservés ne peuvent pas être utilisés en tant qu’identificateurs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604987"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="f063c-102">Après une mise à niveau, les nouveaux mots clés réservés ne peuvent pas être utilisés comme identificateurs</span><span class="sxs-lookup"><span data-stu-id="f063c-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="f063c-103">Le Conseiller de mise à niveau a détecté l'utilisation de mots qui sont des mots clés réservés.</span><span class="sxs-lookup"><span data-stu-id="f063c-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="f063c-104">Un mot clé réservé ne peut pas être utilisé comme un identificateur ou nom d'objet sauf si le nom est délimité.</span><span class="sxs-lookup"><span data-stu-id="f063c-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f063c-105">Composant</span><span class="sxs-lookup"><span data-stu-id="f063c-105">Component</span></span>  
 <span data-ttu-id="f063c-106">Moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="f063c-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="f063c-107">Description</span><span class="sxs-lookup"><span data-stu-id="f063c-107">Description</span></span>  
 <span data-ttu-id="f063c-108">Au niveau de compatibilité 90 ou inférieur, les mots suivants ne sont pas des mots clés réservés et peuvent être utilisés comme identificateur ou nom d'objet dans les scripts [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f063c-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="f063c-109">Au niveau de compatibilité 100, ces mots sont des mots clé réservés à part entière et ne doivent pas être utilisés comme identificateurs ou noms d'objet.</span><span class="sxs-lookup"><span data-stu-id="f063c-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="f063c-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="f063c-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="f063c-111">MERGE</span><span class="sxs-lookup"><span data-stu-id="f063c-111">MERGE</span></span>  
  
-   <span data-ttu-id="f063c-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="f063c-112">PIVOT</span></span>  
  
-   <span data-ttu-id="f063c-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="f063c-113">REVERT</span></span>  
  
-   <span data-ttu-id="f063c-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="f063c-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="f063c-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="f063c-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="f063c-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="f063c-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f063c-117">Action corrective</span><span class="sxs-lookup"><span data-stu-id="f063c-117">Corrective Action</span></span>  
 <span data-ttu-id="f063c-118">Nous vous recommandons de renommer l'objet.</span><span class="sxs-lookup"><span data-stu-id="f063c-118">We recommend that you rename the object.</span></span> <span data-ttu-id="f063c-119">Si cette opération ne peut pas être effectuée avant la mise à niveau, utilisez l'une des méthodes suivantes jusqu'à ce que vous puissiez modifier le nom :</span><span class="sxs-lookup"><span data-stu-id="f063c-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="f063c-120">Conservez la compatibilité de base de données au niveau 90 ou inférieur.</span><span class="sxs-lookup"><span data-stu-id="f063c-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="f063c-121">Faites référence à l'objet en utilisant des identificateurs délimités.</span><span class="sxs-lookup"><span data-stu-id="f063c-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="f063c-122">Par exemple, l’instruction `CREATE TABLE [MERGE] ([MERGE] int);` utilise des crochets pour délimiter la fusion du nom de l’objet.</span><span class="sxs-lookup"><span data-stu-id="f063c-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="f063c-123">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="f063c-123">External Resources</span></span>  
 [<span data-ttu-id="f063c-124">Mots clés réservés &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f063c-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="f063c-125">MERGE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f063c-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="f063c-126">Identificateurs délimités (Moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f063c-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="f063c-127">Niveau de compatibilité ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f063c-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
