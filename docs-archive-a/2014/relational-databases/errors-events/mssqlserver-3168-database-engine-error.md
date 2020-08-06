---
title: MSSQLSERVER_3168 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3168 (Database Engine error)
ms.assetid: 991111d9-1eb3-43e9-9333-a75a775c3200
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 764f456653365c085e9f756a749910bbd03b4259
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605473"
---
# <a name="mssqlserver_3168"></a><span data-ttu-id="0f635-102">MSSQLSERVER_3168</span><span class="sxs-lookup"><span data-stu-id="0f635-102">MSSQLSERVER_3168</span></span>
    
## <a name="details"></a><span data-ttu-id="0f635-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0f635-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f635-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0f635-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0f635-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0f635-105">Event ID</span></span>|<span data-ttu-id="0f635-106">3168</span><span class="sxs-lookup"><span data-stu-id="0f635-106">3168</span></span>|  
|<span data-ttu-id="0f635-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0f635-107">Event Source</span></span>|<span data-ttu-id="0f635-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0f635-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0f635-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0f635-109">Component</span></span>|<span data-ttu-id="0f635-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0f635-110">SQLEngine</span></span>|  
|<span data-ttu-id="0f635-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0f635-111">Symbolic Name</span></span>|<span data-ttu-id="0f635-112">LDDB_SYSTEMWRONGVER</span><span class="sxs-lookup"><span data-stu-id="0f635-112">LDDB_SYSTEMWRONGVER</span></span>|  
|<span data-ttu-id="0f635-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0f635-113">Message Text</span></span>|<span data-ttu-id="0f635-114">Impossible de restaurer la sauvegarde de la base de données système de l'unité %ls car elle a été créée par une autre version de serveur (%ls) que celle-ci (%ls).</span><span class="sxs-lookup"><span data-stu-id="0f635-114">The backup of the system database on the device %ls cannot be restored because it was created by a different version of the server (%ls) than this server (%ls).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0f635-115">Explication</span><span class="sxs-lookup"><span data-stu-id="0f635-115">Explanation</span></span>  
 <span data-ttu-id="0f635-116">Vous ne pouvez pas restaurer la sauvegarde d’une base de données système (**MASTER**, **model** ou **msdb**) sur une version de serveur différente de la version sur laquelle la sauvegarde a été effectuée à l’origine.</span><span class="sxs-lookup"><span data-stu-id="0f635-116">You cannot restore a backup of a system database (**master**, **model**, or **msdb**) on a server build that differs from the build on which the backup was originally performed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f635-117">L'installation d'un Service Pack ou d'un correctif modifie le numéro de build du serveur et les versions des serveurs sont toujours incrémentielles.</span><span class="sxs-lookup"><span data-stu-id="0f635-117">Installing a service pack or a hotfix build changes the server build number, and server builds are always incremental.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0f635-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="0f635-118">Possible Causes</span></span>  
 <span data-ttu-id="0f635-119">Le schéma de la base de données des bases de données système a peut-être été changé sur les versions de serveur.</span><span class="sxs-lookup"><span data-stu-id="0f635-119">The database schema for system databases may be changed across server builds.</span></span> <span data-ttu-id="0f635-120">Pour vous assurer qu'une modification de schéma ne produit pas des incohérences, l'instruction RESTORE compare le numéro de build du serveur dans le fichier de sauvegarde avec le numéro de build du serveur sur lequel vous tentez de restaurer la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0f635-120">To make sure that a schema change does not cause inconsistencies, the RESTORE statement compares the server build number on the backup file to the build number of the server on which you are trying to restore the backup.</span></span> <span data-ttu-id="0f635-121">Si les versions diffèrent, l'instruction émet le message d'erreur 3168 et l'opération de restauration se termine anormalement.</span><span class="sxs-lookup"><span data-stu-id="0f635-121">If the builds are different, the statement issues the 3168 error message, and the restore operation terminates abnormally.</span></span>  
  
 <span data-ttu-id="0f635-122">Certains scénarios dans lesquels ce problème est susceptible de se poser sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="0f635-122">Some scenarios in which this problem may occur include the following:</span></span>  
  
-   <span data-ttu-id="0f635-123">Un utilisateur tente de restaurer une base de données système sur le serveur A à partir d'une sauvegarde réalisée sur le serveur B. Les serveurs A et B se trouvent sur des serveurs de version différente.</span><span class="sxs-lookup"><span data-stu-id="0f635-123">A user tries to restore a system database on Server A from a backup taken on Server B. Servers A and B are on different server builds.</span></span> <span data-ttu-id="0f635-124">Par exemple, le serveur A peut se situer sur la version d'origine et le serveur B sur une version de Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="0f635-124">For example, Server A might be on the original release version build and Server B might be on a service pack 1 (SP1) build.</span></span>  
  
-   <span data-ttu-id="0f635-125">Un utilisateur tente de restaurer une base de données système à partir d'une sauvegarde réalisée sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="0f635-125">A user tries to restore a system database from a backup taken on the same server.</span></span> <span data-ttu-id="0f635-126">Cependant, le serveur exécutait une version différente au moment de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0f635-126">However, the server was running a different build when the backup occurred.</span></span> <span data-ttu-id="0f635-127">Cela signifie que le serveur a été mis à niveau depuis la réalisation de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0f635-127">That is, the server was upgraded since the backup was performed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0f635-128">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0f635-128">User Action</span></span>  
 <span data-ttu-id="0f635-129">Le processus de restauration intervient en bonne partie dans cette situation et n'est utilisé qu'en dernier recours.</span><span class="sxs-lookup"><span data-stu-id="0f635-129">The restore process in this situation is fairly involved, and used only as a last resort.</span></span> <span data-ttu-id="0f635-130">Pour plus d’informations, consultez «[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)».</span><span class="sxs-lookup"><span data-stu-id="0f635-130">For more information, see"[You cannot restore system database backups to a different build of SQL Server](https://support.microsoft.com/kb/264474)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f635-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f635-131">See Also</span></span>  
 [<span data-ttu-id="0f635-132">Sauvegarde et restauration des bases de données système &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0f635-132">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
  
