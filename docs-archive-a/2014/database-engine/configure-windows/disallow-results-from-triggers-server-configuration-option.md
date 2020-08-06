---
title: disallow results from triggers (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694707"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="9d6e8-102">disallow results from triggers (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="9d6e8-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="9d6e8-103">L’option **disallow results from triggers** permet de spécifier si les déclencheurs doivent ou non retourner des ensembles de résultats.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="9d6e8-104">Les déclencheurs qui renvoient des jeux de résultats peuvent provoquer un comportement inattendu des applications qui ne sont pas conçues pour interagir avec eux.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="9d6e8-105">Nous vous conseillons de définir cette valeur sur 1.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="9d6e8-106">L’option **disallow results from triggers** est activée quand la valeur 1 lui est attribuée.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="9d6e8-107">La valeur par défaut de cette option est 0 (désactivé).</span><span class="sxs-lookup"><span data-stu-id="9d6e8-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="9d6e8-108">Si cette option est définie sur 1 (activé), toute tentative de la part d'un déclencheur de renvoyer un ensemble de résultats échoue, tandis l'utilisateur obtient le message d'erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="9d6e8-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="9d6e8-109">« Msg 524, Niveau 16, État 1, Procédure \<Procedure Name>, Ligne \<Line#></span><span class="sxs-lookup"><span data-stu-id="9d6e8-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="9d6e8-110">« Un déclencheur a retourné un ensemble de résultats et l'option de serveur « disallow_results_from_triggers » a la valeur TRUE. »</span><span class="sxs-lookup"><span data-stu-id="9d6e8-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="9d6e8-111">L’option **disallow results from triggers** s’applique au niveau de l’instance [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et détermine le comportement de tous les déclencheurs qui existent au sein de l’instance.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="9d6e8-112">L’option **disallow results from triggers** est une option avancée.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="9d6e8-113">Si vous utilisez la procédure stockée système **sp_configure** pour changer sa valeur, vous ne pouvez modifier l’option disallow results from triggers que si l’option **show advanced options** a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="9d6e8-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="9d6e8-114">Le paramètre prend effet immédiatement (sans redémarrage du serveur).</span><span class="sxs-lookup"><span data-stu-id="9d6e8-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6e8-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9d6e8-115">See Also</span></span>  
 <span data-ttu-id="9d6e8-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9d6e8-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="9d6e8-117">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9d6e8-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="9d6e8-118">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d6e8-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
