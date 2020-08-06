---
title: Sécurité de l’Agent de lecture du journal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.LRA.f1
helpviewer_keywords:
- Log Reader Agent Security dialog box
ms.assetid: d6981e74-ddb8-41b8-9ea1-56c2ece63b8a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4be41aa9135e20a334616b9cb9d76a773f8d0e9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707371"
---
# <a name="log-reader-agent-security"></a><span data-ttu-id="4fa28-102">Sécurité de l'Agent de lecture du journal</span><span class="sxs-lookup"><span data-stu-id="4fa28-102">Log Reader Agent Security</span></span>
  <span data-ttu-id="4fa28-103">La boîte de dialogue **Sécurité de l'Agent de lecture du journal** permet de spécifier :</span><span class="sxs-lookup"><span data-stu-id="4fa28-103">The **Log Reader Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="4fa28-104">Le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sous lequel l'Agent de lecture du journal s'exécute dans le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="4fa28-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="4fa28-105">Ce compte Windows est également baptisé *compte de processus*du fait que le processus agent s'exécute sous ce compte.</span><span class="sxs-lookup"><span data-stu-id="4fa28-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="4fa28-106">Le contexte dans lequel l’Agent de lecture du journal établit les connexions avec le serveur de publication [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fa28-106">The context under which the Log Reader Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="4fa28-107">La connexion peut avoir lieu en empruntant l'identité du compte Windows ou dans le contexte d'un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="4fa28-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4fa28-108">L'Agent de lecture du journal établit des connexions avec le serveur de publication même si celui-ci et le serveur de publication se trouvent sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="4fa28-108">The Log Reader Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="4fa28-109">L'Agent de lecture du journal établit également des connexions avec le serveur de distribution ; ces connexions ont toujours lieu en empruntant l'identité du compte Windows sous lequel s'exécute l'agent.</span><span class="sxs-lookup"><span data-stu-id="4fa28-109">The Log Reader Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="4fa28-110">Pour les serveurs de publication Oracle, spécifiez le contexte dans lequel l'Agent de lecture du journal se connecte au serveur de publication dans la boîte de dialogue **Propriétés du serveur de publication** (disponible à partir de la boîte de dialogue **Propriétés du serveur de distribution** ).</span><span class="sxs-lookup"><span data-stu-id="4fa28-110">For Oracle Publishers, specify the context under which the Log Reader Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="4fa28-111">Pour plus d’informations, consultez [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4fa28-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="4fa28-112">Tous les comptes doivent être valides, le mot de passe correct étant spécifié pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="4fa28-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="4fa28-113">Les comptes et les mots de passe ne sont pas validés tant qu'un agent ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="4fa28-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4fa28-114">Options</span><span class="sxs-lookup"><span data-stu-id="4fa28-114">Options</span></span>  
 <span data-ttu-id="4fa28-115">**Compte de processus**</span><span class="sxs-lookup"><span data-stu-id="4fa28-115">**Process account**</span></span>  
 <span data-ttu-id="4fa28-116">Entrez le compte Windows sous lequel l'Agent de lecture du journal s'exécute dans le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="4fa28-116">Enter a Windows account under which the Log Reader Agent runs at the Distributor.</span></span> <span data-ttu-id="4fa28-117">Le compte Windows que vous spécifiez doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de distribution.</span><span class="sxs-lookup"><span data-stu-id="4fa28-117">The Windows account you specify must at minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
 <span data-ttu-id="4fa28-118">**Mot de passe** et **Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="4fa28-118">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="4fa28-119">Entrez le mot de passe du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="4fa28-119">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="4fa28-120">**Connexion au serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="4fa28-120">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="4fa28-121">Sélectionnez si l'Agent de lecture du journal doit établir les connexions au serveur de publication en empruntant l'identité du compte spécifié dans la zone de texte **Compte de processus** ou en utilisant un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fa28-121">Select whether the Log Reader Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="4fa28-122">Si vous choisissez d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , entrez un nom de connexion et un mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fa28-122">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="4fa28-123">recommande de choisir d'emprunter l'identité du compte Windows plutôt que d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4fa28-123">recommends that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="4fa28-124">Le compte Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisé pour la connexion doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="4fa28-124">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa28-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fa28-125">See Also</span></span>  
 <span data-ttu-id="4fa28-126">[Gérer les comptes de connexion et les mots de passe dans la réplication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="4fa28-126">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="4fa28-127">[Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="4fa28-127">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="4fa28-128">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="4fa28-128">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="4fa28-129">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="4fa28-129">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
