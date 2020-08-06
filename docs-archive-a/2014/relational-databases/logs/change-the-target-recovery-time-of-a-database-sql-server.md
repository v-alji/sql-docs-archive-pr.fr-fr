---
title: Modifier la durée de récupération cible d’une base de données (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603996"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="c5558-102">Modifier la durée de récupération cible d'une base de données (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c5558-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="c5558-103">Cette rubrique explique comment modifier le temps de récupération cible d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5558-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c5558-104">Par défaut, le temps de récupération cible est 0, et la base de données utilise des *points de contrôle automatiques* (qui sont contrôlés par l'option de serveur **intervalle de récupération** ).</span><span class="sxs-lookup"><span data-stu-id="c5558-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="c5558-105">La définition du temps de récupération cible avec une valeur supérieure à 0 entraîne l'utilisation par la base de données de *points de contrôle indirects* et établit une limite supérieure sur le temps de récupération de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="c5558-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c5558-106">La limite supérieure spécifiée pour une base de données spécifique par son paramètre de temps de récupération cible peut être dépassée si une transaction longue entraîne des durées UNDO excessives.</span><span class="sxs-lookup"><span data-stu-id="c5558-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="c5558-107">**Avant de commencer :**  [Limitations et restrictions](#Restrictions), [sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="c5558-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="c5558-108">**Pour changer le temps de récupération cible à l’aide de :**  [SQL Server Management Studio](#SSMSProcedure) ou de [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="c5558-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5558-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c5558-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="c5558-110">Une charge de travail transactionnelle en ligne sur une base de données configurée pour les points de contrôle indirects peut rencontrer une dégradation des performances.</span><span class="sxs-lookup"><span data-stu-id="c5558-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="c5558-111">Les points de contrôle indirects permettent de s’assurer que le nombre de pages de modifications est inférieur à un certain seuil afin que la récupération de la base de données se termine dans le temps de récupération cible.</span><span class="sxs-lookup"><span data-stu-id="c5558-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="c5558-112">L’option de configuration de l’intervalle de récupération utilise le nombre de transactions pour déterminer le temps de récupération, contrairement aux points de contrôle indirects qui utilisent le nombre de pages de modifications.</span><span class="sxs-lookup"><span data-stu-id="c5558-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="c5558-113">Quand des points de contrôle indirects sont activés sur une base de données recevant un grand nombre d’opérations DML, l’enregistreur en arrière-plan peut commencer à vider de manière intense les mémoires tampons modifiées sur le disque afin de s’assurer que le délai nécessaire à la récupération se situe dans le temps de récupération cible défini de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5558-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="c5558-114">Cela peut entraîner une activité supplémentaire en termes d’E/S sur certains systèmes, ce qui peut contribuer à un goulot d’étranglement des performances si le sous-système du disque fonctionne au-delà du seuil d’E/S ou s’en rapproche.</span><span class="sxs-lookup"><span data-stu-id="c5558-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5558-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c5558-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5558-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c5558-116">Permissions</span></span>  
 <span data-ttu-id="c5558-117">Nécessite l'autorisation ALTER sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5558-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c5558-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5558-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c5558-119">**Pour modifier le temps de récupération cible**</span><span class="sxs-lookup"><span data-stu-id="c5558-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="c5558-120">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]et développez-la.</span><span class="sxs-lookup"><span data-stu-id="c5558-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="c5558-121">Cliquez avec le bouton droit sur la base de données à modifier, puis sélectionnez la commande **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="c5558-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="c5558-122">Dans la boîte de dialogue **Propriétés de la base de données** , cliquez sur la page **Options** .</span><span class="sxs-lookup"><span data-stu-id="c5558-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="c5558-123">Dans le volet **Récupération** , dans le champ **Temps de récupération cible (secondes)** , spécifiez le nombre de secondes de votre choix pour définir la limite supérieure du temps de récupération de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="c5558-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c5558-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5558-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="c5558-125">**Pour modifier le temps de récupération cible**</span><span class="sxs-lookup"><span data-stu-id="c5558-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="c5558-126">Connectez-vous à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] où réside la base de données.</span><span class="sxs-lookup"><span data-stu-id="c5558-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="c5558-127">Utilisez l'instruction [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)suivante, comme suit :</span><span class="sxs-lookup"><span data-stu-id="c5558-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="c5558-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="c5558-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="c5558-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="c5558-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="c5558-130">Lorsque la valeur est supérieure à 0 (valeur par défaut), spécifie la limite supérieure du temps de récupération de la base de données spécifiée en cas de sinistre.</span><span class="sxs-lookup"><span data-stu-id="c5558-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="c5558-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="c5558-131">SECONDS</span></span>  
     <span data-ttu-id="c5558-132">Indique que *target_recovery_time* correspond au nombre de secondes.</span><span class="sxs-lookup"><span data-stu-id="c5558-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="c5558-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="c5558-133">MINUTES</span></span>  
     <span data-ttu-id="c5558-134">Indique que *target_recovery_time* correspond au nombre de minutes.</span><span class="sxs-lookup"><span data-stu-id="c5558-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="c5558-135">L'exemple suivant définit le temps de récupération cible de la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sur `60` secondes.</span><span class="sxs-lookup"><span data-stu-id="c5558-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c5558-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5558-136">See Also</span></span>  
 <span data-ttu-id="c5558-137">[Points de contrôle de base de données &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5558-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="c5558-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5558-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
