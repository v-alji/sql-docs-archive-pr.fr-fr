---
title: 'Leçon 3 : Configuration de la distribution | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707376"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="c01ea-102">Leçon 3 : Configuration de la distribution</span><span class="sxs-lookup"><span data-stu-id="c01ea-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="c01ea-103">Dans cette leçon, vous allez configurer la distribution sur le serveur de publication et définir les autorisations requises sur les bases de données de publication et de distribution.</span><span class="sxs-lookup"><span data-stu-id="c01ea-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="c01ea-104">Si vous avez déjà configuré le serveur de distribution, vous devez d'abord désactiver la publication et la distribution avant de commencer cette leçon.</span><span class="sxs-lookup"><span data-stu-id="c01ea-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="c01ea-105">Ne procédez pas ainsi si vous devez conserver une topologie de réplication existante.</span><span class="sxs-lookup"><span data-stu-id="c01ea-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="c01ea-106">La configuration d'un serveur de publication avec un serveur de distribution distant dépasse le cadre de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="c01ea-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="c01ea-107">Configuration de la distribution sur le serveur de publication</span><span class="sxs-lookup"><span data-stu-id="c01ea-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="c01ea-108">Connectez-vous au serveur de publication dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="c01ea-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="c01ea-109">Cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Configurer la distribution**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c01ea-110">Si vous êtes connecté à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de **localhost** au lieu du nom du serveur réel, un avertissement vous indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne peut pas se connecter au serveur **'localhost'**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="c01ea-111">Cliquez sur **OK** dans la boîte de dialogue d’avertissement.</span><span class="sxs-lookup"><span data-stu-id="c01ea-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="c01ea-112">Dans la boîte de dialogue **Se connecter au serveur** , remplacez le **Nom du serveur** , qui indique **localhost** , par le nom de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="c01ea-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="c01ea-113">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="c01ea-114">L'Assistant Configuration de la distribution démarre.</span><span class="sxs-lookup"><span data-stu-id="c01ea-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="c01ea-115">Sur la page serveur de **distribution** , sélectionnez **«** _\<ServerName>_ **» agit comme son propre serveur de distribution ; SQL Server créera une base de données de distribution et un journal**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c01ea-116">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne s’exécute pas, dans la page de démarrage de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent**, sélectionnez **Oui**, configurez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pour qu’il démarre automatiquement.</span><span class="sxs-lookup"><span data-stu-id="c01ea-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="c01ea-117">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="c01ea-118">Entrez **\\\\** \<_Machine_Name> _**\repldata** dans la zone de texte **dossier d’instantanés** , où \<*Machine_Name> \* est le nom du serveur de publication, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="c01ea-119">Acceptez les valeurs par défaut sur les pages restantes de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c01ea-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="c01ea-120">Cliquez sur **Terminer** pour activer la distribution.</span><span class="sxs-lookup"><span data-stu-id="c01ea-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="c01ea-121">Définition des autorisations de base de données sur le serveur de publication</span><span class="sxs-lookup"><span data-stu-id="c01ea-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="c01ea-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , développez **sécurité**, cliquez avec le bouton droit sur **connexions**, puis sélectionnez **nouvelle connexion**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="c01ea-123">Sur la page **général** , cliquez sur **Rechercher**, entrez \<_Machine_Name> _**\ repl_snapshot** dans la zone **Entrez le nom de l’objet à sélectionner** , où \<*Machine_Name> \* est le nom du serveur de publication local, cliquez sur vérifier les **noms**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c01ea-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c01ea-124">Dans la page mappage de l' **utilisateur** , dans la liste **utilisateurs mappés à cette connexion** , sélectionnez la **distribution** et les [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] bases de données.</span><span class="sxs-lookup"><span data-stu-id="c01ea-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="c01ea-125">Dans la liste **appartenance au rôle de base de données** , sélectionnez le `db_owner` rôle de connexion pour les deux bases de données.</span><span class="sxs-lookup"><span data-stu-id="c01ea-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="c01ea-126">Cliquez sur **OK** pour créer la connexion.</span><span class="sxs-lookup"><span data-stu-id="c01ea-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="c01ea-127">Répétez les étapes 1 à 4 pour créer une connexion pour le compte local repl_logreader.</span><span class="sxs-lookup"><span data-stu-id="c01ea-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="c01ea-128">Cette connexion doit également être mappée aux utilisateurs membres du `db_owner` rôle de base de données fixe dans les bases de données de **distribution** et **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="c01ea-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="c01ea-129">Répétez les étapes 1 à 4 pour créer une connexion pour le compte local repl_distribution.</span><span class="sxs-lookup"><span data-stu-id="c01ea-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="c01ea-130">Cette connexion doit être mappée à un utilisateur membre du `db_owner` rôle de base de données fixe dans la base de données de **distribution** .</span><span class="sxs-lookup"><span data-stu-id="c01ea-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="c01ea-131">Répétez les étapes 1 à 4 pour créer une connexion pour le compte local repl_merge.</span><span class="sxs-lookup"><span data-stu-id="c01ea-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="c01ea-132">Cette connexion doit avoir les mappages d'utilisateur des bases de données de **distribution** et **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="c01ea-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c01ea-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c01ea-133">See Also</span></span>  
 <span data-ttu-id="c01ea-134">[Configurer la distribution](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c01ea-134">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="c01ea-135">Modèle de sécurité de l’Agent de réplication</span><span class="sxs-lookup"><span data-stu-id="c01ea-135">Replication Agent Security Model</span></span>](security/replication-agent-security-model.md)  
  
  
