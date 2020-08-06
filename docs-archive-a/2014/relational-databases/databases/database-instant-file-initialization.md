---
title: Initialisation instantanée des fichiers de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604554"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="019b7-102">Initialisation instantanée des fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="019b7-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="019b7-103">Les fichiers de données et les fichiers journaux sont initialisés pour remplacer toutes les données existantes laissées sur le disque par des fichiers précédemment supprimés.</span><span class="sxs-lookup"><span data-stu-id="019b7-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="019b7-104">Les fichiers de données et les fichiers journaux sont d'abord initialisés en étant remplis avec des zéros quand vous effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="019b7-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="019b7-105">Créer une base de données.</span><span class="sxs-lookup"><span data-stu-id="019b7-105">Create a database.</span></span>  
  
-   <span data-ttu-id="019b7-106">ajouter des fichiers, un journal ou des données à une base de données existante ;</span><span class="sxs-lookup"><span data-stu-id="019b7-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="019b7-107">Augmenter la taille d'un fichier existant (opérations de croissance automatique incluses).</span><span class="sxs-lookup"><span data-stu-id="019b7-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="019b7-108">Restaurer une base de données ou un groupe de fichiers.</span><span class="sxs-lookup"><span data-stu-id="019b7-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="019b7-109">L'initialisation des fichiers augmente le temps d'exécution de ces opérations.</span><span class="sxs-lookup"><span data-stu-id="019b7-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="019b7-110">En revanche, quand les données sont écrites dans les fichiers pour la première fois, le système d'exploitation n'a pas besoin de remplir ces fichiers à l'aide de zéros.</span><span class="sxs-lookup"><span data-stu-id="019b7-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="019b7-111">Initialisation instantanée de fichiers</span><span class="sxs-lookup"><span data-stu-id="019b7-111">Instant File Initialization</span></span>  
 <span data-ttu-id="019b7-112">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les fichiers de données peuvent être initialisés instantanément.</span><span class="sxs-lookup"><span data-stu-id="019b7-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="019b7-113">Cela permet une exécution rapide des opérations mentionnées plus haut.</span><span class="sxs-lookup"><span data-stu-id="019b7-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="019b7-114">L'initialisation instantanée des fichiers récupère l'espace disque utilisé sans le remplir avec des zéros.</span><span class="sxs-lookup"><span data-stu-id="019b7-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="019b7-115">À la place, le contenu du disque est remplacé à mesure que de nouvelles données sont écrites dans les fichiers.</span><span class="sxs-lookup"><span data-stu-id="019b7-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="019b7-116">Les fichiers journaux ne peuvent pas être initialisés instantanément.</span><span class="sxs-lookup"><span data-stu-id="019b7-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="019b7-117">L’initialisation instantanée des fichiers n’est disponible que sur [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] ou [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] (ou versions ultérieures).</span><span class="sxs-lookup"><span data-stu-id="019b7-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="019b7-118">L'initialisation instantanée des fichiers n'est disponible que si l'autorisation SE_MANAGE_VOLUME_NAME a été octroyée au compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="019b7-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="019b7-119">Les membres du groupe Administrateurs Windows disposent de ce droit et peuvent l’attribuer aux autres utilisateurs en les ajoutant à la stratégie de sécurité **Effectuer les tâches de maintenance de volume** .</span><span class="sxs-lookup"><span data-stu-id="019b7-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="019b7-120">Pour plus d'informations sur l'affectation de droits de l'utilisateur, consultez la documentation de Windows.</span><span class="sxs-lookup"><span data-stu-id="019b7-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="019b7-121">L'initialisation instantanée des fichiers n'est pas disponible quand le chiffrement transparent des données est activé.</span><span class="sxs-lookup"><span data-stu-id="019b7-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="019b7-122">Pour accorder l'autorisation `Perform volume maintenance tasks` à un compte</span><span class="sxs-lookup"><span data-stu-id="019b7-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="019b7-123">Sur l'ordinateur où le fichier de sauvegarde doit être créé, ouvrez l'application `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="019b7-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="019b7-124">Dans le volet gauche, développez **Stratégies locales**, puis cliquez sur **Attribution des droits utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="019b7-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="019b7-125">Dans le volet droit, double-cliquez sur **Effectuer des tâches de maintenance sur les volumes**.</span><span class="sxs-lookup"><span data-stu-id="019b7-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="019b7-126">Cliquez sur **Ajouter un utilisateur ou un groupe** et ajoutez tout compte d’utilisateur utilisé pour les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="019b7-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="019b7-127">Cliquez sur **appliquer**, puis fermez toutes les `Local Security Policy` boîtes de dialogue.</span><span class="sxs-lookup"><span data-stu-id="019b7-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="019b7-128">Considérations relatives à la sécurité</span><span class="sxs-lookup"><span data-stu-id="019b7-128">Security Considerations</span></span>  
 <span data-ttu-id="019b7-129">Comme le contenu du disque supprimé n'est remplacé qu'au moment où de nouvelles données sont écrites dans les fichiers, il est éventuellement accessible à un principal non autorisé.</span><span class="sxs-lookup"><span data-stu-id="019b7-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="019b7-130">Même si le fichier de base de données est attaché à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le risque de divulgation de ces informations est limité par la liste de contrôle d'accès discrétionnaire (DACL, Discretionary Access Control List) du fichier.</span><span class="sxs-lookup"><span data-stu-id="019b7-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="019b7-131">Cette liste DACL n'autorise l'accès au fichier qu'à l'administrateur local et au compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="019b7-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="019b7-132">Cependant, quand le fichier est détaché, un utilisateur ou un service ne bénéficiant pas de l'autorisation SE_MANAGE_VOLUME_NAME peut y accéder.</span><span class="sxs-lookup"><span data-stu-id="019b7-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="019b7-133">Un risque similaire existe quand la base de données est sauvegardée.</span><span class="sxs-lookup"><span data-stu-id="019b7-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="019b7-134">Un service ou un utilisateur non autorisé peut accéder au contenu supprimé si le fichier de sauvegarde n'est pas protégé par une liste DACL appropriée.</span><span class="sxs-lookup"><span data-stu-id="019b7-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="019b7-135">Si le risque de divulgation du contenu supprimé constitue un problème, effectuez l'une et/ou l'autre des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="019b7-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="019b7-136">Assurez-vous toujours que les fichiers de sauvegarde et les fichiers de données détachés possèdent des listes DACL restrictives.</span><span class="sxs-lookup"><span data-stu-id="019b7-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="019b7-137">Désactivez l'initialisation instantanée des fichiers pour l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en révoquant l'autorisation SE_MANAGE_VOLUME_NAME au compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="019b7-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="019b7-138">La désactivation de l'initialisation instantanée des fichiers n'affecte que les fichiers créés ou dont la taille a augmenté après la révocation du droit de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="019b7-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019b7-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="019b7-139">See Also</span></span>  
 [<span data-ttu-id="019b7-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="019b7-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
