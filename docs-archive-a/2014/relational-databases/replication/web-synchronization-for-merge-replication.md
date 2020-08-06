---
title: Synchronisation Web pour la réplication de fusion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613426"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="efc30-102">Synchronisation Web pour la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="efc30-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="efc30-103">La synchronisation Web pour la réplication de fusion permet de répliquer des données à l'aide du protocole HTTPS ; elle est utile dans les scénarios suivants :</span><span class="sxs-lookup"><span data-stu-id="efc30-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="efc30-104">Synchronisation de données d'utilisateurs mobiles via Internet.</span><span class="sxs-lookup"><span data-stu-id="efc30-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="efc30-105">Synchronisation de données entre bases de données [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] via un pare-feu d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="efc30-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="efc30-106">Par exemple, un représentant commercial en déplacement peut se servir de la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="efc30-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="efc30-107">L'entreprise, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], dispose de représentants commerciaux qui se déplacent dans différents magasins et chez différents fournisseurs dans toutes les régions.</span><span class="sxs-lookup"><span data-stu-id="efc30-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="efc30-108">Lors de déplacements prolongés, les représentants restent à l'hôtel et ont besoin d'un moyen pratique pour charger les chiffres des ventes et télécharger les mises à jour des produits tous les jours en fin de journée.</span><span class="sxs-lookup"><span data-stu-id="efc30-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="efc30-109">Le service informatique de [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] a configuré chaque ordinateur portable avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et activé la réplication de fusion pour utiliser la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="efc30-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="efc30-110">L'Agent de fusion de chaque ordinateur portable contient une adresse URL qui pointe vers les composants de réplication installés sur un ordinateur exécutant [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="efc30-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="efc30-111">Ces composants synchronisent l'Abonné avec le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="efc30-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="efc30-112">Chaque représentant peut désormais se connecter par le biais d'une connexion Internet disponible sans avoir recours à une connexion d'accès à distance, et peut charger et télécharger les données appropriées.</span><span class="sxs-lookup"><span data-stu-id="efc30-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="efc30-113">La connexion Internet utilise SSL (Secure Sockets Layer) ; un réseau privé virtuel (VPN) n'est donc pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="efc30-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="efc30-114">Pour obtenir des informations sur la façon de configurer les composants requis pour la synchronisation Web, consultez [configurer la synchronisation Web](configure-web-synchronization.md), [Configurer IIS pour la synchronisation Web](configure-iis-for-web-synchronization.md) et [Configurer IIS 7 pour la synchronisation Web](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="efc30-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="efc30-115">La synchronisation Web est conçue pour synchroniser des données avec des ordinateurs portables, des périphériques de poche et d'autres clients.</span><span class="sxs-lookup"><span data-stu-id="efc30-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="efc30-116">Elle n'est pas conçue pour des applications de serveur à serveur pour des volumes élevés.</span><span class="sxs-lookup"><span data-stu-id="efc30-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="efc30-117">Aperçu du fonctionnement de la synchronisation Web</span><span class="sxs-lookup"><span data-stu-id="efc30-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="efc30-118">Lorsque la synchronisation Web est utilisée, les mises à jour sur l'Abonné sont empaquetées et envoyées sous forme de message XML sur l'ordinateur exécutant IIS via le protocole HTTPS.</span><span class="sxs-lookup"><span data-stu-id="efc30-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="efc30-119">L'ordinateur exécutant IIS envoie ensuite les commandes au serveur de publication sous un format binaire, généralement à l'aide de TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="efc30-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="efc30-120">Les mises à jour sur l'Abonné sont envoyées à l'ordinateur exécutant IIS, puis empaquetées sous forme de message XML pour la remise à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="efc30-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="efc30-121">L'illustration suivante montre certains des composants concernés par la synchronisation Web pour la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="efc30-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="efc30-122">![Composants et flux de données de synchronisation web](media/web-sync01.gif "Composants et flux de données de synchronisation web")</span><span class="sxs-lookup"><span data-stu-id="efc30-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="efc30-123">La synchronisation Web est une option disponible uniquement pour les abonnements par extraction de données (pull) ; un Agent de fusion sera donc toujours exécuté sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="efc30-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="efc30-124">Il peut s'agir de l'Agent de fusion standard, du contrôle ActiveX de l'Agent de fusion, ou d'une application assurant la synchronisation par le biais de Replication Management Objects.</span><span class="sxs-lookup"><span data-stu-id="efc30-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="efc30-125">Pour spécifier l’emplacement de l’ordinateur exécutant IIS, utilisez le paramètre **-InternetUrl** pour l’agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="efc30-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="efc30-126">L'écouteur de réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (Replisapi.dll) est configuré sur l'ordinateur exécutant IIS ; il est également responsable de la gestion des messages qui sont envoyés au serveur à partir du serveur de publication et des Abonnés.</span><span class="sxs-lookup"><span data-stu-id="efc30-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="efc30-127">Chaque nœud de la topologie gère le flux de données XML par le biais du réconciliateur de réplication de fusion (Replrec.dll).</span><span class="sxs-lookup"><span data-stu-id="efc30-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="efc30-128">ou une version ultérieure est nécessaire pour tous les ordinateurs impliqués dans des opérations de synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="efc30-128">or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="efc30-129">Processus de synchronisation</span><span class="sxs-lookup"><span data-stu-id="efc30-129">Synchronization Process</span></span>
 <span data-ttu-id="efc30-130">Les étapes inhérentes au processus de synchronisation sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="efc30-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="efc30-131">L'Agent de fusion est démarré sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="efc30-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="efc30-132">L'agent réalise les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="efc30-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="efc30-133">Il établit une connexion SQL avec la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="efc30-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="efc30-134">Il extrait toutes les modifications de la base de données.</span><span class="sxs-lookup"><span data-stu-id="efc30-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="efc30-135">Il envoie une demande HTTPS à l'ordinateur exécutant IIS.</span><span class="sxs-lookup"><span data-stu-id="efc30-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="efc30-136">Il télécharge les modifications apportées aux données sous forme de message XML.</span><span class="sxs-lookup"><span data-stu-id="efc30-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="efc30-137">L'écouteur de réplication [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le réconciliateur de réplication de fusion hébergés sur l'ordinateur exécutant IIS effectuent les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="efc30-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="efc30-138">Ils répondent à la demande HTTPS.</span><span class="sxs-lookup"><span data-stu-id="efc30-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="efc30-139">Ils établissent une connexion SQL avec la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="efc30-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="efc30-140">Ils appliquent les modifications téléchargées à la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="efc30-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="efc30-141">Ils extraient les modifications téléchargées pour l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="efc30-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="efc30-142">Ils renvoient une réponse HTTPS à l'Agent de fusion.</span><span class="sxs-lookup"><span data-stu-id="efc30-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="efc30-143">L'Agent de fusion sur l'Abonné accepte ensuite la réponse HTTPS et applique les modifications téléchargées à la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="efc30-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="efc30-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efc30-144">See Also</span></span>
 <span data-ttu-id="efc30-145">[Configurer](configure-web-synchronization.md) [des topologies de synchronisation Web pour la synchronisation Web](topologies-for-web-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="efc30-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


