---
title: Interrogation des procédures stockées étendues installées dans SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602847"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="9a1c5-102">Interrogation des procédures stockées étendues installées dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a1c5-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9a1c5-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="9a1c5-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9a1c5-104">Un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisateur authentifié peut afficher les procédures stockées étendues actuellement définies et le nom de la dll à laquelle chaque appartient en exécutant la procédure système **sp_helpextendedproc** .</span><span class="sxs-lookup"><span data-stu-id="9a1c5-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="9a1c5-105">Par exemple, l’exemple suivant retourne la DLL à laquelle **xp_hello** appartient :</span><span class="sxs-lookup"><span data-stu-id="9a1c5-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="9a1c5-106">Si **sp_helpextendedproc** est exécutée sans spécifier de procédure stockée étendue, toutes les procédures stockées étendues et leurs dll sont affichées.</span><span class="sxs-lookup"><span data-stu-id="9a1c5-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9a1c5-107">Des informations sont retournées uniquement pour les procédures stockées étendues qui appartiennent à l'utilisateur connecté ou sur lesquelles il possède des autorisations.</span><span class="sxs-lookup"><span data-stu-id="9a1c5-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="9a1c5-108">Seuls les membres du rôle serveur fixe **sysadmin** et des rôles de base de données fixe **db_owner**, **db_securityadmin**et **db_ddladmin** peuvent afficher des informations pour toutes les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="9a1c5-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1c5-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a1c5-109">See Also</span></span>  
 <span data-ttu-id="9a1c5-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9a1c5-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="9a1c5-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9a1c5-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="9a1c5-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a1c5-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
