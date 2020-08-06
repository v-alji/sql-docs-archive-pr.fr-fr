---
title: Configurer des notifications par e-mail (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- e-mail [Master Data Services], configuring
- notifications [Master Data Services], configuring notifications
ms.assetid: 4241a6ab-7465-471b-9890-57c6b572037e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: baf60677435122af00f5ee5492e47bafaa45a3ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615195"
---
# <a name="configure-email-notifications-master-data-services"></a><span data-ttu-id="31154-102">Configurer des notifications par courrier électronique (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="31154-102">Configure Email Notifications (Master Data Services)</span></span>
  <span data-ttu-id="31154-103">Configurez des e-mail de notification lorsque vous souhaitez que [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] envoie automatiquement des e-mails.</span><span class="sxs-lookup"><span data-stu-id="31154-103">Configure notification emails when you want [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] to send email messages automatically.</span></span>  
  
### <a name="to-configure-notifications"></a><span data-ttu-id="31154-104">Pour configurer des notifications</span><span class="sxs-lookup"><span data-stu-id="31154-104">To configure notifications</span></span>  
  
1.  <span data-ttu-id="31154-105">Dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], dans la page **Base de données** , sélectionnez votre base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31154-105">In [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)], on the **Database** page, select your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="31154-106">Dans la section **Paramètres système** , cliquez sur **Créer un profil**.</span><span class="sxs-lookup"><span data-stu-id="31154-106">In the **System Settings** section, click **Create Profile**.</span></span>  
  
3.  <span data-ttu-id="31154-107">Complétez tous les champs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="31154-107">Complete all required fields.</span></span> <span data-ttu-id="31154-108">Pour plus d’informations, consultez [Boîte de dialogue Créer un compte et un profil de messagerie de base de données &#40;Gestionnaire de configuration des services de données de référence&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="31154-108">For more information, see [Create Database Mail Profile and Account Dialog Box &#40;Master Data Services Configuration Manager&#41;](../../2014/master-data-services/create-database-mail-profile-and-account-dialog-box.md).</span></span>  
  
4.  <span data-ttu-id="31154-109">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="31154-109">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="31154-110">Après avoir configuré des notifications, vous ne pouvez pas utiliser le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] pour apporter des modifications.</span><span class="sxs-lookup"><span data-stu-id="31154-110">After you configure notifications, you cannot use [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] to make changes.</span></span> <span data-ttu-id="31154-111">Vous devez apporter les modifications directement dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31154-111">You must make changes directly in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="31154-112">Pour plus d’informations, consultez [Objets de configuration de la messagerie de base de données](../relational-databases/database-mail/database-mail-configuration-objects.md).</span><span class="sxs-lookup"><span data-stu-id="31154-112">For more information, see [Database Mail Configuration Objects](../relational-databases/database-mail/database-mail-configuration-objects.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31154-113">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="31154-113">Next Steps</span></span>  
  
-   <span data-ttu-id="31154-114">Il existe des paramètres dans le [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] qui affectent les notifications.</span><span class="sxs-lookup"><span data-stu-id="31154-114">There are settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] that affect notifications.</span></span> <span data-ttu-id="31154-115">Vous pouvez ajuster ces paramètres dans [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] ou directement dans la table Paramètres système dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31154-115">You can adjust these settings in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] or directly in the System Settings table in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="31154-116">Pour plus d’informations, consultez [Paramètres système &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="31154-116">For more information, see [System Settings &#40;Master Data Services&#41;](system-settings-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31154-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31154-117">See Also</span></span>  
 <span data-ttu-id="31154-118">[&#40;de notifications Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="31154-118">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="31154-119">[Résolution des problèmes de notifications par courrier électronique (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span><span class="sxs-lookup"><span data-stu-id="31154-119">[Troubleshooting Email Notifications (Master Data Services)](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-email-notifications-master-data-services.aspx) </span></span>  
 [<span data-ttu-id="31154-120">Configurer des règles d’entreprise pour envoyer des notifications &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="31154-120">Configure Business Rules to Send Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md)  
  
  
