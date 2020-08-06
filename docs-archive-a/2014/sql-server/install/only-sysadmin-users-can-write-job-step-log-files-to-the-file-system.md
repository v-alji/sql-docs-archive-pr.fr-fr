---
title: Seuls les utilisateurs sysadmin peuvent écrire des fichiers journaux d’étapes de travail dans le système de fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- job step log files [SQL Server Agent]
- log files [SQL Server Agent]
- writing job step log files
ms.assetid: d26a7cef-1a60-4c95-b9df-f8b4fec59f9b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e2bf5095ac1e6b67f6c6f3f87444879913916e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605898"
---
# <a name="only-sysadmin-users-can-write-job-step-log-files-to-the-file-system"></a><span data-ttu-id="546ea-102">Seuls les utilisateurs sysadmin peuvent écrire des fichiers journaux des étapes de travail dans le système de fichiers</span><span class="sxs-lookup"><span data-stu-id="546ea-102">Only sysadmin users can write job step log files to the file system</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="546ea-103">écrit éventuellement un journal pour chaque étape de travail.</span><span class="sxs-lookup"><span data-stu-id="546ea-103">optionally writes a log for each job step.</span></span>  
  
## <a name="component"></a><span data-ttu-id="546ea-104">Composant</span><span class="sxs-lookup"><span data-stu-id="546ea-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="546ea-105">Agent</span><span class="sxs-lookup"><span data-stu-id="546ea-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="546ea-106">Description</span><span class="sxs-lookup"><span data-stu-id="546ea-106">Description</span></span>  
 <span data-ttu-id="546ea-107">Dans [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent peut écrire des journaux dans le système de fichiers pour les travaux qui sont détenus par les membres du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="546ea-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system for jobs that are owned by members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="546ea-108">Si le propriétaire du travail n’est pas membre du rôle **sysadmin** et si le compte proxy est activé, l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent peut écrire des journaux dans le système de fichiers en utilisant les informations d’identification du compte proxy.</span><span class="sxs-lookup"><span data-stu-id="546ea-108">If the job owner is not a member of the **sysadmin** role and if the proxy account is enabled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system by using the credentials of the proxy account.</span></span>  
  
 <span data-ttu-id="546ea-109">Après la mise à niveau, les travaux qui sont détenus par des utilisateurs qui ne sont pas membres du rôle serveur fixe **sysadmin** ne peuvent plus écrire de journaux dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="546ea-109">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** fixed server role can no longer write logs to the file system.</span></span> <span data-ttu-id="546ea-110">Au lieu de cela, ces utilisateurs peuvent sélectionner l’option permettant d’écrire leurs journaux dans une table de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="546ea-110">Instead, these users can select the option to write their logs to a table in the **msdb** database.</span></span> <span data-ttu-id="546ea-111">Les membres du rôle **sysadmin** peuvent toujours écrire des fichiers journaux dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="546ea-111">Members of the **sysadmin** role can still write log files to the file system.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="546ea-112">Action corrective</span><span class="sxs-lookup"><span data-stu-id="546ea-112">Corrective Action</span></span>  
 <span data-ttu-id="546ea-113">Après la mise à niveau, les travaux qui sont détenus par des utilisateurs qui ne sont pas membres du rôle **sysadmin** continuent à s’exécuter, mais les journaux ne seront pas créés.</span><span class="sxs-lookup"><span data-stu-id="546ea-113">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** role will continue to run, but logs will not be created.</span></span> <span data-ttu-id="546ea-114">Pour consigner des étapes de travail dans une table, les utilisateurs qui ne sont pas membres du rôle **sysadmin** doivent mettre à jour manuellement leurs travaux.</span><span class="sxs-lookup"><span data-stu-id="546ea-114">To log job steps to a table, users who are not members of the **sysadmin** role must manually update their jobs.</span></span>  
  
 <span data-ttu-id="546ea-115">Pour plus d'informations, consultez les rubriques « Création de travaux », « Création d'étapes de travail » et « Gestion de plusieurs étapes de travail » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="546ea-115">For more information, see the topics "Creating Jobs," "Creating Job Steps," and "Handling Multiple Job Steps" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546ea-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="546ea-116">See Also</span></span>  
 [<span data-ttu-id="546ea-117">Problèmes de mise à niveau de l'Agent SQL Server</span><span class="sxs-lookup"><span data-stu-id="546ea-117">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
