---
title: Connexion des abonnements pouvant être mis à jour | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707367"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="212d8-102">Nom de connexion pour les abonnements pouvant être mis à jour</span><span class="sxs-lookup"><span data-stu-id="212d8-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="212d8-103">Si vous avez sélectionné **répliquer** dans la page **abonnements pouvant être mis à jour** de cet Assistant, vous devez spécifier un compte sur l’abonné sous lequel les connexions au serveur de publication sont effectuées pour les abonnements avec mise à jour immédiate.</span><span class="sxs-lookup"><span data-stu-id="212d8-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="212d8-104">Les connexions sont utilisées par les déclencheurs qui s'exécutent pour l'abonné et propagent les modifications sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="212d8-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="212d8-105">Ce compte est requis même si vous avez sélectionné **modifier la file d’attente et valider dès que possible** dans la page **abonnements pouvant être mis** à jour, car par défaut, l’Assistant nouvel abonnement configure la mise à jour en attente avec la possibilité de basculer vers la mise à jour immédiate, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="212d8-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="212d8-106">Le compte spécifié pour la connexion doit uniquement avoir l'autorisation d'insérer, de mettre à jour et de supprimer des données sur les vues créées par la réplication dans la base de données de publication. Il ne doit pas bénéficier d'autres autorisations.</span><span class="sxs-lookup"><span data-stu-id="212d8-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="212d8-107">Octroyez des autorisations sur les vues de la base de données de publication qui sont mentionnées dans le panneau **syncobj_** _\<HexadecimalNumber>_ pour le compte que vous avez configuré pour chaque abonné.</span><span class="sxs-lookup"><span data-stu-id="212d8-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="212d8-108">Trois options sont possibles pour le type de connexion :</span><span class="sxs-lookup"><span data-stu-id="212d8-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="212d8-109">Un serveur lié ou distant que vous avez déjà défini.</span><span class="sxs-lookup"><span data-stu-id="212d8-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="212d8-110">Un serveur lié créé par la réplication. La connexion se fait à l'aide des informations d'identification spécifiées dans cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="212d8-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="212d8-111">Un serveur lié créé par la réplication. La connexion se fait à l'aide des informations d'identification de l'utilisateur qui apporte la modification pour l'abonné.</span><span class="sxs-lookup"><span data-stu-id="212d8-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="212d8-112">Vous pouvez spécifier les deux premières options dans cet Assistant.</span><span class="sxs-lookup"><span data-stu-id="212d8-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="212d8-113">La dernière option peut uniquement être spécifiée à l’aide de [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); Spécifiez la valeur **1** pour le paramètre **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="212d8-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="212d8-114">Options</span><span class="sxs-lookup"><span data-stu-id="212d8-114">Options</span></span>  
 <span data-ttu-id="212d8-115">**Créer un serveur lié qui se connecte par une connexion d'authentification SQL Server :**</span><span class="sxs-lookup"><span data-stu-id="212d8-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="212d8-116">La réplication crée un serveur lié au moyen des informations d'identification spécifiées dans les champs **Connexion** et **Mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="212d8-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="212d8-117">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="212d8-117">**Login**</span></span>  
 <span data-ttu-id="212d8-118">Entrez un nom de connexion [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui bénéficie uniquement des autorisations décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="212d8-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="212d8-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="212d8-119">**Password**</span></span>  
 <span data-ttu-id="212d8-120">Entrez un mot de passe fort pour la **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="212d8-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="212d8-121">**Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="212d8-121">**Confirm Password**</span></span>  
 <span data-ttu-id="212d8-122">Entrez une nouvelle fois le mot de passe afin de confirmer qu'il a été saisi correctement.</span><span class="sxs-lookup"><span data-stu-id="212d8-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="212d8-123">**Utiliser un serveur lié ou un serveur distant que vous avez déjà défini.**</span><span class="sxs-lookup"><span data-stu-id="212d8-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="212d8-124">Cette option nécessite un serveur lié ou distant déjà défini.</span><span class="sxs-lookup"><span data-stu-id="212d8-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="212d8-125">Pour plus d’informations, consultez [Serveurs liés &#40;moteur de base de données&#41;](../linked-servers/linked-servers-database-engine.md) et [Serveurs distants](../../database-engine/configure-windows/remote-servers.md).</span><span class="sxs-lookup"><span data-stu-id="212d8-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="212d8-126">Assurez-vous que la connexion utilisée pour le serveur lié ou distant est associée un mot de passe fort et possède uniquement les autorisations décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="212d8-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="212d8-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="212d8-127">See Also</span></span>  
 <span data-ttu-id="212d8-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="212d8-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="212d8-129">[Afficher et modifier les paramètres de sécurité de la réplication](security/view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="212d8-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="212d8-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="212d8-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="212d8-131">S'abonner à des publications</span><span class="sxs-lookup"><span data-stu-id="212d8-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
