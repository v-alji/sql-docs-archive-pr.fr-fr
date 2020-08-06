---
title: Aide sur le Gestionnaire de configuration SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, help
ms.assetid: 6e909911-39a6-469b-b22a-3afdfd08a30b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10a6d6052fe109892f975774a1ed65b818ef0581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705776"
---
# <a name="sql-server-configuration-manager-help"></a><span data-ttu-id="b464d-102">Aide sur le Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="b464d-102">SQL Server Configuration Manager Help</span></span>
  <span data-ttu-id="b464d-103">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous permet de configurer les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la connectivité réseau.</span><span class="sxs-lookup"><span data-stu-id="b464d-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and configure network connectivity.</span></span> <span data-ttu-id="b464d-104">Pour créer ou gérer des objets de base de données, configurer la sécurité et écrire des requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] , utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b464d-104">To create or manage database objects, configure security, and write [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b464d-105">Pour plus d'informations sur [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consultez la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b464d-105">For more information about [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="b464d-106">Cette section contient les rubriques d'aide accessibles au moyen de la touche F1, relatives aux boîtes de dialogue du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b464d-106">This section contains the F1 Help topics for the dialogs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b464d-107">Le Gestionnaire de configuration ne peut pas configurer les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b464d-107">Configuration Manager cannot configure versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="services"></a><span data-ttu-id="b464d-108">Services</span><span class="sxs-lookup"><span data-stu-id="b464d-108">Services</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b464d-109">gère les services liés à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b464d-109">Configuration Manager manages services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b464d-110">Bien que beaucoup de ces tâches puissent être réalisées à l'aide de la boîte de dialogue Services [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, il est important de noter que le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] effectue des opérations supplémentaires sur les services qu'il gère, telles que l'application des autorisations adéquates lors de la modification du compte des services.</span><span class="sxs-lookup"><span data-stu-id="b464d-110">Although many of these tasks can be accomplished using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services dialog, is important to note that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager performs additional operations on the services it manages, such as applying the correct permissions when the service account is changed.</span></span> <span data-ttu-id="b464d-111">L'utilisation de la boîte de dialogue Services Windows normale pour configurer l'un des services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut provoquer un dysfonctionnement de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="b464d-111">Using the normal Windows Services dialog to configure any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services might cause the service to malfunction.</span></span>  
  
 <span data-ttu-id="b464d-112">Utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour accomplir les tâches suivantes relatives aux services :</span><span class="sxs-lookup"><span data-stu-id="b464d-112">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks for services:</span></span>  
  
-   <span data-ttu-id="b464d-113">Démarrer, arrêter et suspendre les services</span><span class="sxs-lookup"><span data-stu-id="b464d-113">Start, stop, and pause services</span></span>  
  
-   <span data-ttu-id="b464d-114">Configurer les services de manière à ce qu'ils démarrent automatiquement ou manuellement, désactiver les services ou modifier d'autres paramètres des services</span><span class="sxs-lookup"><span data-stu-id="b464d-114">Configure services to start automatically or manually, disable the services, or change other service settings</span></span>  
  
-   <span data-ttu-id="b464d-115">Modifier les mots de passe des comptes utilisés par les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b464d-115">Change the passwords for the accounts used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services</span></span>  
  
-   <span data-ttu-id="b464d-116">Démarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide d’indicateurs de trace (paramètres de ligne de commande)</span><span class="sxs-lookup"><span data-stu-id="b464d-116">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using trace flags (command line parameters)</span></span>  
  
-   <span data-ttu-id="b464d-117">Afficher les propriétés des services</span><span class="sxs-lookup"><span data-stu-id="b464d-117">View the properties of services</span></span>  
  
## <a name="sql-server-network-configuration"></a><span data-ttu-id="b464d-118">Configuration du réseau SQL Server</span><span class="sxs-lookup"><span data-stu-id="b464d-118">SQL Server Network Configuration</span></span>  
 <span data-ttu-id="b464d-119">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous permet de réaliser les tâches suivantes relatives aux services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installés sur cet ordinateur :</span><span class="sxs-lookup"><span data-stu-id="b464d-119">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services on this computer:</span></span>  
  
-   <span data-ttu-id="b464d-120">Activer ou désactiver un protocole réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b464d-120">Enable or disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
-   <span data-ttu-id="b464d-121">Configurer un protocole réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b464d-121">Configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b464d-122">Pour vous procurer un didacticiel sommaire sur la manière de configurer les protocoles et de se connecter au [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], consultez [Didacticiel : Mise en route du moteur de base de données](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="b464d-122">For a short tutorial about how to configure protocols and connect to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], see [Tutorial: Getting Started with the Database Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span></span>  
  
## <a name="sql-server-native-client-configuration"></a><span data-ttu-id="b464d-123">Configuration de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="b464d-123">SQL Server Native Client Configuration</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b464d-124">se connectent à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide de la bibliothèque réseau [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="b464d-124">clients connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client network library.</span></span> <span data-ttu-id="b464d-125">Le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous permet de réaliser les tâches suivantes relatives aux applications clientes installées sur cet ordinateur :</span><span class="sxs-lookup"><span data-stu-id="b464d-125">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to client applications on this computer:</span></span>  
  
-   <span data-ttu-id="b464d-126">Pour les applications clientes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installées sur cet ordinateur, spécifier l'ordre des protocoles lors de la connexion à des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b464d-126">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications on this computer, specify the protocol order, when connecting to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b464d-127">Configurer les protocoles de connexion clients</span><span class="sxs-lookup"><span data-stu-id="b464d-127">Configure client connection protocols.</span></span>  
  
-   <span data-ttu-id="b464d-128">Pour les applications clientes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , créer des alias pour les instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]afin que les clients puissent se connecter à l'aide d'une chaîne de connexion personnalisée</span><span class="sxs-lookup"><span data-stu-id="b464d-128">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications, create aliases for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so that clients can connect using a custom connection string.</span></span>  
  
 <span data-ttu-id="b464d-129">Pour plus d'informations sur chacune de ces tâches, consultez la rubrique d'aide correspondante accessible à l'aide de la touche F1.</span><span class="sxs-lookup"><span data-stu-id="b464d-129">For more information about each of these tasks, see F1 help for each task.</span></span>  
  
#### <a name="to-open-sql-server-configuration-manager"></a><span data-ttu-id="b464d-130">Pour ouvrir le Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="b464d-130">To open SQL Server Configuration Manager</span></span>  
  
-   <span data-ttu-id="b464d-131">Dans le menu **Démarrer** , pointez successivement sur **Tous les programmes**, sur **Microsoft SQL Server** (version), sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b464d-131">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server** (version), point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b464d-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b464d-132">See Also</span></span>  
 <span data-ttu-id="b464d-133">[Services SQL Server](../../../2014/tools/configuration-manager/sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="b464d-133">[SQL Server Services](../../../2014/tools/configuration-manager/sql-server-services.md) </span></span>  
 <span data-ttu-id="b464d-134">[Configuration réseau SQL Server](sql-server-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b464d-134">[SQL Server Network Configuration](sql-server-network-configuration.md) </span></span>  
 <span data-ttu-id="b464d-135">[Configuration de SQL Native Client 11,0](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b464d-135">[SQL Native Client 11.0 Configuration](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span></span>  
 [<span data-ttu-id="b464d-136">Choix d'un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="b464d-136">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
