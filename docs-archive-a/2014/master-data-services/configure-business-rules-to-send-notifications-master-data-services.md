---
title: Configurer des règles d’entreprise pour envoyer des notifications (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], configuring notifications
- e-mail [Master Data Services], configuring business rules
- notifications [Master Data Services], configuring business rules
ms.assetid: b24f7b11-ab53-4642-999c-e17b543b3558
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cb1a12167dffe123e55760f031e21499fe22a945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615196"
---
# <a name="configure-business-rules-to-send-notifications-master-data-services"></a><span data-ttu-id="1e711-102">Configurer des règles d'entreprise pour envoyer des notifications (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1e711-102">Configure Business Rules to Send Notifications (Master Data Services)</span></span>
  <span data-ttu-id="1e711-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configurez des règles d'entreprise pour envoyer des notifications lorsque vous souhaitez informer les utilisateurs des modifications apportées aux valeurs d'attribut.</span><span class="sxs-lookup"><span data-stu-id="1e711-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], configure business rules to send notifications when you want to notify users about attribute value changes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e711-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="1e711-104">Prerequisites</span></span>  
 <span data-ttu-id="1e711-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="1e711-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="1e711-106">Vous devez avoir l'autorisation d'accéder aux zones fonctionnelles **Administration de système** et **Autorisations d'accès** .</span><span class="sxs-lookup"><span data-stu-id="1e711-106">You must have permission to access the **System Administration** and **User and Group Permissions** functional areas.</span></span> <span data-ttu-id="1e711-107">Si vous n'avez pas d'autorisation sur la zone fonctionnelle **Autorisations d'accès** , vous ne pouvez pas afficher la liste des utilisateurs et groupes auxquels envoyer des notifications.</span><span class="sxs-lookup"><span data-stu-id="1e711-107">If you do not have permission to the **User and Group Permissions** functional area, you cannot view the list of users and groups to send notifications to.</span></span>  
  
-   <span data-ttu-id="1e711-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="1e711-108">You must be a model administrator.</span></span> <span data-ttu-id="1e711-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e711-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="1e711-110">Une règle d'entreprise qui utilise une action de validation doit déjà exister.</span><span class="sxs-lookup"><span data-stu-id="1e711-110">A business rule that uses a validation action must already exist.</span></span> <span data-ttu-id="1e711-111">Pour plus d’informations, consultez [Créer et publier une règle d’entreprise &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1e711-111">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="1e711-112">L’utilisateur ou le groupe qui reçoit la notification doit avoir au moins l’autorisation **Lecture seule** sur l’attribut qui n’a pas été validé.</span><span class="sxs-lookup"><span data-stu-id="1e711-112">The user or group that receives the notification must have at least **Read-only** permission to the attribute that fails validation.</span></span> <span data-ttu-id="1e711-113">Les utilisateurs ou les groupes qui se voient refuser explicitement ou implicitement l'autorisation à l'attribut recevront le courrier électronique, mais ne seront pas en mesure d'accéder à l'attribut dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e711-113">Users or groups that are explicitly or implicitly denied permission to the attribute will receive the email but will not be able to access the attribute in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="1e711-114">Si un courrier électronique est envoyé à un groupe, seuls les membres du groupe qui ont accédé à [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] le recevront.</span><span class="sxs-lookup"><span data-stu-id="1e711-114">If mail is sent to a group, only members of the group that have accessed [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] will get the email.</span></span>  
  
### <a name="to-configure-business-rules-to-send-notifications"></a><span data-ttu-id="1e711-115">Pour configurer des règles d'entreprise pour envoyer des notifications</span><span class="sxs-lookup"><span data-stu-id="1e711-115">To configure business rules to send notifications</span></span>  
  
1.  <span data-ttu-id="1e711-116">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="1e711-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="1e711-117">Dans la barre de menus, pointez sur **Gérer** et cliquez sur **Règles d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1e711-117">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="1e711-118">Dans la page **Maintenance des règles d’entreprise** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="1e711-118">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="1e711-119">Dans la liste **Entité** , sélectionnez une entité.</span><span class="sxs-lookup"><span data-stu-id="1e711-119">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="1e711-120">Dans la liste **type de membre** , sélectionnez un type de membre.</span><span class="sxs-lookup"><span data-stu-id="1e711-120">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="1e711-121">Dans la liste **Attribut** , sélectionnez un attribut ou conservez l’option par défaut **Tout**.</span><span class="sxs-lookup"><span data-stu-id="1e711-121">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="1e711-122">Dans la grille, dans la ligne de la règle d’entreprise, double-cliquez sur le champ de **notification** .</span><span class="sxs-lookup"><span data-stu-id="1e711-122">In the grid, in the row for the business rule, double-click the **Notification** field.</span></span>  
  
8.  <span data-ttu-id="1e711-123">Dans le sous-menu, cliquez sur un utilisateur ou un groupe auquel envoyer la notification par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="1e711-123">From the sub-menu, click a user or group to send the email notification to.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1e711-124">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="1e711-124">Next Steps</span></span>  
  
-   <span data-ttu-id="1e711-125">Appliquez des règles d'entreprise aux données en suivant l'une de ces procédures :</span><span class="sxs-lookup"><span data-stu-id="1e711-125">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="1e711-126">Valider des membres spécifiques par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1e711-126">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="1e711-127">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1e711-127">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   <span data-ttu-id="1e711-128">Configurez le protocole de messagerie comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e711-128">Configure the email protocol as follows:</span></span>  
  
    -   [<span data-ttu-id="1e711-129">Configurer des notifications par courrier électronique &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1e711-129">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e711-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e711-130">See Also</span></span>  
 <span data-ttu-id="1e711-131">[&#40;de notifications Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1e711-131">[Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/notifications-master-data-services.md) </span></span>  
 [<span data-ttu-id="1e711-132">Configurer des notifications par courrier électronique &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1e711-132">Configure Email Notifications &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/configure-email-notifications-master-data-services.md)  
  
  
