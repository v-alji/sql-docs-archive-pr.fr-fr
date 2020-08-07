---
title: Activation de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704148"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="aee06-102">Activation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="aee06-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="aee06-103">La fonctionnalité d'intégration du Common Language Runtime (CLR) est désactivée par défaut et doit être activée pour pouvoir utiliser des objets implémentés à l'aide de l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="aee06-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="aee06-104">Pour activer l’intégration du CLR, utilisez l’option **CLR activé** de la procédure stockée **sp_configure** :</span><span class="sxs-lookup"><span data-stu-id="aee06-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="aee06-105">Vous pouvez désactiver l’intégration du CLR en affectant à l’option **clr enabled** la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="aee06-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="aee06-106">Lorsque vous désactivez l'intégration du CLR, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] arrête l'exécution de toutes les routines CLR et décharge tous les domaines d'application.</span><span class="sxs-lookup"><span data-stu-id="aee06-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aee06-107">Pour activer l’intégration du CLR, vous devez disposer de l’autorisation de niveau serveur ALTER SETTINGs, qui est implicitement détenue par les membres des rôles serveur fixes **sysadmin** et **ServerAdmin** .</span><span class="sxs-lookup"><span data-stu-id="aee06-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aee06-108">Il est possible que les ordinateurs dotés de grandes quantités de mémoire et d'un grand nombre de processeurs ne puissent pas charger la fonctionnalité d'intégration du CLR de SQL Server au démarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="aee06-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="aee06-109">Pour résoudre ce problème, démarrez le serveur à l’aide de l’option de démarrage du service **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et spécifiez une valeur de mémoire suffisamment élevée.</span><span class="sxs-lookup"><span data-stu-id="aee06-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="aee06-110">Pour plus d’informations, consultez [Options de démarrage du service moteur de base de données](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="aee06-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aee06-111">L'exécution du CLR (Common Language Runtime) n'est pas prise en charge sous l'option lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="aee06-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="aee06-112">Avant d'activer l'intégration du CLR, vous devez désactiver le regroupement léger.</span><span class="sxs-lookup"><span data-stu-id="aee06-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="aee06-113">Pour plus d’informations, consultez [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="aee06-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aee06-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aee06-114">See Also</span></span>  
 <span data-ttu-id="aee06-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aee06-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="aee06-116">[clr enabled (option de configuration de serveur)](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="aee06-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="aee06-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aee06-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="aee06-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aee06-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="aee06-119">Rôles de niveau serveur</span><span class="sxs-lookup"><span data-stu-id="aee06-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
