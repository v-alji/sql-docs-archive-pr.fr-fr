---
title: Modifications du comportement dans syslockinfo et sp_lock | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604970"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="189c1-102">Modifications du comportement dans syslockinfo et sp_lock</span><span class="sxs-lookup"><span data-stu-id="189c1-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="189c1-103">**syslockinfo** et **sp_lock** peuvent retourner des valeurs inattendues.</span><span class="sxs-lookup"><span data-stu-id="189c1-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="189c1-104">Ils peuvent également retourner des lignes supplémentaires, alors que les versions antérieures de **syslockinfo** et de **sp_lock** retournaient un maximum de deux lignes par ressource de verrou.</span><span class="sxs-lookup"><span data-stu-id="189c1-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="189c1-105">L'accès à des informations à partir de **syslockinfo** et l'exécution de **sp_lock** requièrent l'autorisation VIEW SERVER STATE sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="189c1-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="189c1-106">Composant</span><span class="sxs-lookup"><span data-stu-id="189c1-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="189c1-107">Description</span><span class="sxs-lookup"><span data-stu-id="189c1-107">Description</span></span>  
 <span data-ttu-id="189c1-108">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], les colonnes **rsc_objid** et **rsc_indid** dans **syslockinfo** et les colonnes **objid** et **indid** dans **sp_lock** retournent toujours l'ID d'objet et l'ID d'index.</span><span class="sxs-lookup"><span data-stu-id="189c1-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="189c1-109">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], la valeur 0 peut être renvoyée.</span><span class="sxs-lookup"><span data-stu-id="189c1-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="189c1-110">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** et **sp_lock** retournent un maximum de deux lignes pour toute ressource de verrou donnée dans une même transaction.</span><span class="sxs-lookup"><span data-stu-id="189c1-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="189c1-111">À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], lorsque le partitionnement de verrous est activé, plusieurs lignes peuvent être renvoyées pour la même ressource s'exécutant sous une transaction.</span><span class="sxs-lookup"><span data-stu-id="189c1-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="189c1-112">Il peut y avoir jusqu’à N + 1 lignes, où N est le nombre de processeurs.</span><span class="sxs-lookup"><span data-stu-id="189c1-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="189c1-113">En outre, il est maintenant possible d'afficher des demandes GRANTED et WAITING pour la même ressource, alors que cela n'était pas possible dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="189c1-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="189c1-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="189c1-114">Permissions</span></span>  
 <span data-ttu-id="189c1-115">requièrent l'autorisation VIEW SERVER STATE sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="189c1-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="189c1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="189c1-116">See Also</span></span>  
 <span data-ttu-id="189c1-117">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="189c1-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="189c1-118">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="189c1-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
