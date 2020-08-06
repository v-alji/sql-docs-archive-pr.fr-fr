---
title: Sécurité de l’Agent de distribution (réplication d’égal à égal) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601375"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a><span data-ttu-id="4dd3e-102">Sécurité de l'Agent de distribution (réplication d'égal à égal)</span><span class="sxs-lookup"><span data-stu-id="4dd3e-102">Distribution Agent Security (Peer-to-Peer Replication)</span></span>
  <span data-ttu-id="4dd3e-103">La page **Sécurité de l'Agent de distribution** permet de spécifier les comptes sous lesquels l'Agent de distribution s'exécute et établit les connexions avec les ordinateurs dans une topologie d'égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-103">The **Distribution Agent Security** page allows you to specify the accounts under which the Distribution Agent runs and makes connections to the computers in a peer-to-peer topology.</span></span> <span data-ttu-id="4dd3e-104">Pour plus d’informations sur les autorisations exigées par les agents et les bonnes pratiques en matière de sécurité de la réplication, consultez [Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md) et [Bonnes pratiques en matière de sécurité de la réplication](security/replication-security-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="4dd3e-104">For information on permissions required by agents and best practices for replication security, see [Replication Agent Security Model](security/replication-agent-security-model.md) and [Replication Security Best Practices](security/replication-security-best-practices.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4dd3e-105">Si l'Agent de distribution d'un abonnement a déjà été configuré lors d'une précédente exécution de cet Assistant, vous ne pouvez pas modifier les informations d'identification qu'il utilise dans cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-105">If the Distribution Agent for a subscription has already been configured in a previous run of this wizard, you cannot change the credentials it uses in this wizard.</span></span> <span data-ttu-id="4dd3e-106">Si vous spécifiez de nouvelles informations d'identification, elles sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-106">If you specify new credentials, they are ignored.</span></span> <span data-ttu-id="4dd3e-107">Pour modifier ces informations, utilisez la boîte de dialogue **Propriétés de l'abonnement** .</span><span class="sxs-lookup"><span data-stu-id="4dd3e-107">To change credentials, use the **Subscription Properties** dialog box.</span></span> <span data-ttu-id="4dd3e-108">Pour plus d’informations, consultez [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4dd3e-108">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4dd3e-109">Options</span><span class="sxs-lookup"><span data-stu-id="4dd3e-109">Options</span></span>  
 <span data-ttu-id="4dd3e-110">Cliquez sur le bouton de propriétés ( **...** ) dans la ligne de chaque Abonné pour accéder à la boîte de dialogue **Sécurité de l'Agent de distribution** .</span><span class="sxs-lookup"><span data-stu-id="4dd3e-110">Click the properties button (**...**) in the row for each Subscriber to access the **Distribution Agent Security** dialog box.</span></span> <span data-ttu-id="4dd3e-111">Cliquez sur **Aide** dans la boîte de dialogue **Sécurité de l'Agent de distribution** qui s'affiche pour obtenir plus d'informations sur les autorisations indispensables pour les comptes utilisés par les agents.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-111">Click **Help** on the **Distribution Agent Security** dialog box that is launched for more information on the permissions required for accounts used by the agents.</span></span>  
  
 <span data-ttu-id="4dd3e-112">Après avoir entré les paramètres dans l'une des boîtes de dialogue, les informations de connexion de l'Abonné s'affichent dans la grille.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-112">After settings have been entered in one of the dialog boxes, connection information for the Subscriber is displayed in the grid.</span></span>  
  
 <span data-ttu-id="4dd3e-113">**Agent de l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="4dd3e-113">**Agent for Subscriber**</span></span>  
 <span data-ttu-id="4dd3e-114">Nom de chaque homologue.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-114">The name of each peer.</span></span>  
  
 <span data-ttu-id="4dd3e-115">**Base de données d'homologues**</span><span class="sxs-lookup"><span data-stu-id="4dd3e-115">**Peer Database**</span></span>  
 <span data-ttu-id="4dd3e-116">Base de données de l'homologue utilisée à la fois comme base de données de publication et d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-116">The database at the peer that will serve as both a publication database and subscription database.</span></span>  
  
 <span data-ttu-id="4dd3e-117">**Connexion au serveur de distribution**</span><span class="sxs-lookup"><span data-stu-id="4dd3e-117">**Connection to Distributor**</span></span>  
 <span data-ttu-id="4dd3e-118">Le contexte dans lequel la connexion au serveur de distribution s'établit.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-118">The context under which the connection to the Distributor is made.</span></span> <span data-ttu-id="4dd3e-119">Les connexions locales sont toujours établies en utilisant le contexte du compte Windows dans lequel s'exécute l'agent.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-119">Local connections are always made using the context of the Windows account under which the agent runs.</span></span> <span data-ttu-id="4dd3e-120">Cet Assistant crée les abonnements par envoi (la connexion locale est celle du serveur de distribution). Ce champ affiche donc toujours : **Emprunter l’identité « \<Domain>\\<Connexion\> »** ou **Emprunter l’identité « \<Computer>\\<Connexion\> »** .</span><span class="sxs-lookup"><span data-stu-id="4dd3e-120">This wizard creates push subscriptions (the local connection is the connection to the Distributor), so this field will always display: **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span>  
  
 <span data-ttu-id="4dd3e-121">**Connexion à l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="4dd3e-121">**Connection to Subscriber**</span></span>  
 <span data-ttu-id="4dd3e-122">Le contexte dans lequel la connexion à l'abonné s'établit.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-122">The context under which the connection to the Subscriber is made.</span></span> <span data-ttu-id="4dd3e-123">Il est possible d'établir la connexion en utilisant le contexte du compte Windows sous lequel s'exécute l'agent ou le contexte d'une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4dd3e-123">The connection can be made using the context of the Windows account under which the agent runs or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="4dd3e-124">Le champ affiche l’un des éléments suivants : **Utiliser la connexion « \<Login> »** , **Emprunter l’identité « \<Domain>\\<Connexion\> »** ou **Emprunter l’identité « \<Computer>\\<Connexion\> »** .</span><span class="sxs-lookup"><span data-stu-id="4dd3e-124">The field displays one of the following: **Use login '\<Login>'**, **Impersonate '\<Domain>\\<Login\>'** or **Impersonate '\<Computer>\\<Login\>'**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4dd3e-125">recommande d'établir toutes les connexions dans le contexte du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="4dd3e-125">recommends that all connections be made using the context of the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd3e-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dd3e-126">See Also</span></span>  
 <span data-ttu-id="4dd3e-127">[Administrer une topologie d’égal à égal &#40;programmation Transact-SQL de la réplication&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span><span class="sxs-lookup"><span data-stu-id="4dd3e-127">[Administer a Peer-to-Peer Topology &#40;Replication Transact-SQL Programming&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md) </span></span>  
 [<span data-ttu-id="4dd3e-128">Peer-to-Peer Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="4dd3e-128">Peer-to-Peer Transactional Replication</span></span>](transactional/peer-to-peer-transactional-replication.md)  
  
  
