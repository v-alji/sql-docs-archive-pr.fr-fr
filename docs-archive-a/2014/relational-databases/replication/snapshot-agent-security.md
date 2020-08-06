---
title: Sécurité de l’Agent d’instantané | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.SSA.f1
helpviewer_keywords:
- Snapshot Agent Security dialog box
ms.assetid: 64e84c67-acc6-4906-98d4-3451767363fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 288dc294b7ace9ea5cb098c8deec53c3ae4569a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614497"
---
# <a name="snapshot-agent-security"></a><span data-ttu-id="b8039-102">Sécurité de l'Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="b8039-102">Snapshot Agent Security</span></span>
  <span data-ttu-id="b8039-103">La boîte de dialogue **Sécurité de l'Agent d'instantané** permet de définir :</span><span class="sxs-lookup"><span data-stu-id="b8039-103">The **Snapshot Agent Security** dialog box allows you to specify:</span></span>  
  
-   <span data-ttu-id="b8039-104">Le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows sous lequel l'Agent d'instantané s'exécute le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="b8039-104">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="b8039-105">Ce compte Windows est également baptisé *compte de processus*du fait que le processus agent s'exécute sous ce compte.</span><span class="sxs-lookup"><span data-stu-id="b8039-105">The Windows account is also referred to as the *process account*, because the agent process runs under this account.</span></span>  
  
-   <span data-ttu-id="b8039-106">Le contexte sous lequel l’Agent d’instantané établit des connexions au serveur de publication [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8039-106">The context under which the Snapshot Agent makes connections to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher.</span></span> <span data-ttu-id="b8039-107">La connexion peut avoir lieu en empruntant l'identité du compte Windows ou dans le contexte d'un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="b8039-107">The connection can be made by impersonating the Windows account or under the context of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account you specify.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8039-108">L'Agent d'instantané établit des connexions au serveur de publication, même si le serveur de publication et le serveur de distribution se trouvent sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b8039-108">The Snapshot Agent makes connections to the Publisher even if the Publisher and Distributor are on the same computer.</span></span> <span data-ttu-id="b8039-109">L'Agent d'instantané établit également des connexions au serveur de distribution ; ces connexions sont toujours établies en imitant le compte Windows sous lequel l'Agent s'exécute.</span><span class="sxs-lookup"><span data-stu-id="b8039-109">The Snapshot Agent also makes connections to the Distributor; these connections are always made by impersonating the Windows account under which the agent runs.</span></span>  
  
     <span data-ttu-id="b8039-110">Pour les serveurs de publication Oracle, définissez le contexte sous lequel l'Agent d'instantané se connecte au serveur de publication dans la boîte **Propriétés du serveur de publication** (accessible depuis la boîte de dialogue **Propriété du serveur de distribution** ).</span><span class="sxs-lookup"><span data-stu-id="b8039-110">For Oracle Publishers, specify the context under which the Snapshot Agent connects to the Publisher in the **Publisher Properties** dialog box (available from the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="b8039-111">Pour plus d’informations, consultez [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b8039-111">For more information, see [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="b8039-112">Tous les comptes doivent être valides, le mot de passe correct étant spécifié pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="b8039-112">All accounts must be valid, with the correct password specified for each account.</span></span> <span data-ttu-id="b8039-113">Les comptes et les mots de passe ne sont pas validés tant qu'un agent ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="b8039-113">Accounts and passwords are not validated until an agent runs.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b8039-114">Options</span><span class="sxs-lookup"><span data-stu-id="b8039-114">Options</span></span>  
 <span data-ttu-id="b8039-115">**Compte de processus**</span><span class="sxs-lookup"><span data-stu-id="b8039-115">**Process account**</span></span>  
 <span data-ttu-id="b8039-116">Entrez le compte Windows sous lequel l'Agent d'instantané s'exécute sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="b8039-116">Enter a Windows account under which the Snapshot Agent runs at the Distributor.</span></span> <span data-ttu-id="b8039-117">Le compte Windows que vous définissez doit :</span><span class="sxs-lookup"><span data-stu-id="b8039-117">The Windows account you specify must:</span></span>  
  
-   <span data-ttu-id="b8039-118">être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de distribution ;</span><span class="sxs-lookup"><span data-stu-id="b8039-118">At minimum be a member of the **db_owner** fixed database role in the distribution database.</span></span>  
  
-   <span data-ttu-id="b8039-119">pouvoir écrire dans le partage de fichiers de instantanés.</span><span class="sxs-lookup"><span data-stu-id="b8039-119">Have write permissions on the snapshot share.</span></span>  
  
 <span data-ttu-id="b8039-120">**Mot de passe** et **Confirmer le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b8039-120">**Password** and **Confirm password**</span></span>  
 <span data-ttu-id="b8039-121">Entrez le mot de passe du compte Windows.</span><span class="sxs-lookup"><span data-stu-id="b8039-121">Enter the password for the Windows account.</span></span>  
  
 <span data-ttu-id="b8039-122">**Connexion au serveur de publication**</span><span class="sxs-lookup"><span data-stu-id="b8039-122">**Connect to the Publisher**</span></span>  
 <span data-ttu-id="b8039-123">Indiquez si l'Agent d'instantané doit établir des connexions au serveur de publication en imitant le compte défini dans la zone de texte **Compte de processus** en utilisant un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8039-123">Select whether the Snapshot Agent should make connections to the Publisher by impersonating the account specified in the **Process account** text box or by using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span> <span data-ttu-id="b8039-124">Si vous choisissez d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , entrez un nom de connexion et un mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8039-124">If you select to use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account, enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b8039-125">Il est recommandé de choisir d'emprunter l'identité du compte Windows plutôt que d'utiliser un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8039-125">It is recommended that you select to impersonate the Windows account rather than using a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
 <span data-ttu-id="b8039-126">Le compte Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisé pour la connexion doit être au moins un membre du rôle de base de données fixe **db_owner** dans la base de données de publication.</span><span class="sxs-lookup"><span data-stu-id="b8039-126">The Windows account or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account used for the connection must at minimum be a member of the **db_owner** fixed database role in the publication database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8039-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8039-127">See Also</span></span>  
 <span data-ttu-id="b8039-128">[Gérer les comptes de connexion et les mots de passe dans la réplication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span><span class="sxs-lookup"><span data-stu-id="b8039-128">[Manage Logins and Passwords in Replication](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication) </span></span>  
 <span data-ttu-id="b8039-129">[Modèle de sécurité de l’Agent de réplication](security/replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="b8039-129">[Replication Agent Security Model](security/replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="b8039-130">[Présentation des Agents de réplication](agents/replication-agents-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b8039-130">[Replication Agents Overview](agents/replication-agents-overview.md) </span></span>  
 [<span data-ttu-id="b8039-131">Bonnes pratiques en matière de sécurité de la réplication</span><span class="sxs-lookup"><span data-stu-id="b8039-131">Replication Security Best Practices</span></span>](security/replication-security-best-practices.md)  
  
  
