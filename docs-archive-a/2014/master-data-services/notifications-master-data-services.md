---
title: Notifications (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- notifications [Master Data Services]
- notifications [Master Data Services], about notifications
- e-mail [Master Data Services]
- e-mail [Master Data Services], about e-mail notifications
ms.assetid: d7ad32d5-9fe5-48fd-8c61-0b00c0aff082
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a61825f9450dd5b708aff8c3fc72f0f12732337b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614126"
---
# <a name="notifications-master-data-services"></a><span data-ttu-id="6de2d-102">Notifications (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6de2d-102">Notifications (Master Data Services)</span></span>
  [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]<span data-ttu-id="6de2d-103">peut être configuré pour envoyer une notification par courrier électronique en cas d’échec de la validation de la règle d’entreprise ou de modification de l’état d’une version de modèle.</span><span class="sxs-lookup"><span data-stu-id="6de2d-103">can be configured to send an email notification when business rule validation fails or the status of a model version changes.</span></span>  
  
## <a name="how-notifications-are-sent"></a><span data-ttu-id="6de2d-104">Mode d'envoi des notifications</span><span class="sxs-lookup"><span data-stu-id="6de2d-104">How Notifications Are Sent</span></span>  
 <span data-ttu-id="6de2d-105">Vous pouvez configurer les notifications dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6de2d-105">You configure notifications in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="6de2d-106">Les notifications envoient des messages électroniques à l’aide de Database Mail sur l’instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] qui héberge la [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="6de2d-106">Notifications send email messages by using Database Mail on the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that hosts the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="6de2d-107">Pour plus d’informations sur la messagerie de base de données, consultez [Objets de configuration de la messagerie de base de données](../relational-databases/database-mail/database-mail-configuration-objects.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6de2d-107">For more information about Database Mail, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md) in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="when-notifications-are-sent"></a><span data-ttu-id="6de2d-108">Critères d'envoi des notifications</span><span class="sxs-lookup"><span data-stu-id="6de2d-108">When Notifications Are Sent</span></span>  
 <span data-ttu-id="6de2d-109">Une fois les notifications configurées, elles peuvent être envoyées automatiquement par courrier électronique dans les cas suivants.</span><span class="sxs-lookup"><span data-stu-id="6de2d-109">After notifications are configured, automated email notifications can be sent in the following instances.</span></span>  
  
|<span data-ttu-id="6de2d-110">Instance</span><span class="sxs-lookup"><span data-stu-id="6de2d-110">Instance</span></span>|<span data-ttu-id="6de2d-111">Description</span><span class="sxs-lookup"><span data-stu-id="6de2d-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6de2d-112">Les données ne remplissent pas les conditions de validation des règles d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="6de2d-112">Data fails business rule validation</span></span>|<span data-ttu-id="6de2d-113">Les règles d'entreprise doivent être configurées individuellement pour envoyer des messages électroniques lorsqu'une valeur d'attribut fait échouer la validation de la règle d'entreprise.</span><span class="sxs-lookup"><span data-stu-id="6de2d-113">Individual business rules must be configured to send email when an attribute value fails business rule validation.</span></span> <span data-ttu-id="6de2d-114">Pour plus d’informations, consultez [Configurer des règles d’entreprise pour envoyer des notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6de2d-114">For more information, see [Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](configure-business-rules-to-send-notifications-master-data-services.md).</span></span>|  
|<span data-ttu-id="6de2d-115">L'état d'une version de modèle change</span><span class="sxs-lookup"><span data-stu-id="6de2d-115">Model version status changes</span></span>|<span data-ttu-id="6de2d-116">Chaque fois que l'état d'une version de modèle change, les utilisateurs qui sont des administrateurs de modèle reçoivent automatiquement des notifications.</span><span class="sxs-lookup"><span data-stu-id="6de2d-116">Each time a model version's status changes, users that are model administrators receive notifications automatically.</span></span> <span data-ttu-id="6de2d-117">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6de2d-117">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>|  
  
## <a name="system-settings"></a><span data-ttu-id="6de2d-118">Paramètres système</span><span class="sxs-lookup"><span data-stu-id="6de2d-118">System Settings</span></span>  
 <span data-ttu-id="6de2d-119">Il existe des paramètres dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] qui affectent les notifications.</span><span class="sxs-lookup"><span data-stu-id="6de2d-119">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="6de2d-120">Vous pouvez ajuster ces paramètres dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou directement dans la table Paramètres système dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6de2d-120">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="6de2d-121">Pour plus d’informations, consultez [Paramètres système &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6de2d-121">For more information, see [System Settings &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="6de2d-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6de2d-122">Related Tasks</span></span>  
  
|<span data-ttu-id="6de2d-123">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="6de2d-123">Task Description</span></span>|<span data-ttu-id="6de2d-124">Rubrique</span><span class="sxs-lookup"><span data-stu-id="6de2d-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="6de2d-125">Configurer [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] pour envoyer des notifications par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="6de2d-125">Configure [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email notifications.</span></span>|[<span data-ttu-id="6de2d-126">Configurer des notifications par courrier électronique &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6de2d-126">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)|  
|<span data-ttu-id="6de2d-127">Configurer [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour envoyer des notifications lorsque les valeurs d'attribut changent.</span><span class="sxs-lookup"><span data-stu-id="6de2d-127">Configure [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to send notifications when attribute values change.</span></span>|[<span data-ttu-id="6de2d-128">Configurer des règles d’entreprise pour envoyer des notifications &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6de2d-128">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](configure-business-rules-to-send-notifications-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="6de2d-129">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="6de2d-129">Related Content</span></span>  
  
-   [<span data-ttu-id="6de2d-130">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6de2d-130">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="6de2d-131">Versions &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6de2d-131">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
-   [<span data-ttu-id="6de2d-132">Résolution des problèmes liés aux notifications par courrier électronique (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6de2d-132">Troubleshooting Email Notifications (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx)  
  
  
