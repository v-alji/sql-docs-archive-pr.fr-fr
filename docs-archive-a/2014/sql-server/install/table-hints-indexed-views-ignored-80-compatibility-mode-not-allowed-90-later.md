---
title: Les indicateurs de table dans les définitions de vues indexées sont ignorés en mode de compatibilité 80 et ne sont pas autorisés en mode 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704675"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="51293-102">Les indicateurs de table dans les définitions de vues indexées sont ignorés en mode de compatibilité 80 et ne sont pas autorisés en mode 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="51293-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="51293-103">Les indicateurs de table dans les définitions de vues indexées ne sont pas autorisés en mode de compatibilité 90 ou supérieur.</span><span class="sxs-lookup"><span data-stu-id="51293-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="51293-104">Pour plus d'informations, consultez les rubriques suivantes dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : « Conception des vues indexées », "Création de vues indexées » et « Indicateur de requête ([!INCLUDE[tsql](../../includes/tsql-md.md)]) ».</span><span class="sxs-lookup"><span data-stu-id="51293-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="51293-105">Composant</span><span class="sxs-lookup"><span data-stu-id="51293-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="51293-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="51293-106">Corrective Action</span></span>  
 <span data-ttu-id="51293-107">Les indicateurs de table doivent être supprimés des définitions des vues indexées.</span><span class="sxs-lookup"><span data-stu-id="51293-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="51293-108">Quel que soit le mode de compatibilité utilisé, nous vous recommandons de tester l'application.</span><span class="sxs-lookup"><span data-stu-id="51293-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="51293-109">Tester l'application vous permet de vérifier qu'elle fonctionne comme prévu lors de la création, de la mise à jour et de l'ouverture de vues indexées, notamment lorsque ces dernières sont mises en correspondance avec des requêtes.</span><span class="sxs-lookup"><span data-stu-id="51293-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51293-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51293-110">See Also</span></span>  
 <span data-ttu-id="51293-111">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="51293-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="51293-112">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="51293-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
