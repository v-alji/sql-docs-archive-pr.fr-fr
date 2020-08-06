---
title: Fenêtre Threads
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Threads Window [Transact-SQL]
ms.assetid: e153f619-0049-4162-9076-c24a454f3278
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3460c892c182996a753c2a16076418a6b2008f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697872"
---
# <a name="threads-window"></a><span data-ttu-id="f9e4c-102">Fenêtre Threads</span><span class="sxs-lookup"><span data-stu-id="f9e4c-102">Threads Window</span></span>
  <span data-ttu-id="f9e4c-103">La fenêtre **Threads** affiche des informations sur le thread du [!INCLUDE[ssDE](../../includes/ssde-md.md)] utilisé par la session de l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] en cours de débogage.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-103">The **Threads** window displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] thread that is used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor session that is being debugged.</span></span> <span data-ttu-id="f9e4c-104">Vous devez être en mode débogage pour afficher les informations sur le thread.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-104">You must be in debug mode to display the thread information.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="f9e4c-105">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="f9e4c-105">Task List</span></span>  
 <span data-ttu-id="f9e4c-106">**Pour accéder à la fenêtre Threads**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-106">**To access the Threads window**</span></span>  
  
-   <span data-ttu-id="f9e4c-107">Dans le menu **Déboguer** , cliquez sur **Fenêtres**, puis sur **Threads**.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-107">On the **Debug** menu, click **Windows**, and then click **Threads**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="f9e4c-108">Colonnes</span><span class="sxs-lookup"><span data-stu-id="f9e4c-108">Columns</span></span>  
 <span data-ttu-id="f9e4c-109">**Identifiant**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-109">**ID**</span></span>  
 <span data-ttu-id="f9e4c-110">Numéro d'identification unique que le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] attribue au thread.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-110">Is a unique identifying number that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger assigns to the thread.</span></span> <span data-ttu-id="f9e4c-111">Vous pouvez obtenir des d'informations supplémentaires sur le thread en sélectionnant une ligne dans la vue de gestion dynamique sys.dm_os_threads.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-111">You can find more information about the thread by selecting a row from the sys.dm_os_threads dynamic management view.</span></span>  
  
 <span data-ttu-id="f9e4c-112">Si vous n’êtes pas en mode Regroupement léger, sélectionnez la ligne dont la valeur dans os_thread_id correspond à la valeur dans la colonne **ID** .</span><span class="sxs-lookup"><span data-stu-id="f9e4c-112">If you are not running in lightweight pooling mode, select the row in which the value in os_thread_id matches the value in the **ID** column.</span></span> <span data-ttu-id="f9e4c-113">Si vous êtes en mode Regroupement léger, sélectionnez la ligne dont la valeur dans fiber_context_address correspond à la valeur dans la colonne **ID** .</span><span class="sxs-lookup"><span data-stu-id="f9e4c-113">If you are running in lightweight pooling mode, select the row in which the value in fiber_context_address matches the value in the **ID** column.</span></span>  
  
 <span data-ttu-id="f9e4c-114">**Nom**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-114">**Name**</span></span>  
 <span data-ttu-id="f9e4c-115">Affiche des informations sur la session du [!INCLUDE[ssDE](../../includes/ssde-md.md)] au format **nom_ordinateur/nom_instance [SPID]** .</span><span class="sxs-lookup"><span data-stu-id="f9e4c-115">Displays information about the [!INCLUDE[ssDE](../../includes/ssde-md.md)] session in the format **ComputerName/InstanceName [SPID]**.</span></span>  
  
 <span data-ttu-id="f9e4c-116">**ComputerName**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-116">**ComputerName**</span></span>  
 <span data-ttu-id="f9e4c-117">Nom de l'ordinateur qui exécute l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à laquelle la session de l'éditeur de requête est connectée.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-117">The name of the computer that is running the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="f9e4c-118">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-118">**InstanceName**</span></span>  
 <span data-ttu-id="f9e4c-119">Nom de l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] à laquelle la session de l'éditeur de requête est connectée.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-119">The name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that the Query Editor session is connected to.</span></span>  
  
 <span data-ttu-id="f9e4c-120">**[SPID]**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-120">**[SPID]**</span></span>  
 <span data-ttu-id="f9e4c-121">ID de processus de session [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui identifie de façon unique cette session.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-121">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session process ID that uniquely identifies this session.</span></span> <span data-ttu-id="f9e4c-122">Vous pouvez obtenir des informations supplémentaires sur la session en sélectionnant la ligne dans la vue sys.sysprocesses dont la valeur est la même dans la colonne spid.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-122">You can obtain more information about the session by selecting the row in the sys.sysprocesses view that has the same value in the spid column.</span></span>  
  
 <span data-ttu-id="f9e4c-123">**Lieu**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-123">**Location**</span></span>  
 <span data-ttu-id="f9e4c-124">Affiche le nom du fichier de script utilisé dans la session de l'éditeur de requête en cours de débogage.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-124">Displays the name of the script file that is used in the Query Editor session that is being debugged.</span></span>  
  
 <span data-ttu-id="f9e4c-125">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-125">**Priority**</span></span>  
 <span data-ttu-id="f9e4c-126">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ne prend pas en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-126">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="f9e4c-127">**Suspendre**</span><span class="sxs-lookup"><span data-stu-id="f9e4c-127">**Suspend**</span></span>  
 <span data-ttu-id="f9e4c-128">Le débogueur [!INCLUDE[tsql](../../includes/tsql-md.md)] ne prend pas en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f9e4c-128">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e4c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9e4c-129">See Also</span></span>  
 <span data-ttu-id="f9e4c-130">[Débogueur Transact-SQL](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="f9e4c-130">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="f9e4c-131">[Informations du débogueur Transact-SQL](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="f9e4c-131">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="f9e4c-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9e4c-132">[sys.dm_os_threads &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-threads-transact-sql) </span></span>  
 [<span data-ttu-id="f9e4c-133">sys.sysprocesses &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9e4c-133">sys.sysprocesses &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysprocesses-transact-sql)  
