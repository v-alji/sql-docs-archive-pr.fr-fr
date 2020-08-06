---
title: Sécurité de l’Agent de lecture de la file d’attente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613428"
---
# <a name="queue-reader-agent-security"></a><span data-ttu-id="24ccc-102">Sécurité de l'Agent de lecture de la file d'attente</span><span class="sxs-lookup"><span data-stu-id="24ccc-102">Queue Reader Agent Security</span></span>
  <span data-ttu-id="24ccc-103">La boîte de dialogue **Sécurité de l'Agent de lecture de la file d'attente** permet de définir le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sous lequel l'Agent de lecture de la file d'attente s'exécute et établit des connexions locales avec le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="24ccc-103">The **Queue Reader Agent Security** dialog box allows you to specify the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Queue Reader Agent runs and makes local connections to the Distributor.</span></span> <span data-ttu-id="24ccc-104">L'Agent se connecte au serveur de publication en utilisant le compte défini dans la boîte de dialogue **Propriétés du serveur de publication** (accessible depuis la boîte de dialogue **Propriétés du serveur de distribution** ) ; l'Agent se connecte à l'Abonné en utilisant le même contexte que l'Agent de distribution pour l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="24ccc-104">The agent connects to the Publisher using the account specified in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box); the agent connects to the Subscriber using the same context as the Distribution Agent for the subscription.</span></span> <span data-ttu-id="24ccc-105">Pour plus d’informations, consultez [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="24ccc-105">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="24ccc-106">Le compte doit être valide avec le mot de passe correct défini.</span><span class="sxs-lookup"><span data-stu-id="24ccc-106">The account must be valid with the correct password specified.</span></span> <span data-ttu-id="24ccc-107">Les comptes et les mots de passe ne sont pas validés tant qu'un agent ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="24ccc-107">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24ccc-108">Options</span><span class="sxs-lookup"><span data-stu-id="24ccc-108">Options</span></span>  
 <span data-ttu-id="24ccc-109">**Compte de processus**</span><span class="sxs-lookup"><span data-stu-id="24ccc-109">**Process account**</span></span>  
 <span data-ttu-id="24ccc-110">Tapez un compte Windows sous lequel l'Agent de lecture de la file d'attente s'exécute sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="24ccc-110">Enter a Windows account under which the Queue Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="24ccc-111">Le compte Windows que vous spécifiez doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="24ccc-111">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="24ccc-112">**Mot de passe** et **Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="24ccc-112">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="24ccc-113">Entrez le mot de passe du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="24ccc-113">Enter the password for the Windows account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ccc-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24ccc-114">See Also</span></span>  
 <span data-ttu-id="24ccc-115">[Gérer les comptes de connexion et les mots de passe dans la réplication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="24ccc-115">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="24ccc-116">[Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="24ccc-116">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="24ccc-117">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="24ccc-117">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="24ccc-118">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="24ccc-118">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
