---
title: Propriétés de l’éditeur de Réplication SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701046"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="467d4-102">Propriétés de l’éditeur de Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="467d4-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="467d4-103">Cette section contient des informations sur les propriétés du serveur de publication disponibles sur le serveur de distribution et sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="467d4-104">Général</span><span class="sxs-lookup"><span data-stu-id="467d4-104">General</span></span>  
  <span data-ttu-id="467d4-105"> La page **Général** de la boîte de dialogue **Propriétés du serveur de publication** contient des informations en lecture seule sur le serveur de distribution et la base de données de distribution qu’utilise le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="467d4-106">Pour changer le serveur de distribution ou la base de données de distribution d'un serveur de publication :</span><span class="sxs-lookup"><span data-stu-id="467d4-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="467d4-107">Désactivez la publication sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="467d4-108">Pour plus d’informations, consultez [Désactiver la publication et la distribution](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="467d4-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="467d4-109">Reconfigurez la publication et la distribution.</span><span class="sxs-lookup"><span data-stu-id="467d4-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="467d4-110">Pour plus d’informations, consultez [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="467d4-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="467d4-111">Serveur de distribution</span><span class="sxs-lookup"><span data-stu-id="467d4-111">Distributor</span></span>
  <span data-ttu-id="467d4-112"> La boîte de dialogue **Propriétés du serveur de publication** permet d’afficher et de modifier les propriétés associées à la relation existant entre le serveur de publication et son serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="467d4-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="467d4-113">Options</span><span class="sxs-lookup"><span data-stu-id="467d4-113">Options</span></span>  
 <span data-ttu-id="467d4-114">**Connexion de l'agent au serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="467d4-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="467d4-115">Permet d'ajouter le contexte selon lequel les agents suivants établissent les connexions du serveur de distribution au serveur de publication :</span><span class="sxs-lookup"><span data-stu-id="467d4-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="467d4-116">l'Agent de lecture de la file d'attente propre aux publications transactionnelles autorisant les abonnements de mise à jour dans la file d'attente ;</span><span class="sxs-lookup"><span data-stu-id="467d4-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="467d4-117">l'Agent d'instantané et l'Agent de lecture du journal pour les publications Oracle.</span><span class="sxs-lookup"><span data-stu-id="467d4-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="467d4-118">Choisissez l'option **Imiter le compte de processus de l'Agent** afin d'établir des connexions au serveur de publication grâce au contexte du compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows fourni et sous lequel ces agents doivent s'exécuter, ou bien choisissez **Authentification SQL Server**et saisissez alors une valeur pour chacun des champs **Connexion** et **Mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="467d4-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="467d4-119">Nous vous recommandons de sélectionner plutôt l'option **Imiter le compte de processus de l'Agent**.</span><span class="sxs-lookup"><span data-stu-id="467d4-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="467d4-120">Pour plus d’informations sur la sécurité de l’agent, consultez [Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="467d4-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="467d4-121">Les comptes Windows sous lesquels ces agents s'exécutent sont précisés dans l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="467d4-122">Ces comptes peuvent être modifiés de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="467d4-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="467d4-123">dans la boîte de dialogue **Propriétés du serveur de distribution** , en ce qui concerne l'Agent de lecture de la file d'attente ;</span><span class="sxs-lookup"><span data-stu-id="467d4-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="467d4-124">dans la boîte de dialogue **Propriétés du serveur de publication** , dans le cas de l'Agent d'instantané et de l'Agent de lecture du journal.</span><span class="sxs-lookup"><span data-stu-id="467d4-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="467d4-125">**Divers**</span><span class="sxs-lookup"><span data-stu-id="467d4-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="467d4-126">Les propriétés **Type de serveur de publication** et **Nom de la base de données de distribution** sont des propriétés en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="467d4-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="467d4-127">La propriété **Dossier d'instantanés par défaut** est cependant modifiable.</span><span class="sxs-lookup"><span data-stu-id="467d4-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="467d4-128">Pour plus d’informations sur le dossier d’instantanés, consultez [Sécuriser le dossier d’instantanés](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="467d4-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="467d4-129">Bases de données de publication</span><span class="sxs-lookup"><span data-stu-id="467d4-129">Publication Databases</span></span>
  <span data-ttu-id="467d4-130">La page **Bases de données de publication** de la boîte de dialogue **Propriétés du serveur de publication** permet à un utilisateur dans le rôle serveur fixe **sysadmin** d'autoriser la réplication des bases de données.</span><span class="sxs-lookup"><span data-stu-id="467d4-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="467d4-131">L'activation d'une base de données ne publie pas la base de données ; elle permet à un utilisateur du rôle fixe de base de données **db_owner** de créer des publications dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="467d4-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="467d4-132">Options</span><span class="sxs-lookup"><span data-stu-id="467d4-132">Options</span></span>  
 <span data-ttu-id="467d4-133">**Transactionnelle**</span><span class="sxs-lookup"><span data-stu-id="467d4-133">**Transactional**</span></span>  
 <span data-ttu-id="467d4-134">Activez cette case à cocher pour permettre aux utilisateurs du rôle de base de données fixe **db_owner** de créer des publications d'instantanés ou des publications transactionnelles dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="467d4-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="467d4-135">**Fusionner**</span><span class="sxs-lookup"><span data-stu-id="467d4-135">**Merge**</span></span>  
 <span data-ttu-id="467d4-136">Activez cette case à cocher pour permettre aux utilisateurs du rôle de base de données fixe **db_owner** de créer des publications de fusion dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="467d4-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="467d4-137">Abonnés</span><span class="sxs-lookup"><span data-stu-id="467d4-137">Subscribers</span></span>

  <span data-ttu-id="467d4-138">La page **Abonnés** de la boîte de dialogue **Propriétés du serveur de publication** est utilisée pour les serveurs de publication qui exécutent les versions de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="467d4-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="467d4-139">Cette page permet d'indiquer que les abonnés peuvent recevoir des données des publications de ce serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="467d4-140">La possibilité pour un abonné de recevoir des données du serveur de publication ne crée pas d'abonnements aux publications sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="467d4-141">Pour créer un abonnement, vous devez utiliser l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="467d4-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="467d4-142">Options</span><span class="sxs-lookup"><span data-stu-id="467d4-142">Options</span></span>  
 <span data-ttu-id="467d4-143">**Abonnés**</span><span class="sxs-lookup"><span data-stu-id="467d4-143">**Subscribers**</span></span>  
 <span data-ttu-id="467d4-144">La grille de propriétés **Abonnés** indique les abonnés qui peuvent recevoir des données de publication du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="467d4-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="467d4-145">Cliquez sur le bouton des propriétés (**...**) à côté d'un abonné pour afficher et définir des propriétés supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="467d4-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="467d4-146">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="467d4-146">**Add**</span></span>  
 <span data-ttu-id="467d4-147">Cliquez sur **Ajouter** pour ajouter un abonné, puis cliquez sur **Ajout un Abonné SQL Server** ou **Ajouter un Abonné non-SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="467d4-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="467d4-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="467d4-148">See Also</span></span>  
 [<span data-ttu-id="467d4-149">Afficher et modifier les propriétés d’un serveur de distribution ou d’un serveur de publication</span><span class="sxs-lookup"><span data-stu-id="467d4-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
