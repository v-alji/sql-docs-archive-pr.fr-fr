---
title: Supprimer les références aux procédures stockées système déconseillées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704704"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="a8f76-102">Supprimer les références aux procédures stockées système déconseillées</span><span class="sxs-lookup"><span data-stu-id="a8f76-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="a8f76-103">Le Conseiller de mise à niveau a détecté des instructions faisant référence à des procédures stockées système non documentées et à des procédures stockées étendues qui ne sont plus disponibles dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8f76-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a8f76-104">Les instructions faisant référence à ces objets échoueront.</span><span class="sxs-lookup"><span data-stu-id="a8f76-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="a8f76-105">N'utilisez pas les objets système et les API non documentés car la fonctionnalité peut être modifiée ou supprimée sans préavis dans une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a8f76-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a8f76-106">Composant</span><span class="sxs-lookup"><span data-stu-id="a8f76-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a8f76-107">Description</span><span class="sxs-lookup"><span data-stu-id="a8f76-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="a8f76-108">Procédures stockées système documentées</span><span class="sxs-lookup"><span data-stu-id="a8f76-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="a8f76-109">Les procédures stockées système documentées suivantes ont été supprimées :</span><span class="sxs-lookup"><span data-stu-id="a8f76-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="a8f76-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="a8f76-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="a8f76-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="a8f76-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="a8f76-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="a8f76-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="a8f76-115">Procédures stockées système non documentées</span><span class="sxs-lookup"><span data-stu-id="a8f76-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="a8f76-116">Les procédures stockées système non documentées et les procédures stockées étendues suivantes ont été supprimées :</span><span class="sxs-lookup"><span data-stu-id="a8f76-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="a8f76-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="a8f76-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="a8f76-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="a8f76-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="a8f76-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="a8f76-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="a8f76-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="a8f76-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="a8f76-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="a8f76-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="a8f76-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="a8f76-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="a8f76-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="a8f76-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="a8f76-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="a8f76-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="a8f76-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="a8f76-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="a8f76-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="a8f76-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="a8f76-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="a8f76-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="a8f76-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="a8f76-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="a8f76-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="a8f76-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="a8f76-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="a8f76-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="a8f76-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="a8f76-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="a8f76-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="a8f76-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="a8f76-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="a8f76-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="a8f76-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="a8f76-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="a8f76-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="a8f76-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="a8f76-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="a8f76-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="a8f76-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="a8f76-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="a8f76-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="a8f76-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a8f76-139">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a8f76-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="a8f76-140">Procédures stockées système documentées</span><span class="sxs-lookup"><span data-stu-id="a8f76-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="a8f76-141">Modifiez vos applications d'après le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a8f76-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="a8f76-142">À la place de</span><span class="sxs-lookup"><span data-stu-id="a8f76-142">Instead of</span></span>|<span data-ttu-id="a8f76-143">Action</span><span class="sxs-lookup"><span data-stu-id="a8f76-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="a8f76-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="a8f76-144">sp_addalias</span></span>|<span data-ttu-id="a8f76-145">Remplacez les alias par une combinaison de comptes d'utilisateurs et de rôles de base de données.</span><span class="sxs-lookup"><span data-stu-id="a8f76-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="a8f76-146">Pour plus d'informations, consultez « CREATE USER (Transact-SQL) » et « CREATE ROLE (Transact-SQL) » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8f76-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="a8f76-147">Supprimez les alias dans les bases de données mises à niveau à l'aide de sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="a8f76-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="a8f76-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="a8f76-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="a8f76-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="a8f76-150">sp_helpgroup</span></span>|<span data-ttu-id="a8f76-151">Utilisez des rôles.</span><span class="sxs-lookup"><span data-stu-id="a8f76-151">Use roles.</span></span> <span data-ttu-id="a8f76-152">Pour plus d'informations, consultez « Server-Level Roles » et « Database-Level Roles » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8f76-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="a8f76-153">Procédures stockées système Undocmented</span><span class="sxs-lookup"><span data-stu-id="a8f76-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="a8f76-154">Vous pouvez créer des procédures stockées CLR dotées de fonctionnalités équivalentes pour remplacer ces procédures stockées système non documentées.</span><span class="sxs-lookup"><span data-stu-id="a8f76-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="a8f76-155">Pour plus d'informations, consultez la rubrique « Procédures stockées CLR » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a8f76-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f76-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8f76-156">See Also</span></span>  
 <span data-ttu-id="a8f76-157">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a8f76-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a8f76-158">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="a8f76-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
