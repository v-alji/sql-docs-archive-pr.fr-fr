---
title: Agent de lecture de la file d’attente de réplication | Microsoft Docs
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601404"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="a5a5c-102">Agent de lecture de la file d'attente de réplication</span><span class="sxs-lookup"><span data-stu-id="a5a5c-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="a5a5c-103">L’Agent de lecture de la file d’attente de réplication est un fichier exécutable qui lit les messages stockés dans une file d’attente [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ou une file d’attente de messages [!INCLUDE[msCoName](../../../includes/msconame-md.md)], puis qui applique ces messages au serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="a5a5c-104">L'Agent de lecture de la file d'attente est utilisé avec les publications transactionnelles et les publications d'instantané qui autorisent la mise à jour en attente.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5a5c-105">Les paramètres peuvent être spécifiés dans n'importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="a5a5c-106">Lorsque les paramètres optionnels ne sont pas spécifiés, les valeurs prédéfinies basées sur le profil d'agent par défaut sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5a5c-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a5a5c-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a5a5c-108">Arguments</span><span class="sxs-lookup"><span data-stu-id="a5a5c-108">Arguments</span></span>  
 <span data-ttu-id="a5a5c-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-109">**-?**</span></span>  
 <span data-ttu-id="a5a5c-110">Affiche des informations sur l’utilisation.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="a5a5c-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-111">**-Continuous**</span></span>  
 <span data-ttu-id="a5a5c-112">Spécifie si l'agent tente de traiter les transactions en attente de manière continue.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="a5a5c-113">S'il est spécifié, l'agent poursuit l'exécution même si aucune transaction n'est en attente au niveau des Abonnés.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="a5a5c-114">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="a5a5c-115">Chemin d'accès du fichier de définition d'agent.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="a5a5c-116">Un fichier de définition d'agent contient des arguments de ligne de commande pour l'agent.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="a5a5c-117">Le contenu du fichier est analysé en tant que fichier exécutable.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="a5a5c-118">Utilisez des guillemets doubles (") pour spécifier des valeurs d'argument qui contiennent des caractères arbitraires.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="a5a5c-119">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="a5a5c-120">Nom du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-120">Is the Distributor name.</span></span> <span data-ttu-id="a5a5c-121">Spécifiez *server_name* pour l'instance par défaut de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="a5a5c-122">Spécifiez *server_name*\\*instance_name* pour une instance nommée de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="a5a5c-123">S'il n'est pas spécifié, le nom a comme valeur par défaut le nom de l'instance par défaut de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="a5a5c-124">**-DistributionDB** _distribution_database_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="a5a5c-125">Nom de la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="a5a5c-126">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="a5a5c-127">Nom de connexion du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="a5a5c-128">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="a5a5c-129">Mot de passe du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="a5a5c-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="a5a5c-131">Spécifie le mode de sécurité du serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="a5a5c-132">La valeur **0** indique le mode d'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (par défaut), tandis que la valeur **1** indique le mode d'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="a5a5c-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="a5a5c-134">Niveau du chiffrement SSL (Secure Sockets Layer) utilisé par l'Agent de lecture de la file d'attente lors de l'établissement de connexions.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="a5a5c-135">Valeur EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="a5a5c-135">EncryptionLevel value</span></span>|<span data-ttu-id="a5a5c-136">Description</span><span class="sxs-lookup"><span data-stu-id="a5a5c-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a5a5c-137">**0**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-137">**0**</span></span>|<span data-ttu-id="a5a5c-138">Spécifie que le chiffrement SSL n'est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="a5a5c-139">**1**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-139">**1**</span></span>|<span data-ttu-id="a5a5c-140">Spécifie que le chiffrement SSL est utilisé, mais que l'agent ne vérifie pas si le certificat de serveur SSL est signé par un émetteur de confiance.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="a5a5c-141">**2**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-141">**2**</span></span>|<span data-ttu-id="a5a5c-142">Spécifie que le chiffrement SSL est utilisé et que le certificat est vérifié.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="a5a5c-143">Un certificat SSL valide est défini avec le nom de domaine complet de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="a5a5c-144">Pour que l’agent puisse se connecter lorsque vous définissez EncryptionLevel sur 2, créez un alias sur l’instance locale de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="a5a5c-145">Le paramètre « Nom de l’alias » doit correspondre au nom du serveur, et le paramètre « Serveur » doit être défini sur le nom complet de l’instance SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="a5a5c-146">Pour plus d’informations, consultez [réplication SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="a5a5c-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="a5a5c-148">Spécifie la quantité d'informations d'historique journalisées pendant une opération de lecture de la file d'attente.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="a5a5c-149">Vous pouvez réduire l'effet de la journalisation d'historique sur les performances en sélectionnant **1**.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="a5a5c-150">Valeur HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="a5a5c-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="a5a5c-151">Description</span><span class="sxs-lookup"><span data-stu-id="a5a5c-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="a5a5c-152">**0**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-152">**0**</span></span>|<span data-ttu-id="a5a5c-153">Aucune journalisation d'historique (non recommandé).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="a5a5c-154">**1**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-154">**1**</span></span>|<span data-ttu-id="a5a5c-155">Par défaut.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-155">Default.</span></span> <span data-ttu-id="a5a5c-156">Met toujours à jour un message d'historique précédent du même état (démarrage, progression, succès, et ainsi de suite).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="a5a5c-157">Si aucun enregistrement précédent du même état n'existe, insère un nouvel enregistrement.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="a5a5c-158">**2**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-158">**2**</span></span>|<span data-ttu-id="a5a5c-159">Insère de nouveaux enregistrements d'historique, y compris des messages inactifs ou des messages de travail de longue durée.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="a5a5c-160">**3**</span><span class="sxs-lookup"><span data-stu-id="a5a5c-160">**3**</span></span>|<span data-ttu-id="a5a5c-161">Insère de nouveaux enregistrements d'historique incluant des détails supplémentaires qui peuvent s'avérer utiles pour le dépannage.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="a5a5c-162">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="a5a5c-163">Nombre de secondes avant l'expiration de la connexion. La valeur par défaut est 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="a5a5c-164">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="a5a5c-165">Chemin d'accès du fichier de sortie de l'agent.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-165">Is the path of the agent output file.</span></span> <span data-ttu-id="a5a5c-166">Si le nom du fichier n'est pas spécifié, la sortie est envoyée à la console.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="a5a5c-167">Si le nom de fichier spécifié existe, la sortie est ajoutée au fichier.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="a5a5c-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="a5a5c-169">Spécifie si la sortie doit être en clair.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="a5a5c-170">Si le niveau de détail est **0**, seuls les messages d'erreur sont imprimés.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="a5a5c-171">Si le niveau de détail est **1**, tous les messages du rapport de progression sont imprimés.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="a5a5c-172">Si le niveau de détail est **2** (valeur par défaut), tous les messages d'erreur et tous les messages du rapport de progression sont imprimés, ce qui peut s'avérer utile lors du débogage.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="a5a5c-173">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="a5a5c-174">Ne s'applique qu'à la mise à jour d'abonnements qui utilisent des files d'attente basées sur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a5a5c-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="a5a5c-175">Spécifie la fréquence, en secondes, à laquelle la file d'attente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est interrogée au sujet des transactions de file d'attente en cours.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="a5a5c-176">La valeur peut être comprise entre 0 et 240 secondes.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="a5a5c-177">La valeur par défaut est 5 secondes.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="a5a5c-178">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="a5a5c-179">Spécifie l'instance du partenaire de basculement de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participant à une session de mise en miroir de bases de données avec la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="a5a5c-180">Pour plus d’informations, consultez [Mise en miroir de bases de données et réplication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="a5a5c-181">**-ProfileName** _agent_profile_name_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="a5a5c-182">Nom d'un profil d'agent utilisé pour fournir un jeu de valeurs par défaut à l'agent.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="a5a5c-183">Pour plus d’informations, consultez [Profils de l’Agent de réplication](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="a5a5c-184">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="a5a5c-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="a5a5c-185">Nombre de secondes avant l'expiration de la requête. La valeur par défaut est 1800 secondes.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="a5a5c-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="a5a5c-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="a5a5c-187">Spécifie comment les conflits de mise à jour en attente sont résolus.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="a5a5c-188">La valeur **1** indique que le serveur de publication remporte le conflit. Dans ce cas, la transaction en file d'attente actuellement en conflit est restaurée sur le serveur de publication et sur l'Abonné de mise à jour d'origine ; le traitement des transactions en file d'attente suivantes continue.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="a5a5c-189">La valeur **2** indique que l'Abonné remporte le conflit, et la transaction en file d'attente remplace les valeurs sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="a5a5c-190">La valeur **3** indique que tout conflit provoquera la réinitialisation de l'Abonné ; le serveur de publication remporte le conflit, le traitement des transactions en file d'attente suivantes est terminé, et l'abonnement est réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="a5a5c-191">Le paramètre par défaut est **1** pour les publications transactionnelles et **3** pour les publications d'instantané.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5a5c-192">Notes</span><span class="sxs-lookup"><span data-stu-id="a5a5c-192">Remarks</span></span>  
 <span data-ttu-id="a5a5c-193">Pour démarrer l'Agent de lecture de la file d'attente, exécutez **qrdrsvc.exe** à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="a5a5c-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="a5a5c-194">Pour plus d'informations, consultez [Concepts des exécutables de l'agent de réplication](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a5a5c-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a5c-195">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5a5c-195">See Also</span></span>  
 [<span data-ttu-id="a5a5c-196">Administration de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="a5a5c-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
