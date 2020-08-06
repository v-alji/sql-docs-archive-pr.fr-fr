---
title: Propriétés de SQL Server Agent (page Système d’alerte) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613265"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="4be83-102">Propriétés de SQL Server Agent (page Système d'alerte)</span><span class="sxs-lookup"><span data-stu-id="4be83-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="4be83-103">Cette page vous permet d’afficher et de modifier les paramètres des messages envoyés par les alertes de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4be83-104">Options</span><span class="sxs-lookup"><span data-stu-id="4be83-104">Options</span></span>  
 <span data-ttu-id="4be83-105">**Session de messagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-105">**Mail session**</span></span>  
 <span data-ttu-id="4be83-106">Les options de cette section permettent de configurer la messagerie de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="4be83-107">**Activer le profil de messagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="4be83-108">Active la messagerie de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="4be83-109">Par défaut, la messagerie de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent est désactivée.</span><span class="sxs-lookup"><span data-stu-id="4be83-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="4be83-110">**Système de messagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-110">**Mail System**</span></span>  
 <span data-ttu-id="4be83-111">Définit le système de messagerie que doit utiliser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="4be83-112">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="4be83-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4be83-113">Une fois que vous avez changé le système de messagerie, vous devez redémarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pour que la modification soit prise en compte.</span><span class="sxs-lookup"><span data-stu-id="4be83-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="4be83-114">**Profil de la messagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-114">**Mail Profile**</span></span>  
 <span data-ttu-id="4be83-115">Définit le profil que doit utiliser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="4be83-116">Vous pouvez également sélectionner **\<new Database Mail profile...>** pour créer un profil.</span><span class="sxs-lookup"><span data-stu-id="4be83-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="4be83-117">**Messages de radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="4be83-118">Les options de cette section vous permettent de configurer les messages électroniques envoyés à des adresses de radiomessagerie pour qu'ils fonctionnent avec votre système de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="4be83-119">**Format d'adresse pour les messages de radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="4be83-120">Cette section vous permet de spécifier le format des adresses et la ligne Objet incluse dans les messages de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="4be83-121">**Ligne À**</span><span class="sxs-lookup"><span data-stu-id="4be83-121">**To line**</span></span>  
 <span data-ttu-id="4be83-122">Spécifie les options relatives à la ligne **À** du message.</span><span class="sxs-lookup"><span data-stu-id="4be83-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="4be83-123">**Préfixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-123">**Prefix**</span></span>  
 <span data-ttu-id="4be83-124">Tapez le texte prédéfini, requis par votre système au début de la ligne **À** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-125">**Radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-125">**Pager**</span></span>  
 <span data-ttu-id="4be83-126">Inclut l'adresse de messagerie du message entre le préfixe et le suffixe.</span><span class="sxs-lookup"><span data-stu-id="4be83-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="4be83-127">**Suffixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-127">**Suffix**</span></span>  
 <span data-ttu-id="4be83-128">Tapez le texte prédéfini, requis par votre système de radiomessagerie à la fin de la ligne **À** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-129">**Ligne Cc**</span><span class="sxs-lookup"><span data-stu-id="4be83-129">**Cc line**</span></span>  
 <span data-ttu-id="4be83-130">Spécifie les options relatives à la ligne **Cc** du message.</span><span class="sxs-lookup"><span data-stu-id="4be83-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="4be83-131">**Préfixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-131">**Prefix**</span></span>  
 <span data-ttu-id="4be83-132">Tapez le texte prédéfini, requis par votre système au début de la ligne **Cc** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-133">**Radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="4be83-133">**Pager**</span></span>  
 <span data-ttu-id="4be83-134">Inclut l'adresse de messagerie du message entre le préfixe et le suffixe.</span><span class="sxs-lookup"><span data-stu-id="4be83-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="4be83-135">**Suffixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-135">**Suffix**</span></span>  
 <span data-ttu-id="4be83-136">Tapez le texte prédéfini, requis par votre système de radiomessagerie à la fin de la ligne **Cc** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-137">**Subject**</span><span class="sxs-lookup"><span data-stu-id="4be83-137">**Subject**</span></span>  
 <span data-ttu-id="4be83-138">Spécifie les options relatives à l'objet du message</span><span class="sxs-lookup"><span data-stu-id="4be83-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="4be83-139">**Préfixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-139">**Prefix**</span></span>  
 <span data-ttu-id="4be83-140">Tapez le texte prédéfini, requis par votre système de radiomessagerie au début de la ligne **Objet** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-141">**Suffixe**</span><span class="sxs-lookup"><span data-stu-id="4be83-141">**Suffix**</span></span>  
 <span data-ttu-id="4be83-142">Tapez le texte prédéfini, requis par votre système de radiomessagerie à la fin de la ligne **Objet** des messages envoyés à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="4be83-143">**Inclure le corps du message dans le message de notification**</span><span class="sxs-lookup"><span data-stu-id="4be83-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="4be83-144">Inclut le corps du message électronique dans le message envoyé au récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="4be83-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="4be83-145">**Opérateur de prévention de défaillance**</span><span class="sxs-lookup"><span data-stu-id="4be83-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="4be83-146">Cette section vous permet de spécifier les options relatives à l'opérateur de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="4be83-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="4be83-147">**Activer l'opérateur de prévention de défaillance**</span><span class="sxs-lookup"><span data-stu-id="4be83-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="4be83-148">Spécifie un opérateur de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="4be83-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="4be83-149">**Opérateur**</span><span class="sxs-lookup"><span data-stu-id="4be83-149">**Operator**</span></span>  
 <span data-ttu-id="4be83-150">Définit le nom de l'opérateur qui doit recevoir les notifications pour la prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="4be83-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="4be83-151">**Notifier en utilisant**</span><span class="sxs-lookup"><span data-stu-id="4be83-151">**Notify using**</span></span>  
 <span data-ttu-id="4be83-152">Définit la méthode à utiliser pour notifier l'opérateur de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="4be83-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="4be83-153">**Remplacement des jetons**</span><span class="sxs-lookup"><span data-stu-id="4be83-153">**Token Replacement**</span></span>  
 <span data-ttu-id="4be83-154">Cette section vous permet d'activer des jetons d'étapes de travail utilisables dans les travaux exécutés par les alertes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="4be83-155">Pour plus d’informations sur les jetons d’étapes de travail, consultez [Utiliser des jetons dans les étapes d’un travail](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="4be83-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4be83-156">Tout utilisateur Windows doté d'autorisations d'accès en écriture sur le Journal des événements Windows peut accéder aux étapes de travail qui sont activées par les alertes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="4be83-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="4be83-157">Pour éviter ce risque de sécurité, les jetons de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent qui peuvent être utilisés dans des travaux activés par des alertes sont désactivés par défaut.</span><span class="sxs-lookup"><span data-stu-id="4be83-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="4be83-158">Il s’agit des jetons suivants : **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** et **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="4be83-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="4be83-159">Si vous avez besoin de les utiliser, assurez-vous avant de les activer que seuls les membres des groupes de sécurité Windows approuvés, tels que le groupe Administrateurs, possèdent des autorisations d'accès en écriture sur le Journal des événements de l'ordinateur sur lequel réside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4be83-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="4be83-160">**Remplacer les jetons pour toutes les réponses de travaux aux alertes**</span><span class="sxs-lookup"><span data-stu-id="4be83-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="4be83-161">Activez cette case à cocher pour permettre le remplacement des jetons pour les travaux qui sont activés par les alertes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4be83-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be83-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4be83-162">See Also</span></span>  
 <span data-ttu-id="4be83-163">[Operator](operators.md) </span><span class="sxs-lookup"><span data-stu-id="4be83-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="4be83-164">[Configurez SQL Server Agent mail pour utiliser Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="4be83-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="4be83-165">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="4be83-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
