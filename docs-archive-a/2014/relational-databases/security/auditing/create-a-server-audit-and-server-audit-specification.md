---
title: Créer un audit du serveur et une spécification d’audit du serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700961"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="d5461-102">Créer un audit du serveur et une spécification d'audit du serveur</span><span class="sxs-lookup"><span data-stu-id="d5461-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="d5461-103">Cette rubrique explique comment créer un audit de serveur et une spécification d'audit de serveur dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5461-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d5461-104">L'*audit* d'une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou d'une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implique le suivi et l'enregistrement des événements qui se produisent sur le système.</span><span class="sxs-lookup"><span data-stu-id="d5461-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="d5461-105">L’objet *Audit SQL Server* recueille une seule instance des actions et des groupes d’actions au niveau du serveur ou de la base de données à surveiller.</span><span class="sxs-lookup"><span data-stu-id="d5461-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="d5461-106">L'audit s'effectue au niveau de l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5461-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="d5461-107">Vous pouvez exécuter plusieurs audits par instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5461-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d5461-108">L'objet *Spécification de l'audit du serveur* appartient à un audit.</span><span class="sxs-lookup"><span data-stu-id="d5461-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="d5461-109">Vous pouvez créer une spécification d'audit de serveur par audit, car tous deux sont créés au niveau de la portée de l'instance [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5461-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="d5461-110">Pour plus d’informations, consultez [SQL Server Audit &#40;moteur de base de données&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="d5461-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="d5461-111">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d5461-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d5461-112">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d5461-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d5461-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d5461-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="d5461-114">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d5461-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d5461-115">**Pour créer un audit de serveur et une spécification d'audit de serveur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d5461-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="d5461-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5461-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d5461-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d5461-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d5461-118">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d5461-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="d5461-119">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="d5461-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="d5461-120">Un audit doit exister pour que vous puissiez créer une spécification d'audit de serveur correspondante.</span><span class="sxs-lookup"><span data-stu-id="d5461-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="d5461-121">Lorsqu'une spécification d'audit de serveur est créée, elle est dans un état désactivé.</span><span class="sxs-lookup"><span data-stu-id="d5461-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="d5461-122">L'instruction CREATE SERVER AUDIT fait partie de l'étendue d'une transaction.</span><span class="sxs-lookup"><span data-stu-id="d5461-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="d5461-123">Si la transaction est restaurée, l'instruction l'est également.</span><span class="sxs-lookup"><span data-stu-id="d5461-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d5461-124">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d5461-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d5461-125">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d5461-125">Permissions</span></span>  
  
-   <span data-ttu-id="d5461-126">Pour créer, modifier ou supprimer un audit du serveur, les principaux requièrent l'autorisation ALTER ANY SERVER AUDIT ou CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="d5461-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="d5461-127">Les utilisateurs disposant de l'autorisation ALTER ANY SERVER AUDIT peuvent créer des spécifications d'audit du serveur et les lier à un audit quelconque.</span><span class="sxs-lookup"><span data-stu-id="d5461-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="d5461-128">Une fois qu’une spécification d’audit du serveur est créée, elle peut être affichée par des principaux disposant des autorisations CONTROL SERVER ou ALTER ANY SERVER AUDIT, du compte sysadmin ou de principaux ayant un accès explicite à l’audit.</span><span class="sxs-lookup"><span data-stu-id="d5461-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d5461-129">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d5461-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="d5461-130">Pour créer un audit de serveur</span><span class="sxs-lookup"><span data-stu-id="d5461-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="d5461-131">Dans l'Explorateur d'objets, développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="d5461-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="d5461-132">Cliquez avec le bouton droit sur le dossier **Audits** et sélectionnez **Nouvel audit...** .</span><span class="sxs-lookup"><span data-stu-id="d5461-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="d5461-133">Les options suivantes sont disponibles sur la page **Général** de la boîte de dialogue **Créer un audit** .</span><span class="sxs-lookup"><span data-stu-id="d5461-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="d5461-134">**Nom de l'audit**</span><span class="sxs-lookup"><span data-stu-id="d5461-134">**Audit name**</span></span>  
     <span data-ttu-id="d5461-135">Nom de l'audit.</span><span class="sxs-lookup"><span data-stu-id="d5461-135">The name of the audit.</span></span> <span data-ttu-id="d5461-136">Il est généré automatiquement lorsque vous créez un audit, mais il est modifiable.</span><span class="sxs-lookup"><span data-stu-id="d5461-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="d5461-137">**Délai de file d'attente (en millisecondes)**</span><span class="sxs-lookup"><span data-stu-id="d5461-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="d5461-138">Spécifie la durée (en millisecondes) qui peut s'écouler avant que le traitement des actions d'audit ne soit forcé.</span><span class="sxs-lookup"><span data-stu-id="d5461-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="d5461-139">Une valeur de 0 indique la remise synchrone.</span><span class="sxs-lookup"><span data-stu-id="d5461-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="d5461-140">La valeur minimale par défaut est **1000** (1 seconde).</span><span class="sxs-lookup"><span data-stu-id="d5461-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="d5461-141">Le maximum est 2 147 483 647 (2 147 483,647 secondes ou 24 jours, 20 heures, 31 minutes, 23,647 secondes).</span><span class="sxs-lookup"><span data-stu-id="d5461-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="d5461-142">**En cas de défaillance du journal d'audit :**</span><span class="sxs-lookup"><span data-stu-id="d5461-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="d5461-143">**Continuer**</span><span class="sxs-lookup"><span data-stu-id="d5461-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d5461-144">Les opérations continuent.</span><span class="sxs-lookup"><span data-stu-id="d5461-144">operations continue.</span></span> <span data-ttu-id="d5461-145">Les enregistrements d'audit ne sont pas conservés.</span><span class="sxs-lookup"><span data-stu-id="d5461-145">Audit records are not retained.</span></span> <span data-ttu-id="d5461-146">L'audit poursuit sa tentative de consignation des événements et reprend les opérations d'enregistrement une fois la défaillance résolue.</span><span class="sxs-lookup"><span data-stu-id="d5461-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="d5461-147">La sélection de l'option **Continuer** peut permettre l'exécution d'une activité non auditée susceptible d'enfreindre vos stratégies de sécurité.</span><span class="sxs-lookup"><span data-stu-id="d5461-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="d5461-148">Sélectionnez cette option quand la poursuite de l’opération du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] est plus importante que la conservation d’un audit complet.</span><span class="sxs-lookup"><span data-stu-id="d5461-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="d5461-149">Il s'agit de la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5461-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="d5461-150">**Arrêter le serveur**</span><span class="sxs-lookup"><span data-stu-id="d5461-150">**Shut down server**</span></span>  
     <span data-ttu-id="d5461-151">Force un arrêt du serveur lorsque l'instance de serveur qui écrit dans la cible ne peut pas écrire de données dans la cible d'audit.</span><span class="sxs-lookup"><span data-stu-id="d5461-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="d5461-152">La connexion qui émet cette commande d'arrêt doit avoir l'autorisation `SHUTDOWN`.</span><span class="sxs-lookup"><span data-stu-id="d5461-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="d5461-153">Si la connexion n'a pas cette autorisation, cette fonction échoue et un message d'erreur est généré.</span><span class="sxs-lookup"><span data-stu-id="d5461-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="d5461-154">Aucun événement audité ne se produit.</span><span class="sxs-lookup"><span data-stu-id="d5461-154">No audited events occur.</span></span> <span data-ttu-id="d5461-155">Sélectionnez cette option si une défaillance de l'audit risque de compromettre la sécurité ou l'intégrité du système.</span><span class="sxs-lookup"><span data-stu-id="d5461-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="d5461-156">**Faire échouer l'opération**</span><span class="sxs-lookup"><span data-stu-id="d5461-156">**Fail operation**</span></span>  
     <span data-ttu-id="d5461-157">Lorsque l'audit de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne peut pas écrire dans le journal d'audit, cette option provoque l'échec des actions de base de données si celles-ci entraînent des événements audités.</span><span class="sxs-lookup"><span data-stu-id="d5461-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="d5461-158">Aucun événement audité ne se produit.</span><span class="sxs-lookup"><span data-stu-id="d5461-158">No audited events occur.</span></span> <span data-ttu-id="d5461-159">Les actions qui n'entraînent pas d'événements audités peuvent continuer.</span><span class="sxs-lookup"><span data-stu-id="d5461-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="d5461-160">L'audit poursuit sa tentative de consignation des événements et reprend les opérations d'enregistrement une fois la défaillance résolue.</span><span class="sxs-lookup"><span data-stu-id="d5461-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="d5461-161">Sélectionnez cette option quand la conservation d’un audit complet est plus importante que l’accès total au [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5461-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="d5461-162">Lorsque l'audit est en état d'échec, la connexion administrateur dédiée peut continuer à exécuter des événements audités.</span><span class="sxs-lookup"><span data-stu-id="d5461-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="d5461-163">Liste**Destination de l’audit**</span><span class="sxs-lookup"><span data-stu-id="d5461-163">**Audit destination** list</span></span>  
     <span data-ttu-id="d5461-164">Spécifie la cible pour l'audit des données.</span><span class="sxs-lookup"><span data-stu-id="d5461-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="d5461-165">Les options disponibles sont un fichier binaire, le journal des applications Windows ou le journal de sécurité Windows.</span><span class="sxs-lookup"><span data-stu-id="d5461-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d5461-166">ne peut pas écrire dans le journal de sécurité Windows sans configurer d'autres paramètres dans Windows.</span><span class="sxs-lookup"><span data-stu-id="d5461-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="d5461-167">Pour plus d’informations, consultez [Écrire des événements d’audit SQL Server dans le journal de sécurité](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="d5461-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="d5461-168">**Chemin de fichier**</span><span class="sxs-lookup"><span data-stu-id="d5461-168">**File path**</span></span>  
     <span data-ttu-id="d5461-169">Spécifie l’emplacement du dossier dans lequel les données d’audit sont écrites quand la **destination de l’audit** est un fichier.</span><span class="sxs-lookup"><span data-stu-id="d5461-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="d5461-170">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="d5461-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d5461-171">Ouvre la boîte de dialogue **localiser le dossier-**_SERVER_NAME_ qui permet de spécifier un chemin d’accès de fichier ou de créer un dossier dans lequel le fichier d’audit est écrit.</span><span class="sxs-lookup"><span data-stu-id="d5461-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="d5461-172">**Limites maximales du fichier d'audit :**</span><span class="sxs-lookup"><span data-stu-id="d5461-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="d5461-173">**Fichiers de substitution maximale**</span><span class="sxs-lookup"><span data-stu-id="d5461-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="d5461-174">Spécifie que, lorsque le nombre maximal de fichiers d'audit est atteint, les fichiers d'audit les plus anciens sont remplacés par les nouveaux fichiers.</span><span class="sxs-lookup"><span data-stu-id="d5461-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="d5461-175">**Nombre maximal de fichiers**</span><span class="sxs-lookup"><span data-stu-id="d5461-175">**Maximum files**</span></span>  
     <span data-ttu-id="d5461-176">Spécifie que, lorsque le nombre maximal de fichiers d'audit est atteint, toute action qui entraîne la génération d'événements d'audit supplémentaires échoue et provoque une erreur.</span><span class="sxs-lookup"><span data-stu-id="d5461-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="d5461-177">Case à cocher**Illimité**</span><span class="sxs-lookup"><span data-stu-id="d5461-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="d5461-178">Lorsque la case **Illimité** sous **Nombre maximal de fichiers de substitution** est cochée, aucune limite n’est imposée sur le nombre de fichiers d’audit qui seront créés.</span><span class="sxs-lookup"><span data-stu-id="d5461-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="d5461-179">La case à cocher **Illimité** est sélectionnée par défaut et s'applique aux sélections **Nombre maximal de fichiers de substitution** et **Nombre maximal de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="d5461-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="d5461-180">Zone**Nombre de fichiers**</span><span class="sxs-lookup"><span data-stu-id="d5461-180">**Number of files** box</span></span>  
     <span data-ttu-id="d5461-181">Spécifie le nombre de fichiers d'audit à créer, jusqu'à 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="d5461-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="d5461-182">Cette option est disponible uniquement si **Illimité** est désactivé.</span><span class="sxs-lookup"><span data-stu-id="d5461-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="d5461-183">**Taille de fichier maximale**</span><span class="sxs-lookup"><span data-stu-id="d5461-183">**Maximum file size**</span></span>  
     <span data-ttu-id="d5461-184">Spécifie la taille maximale d'un fichier d'audit, en mégaoctets (MB), en gigaoctets (GB) ou en téraoctets (TB).</span><span class="sxs-lookup"><span data-stu-id="d5461-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="d5461-185">Vous pouvez spécifier une valeur comprise entre 1 024 Mo et 2 147 483 647 To.</span><span class="sxs-lookup"><span data-stu-id="d5461-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="d5461-186">L'activation de la case à cocher **Illimité** ne fixe pas de limite quant à la taille du fichier.</span><span class="sxs-lookup"><span data-stu-id="d5461-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="d5461-187">La spécification d'une valeur inférieure à 1 024 Mo échoue et génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="d5461-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="d5461-188">La case à cocher **Illimité** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5461-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="d5461-189">Case à cocher**Réserver l’espace disque**</span><span class="sxs-lookup"><span data-stu-id="d5461-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="d5461-190">Spécifie qu'une quantité d'espace disque égale à la taille de fichier maximale spécifiée doit être pré-allouée.</span><span class="sxs-lookup"><span data-stu-id="d5461-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="d5461-191">Ce paramètre ne peut être utilisé que si la case à cocher **Illimité** sous **Taille de fichier maximale** n'est pas sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d5461-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="d5461-192">Cette case à cocher n'est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="d5461-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="d5461-193">Éventuellement, sur la page **Filtre** , entrez un prédicat, ou la clause `WHERE` , pour l'audit de serveur afin de définir des options supplémentaires qui ne sont pas disponibles sur la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="d5461-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="d5461-194">Mettez le prédicat entre parenthèses ; par exemple : `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="d5461-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="d5461-195">Lorsque vous avez fini de sélectionner les options, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5461-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="d5461-196">Pour créer une spécification d'audit de serveur</span><span class="sxs-lookup"><span data-stu-id="d5461-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="d5461-197">Dans l'Explorateur d'objets, cliquez sur le signe plus pour développer le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="d5461-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="d5461-198">Cliquez avec le bouton droit sur le dossier **Spécifications de l’audit du serveur**, puis sélectionnez **Nouvelle spécification de l’audit du serveur...** .</span><span class="sxs-lookup"><span data-stu-id="d5461-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="d5461-199">Les options suivantes sont disponibles dans la boîte de dialogue **Créer la spécification de l'audit du serveur** .</span><span class="sxs-lookup"><span data-stu-id="d5461-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="d5461-200">**Nom**</span><span class="sxs-lookup"><span data-stu-id="d5461-200">**Name**</span></span>  
     <span data-ttu-id="d5461-201">Nom de la spécification de l'audit du serveur.</span><span class="sxs-lookup"><span data-stu-id="d5461-201">The name of the server audit specification.</span></span> <span data-ttu-id="d5461-202">Le nom est généré automatiquement lorsque vous créez une spécification d'audit du serveur, mais vous pouvez le modifier.</span><span class="sxs-lookup"><span data-stu-id="d5461-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="d5461-203">**Audit**</span><span class="sxs-lookup"><span data-stu-id="d5461-203">**Audit**</span></span>  
     <span data-ttu-id="d5461-204">Nom d'un audit de serveur existant.</span><span class="sxs-lookup"><span data-stu-id="d5461-204">The name of an existing server audit.</span></span> <span data-ttu-id="d5461-205">Tapez le nom de l'audit ou sélectionnez-le dans la liste.</span><span class="sxs-lookup"><span data-stu-id="d5461-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="d5461-206">**Type d'action de l'audit**</span><span class="sxs-lookup"><span data-stu-id="d5461-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="d5461-207">Spécifie les groupes d'actions d'audit de niveau serveur et les actions d'audit à capturer.</span><span class="sxs-lookup"><span data-stu-id="d5461-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="d5461-208">Pour obtenir la liste d’actions d’audit et de groupes d’actions d’audit de niveau serveur, ainsi qu’une description des événements qu’ils contiennent, consultez [Actions et groupes d’actions SQL Server Audit](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="d5461-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="d5461-209">**Schéma d'objet**</span><span class="sxs-lookup"><span data-stu-id="d5461-209">**Object Schema**</span></span>  
     <span data-ttu-id="d5461-210">Affiche le schéma du **Nom de l’objet**spécifié.</span><span class="sxs-lookup"><span data-stu-id="d5461-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="d5461-211">**Nom de l’objet**</span><span class="sxs-lookup"><span data-stu-id="d5461-211">**Object Name**</span></span>  
     <span data-ttu-id="d5461-212">Nom de l'objet à auditer.</span><span class="sxs-lookup"><span data-stu-id="d5461-212">The name of the object to audit.</span></span> <span data-ttu-id="d5461-213">Disponible uniquement pour les actions d'audit ; ne s'applique pas aux groupes d'audit.</span><span class="sxs-lookup"><span data-stu-id="d5461-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="d5461-214">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="d5461-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d5461-215">Ouvre la boîte de dialogue **Sélectionner des objets** permettant de rechercher et sélectionner un objet disponible, en fonction du **Type d'action de l'audit**spécifié.</span><span class="sxs-lookup"><span data-stu-id="d5461-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="d5461-216">**Nom principal**</span><span class="sxs-lookup"><span data-stu-id="d5461-216">**Principal Name**</span></span>  
     <span data-ttu-id="d5461-217">Compte par lequel filtrer l'audit pour l'objet audité.</span><span class="sxs-lookup"><span data-stu-id="d5461-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="d5461-218">**Points de suspension (...)**</span><span class="sxs-lookup"><span data-stu-id="d5461-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="d5461-219">Ouvre la boîte de dialogue **Sélectionner des objets** permettant de rechercher et sélectionner un objet disponible, en fonction du **Nom de l'objet**spécifié.</span><span class="sxs-lookup"><span data-stu-id="d5461-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="d5461-220">Quand vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5461-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d5461-221">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d5461-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="d5461-222">Pour créer un audit de serveur</span><span class="sxs-lookup"><span data-stu-id="d5461-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="d5461-223">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5461-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d5461-224">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d5461-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d5461-225">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d5461-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="d5461-226">Pour créer une spécification d'audit de serveur</span><span class="sxs-lookup"><span data-stu-id="d5461-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="d5461-227">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5461-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d5461-228">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d5461-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d5461-229">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d5461-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="d5461-230">Pour plus d’informations, consultez [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) et [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d5461-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
