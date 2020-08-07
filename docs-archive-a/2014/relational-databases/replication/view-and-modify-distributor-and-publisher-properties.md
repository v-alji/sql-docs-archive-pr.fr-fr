---
title: Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- viewing replication properties
- Distributors [SQL Server replication], modifying
- modifying replication properties, Distributors
- Distributors [SQL Server replication], properties
ms.assetid: 5dae1d59-c377-4c6e-adc9-b68c5b328f79
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 571f6f3a0d44f0fc87c67885249fca441776946d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603369"
---
# <a name="view-and-modify-distributor-and-publisher-properties"></a><span data-ttu-id="c6be0-102">Afficher et modifier les propriétés d'un serveur de distribution ou d'un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="c6be0-102">View and Modify Distributor and Publisher Properties</span></span>
  <span data-ttu-id="c6be0-103">Cette rubrique décrit comment afficher et modifier les propriétés du serveur de distribution et du serveur de publication dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="c6be0-103">This topic describes how to view and modify Distributor and Publisher properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span>  
  
 <span data-ttu-id="c6be0-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c6be0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c6be0-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c6be0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6be0-106">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c6be0-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c6be0-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c6be0-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6be0-108">**Pour afficher et modifier les propriétés d'un serveur de publication ou d'un serveur de distribution à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="c6be0-108">**To view and modify Distributor and Publisher properties, using:**</span></span>  
  
     [<span data-ttu-id="c6be0-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6be0-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c6be0-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6be0-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="c6be0-111">Objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="c6be0-111">Replication Management Objects (RMO)</span></span>](#RMOProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6be0-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c6be0-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c6be0-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c6be0-113">Recommendations</span></span>  
  
-   <span data-ttu-id="c6be0-114">Pour les serveurs de publication exécutant des versions antérieures à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], un utilisateur avec le rôle serveur fixe **sysadmin** peut enregistrer des Abonnés dans la page **Abonnés**.</span><span class="sxs-lookup"><span data-stu-id="c6be0-114">For Publishers running versions prior to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user in the **sysadmin** fixed server role can register Subscribers on the **Subscribers** page.</span></span> <span data-ttu-id="c6be0-115">À partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], il n'est plus nécessaire d'inscrire de manière explicite les abonnés pour la réplication.</span><span class="sxs-lookup"><span data-stu-id="c6be0-115">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], it is no longer necessary to explicitly register Subscribers for replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6be0-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c6be0-116">Security</span></span>  
 <span data-ttu-id="c6be0-117">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-117">When possible, prompt users to enter security credentials at runtime.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c6be0-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6be0-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="c6be0-119">Pour afficher et modifier les propriétés du serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-119">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="c6be0-120">Connectez-vous au serveur de distribution dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-120">Connect to the Distributor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c6be0-121">Cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Propriétés du serveur de distribution**.</span><span class="sxs-lookup"><span data-stu-id="c6be0-121">Right-click the **Replication** folder, and then click **Distributor Properties**.</span></span>  
  
3.  <span data-ttu-id="c6be0-122">Affichez et modifiez les propriétés dans la boîte de dialogue **Propriétés du serveur de distribution - \<Distributor>** .</span><span class="sxs-lookup"><span data-stu-id="c6be0-122">View and modify properties in the **Distributor Properties - \<Distributor>** dialog box.</span></span>  
  
    -   <span data-ttu-id="c6be0-123">Pour afficher et modifier les propriétés d’une base de données de distribution, cliquez sur le bouton des propriétés ( **...** ) pour la base de données dans la page **Général** de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c6be0-123">To view and modify properties for a distribution database, click the properties button (**...**) for the database on the **General** page of thedialog box.</span></span>  
  
    -   <span data-ttu-id="c6be0-124">Pour afficher et modifier les propriétés du serveur de publication associées au serveur de distribution, cliquez sur le bouton des propriétés ( **...** ) pour le serveur de publication sur la page **Serveurs de publication** de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c6be0-124">To view and modify Publisher properties associated with the Distributor, click the properties button (**...**) for the Publisher on the **Publishers** page of the dialog box.</span></span>  
  
    -   <span data-ttu-id="c6be0-125">Pour accéder aux profils des agents de réplication, cliquez sur le bouton **Profils par défaut** sur la page **Général** de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c6be0-125">To access profiles for replication agents, click the **Profile Defaults** button on the **General** page of the dialog box.</span></span> <span data-ttu-id="c6be0-126">Pour plus d'informations, voir [Replication Agent Profiles](agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c6be0-126">For more information, see [Replication Agent Profiles](agents/replication-agent-profiles.md).</span></span>  
  
    -   <span data-ttu-id="c6be0-127">Pour modifier le mot de passe du compte utilisé lors de l'exécution des procédures stockées administratives sur le serveur de publication et de la mise à jour des informations sur le serveur de distribution, entrez un nouveau mot de passe dans les zones **Mot de passe** et **Confirmer le mot de passe** sur la page **Serveurs de publication** de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c6be0-127">To change the password for the account used when administrative stored procedures execute at the Publisher and update information at the Distributor, enter a new password in the **Password** and **Confirm password** boxes on the **Publishers** page of the dialog box.</span></span> <span data-ttu-id="c6be0-128">Pour plus d’informations, consultez [Protéger le serveur de distribution](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="c6be0-128">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
4.  <span data-ttu-id="c6be0-129">Modifiez les propriétés si nécessaire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6be0-129">Modify any properties if necessary, and then click **OK**.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="c6be0-130">Pour afficher et modifier les propriétés du serveur de publication</span><span class="sxs-lookup"><span data-stu-id="c6be0-130">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="c6be0-131">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-131">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c6be0-132">Cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Propriétés du serveur de publication**.</span><span class="sxs-lookup"><span data-stu-id="c6be0-132">Right-click the **Replication** folder, and then click **Publisher Properties**.</span></span>  
  
3.  <span data-ttu-id="c6be0-133">Affichez et modifiez les propriétés dans la boîte de dialogue Propriétés du serveur de \*\*publication- \< Publisher > \*\* .</span><span class="sxs-lookup"><span data-stu-id="c6be0-133">View and modify properties in the **Publisher Properties - \< Publisher >** dialog box.</span></span>  
  
    -   <span data-ttu-id="c6be0-134">Un utilisateur du rôle serveur fixe **sysadmin** peut activer des bases de données pour la réplication sur la page **Bases de données de publication** .</span><span class="sxs-lookup"><span data-stu-id="c6be0-134">A user in the **sysadmin** fixed server role can enable databases for replication on the **Publication Databases** page.</span></span> <span data-ttu-id="c6be0-135">L'activation d'une base de données ne publie pas cette dernière, elle permet plutôt à n'importe quel utilisateur du rôle de base de données fixe **db_owner** de cette base de données de créer une ou plusieurs publications dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c6be0-135">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications in the database.</span></span>  
  
4.  <span data-ttu-id="c6be0-136">Modifiez les propriétés si nécessaire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6be0-136">Modify any properties if necessary, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c6be0-137">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6be0-137">Using Transact-SQL</span></span>  
 <span data-ttu-id="c6be0-138">Les propriétés du serveur de publication et du serveur de distribution peuvent être affichées par programme en utilisant des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="c6be0-138">Publisher and Distributor properties can be viewed programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-view-distributor-and-distribution-database-properties"></a><span data-ttu-id="c6be0-139">Pour afficher les propriétés du serveur de distribution et de la base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-139">To view Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="c6be0-140">Exécutez [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) pour retourner des informations sur le serveur de distribution, la base de données de distribution et le répertoire de travail.</span><span class="sxs-lookup"><span data-stu-id="c6be0-140">Execute [sp_helpdistributor](/sql/relational-databases/system-stored-procedures/sp-helpdistributor-transact-sql) to return information about the Distributor, distribution database, and working directory.</span></span>  
  
2.  <span data-ttu-id="c6be0-141">Exécutez [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) pour retourner les propriétés d'une base de données de distribution spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c6be0-141">Execute [sp_helpdistributiondb](/sql/relational-databases/system-stored-procedures/sp-helpdistributiondb-transact-sql) to return properties of a specified distribution database.</span></span>  
  
#### <a name="to-change-distributor-and-distribution-database-properties"></a><span data-ttu-id="c6be0-142">Pour modifier les propriétés du serveur de distribution et de la base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-142">To change Distributor and distribution database properties</span></span>  
  
1.  <span data-ttu-id="c6be0-143">Sur le serveur de distribution, exécutez [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) pour modifier les propriétés du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-143">At the Distributor, execute [sp_changedistributor_property](/sql/relational-databases/system-stored-procedures/sp-changedistributor-property-transact-sql) to modify Distributor properties.</span></span>  
  
2.  <span data-ttu-id="c6be0-144">Sur le serveur de distribution, exécutez [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) pour modifier les propriétés de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-144">At the Distributor, execute [sp_changedistributiondb](/sql/relational-databases/system-stored-procedures/sp-changedistributiondb-transact-sql) to modify distribution database properties.</span></span>  
  
3.  <span data-ttu-id="c6be0-145">Sur le serveur de distribution, exécutez [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) pour modifier le mot de passe du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-145">At the Distributor, execute [sp_changedistributor_password](/sql/relational-databases/system-stored-procedures/sp-changedistributor-password-transact-sql) to change the Distributor password.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c6be0-146">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-146">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="c6be0-147">Si vous devez stocker des informations d'identification dans un fichier de script, sécurisez le fichier pour empêcher tout accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="c6be0-147">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
4.  <span data-ttu-id="c6be0-148">Sur le serveur de distribution, exécutez [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) pour modifier les propriétés d'un serveur de publication à l'aide du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-148">At the Distributor, execute [sp_changedistpublisher](/sql/relational-databases/system-stored-procedures/sp-changedistpublisher-transact-sql) to change the properties of a Publisher using the Distributor.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="c6be0-149">Exemples (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c6be0-149">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="c6be0-150">L'exemple de script [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant retourne des informations sur le serveur de distribution et sur la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-150">The following example [!INCLUDE[tsql](../../includes/tsql-md.md)] script returns information about the Distributor and distribution database.</span></span>  
  
 [!code-sql[HowTo#sp_helpdistributor](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributor)]  
  
 [!code-sql[HowTo#sp_helpdistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_helpdistributiondb)]  
  
 <span data-ttu-id="c6be0-151">Cet exemple modifie les périodes de rétention du serveur de distribution, le mot de passe utilisé lors de la connexion au serveur de distribution et l'intervalle auquel le serveur de distribution vérifie l'état de différents Agents de réplication (également appelé intervalle d'interrogation).</span><span class="sxs-lookup"><span data-stu-id="c6be0-151">This example changes retention periods for the Distributor, the password used when connecting to the Distributor, and the interval at which the Distributor checks the status of various replication agents (also known as the heartbeat interval).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6be0-152">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-152">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="c6be0-153">Si vous devez stocker des informations d'identification dans un fichier de script, sécurisez le fichier pour empêcher tout accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="c6be0-153">If you must store credentials in a script file, secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_changedistributor_property](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_property)]  
  
 [!code-sql[HowTo#sp_changedistributiondb](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributiondb)]  
  
 [!code-sql[HowTo#sp_changedistributor_password](../../snippets/tsql/SQL15/replication/howto/tsql/changedistpub.sql#sp_changedistributor_password)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="c6be0-154">Utilisation d'objets RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="c6be0-154">Using Replication Management Objects (RMO)</span></span>  
  
#### <a name="to-view-and-modify-distributor-properties"></a><span data-ttu-id="c6be0-155">Pour afficher et modifier les propriétés du serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-155">To view and modify Distributor properties</span></span>  
  
1.  <span data-ttu-id="c6be0-156">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-156">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c6be0-157">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="c6be0-157">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="c6be0-158">Passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c6be0-158">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="c6be0-159">(Facultatif) Vérifiez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> pour vérifier que le serveur actuellement connecté est un serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-159">(Optional) Check the <xref:Microsoft.SqlServer.Replication.ReplicationServer.IsDistributor%2A> property to verify that the currently connected server is a Distributor.</span></span>  
  
4.  <span data-ttu-id="c6be0-160">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> pour obtenir les propriétés du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-160">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties from the server.</span></span>  
  
5.  <span data-ttu-id="c6be0-161">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une ou de plusieurs des propriétés du serveur de distribution qui peuvent être définies sur l'objet <xref:Microsoft.SqlServer.Replication.ReplicationServer> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-161">(Optional) To change properties, set a new value for one or more of the Distributor properties that can be set on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object.</span></span>  
  
6.  <span data-ttu-id="c6be0-162">(Facultatif) Si la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sur l'objet <xref:Microsoft.SqlServer.Replication.ReplicationServer> a la valeur `true`, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> pour valider les modifications sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-162">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.ReplicationServer> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-distribution-database-properties"></a><span data-ttu-id="c6be0-163">Pour afficher et modifier les propriétés de base de données de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-163">To view and modify distribution database properties</span></span>  
  
1.  <span data-ttu-id="c6be0-164">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-164">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c6be0-165">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.DistributionDatabase>.</span><span class="sxs-lookup"><span data-stu-id="c6be0-165">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> class.</span></span> <span data-ttu-id="c6be0-166">Spécifiez la propriété de nom et passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c6be0-166">Specify the name property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="c6be0-167">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> pour obtenir les propriétés du serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-167">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method to get the properties from the server.</span></span> <span data-ttu-id="c6be0-168">Si cette méthode retourne `false`, la base de données avec le nom spécifié n'existe pas sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-168">If this method returns `false`, the database with the specified name does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="c6be0-169">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.DistributionDatabase> qui peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="c6be0-169">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> properties that can be set.</span></span>  
  
5.  <span data-ttu-id="c6be0-170">(Facultatif) Si la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sur l'objet <xref:Microsoft.SqlServer.Replication.DistributionDatabase> a la valeur `true`, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> pour valider les modifications sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-170">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionDatabase> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-view-and-modify-publisher-properties"></a><span data-ttu-id="c6be0-171">Pour afficher et modifier les propriétés du serveur de publication</span><span class="sxs-lookup"><span data-stu-id="c6be0-171">To view and modify Publisher properties</span></span>  
  
1.  <span data-ttu-id="c6be0-172">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-172">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c6be0-173">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.DistributionPublisher>.</span><span class="sxs-lookup"><span data-stu-id="c6be0-173">Create an instance of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> class.</span></span> <span data-ttu-id="c6be0-174">Spécifiez la propriété <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> et passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c6be0-174">Specify the <xref:Microsoft.SqlServer.Replication.DistributionPublisher.Name%2A> property and pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object from step 1.</span></span>  
  
3.  <span data-ttu-id="c6be0-175">(Facultatif) Pour modifier des propriétés, modifiez la valeur d'une des propriétés <xref:Microsoft.SqlServer.Replication.DistributionPublisher> qui peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="c6be0-175">(Optional) To change properties, set a new value for one of the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> properties that can be set.</span></span>  
  
4.  <span data-ttu-id="c6be0-176">(Facultatif) Si la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> sur l'objet <xref:Microsoft.SqlServer.Replication.DistributionPublisher> a la valeur `true`, appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> pour valider les modifications sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c6be0-176">(Optional) If the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CachePropertyChanges%2A> property on the <xref:Microsoft.SqlServer.Replication.DistributionPublisher> object is set to `true`, call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A> method to commit the changes to the server.</span></span>  
  
#### <a name="to-change-the-password-for-the-administrative-connection-from-the-publisher-to-the-distributor"></a><span data-ttu-id="c6be0-177">Pour modifier le mot de passe pour la connexion administrative du serveur de publication au serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="c6be0-177">To change the password for the administrative connection from the Publisher to the Distributor</span></span>  
  
1.  <span data-ttu-id="c6be0-178">Créez une connexion au serveur de distribution en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-178">Create a connection to the Distributor by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="c6be0-179">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="c6be0-179">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
3.  <span data-ttu-id="c6be0-180">Définissez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en spécifiant la connexion créée à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="c6be0-180">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 1.</span></span>  
  
4.  <span data-ttu-id="c6be0-181">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="c6be0-181">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
5.  <span data-ttu-id="c6be0-182">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-182">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="c6be0-183">Passez la nouvelle valeur de mot de passe pour le paramètre *password* .</span><span class="sxs-lookup"><span data-stu-id="c6be0-183">Pass the new password value for the *password* parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c6be0-184">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-184">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="c6be0-185">Si vous devez stocker des informations d'identification, utilisez les [Services de chiffrement](https://go.microsoft.com/fwlink/?LinkId=34733) fournis par [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c6be0-185">If you must store credentials, use the [cryptographic services](https://go.microsoft.com/fwlink/?LinkId=34733) provided by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows .NET Framework.</span></span>  
  
6.  <span data-ttu-id="c6be0-186">(Facultatif) Effectuez la procédure suivante pour modifier le mot de passe sur chaque serveur de publication distant qui utilise ce serveur de distribution :</span><span class="sxs-lookup"><span data-stu-id="c6be0-186">(Optional) Perform the following steps to change the password at each remote Publisher that uses this Distributor:</span></span>  
  
    1.  <span data-ttu-id="c6be0-187">Créez une connexion au serveur de publication en utilisant la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-187">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
    2.  <span data-ttu-id="c6be0-188">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="c6be0-188">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span>  
  
    3.  <span data-ttu-id="c6be0-189">Définissez la propriété <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> en spécifiant la connexion créée à l'étape 6a.</span><span class="sxs-lookup"><span data-stu-id="c6be0-189">Set the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property to the connection created in step 6a.</span></span>  
  
    4.  <span data-ttu-id="c6be0-190">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> pour obtenir les propriétés de l'objet.</span><span class="sxs-lookup"><span data-stu-id="c6be0-190">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.Load%2A> method to get the properties of the object.</span></span>  
  
    5.  <span data-ttu-id="c6be0-191">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> .</span><span class="sxs-lookup"><span data-stu-id="c6be0-191">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.ChangeDistributorPassword%2A> method.</span></span> <span data-ttu-id="c6be0-192">Passez la nouvelle valeur de mot de passe spécifiée à l'étape 5 pour le paramètre *password* .</span><span class="sxs-lookup"><span data-stu-id="c6be0-192">Pass the new password value from Step 5 for the *password* parameter.</span></span>  
  
###  <a name="example-rmo"></a><a name="PShellExample"></a> <span data-ttu-id="c6be0-193">Exemple (RMO)</span><span class="sxs-lookup"><span data-stu-id="c6be0-193">Example (RMO)</span></span>  
 <span data-ttu-id="c6be0-194">Cet exemple montre comment modifier les propriétés du serveur de distribution et de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-194">This example shows how to change Distribution and distribution database properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6be0-195">Pour éviter de stocker les informations d'identification dans le code, le nouveau mot de passe du serveur de distribution est fourni au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="c6be0-195">To avoid storing credentials in the code, the new Distributor password is supplied at runtime.</span></span>  
  
 [!code-csharp[HowTo#rmo_ChangeDistPub](../../snippets/csharp/SQL15/replication/howto/cs/rmotestevelope.cs#rmo_changedistpub)]  
  
 [!code-vb[HowTo#rmo_vb_ChangeDistPub](../../snippets/visualbasic/SQL15/replication/howto/vb/rmotestenv.vb#rmo_vb_changedistpub)]  
  
## <a name="see-also"></a><span data-ttu-id="c6be0-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6be0-196">See Also</span></span>  
 <span data-ttu-id="c6be0-197">[Concepts liés à RMO (Replication Management Objects)](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-197">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="c6be0-198">[Désactiver la publication et la distribution](disable-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-198">[Disable Publishing and Distribution](disable-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="c6be0-199">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-199">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="c6be0-200">[Concepts liés à RMO (Replication Management Objects)](concepts/replication-management-objects-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-200">[Replication Management Objects Concepts](concepts/replication-management-objects-concepts.md) </span></span>  
 <span data-ttu-id="c6be0-201">[Script d’information du serveur de distribution et du serveur de publication](administration/distributor-and-publisher-information-script.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-201">[Distributor and Publisher Information Script](administration/distributor-and-publisher-information-script.md) </span></span>  
 <span data-ttu-id="c6be0-202">[Concepts liés aux procédures stockées système de réplication](concepts/replication-system-stored-procedures-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c6be0-202">[Replication System Stored Procedures Concepts](concepts/replication-system-stored-procedures-concepts.md) </span></span>  
 [<span data-ttu-id="c6be0-203">Afficher des informations et effectuer des tâches à l’aide du moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="c6be0-203">View Information and Perform Tasks using Replication Monitor</span></span>](monitor/view-information-and-perform-tasks-replication-monitor.md)  
  
  
