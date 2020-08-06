---
title: Renommer les connexions correspondant aux noms de rôles serveur fixes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704700"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="b9212-102">Renommer les accès correspondant aux noms de rôles serveur fixes</span><span class="sxs-lookup"><span data-stu-id="b9212-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="b9212-103">Le Conseiller de mise à niveau a détecté un ou plusieurs noms de comptes de connexion définis par l'utilisateur correspondant aux noms des rôles serveur fixes.</span><span class="sxs-lookup"><span data-stu-id="b9212-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="b9212-104">Les noms des rôles serveur fixes sont réservés.</span><span class="sxs-lookup"><span data-stu-id="b9212-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="b9212-105">Renommez l'accès avant la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="b9212-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b9212-106">Composant</span><span class="sxs-lookup"><span data-stu-id="b9212-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b9212-107">Description</span><span class="sxs-lookup"><span data-stu-id="b9212-107">Description</span></span>  
 <span data-ttu-id="b9212-108">Les noms de rôle serveur fixe suivants sont réservés et ne peuvent pas être utilisés comme noms de compte de connexion défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9212-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="b9212-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="b9212-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="b9212-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="b9212-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="b9212-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="b9212-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="b9212-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="b9212-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="b9212-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="b9212-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b9212-117">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b9212-117">Corrective Action</span></span>  
 <span data-ttu-id="b9212-118">Avant d'effectuer la mise à niveau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b9212-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="b9212-119">Enregistrez les SID (identificateurs de sécurité) des connexions en exécutant l'instruction suivante.</span><span class="sxs-lookup"><span data-stu-id="b9212-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="b9212-120">Supprimez les connexions.</span><span class="sxs-lookup"><span data-stu-id="b9212-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="b9212-121">Utilisez la procédure système **sp_addlogin** pour créer des connexions.</span><span class="sxs-lookup"><span data-stu-id="b9212-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="b9212-122">Spécifiez le SID retourné à l’étape 1 dans le paramètre \*\* \@ sid\*\* pour chaque connexion correspondante.</span><span class="sxs-lookup"><span data-stu-id="b9212-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9212-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9212-123">See Also</span></span>  
 <span data-ttu-id="b9212-124">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b9212-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b9212-125">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="b9212-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
