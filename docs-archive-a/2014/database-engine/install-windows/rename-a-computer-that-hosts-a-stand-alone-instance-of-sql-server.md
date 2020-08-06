---
title: Renommer un ordinateur qui héberge une instance autonome de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- remote login errors [SQL Server]
- standalone computer names [SQL Server]
- names [SQL Server], standalone instances of SQL Server
- renaming standalone instances of SQL Server
- sysservers system table
- removing remote logins
- deleting remote logins
- dropping remote logins
ms.assetid: bbaf1445-b8a2-4ebf-babe-17d8cf20b037
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 079348921900a7cbf880027433280253df1a9e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707767"
---
# <a name="rename-a-computer-that-hosts-a-stand-alone-instance-of-sql-server"></a><span data-ttu-id="c5963-102">Renommer un ordinateur qui héberge une instance autonome de SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5963-102">Rename a Computer that Hosts a Stand-Alone Instance of SQL Server</span></span>
  <span data-ttu-id="c5963-103">Lorsque vous modifiez le nom de l'ordinateur qui exécute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le nouveau nom est reconnu au démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5963-103">When you change the name of the computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the new name is recognized during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup.</span></span> <span data-ttu-id="c5963-104">Vous n'avez pas besoin de réexécuter le programme d'installation pour réinitialiser le nom d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-104">You do not have to run Setup again to reset the computer name.</span></span> <span data-ttu-id="c5963-105">À la place, utilisez la procédure suivante pour mettre à jour les métadonnées système qui sont stockées dans sys.servers et signalées par la fonction système @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="c5963-105">Instead, use the following steps to update system metadata that is stored in sys.servers and reported by the system function @@SERVERNAME.</span></span> <span data-ttu-id="c5963-106">Mettez à jour les métadonnées système pour refléter les modifications opérées dans les noms d’ordinateurs pour les connexions à distance et les applications qui utilisent @@SERVERNAME, ou qui interrogent le nom du serveur à partir de sys.servers.</span><span class="sxs-lookup"><span data-stu-id="c5963-106">Update system metadata to reflect computer name changes for remote connections and applications that use @@SERVERNAME, or that query the server name from sys.servers.</span></span>  
  
 <span data-ttu-id="c5963-107">Les procédures suivantes ne vous permettent pas de renommer une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-107">The following steps cannot be used to rename an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5963-108">Elles ne peuvent être utilisées que pour renommer la partie du nom de l'instance qui correspond au nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-108">They can be used only to rename the part of the instance name that corresponds to the computer name.</span></span> <span data-ttu-id="c5963-109">Par exemple, vous pouvez remplacer le nom d'un ordinateur nommé MB1 qui héberge une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nommée Instance1 par un autre nom, tel que MB2.</span><span class="sxs-lookup"><span data-stu-id="c5963-109">For example, you can change a computer named MB1 that hosts an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] named Instance1 to another name, such as MB2.</span></span> <span data-ttu-id="c5963-110">Cependant, la partie d'instance du nom, Instance1, restera inchangée.</span><span class="sxs-lookup"><span data-stu-id="c5963-110">However, the instance part of the name, Instance1, will remain unchanged.</span></span> <span data-ttu-id="c5963-111">Dans cet exemple, la partie \\\\*Nom_ordinateur*\\*Nom_instance* nommée \\\MB1\Instance1 sera remplacée par \\\MB2\Instance1.</span><span class="sxs-lookup"><span data-stu-id="c5963-111">In this example, the \\\\*ComputerName*\\*InstanceName* would be changed from \\\MB1\Instance1 to \\\MB2\Instance1.</span></span>  
  
 <span data-ttu-id="c5963-112">**Avant de commencer**</span><span class="sxs-lookup"><span data-stu-id="c5963-112">**Before you begin**</span></span>  
  
 <span data-ttu-id="c5963-113">Avant d'entamer la procédure consistant à attribuer un nouveau nom, prenez connaissance des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c5963-113">Before you begin the renaming process, review the following information:</span></span>  
  
-   <span data-ttu-id="c5963-114">Lorsqu'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fait partie d'un cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le processus permettant de renommer l'ordinateur diffère du processus permettant de renommer un ordinateur qui héberge une instance autonome.</span><span class="sxs-lookup"><span data-stu-id="c5963-114">When an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the computer renaming process differs from a computer that hosts a stand-alone instance.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c5963-115">ne prend pas en charge la modification de nom des ordinateurs impliqués dans la réplication, excepté lorsque vous utilisez la copie des journaux de transaction avec la réplication.</span><span class="sxs-lookup"><span data-stu-id="c5963-115">does not support renaming computers that are involved in replication, except when you use log shipping with replication.</span></span> <span data-ttu-id="c5963-116">L'ordinateur secondaire pour la copie des journaux de transaction peut être renommé si l'ordinateur principal est définitivement perdu.</span><span class="sxs-lookup"><span data-stu-id="c5963-116">The secondary computer in log shipping can be renamed if the primary computer is permanently lost.</span></span> <span data-ttu-id="c5963-117">Pour plus d’informations, consultez [Copie des journaux de transaction et réplication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c5963-117">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c5963-118">Lorsque vous renommez un ordinateur configuré pour utiliser [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] peut ne pas être disponible après la modification du nom d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-118">When you rename a computer that is configured to use [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might not be available after the computer name change.</span></span> <span data-ttu-id="c5963-119">Pour plus d’informations, consultez [Changement de nom d’un ordinateur serveur de rapports](../../reporting-services/report-server/rename-a-report-server-computer.md).</span><span class="sxs-lookup"><span data-stu-id="c5963-119">For more information, see [Rename a Report Server Computer](../../reporting-services/report-server/rename-a-report-server-computer.md).</span></span>  
  
-   <span data-ttu-id="c5963-120">Lorsque vous renommez un ordinateur configuré pour utiliser la mise en miroir de bases de données, vous devez désactiver cette fonction avant de modifier le nom.</span><span class="sxs-lookup"><span data-stu-id="c5963-120">When you rename a computer that is configured to use database mirroring, you must turn off database mirroring before the renaming operation.</span></span> <span data-ttu-id="c5963-121">Ensuite, vous devez la réactiver avec le nouveau nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-121">Then, re-establish database mirroring with the new computer name.</span></span> <span data-ttu-id="c5963-122">Les métadonnées de la mise en miroir de la base de données ne seront pas mises à jour automatiquement de façon à refléter le nouveau nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-122">Metadata for database mirroring will not be updated automatically to reflect the new computer name.</span></span> <span data-ttu-id="c5963-123">Procédez comme suit pour mettre à jour les métadonnées système :</span><span class="sxs-lookup"><span data-stu-id="c5963-123">Use the following steps to update system metadata.</span></span>  
  
-   <span data-ttu-id="c5963-124">Les utilisateurs qui se connectent à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le biais d'un groupe Windows utilisant une référence codée en dur au nom de l'ordinateur risquent de ne pas pouvoir se connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-124">Users who connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through a Windows group that uses a hard-coded reference to the computer name might not be able to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5963-125">Cela peut se produire après l'attribution du nouveau nom si le groupe Windows spécifie l'ancien nom d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-125">This can occur after the rename if the Windows group specifies the old computer name.</span></span> <span data-ttu-id="c5963-126">Pour vous assurer que ces groupes Windows bénéficient de la connectivité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] après l'opération de changement de nom, mettez à jour le groupe Windows pour spécifier le nouveau nom de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-126">To ensure that such Windows groups have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connectivity following the renaming operation, update the Windows group to specify the new computer name.</span></span>  
  
 <span data-ttu-id="c5963-127">Vous pouvez vous connecter à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du nouveau nom d'ordinateur après avoir redémarré [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-127">You can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the new computer name after you have restarted [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c5963-128">Pour vous assurer que @@SERVERNAME retourne le nom mis à jour de l’instance de serveur local, vous devez exécuter manuellement la procédure suivante qui s’applique à votre scénario.</span><span class="sxs-lookup"><span data-stu-id="c5963-128">To ensure that @@SERVERNAME returns the updated name of the local server instance, you should manually run the following procedure that applies to your scenario.</span></span> <span data-ttu-id="c5963-129">La procédure à utiliser varie selon que vous mettez à jour un ordinateur qui héberge une instance par défaut ou une instance nommée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-129">The procedure you use depends on whether you are updating a computer that hosts a default or named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-rename-a-computer-that-hosts-a-stand-alone-instance-of-ssnoversion"></a><span data-ttu-id="c5963-130">Pour renommer un ordinateur qui héberge une instance autonome de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5963-130">To rename a computer that hosts a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="c5963-131">Dans le cas d'un ordinateur renommé qui héberge une instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exécutez les procédures ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c5963-131">For a renamed computer that hosts a default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name>;  
    GO  
    sp_addserver <new_name>, local;  
    GO  
    ```  
  
     <span data-ttu-id="c5963-132">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-132">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c5963-133">Dans le cas d'un ordinateur renommé qui héberge une instance nommée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], exécutez les procédures ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c5963-133">For a renamed computer that hosts a named instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run the following procedures:</span></span>  
  
    ```  
    sp_dropserver <old_name\instancename>;  
    GO  
    sp_addserver <new_name\instancename>, local;  
    GO  
    ```  
  
     <span data-ttu-id="c5963-134">Redémarrez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5963-134">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="after-the-renaming-operation"></a><span data-ttu-id="c5963-135">Après l'opération d'attribution d'un nouveau nom</span><span class="sxs-lookup"><span data-stu-id="c5963-135">After the Renaming Operation</span></span>  
 <span data-ttu-id="c5963-136">Une fois l'ordinateur redémarré, toutes les connexions qui utilisaient l'ancien nom d'ordinateur doivent se connecter à l'aide du nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="c5963-136">After a computer has been renamed, any connections that used the old computer name must connect by using the new name.</span></span>  
  
#### <a name="to-verify-that-the-renaming-operation-has-completed-successfully"></a><span data-ttu-id="c5963-137">Pour vérifier si la modification du nom s'est effectuée correctement</span><span class="sxs-lookup"><span data-stu-id="c5963-137">To verify that the renaming operation has completed successfully</span></span>  
  
-   <span data-ttu-id="c5963-138">Sélectionnez des informations à partir de @@SERVERNAME ou sys.servers.</span><span class="sxs-lookup"><span data-stu-id="c5963-138">Select information from either @@SERVERNAME or sys.servers.</span></span> <span data-ttu-id="c5963-139">La fonction @@SERVERNAME renvoie le nouveau nom et la table sys.servers affiche le nouveau nom.</span><span class="sxs-lookup"><span data-stu-id="c5963-139">The @@SERVERNAME function will return the new name, and the sys.servers table will show the new name.</span></span> <span data-ttu-id="c5963-140">L’exemple suivant illustre l’utilisation de @@SERVERNAME .</span><span class="sxs-lookup"><span data-stu-id="c5963-140">The following example shows the use of @@SERVERNAME.</span></span>  
  
    ```  
    SELECT @@SERVERNAME AS 'Server Name';  
    ```  
  
## <a name="additional-considerations"></a><span data-ttu-id="c5963-141">Considérations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c5963-141">Additional Considerations</span></span>  
 <span data-ttu-id="c5963-142">**Ouvertures de sessions distantes** - Si des sessions à distance sont ouvertes sur l’ordinateur, l’exécution de **sp_dropserver** risque de générer une erreur semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="c5963-142">**Remote Logins** - If the computer has any remote logins, running **sp_dropserver** might generate an error similar to the following:</span></span>  
  
 `Server: Msg 15190, Level 16, State 1, Procedure sp_dropserver, Line 44 There are still remote logins for the server 'SERVER1'.`  
  
 <span data-ttu-id="c5963-143">Pour résoudre l'erreur, vous devez supprimer les ouvertures de session à distance du serveur.</span><span class="sxs-lookup"><span data-stu-id="c5963-143">To resolve the error, you must drop remote logins for this server.</span></span>  
  
#### <a name="to-drop-remote-logins"></a><span data-ttu-id="c5963-144">Pour supprimer les ouvertures de session à distance</span><span class="sxs-lookup"><span data-stu-id="c5963-144">To drop remote logins</span></span>  
  
-   <span data-ttu-id="c5963-145">Dans le cas d'une instance par défaut, suivez la procédure ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c5963-145">For a default instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name;  
    GO  
    ```  
  
-   <span data-ttu-id="c5963-146">Dans le cas d'une instance nommée, suivez la procédure ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c5963-146">For a named instance, run the following procedure:</span></span>  
  
    ```  
    sp_dropremotelogin old_name\instancename;  
    GO  
    ```  
  
 <span data-ttu-id="c5963-147">**Configurations de serveur lié** - Les configurations de serveur lié seront affectées par l’opération d’attribution d’un nouveau nom à l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-147">**Linked Server Configurations** - Linked server configurations will be affected by the computer renaming operation.</span></span> <span data-ttu-id="c5963-148">Utilisez `sp_addlinkedserver` ou `sp_setnetname` pour mettre à jour les références de nom d'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-148">Use `sp_addlinkedserver` or `sp_setnetname` to update computer name references.</span></span> <span data-ttu-id="c5963-149">Pour plus d’informations, consultez [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) ou [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5963-149">For more information, see the [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) or [sp_setnetname &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setnetname-transact-sql).</span></span>  
  
 <span data-ttu-id="c5963-150">**Noms d’alias client** - Les alias client qui utilisent des canaux nommés seront affectés par l’opération d’attribution d’un nouveau nom à l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c5963-150">**Client Alias Names** - Client aliases that use named pipes will be affected by the computer renaming operation.</span></span> <span data-ttu-id="c5963-151">Par exemple, si un alias « PROD_SRVR » a été créé pour désigner SRVR1 et utilise le protocole de canaux nommés, le nom de canal ressemblera à `\\SRVR1\pipe\sql\query`.</span><span class="sxs-lookup"><span data-stu-id="c5963-151">For example, if an alias "PROD_SRVR" was created to point to SRVR1 and uses the named pipes protocol, the pipe name will look like `\\SRVR1\pipe\sql\query`.</span></span> <span data-ttu-id="c5963-152">Après avoir renommé l'ordinateur, le chemin d'accès du canal nommé ne sera plus valide.</span><span class="sxs-lookup"><span data-stu-id="c5963-152">After the computer is renamed, the path of the named pipe will no longer be valid and.</span></span> <span data-ttu-id="c5963-153">Pour plus d’informations sur les canaux nommés, consultez [Création d’une chaîne de connexion valide à l’aide de canaux nommés](https://go.microsoft.com/fwlink/?LinkId=111063).</span><span class="sxs-lookup"><span data-stu-id="c5963-153">For more information about named pipes, see the [Creating a Valid Connection String Using Named Pipes](https://go.microsoft.com/fwlink/?LinkId=111063).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5963-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c5963-154">See Also</span></span>  
 [<span data-ttu-id="c5963-155">Installer SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="c5963-155">Install SQL Server 2014</span></span>](../../database-engine/install-windows/install-sql-server.md)  
  
  
