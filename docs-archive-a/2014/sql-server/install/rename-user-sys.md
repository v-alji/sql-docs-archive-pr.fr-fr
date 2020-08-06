---
title: Renommer l’utilisateur sys | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600489"
---
# <a name="rename-user-sys"></a><span data-ttu-id="64c08-102">Renommer l'utilisateur système</span><span class="sxs-lookup"><span data-stu-id="64c08-102">Rename user sys</span></span>
  <span data-ttu-id="64c08-103">Le Conseiller de mise à niveau a détecté le nom d'utilisateur **sys** dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="64c08-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="64c08-104">Ce nom est réservé.</span><span class="sxs-lookup"><span data-stu-id="64c08-104">This name is reserved.</span></span> <span data-ttu-id="64c08-105">Renommez l'utilisateur avant d'effectuer la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="64c08-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="64c08-106">Si l'utilisateur n'est pas renommé, la base de données sera marquée comme étant suspecte après l'opération de mise à niveau et restera indisponible jusqu'à ce qu'elle soit mise en ligne.</span><span class="sxs-lookup"><span data-stu-id="64c08-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="64c08-107">Composant</span><span class="sxs-lookup"><span data-stu-id="64c08-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="64c08-108">Description</span><span class="sxs-lookup"><span data-stu-id="64c08-108">Description</span></span>  
 <span data-ttu-id="64c08-109">L'utilisateur **sys** est réservé.</span><span class="sxs-lookup"><span data-stu-id="64c08-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="64c08-110">Action corrective</span><span class="sxs-lookup"><span data-stu-id="64c08-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="64c08-111">Procédure avant mise à niveau</span><span class="sxs-lookup"><span data-stu-id="64c08-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="64c08-112">Avant la mise à niveau, dans chaque base de données qui contient l'utilisateur **sys**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="64c08-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="64c08-113">Créez un nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64c08-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="64c08-114">Utilisez les instructions suivantes pour afficher toutes les autorisations accordées par l'utilisateur **sys** et accordées à l'utilisateur **sys**.</span><span class="sxs-lookup"><span data-stu-id="64c08-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="64c08-115">Pour transférer l'appartenance de tous les objets possédés par **sys** au nouvel utilisateur, utilisez **sp_changeobjectowner**.</span><span class="sxs-lookup"><span data-stu-id="64c08-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="64c08-116">Supprimez l'utilisateur **sys**.</span><span class="sxs-lookup"><span data-stu-id="64c08-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="64c08-117">Pour restaurer les autorisations d'origine capturées à l'étape 2, utilisez la clause AS *new_user* de l'instruction GRANT.</span><span class="sxs-lookup"><span data-stu-id="64c08-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="64c08-118">Modifiez les scripts pour qu'ils fassent référence au nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="64c08-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="64c08-119">Par exemple, dans les scripts, des instructions telles que `SELECT * FROM sys.my`_`table` doivent être remplacées par `SELECT * FROM new_user.my_table`.</span><span class="sxs-lookup"><span data-stu-id="64c08-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="64c08-120">Procédure après mise à niveau</span><span class="sxs-lookup"><span data-stu-id="64c08-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="64c08-121">Si l'utilisateur **sys** n'a pas été renommé avant la mise à niveau, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="64c08-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="64c08-122">Exécutez l'instruction `ALTER DATABASE db_name SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="64c08-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="64c08-123">La base de données se trouvera en mode SINGLE_USER.</span><span class="sxs-lookup"><span data-stu-id="64c08-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="64c08-124">Exécutez toutes les étapes répertoriées dans la section Procédure avant mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="64c08-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="64c08-125">Exécutez l'instruction `ALTER DATABASE db_name SET MULTI_USER`.</span><span class="sxs-lookup"><span data-stu-id="64c08-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64c08-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64c08-126">See Also</span></span>  
 <span data-ttu-id="64c08-127">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="64c08-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="64c08-128">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="64c08-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
