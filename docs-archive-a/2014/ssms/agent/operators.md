---
title: Opérateurs | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704668"
---
# <a name="operators"></a><span data-ttu-id="b7b35-102">Opérateurs</span><span class="sxs-lookup"><span data-stu-id="b7b35-102">Operators</span></span>
  <span data-ttu-id="b7b35-103">Les opérateurs sont des alias pour les personnes ou les groupes qui peuvent recevoir une notification électronique à la fin des travaux ou en cas d'alertes.</span><span class="sxs-lookup"><span data-stu-id="b7b35-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="b7b35-104">Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prend en charge la notification des administrateurs par le biais des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="b7b35-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="b7b35-105">Les opérateurs activent les fonctions de notification et de surveillance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="b7b35-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="b7b35-106">Attributs et concepts relatifs aux opérateurs</span><span class="sxs-lookup"><span data-stu-id="b7b35-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="b7b35-107">Les attributs principaux d'un opérateur sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="b7b35-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="b7b35-108">Nom de l'opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-108">Operator name</span></span>  
  
-   <span data-ttu-id="b7b35-109">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="b7b35-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="b7b35-110">Désignation d'un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-110">Naming an Operator</span></span>  
 <span data-ttu-id="b7b35-111">Chaque opérateur doit avoir un nom.</span><span class="sxs-lookup"><span data-stu-id="b7b35-111">Every operator must have a name.</span></span> <span data-ttu-id="b7b35-112">Les noms des opérateurs doivent être uniques dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et ne pas dépasser **128** caractères.</span><span class="sxs-lookup"><span data-stu-id="b7b35-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="b7b35-113">Informations de contact</span><span class="sxs-lookup"><span data-stu-id="b7b35-113">Contact Information</span></span>  
 <span data-ttu-id="b7b35-114">Les informations de contact d'un opérateur définissent la façon dont l'opérateur est notifié.</span><span class="sxs-lookup"><span data-stu-id="b7b35-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="b7b35-115">Les opérateurs peuvent être avertis par e-mail, par radiomessagerie ou par la commande **net send** :</span><span class="sxs-lookup"><span data-stu-id="b7b35-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7b35-116">Les options du récepteur de radiomessagerie et **net send** seront supprimées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7b35-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b7b35-117">Évitez d'utiliser ces fonctionnalités dans une nouvelle tâche de développement et prévoyez de modifier les applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="b7b35-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="b7b35-118">**Notification par courrier électronique**</span><span class="sxs-lookup"><span data-stu-id="b7b35-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="b7b35-119">La notification par courrier électronique envoie un message électronique à l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="b7b35-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="b7b35-120">Fournissez l'adresse électronique de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="b7b35-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="b7b35-121">**Notification par radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="b7b35-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="b7b35-122">La radiomessagerie est mise en place à l'aide du courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b7b35-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="b7b35-123">Fournissez l'adresse électronique de l'opérateur à laquelle il recevra les messages de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="b7b35-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="b7b35-124">Pour définir une notification par radiomessagerie, vous devez installer sur le serveur de messagerie un logiciel qui traite le courrier entrant et qui le convertit en message de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="b7b35-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="b7b35-125">Plusieurs approches sont possibles avec le logiciel, notamment :</span><span class="sxs-lookup"><span data-stu-id="b7b35-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="b7b35-126">transmettre le courrier à un serveur de messagerie distant sur le site du fournisseur de radiomessagerie ;</span><span class="sxs-lookup"><span data-stu-id="b7b35-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="b7b35-127">Le fournisseur de services de radiomessagerie doit offrir ce service, même si le logiciel nécessaire fait généralement partie du système de messagerie électronique local.</span><span class="sxs-lookup"><span data-stu-id="b7b35-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="b7b35-128">Pour plus d'informations, consultez la documentation relative à votre récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="b7b35-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="b7b35-129">acheminer le courrier sur le réseau Internet vers un serveur de messagerie sur le site du fournisseur de services de radiomessagerie ;</span><span class="sxs-lookup"><span data-stu-id="b7b35-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="b7b35-130">Il s'agit d'une variation de la première approche.</span><span class="sxs-lookup"><span data-stu-id="b7b35-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="b7b35-131">traiter le courrier entrant et composer le numéro du récepteur de radiomessagerie à l'aide d'un modem auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="b7b35-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="b7b35-132">Ce logiciel est propre au fournisseur de services de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="b7b35-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="b7b35-133">Le logiciel fait office de client de courrier électronique qui traite régulièrement sa boîte de réception en interprétant tout ou partie des informations relatives aux adresses de courrier électronique comme un numéro de récepteur de radiomessagerie, ou en comparant le nom associé au courrier électronique à un numéro de récepteur de radiomessagerie dans une table de correspondance.</span><span class="sxs-lookup"><span data-stu-id="b7b35-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="b7b35-134">Si tous les opérateurs ont le même fournisseur de services de radiomessagerie, vous pouvez utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour spécifier une mise en forme spécifique de courrier électronique exigé par le système de liaison par radiomessagerie/courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b7b35-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="b7b35-135">Cette mise en forme spéciale peut être un préfixe ou un suffixe et elle peut être incluse dans les lignes suivantes du courrier électronique :</span><span class="sxs-lookup"><span data-stu-id="b7b35-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="b7b35-136">**Objet :**</span><span class="sxs-lookup"><span data-stu-id="b7b35-136">**Subject:**</span></span>  
  
         <span data-ttu-id="b7b35-137">**Cc**:</span><span class="sxs-lookup"><span data-stu-id="b7b35-137">**Cc**:</span></span>  
  
         <span data-ttu-id="b7b35-138">**À** :</span><span class="sxs-lookup"><span data-stu-id="b7b35-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7b35-139">Si vous utilisez un système de radiomessagerie alphanumérique à faible capacité, vous pouvez raccourcir le texte à envoyer en éliminant le texte d'erreur de la notification par radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="b7b35-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="b7b35-140">C'est le cas par exemple des systèmes limités à 64 caractères par page.</span><span class="sxs-lookup"><span data-stu-id="b7b35-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="b7b35-141">**Notification net send**</span><span class="sxs-lookup"><span data-stu-id="b7b35-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="b7b35-142">Envoie un message à l’opérateur par le biais de la commande **net send** .</span><span class="sxs-lookup"><span data-stu-id="b7b35-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="b7b35-143">Pour **net send**, spécifiez le destinataire (ordinateur ou utilisateur) du message réseau.</span><span class="sxs-lookup"><span data-stu-id="b7b35-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7b35-144">La commande **net send** utilise Microsoft Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="b7b35-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="b7b35-145">Pour envoyer des alertes, ce service doit s'exécuter à la fois sur l'ordinateur sur lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute et sur l'ordinateur de l'opérateur.</span><span class="sxs-lookup"><span data-stu-id="b7b35-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="b7b35-146">Alertes et opérateurs de prévention de défaillance</span><span class="sxs-lookup"><span data-stu-id="b7b35-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="b7b35-147">Vous pouvez choisir les opérateurs à avertir en réponse à une alerte.</span><span class="sxs-lookup"><span data-stu-id="b7b35-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="b7b35-148">Par exemple, vous pouvez attribuer des responsabilités alternées aux opérateurs, en planifiant des alertes qui les avertissent.</span><span class="sxs-lookup"><span data-stu-id="b7b35-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="b7b35-149">Ainsi, une personne A peut être avertie des alertes intervenant le lundi, le mercredi ou le vendredi, tandis qu'une personne B peut l'être le mardi, le jeudi ou le samedi.</span><span class="sxs-lookup"><span data-stu-id="b7b35-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="b7b35-150">L'opérateur de prévention de défaillance reçoit une notification d'alerte après l'échec de toutes les notifications par radiomessagerie envoyées aux opérateurs désignés.</span><span class="sxs-lookup"><span data-stu-id="b7b35-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="b7b35-151">Si, par exemple, vous définissez trois opérateurs à avertir par radiomessagerie et qu'aucun des trois ne peut être contacté, l'opérateur de prévention de défaillance est averti.</span><span class="sxs-lookup"><span data-stu-id="b7b35-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="b7b35-152">L'opérateur de prévention de défaillance est averti lorsque :</span><span class="sxs-lookup"><span data-stu-id="b7b35-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="b7b35-153">les opérateurs responsables de l'alerte n'ont pas pu être contactés par radiomessagerie ;</span><span class="sxs-lookup"><span data-stu-id="b7b35-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="b7b35-154">Cela peut être dû à l'impossibilité de joindre les principaux opérateurs, par exemple si les adresses de radiomessagerie sont incorrectes ou si les opérateurs ne sont pas en service.</span><span class="sxs-lookup"><span data-stu-id="b7b35-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b7b35-155">Agent ne peut pas avoir accès aux tables système de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="b7b35-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="b7b35-156">La table système **sysnotifications** précise les responsabilités des opérateurs en ce qui concerne les alertes.</span><span class="sxs-lookup"><span data-stu-id="b7b35-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="b7b35-157">L'opérateur de prévention de défaillance est une fonction de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b7b35-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="b7b35-158">Vous ne pouvez pas supprimer l'opérateur affecté en tant que tel sans réaffecter la prévention de défaillance à un autre opérateur ou sans supprimer aussi cette sécurité.</span><span class="sxs-lookup"><span data-stu-id="b7b35-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="b7b35-159">Envoi d'une notification à un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-159">Notifying an Operator</span></span>  
 <span data-ttu-id="b7b35-160">Un ou plusieurs des éléments suivants sont nécessaires pour avertir un opérateur :</span><span class="sxs-lookup"><span data-stu-id="b7b35-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="b7b35-161">Pour envoyer un courrier électronique à l'aide de la fonction de messagerie de base de données, vous devez avoir accès à un serveur de messagerie prenant en charge le protocole SMTP.</span><span class="sxs-lookup"><span data-stu-id="b7b35-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="b7b35-162">Pour la transmission par radiomessagerie, vous devez disposer d'un logiciel et/ou matériel de transmission de radiomessagerie à courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b7b35-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="b7b35-163">Pour utiliser **net send**, l’opérateur doit avoir ouvert une session sur l’ordinateur spécifié et ce dernier doit accepter les messages en provenance de Windows Messenger.</span><span class="sxs-lookup"><span data-stu-id="b7b35-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b7b35-164">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="b7b35-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7b35-165">**Tâches**</span><span class="sxs-lookup"><span data-stu-id="b7b35-165">**Tasks**</span></span>|<span data-ttu-id="b7b35-166">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="b7b35-166">**Topic**</span></span>|  
|<span data-ttu-id="b7b35-167">Tâches associées à la création d'un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="b7b35-168">Créer un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="b7b35-169">Désigner un opérateur de prévention de défaillance</span><span class="sxs-lookup"><span data-stu-id="b7b35-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="b7b35-170">Tâches associées à l'affectation d'alertes</span><span class="sxs-lookup"><span data-stu-id="b7b35-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="b7b35-171">Affecter des alertes à un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="b7b35-172">Définir la réponse à une alerte &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b7b35-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="b7b35-173">sp_add_notification &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b7b35-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="b7b35-174">Affecter des alertes à un opérateur</span><span class="sxs-lookup"><span data-stu-id="b7b35-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b7b35-175">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7b35-175">See Also</span></span>  
 [<span data-ttu-id="b7b35-176">Messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="b7b35-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
