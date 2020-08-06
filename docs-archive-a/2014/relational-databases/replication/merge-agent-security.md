---
title: Sécurité de l’agent de fusion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.MA.f1
helpviewer_keywords:
- Merge Agent Security dialog box
ms.assetid: 9b86171a-4381-4b39-869a-cdc161e7cd15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ecbb044ca87ccfc74c5cb39a016667d15cf7a859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702847"
---
# <a name="merge-agent-security"></a><span data-ttu-id="b6aee-102">Sécurité de l'agent de fusion</span><span class="sxs-lookup"><span data-stu-id="b6aee-102">Merge Agent Security</span></span>
  <span data-ttu-id="b6aee-103">La boîte de dialogue **Sécurité de l'agent de fusion** vous permet de spécifier le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sous lequel l'Agent de fusion doit s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="b6aee-103">The **Merge Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Merge Agent runs.</span></span> <span data-ttu-id="b6aee-104">L'Agent de fusion s'exécute sur le serveur de distribution pour les abonnements envoyés et sur l'Abonné pour les abonnements extraits.</span><span class="sxs-lookup"><span data-stu-id="b6aee-104">The Merge Agent runs at the Distributor for push subscriptions and at the Subscriber for pull subscriptions.</span></span> <span data-ttu-id="b6aee-105">Ce compte Windows est également baptisé *compte de processus*du fait que le processus agent s'exécute sous ce compte.</span><span class="sxs-lookup"><span data-stu-id="b6aee-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span> <span data-ttu-id="b6aee-106">La boîte de dialogue propose des options supplémentaires en fonction de la façon d'y accéder :</span><span class="sxs-lookup"><span data-stu-id="b6aee-106">Additional options available in the dialog box depend on how you access it:</span></span>  
  
-   <span data-ttu-id="b6aee-107">Si la boîte de dialogue est ouverte à partir de l'Assistant Nouvel abonnement, elle vous propose ainsi en plus d'indiquer le contexte dans lequel l'agent de fusion établit les connexions avec l'Abonné (dans le cas d'abonnements envoyés au serveur) ou avec le serveur de publication et le serveur de distribution (dans le cas d'abonnements extraits du serveur).</span><span class="sxs-lookup"><span data-stu-id="b6aee-107">If the dialog box is accessed from the New Subscription Wizard, it also allows you to specify the context under which the Merge Agent makes connections to the Subscriber (for push subscriptions) or the Publisher and Distributor (for pull subscriptions).</span></span> <span data-ttu-id="b6aee-108">La connexion peut s’établir via un compte Windows ou un compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="b6aee-108">The connection can be made using the Windows account or under the context of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
-   <span data-ttu-id="b6aee-109">Si la boîte de dialogue est ouverte à partir de celle intitulée **Propriétés de l'abonnement** , vous devez indiquer le contexte dans lequel l'agent de fusion établit les connexions en cliquant sur le bouton des propriétés ( **...** ) de la ligne **Connexion de l'Abonné** ou **Connexion du serveur de publication** .</span><span class="sxs-lookup"><span data-stu-id="b6aee-109">If the dialog box is accessed from the **Subscription Properties** dialog box, specify the context under which the Merge Agent makes connections by clicking the properties button (**...**) in the **Subscriber Connection** or **Publisher Connection** row of that dialog box.</span></span> <span data-ttu-id="b6aee-110">Pour plus d’informations sur l’accès à la boîte de dialogue **Propriétés de l’abonnement**, consultez [Afficher et modifier les propriétés d’un abonnement par émission de données](view-and-modify-push-subscription-properties.md) et la procédure indiquant comment [Afficher et modifier les propriétés d’un abonnement par extraction](view-and-modify-pull-subscription-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b6aee-110">For more information about accessing the **Subscription Properties** dialog box, see [View and Modify Push Subscription Properties](view-and-modify-push-subscription-properties.md) and how to: [View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md).</span></span>  
  
 <span data-ttu-id="b6aee-111">Tous les comptes doivent être valides, le mot de passe correct étant spécifié pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="b6aee-111">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="b6aee-112">Les comptes et les mots de passe ne sont pas validés tant qu'un agent ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="b6aee-112">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b6aee-113">Options</span><span class="sxs-lookup"><span data-stu-id="b6aee-113">Options</span></span>  
 <span data-ttu-id="b6aee-114">**Process Account**</span><span class="sxs-lookup"><span data-stu-id="b6aee-114">**Process Account**</span></span>  
 <span data-ttu-id="b6aee-115">Permet de saisir un compte sous lequel l'agent de fusion peut s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="b6aee-115">Enter a Windows account under which the Merge Agent runs.</span></span>  
  
-   <span data-ttu-id="b6aee-116">Pour les abonnements par envoi de données, le compte doit :</span><span class="sxs-lookup"><span data-stu-id="b6aee-116">For push subscriptions, the account must:</span></span>  
  
    -   <span data-ttu-id="b6aee-117">être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de distribution ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-117">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
    -   <span data-ttu-id="b6aee-118">être membre de la liste d'accès à la publication (PAL) ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-118">Be a member of the PAL.</span></span>  
  
    -   <span data-ttu-id="b6aee-119">un compte de session associé à un utilisateur enregistré dans la base de données de publication ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-119">Be a login associated with a user in the publication database.</span></span>  
  
    -   <span data-ttu-id="b6aee-120">avoir les autorisations de lecture sur le partage des fichiers d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="b6aee-120">Have read permissions on the snapshot share.</span></span>  
  
-   <span data-ttu-id="b6aee-121">Pour les abonnements par extraction, le compte doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="b6aee-121">For pull subscriptions, the account must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
 <span data-ttu-id="b6aee-122">Des autorisations supplémentaires sont indispensables si l'identité du compte de processus est empruntée lorsque les connexions sont établies.</span><span class="sxs-lookup"><span data-stu-id="b6aee-122">Additional permissions are required if the process account is impersonated when connections are made.</span></span> <span data-ttu-id="b6aee-123">Voir les sections **Connexion au serveur de publication et au serveur de distribution** et **Connexion à l'Abonné** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b6aee-123">See the **Connect to the Publisher and Distributor** and **Connect to the Subscriber** sections below.</span></span>  
  
 <span data-ttu-id="b6aee-124">Le **compte de processus** ne peut pas être indiqué à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] pour des abonnements par extraction, car l’Agent de fusion ne s’exécute pas sur des instances de [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6aee-124">**Process Account** cannot be specified for pull subscriptions to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], because the Merge Agent does not run on instances of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span>  
  
 <span data-ttu-id="b6aee-125">**Mot de passe** et **Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b6aee-125">**Password** and **Confirm Password**</span></span>  
 <span data-ttu-id="b6aee-126">Entrez le mot de passe du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="b6aee-126">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="b6aee-127">**Connexion au serveur de publication et au serveur de distribution**</span><span class="sxs-lookup"><span data-stu-id="b6aee-127">**Connect to the Publisher and Distributor**</span></span>  
 <span data-ttu-id="b6aee-128">Dans le cas d'abonnements envoyés, les connexions au serveur de publication et au serveur de distribution s'établissent toujours en empruntant l'identité du compte indiqué dans la zone de texte **Compte de processus** .</span><span class="sxs-lookup"><span data-stu-id="b6aee-128">For push subscriptions, connections to the Publisher and Distributor are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b6aee-129">Dans le cas d'abonnements extraits, indiquez si vous voulez que l'agent de fusion établisse les connexions au serveur de publication et au serveur de distribution en empruntant l'identité du compte précisé dans la zone de texte **Compte de processus** ou en utilisant un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-129">For pull subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b6aee-130">Si vous choisissez d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , entrez un nom de connexion et un mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-130">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="b6aee-131">recommande de choisir d'emprunter l'identité du compte Windows plutôt que d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-131">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b6aee-132">Le compte Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisé pour la connexion doit :</span><span class="sxs-lookup"><span data-stu-id="b6aee-132">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must:</span></span>  
  
-   <span data-ttu-id="b6aee-133">être membre de la liste d'accès à la publication (PAL) ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-133">Be a member of the PAL.</span></span>  
  
-   <span data-ttu-id="b6aee-134">un compte de session associé à un utilisateur enregistré dans la base de données de publication ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-134">Be a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="b6aee-135">un compte de session associé à un utilisateur enregistré dans la base de données de distribution (bien que l'utilisateur puisse aussi ouvrir sa session en tant qu'Invité) ;</span><span class="sxs-lookup"><span data-stu-id="b6aee-135">Be a login associated with a user in the distribution database (the user can be the Guest user).</span></span>  
  
-   <span data-ttu-id="b6aee-136">avoir les autorisations de lecture sur le partage des fichiers d'instantanés.</span><span class="sxs-lookup"><span data-stu-id="b6aee-136">Have read permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="b6aee-137">**Connexion à l'Abonné**</span><span class="sxs-lookup"><span data-stu-id="b6aee-137">**Connect to the Subscriber**</span></span>  
 <span data-ttu-id="b6aee-138">Pour les abonnements par extraction, les connexions à l'Abonné ont toujours lieu en empruntant l'identité du compte spécifié dans la zone de texte **Compte de processus** .</span><span class="sxs-lookup"><span data-stu-id="b6aee-138">For pull subscriptions, connections to the Subscriber are always made by impersonating the account specified in the **Process account** text box.</span></span>  
  
 <span data-ttu-id="b6aee-139">Dans le cas d'abonnements envoyés, indiquez si vous voulez que l'agent de fusion établisse les connexions au serveur de publication et au serveur de distribution en empruntant l'identité du compte précisé dans la zone de texte **Compte de processus** ou en utilisant un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-139">For push subscriptions, select whether the Merge Agent should make connections to the Publisher and Distributor by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b6aee-140">Si vous choisissez d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , entrez un nom de connexion et un mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-140">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6aee-141">Il est recommandé de choisir d'emprunter l'identité du compte Windows plutôt que d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6aee-141">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b6aee-142">Le compte Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisé pour la connexion avec l'abonné doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="b6aee-142">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection to the Subscriber must at minimum be a member of the **db_owner** fixed database role in the subscription database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6aee-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b6aee-143">See Also</span></span>  
 <span data-ttu-id="b6aee-144">[Gérer les comptes de connexion et les mots de passe dans la réplication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="b6aee-144">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="b6aee-145">[Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="b6aee-145">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="b6aee-146">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b6aee-146">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 <span data-ttu-id="b6aee-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="b6aee-147">[Replication Security Best Practices](security/replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="b6aee-148">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="b6aee-148">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
