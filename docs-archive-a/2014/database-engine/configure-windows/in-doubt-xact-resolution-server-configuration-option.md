---
title: in-doubt xact resolution (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697184"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="2cd49-102">in-doubt xact resolution (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="2cd49-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="2cd49-103">Utilisez l’option **in-doubt xact resolution** pour contrôler le résultat par défaut des transactions que [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) ne peut pas résoudre.</span><span class="sxs-lookup"><span data-stu-id="2cd49-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="2cd49-104">L'incapacité à résoudre des transactions peut être liée au temps d'inactivité MS DTC ou à un résultat de transaction inattendu au moment de la récupération.</span><span class="sxs-lookup"><span data-stu-id="2cd49-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="2cd49-105">Le tableau suivant récapitule les valeurs de résultat possibles pour résoudre une transaction incertaine.</span><span class="sxs-lookup"><span data-stu-id="2cd49-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="2cd49-106">Valeur du résultat</span><span class="sxs-lookup"><span data-stu-id="2cd49-106">Outcome value</span></span>|<span data-ttu-id="2cd49-107">Description</span><span class="sxs-lookup"><span data-stu-id="2cd49-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="2cd49-108">0</span><span class="sxs-lookup"><span data-stu-id="2cd49-108">0</span></span>|<span data-ttu-id="2cd49-109">Pas de présomption.</span><span class="sxs-lookup"><span data-stu-id="2cd49-109">No presumption.</span></span> <span data-ttu-id="2cd49-110">La récupération échoue si MS DTC ne peut pas résoudre les transactions incertaines.</span><span class="sxs-lookup"><span data-stu-id="2cd49-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="2cd49-111">1</span><span class="sxs-lookup"><span data-stu-id="2cd49-111">1</span></span>|<span data-ttu-id="2cd49-112">Validation présumée.</span><span class="sxs-lookup"><span data-stu-id="2cd49-112">Presume commit.</span></span> <span data-ttu-id="2cd49-113">Toutes les transactions incertaines de MS DTC sont supposées être validées.</span><span class="sxs-lookup"><span data-stu-id="2cd49-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="2cd49-114">2</span><span class="sxs-lookup"><span data-stu-id="2cd49-114">2</span></span>|<span data-ttu-id="2cd49-115">Abandon présumé.</span><span class="sxs-lookup"><span data-stu-id="2cd49-115">Presume abort.</span></span> <span data-ttu-id="2cd49-116">Toutes les transactions incertaines de MS DTC sont supposées avoir échoué.</span><span class="sxs-lookup"><span data-stu-id="2cd49-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="2cd49-117">Pour réduire l'éventualité d'un temps d'inactivité prolongé, l'administrateur peut décider de configurer cette option pour présumer la validation ou l'abandon, comme dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2cd49-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="2cd49-118">L'administrateur peut aussi conserver la valeur par défaut (pas de présomption) et autoriser l'échec de la récupération afin d'être averti en cas de défaillance du DTC, comme dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2cd49-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="2cd49-119">L’option **in-doubt xact resolution** est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="2cd49-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="2cd49-120">Si vous utilisez la procédure stockée système **sp_configure** pour changer sa valeur, vous ne pouvez modifier l’option **in-doubt xact resolution** que si l’option **show advanced options** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="2cd49-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="2cd49-121">Le paramètre prend effet immédiatement (sans redémarrage du serveur).</span><span class="sxs-lookup"><span data-stu-id="2cd49-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cd49-122">Une configuration identique de cette option dans toutes les instances de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] impliquées dans les transactions distribuées permet d’éviter des incohérences dans les données.</span><span class="sxs-lookup"><span data-stu-id="2cd49-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd49-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cd49-123">See Also</span></span>  
 <span data-ttu-id="2cd49-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2cd49-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="2cd49-125">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2cd49-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="2cd49-126">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2cd49-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
