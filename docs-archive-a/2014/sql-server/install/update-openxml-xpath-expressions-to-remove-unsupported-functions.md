---
title: Mettre à jour les expressions XPath OPENXML pour supprimer les fonctions non prises en charge | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- OPENXML queries
ms.assetid: b459abaf-8787-4b65-9231-ae30e5469fd0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2c64408d6d705654014b6d071012001374a5f486
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604878"
---
# <a name="update-openxml-xpath-expressions-to-remove-unsupported-functions"></a><span data-ttu-id="3619b-102">Mettre à jour les expressions OPENXML XPath pour supprimer les fonctions non prises en charge</span><span class="sxs-lookup"><span data-stu-id="3619b-102">Update OPENXML XPath expressions to remove unsupported functions</span></span>
  <span data-ttu-id="3619b-103">Le Conseiller de mise à niveau a détecté l'utilisation de la fonctionnalité XPath.</span><span class="sxs-lookup"><span data-stu-id="3619b-103">Upgrade Advisor detected the use of XPath functionality.</span></span> <span data-ttu-id="3619b-104">Vous risquez de subir les effets des modifications apportées à XPath au niveau des fonctionnalités OPENXML après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="3619b-104">You may be affected by changes in XPath functionality for OPENXML features after you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3619b-105">Composant</span><span class="sxs-lookup"><span data-stu-id="3619b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3619b-106">Description</span><span class="sxs-lookup"><span data-stu-id="3619b-106">Description</span></span>  
 <span data-ttu-id="3619b-107">MSXML 3.0 est à présent le moteur sous-jacent qui sert à traiter les expressions XPath utilisées à l'intérieur des requêtes OPENXML.</span><span class="sxs-lookup"><span data-stu-id="3619b-107">MSXML 3.0 is now the underlying engine that is used to process XPath expressions that are used within OPENXML queries.</span></span> <span data-ttu-id="3619b-108">MSXML 3.0 possède un moteur XPath 1.0 plus strict qui ne prend plus en charge les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3619b-108">MSXML 3.0 has a stricter XPath 1.0 engine in which support for the following functions has been removed:</span></span>  
  
-   <span data-ttu-id="3619b-109">format-number()</span><span class="sxs-lookup"><span data-stu-id="3619b-109">format-number()</span></span>  
  
-   <span data-ttu-id="3619b-110">formatNumber()</span><span class="sxs-lookup"><span data-stu-id="3619b-110">formatNumber()</span></span>  
  
-   <span data-ttu-id="3619b-111">current()</span><span class="sxs-lookup"><span data-stu-id="3619b-111">current()</span></span>  
  
-   <span data-ttu-id="3619b-112">element-available()</span><span class="sxs-lookup"><span data-stu-id="3619b-112">element-available()</span></span>  
  
-   <span data-ttu-id="3619b-113">function-available()</span><span class="sxs-lookup"><span data-stu-id="3619b-113">function-available()</span></span>  
  
-   <span data-ttu-id="3619b-114">system-property()</span><span class="sxs-lookup"><span data-stu-id="3619b-114">system-property()</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3619b-115">Action corrective</span><span class="sxs-lookup"><span data-stu-id="3619b-115">Corrective Action</span></span>  
 <span data-ttu-id="3619b-116">Pour format-number() et formatNumber(), vous pouvez utiliser [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3619b-116">In the case of format-number() and formatNumber(), you can use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3619b-117">Pour les autres fonctions présentées précédemment qui ne sont plus prises en charge, il n'existe pas de solution de remplacement directe.</span><span class="sxs-lookup"><span data-stu-id="3619b-117">For the other unsupported functions listed earlier, there is no direct workaround.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3619b-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3619b-118">See Also</span></span>  
 <span data-ttu-id="3619b-119">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3619b-119">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3619b-120">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="3619b-120">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
