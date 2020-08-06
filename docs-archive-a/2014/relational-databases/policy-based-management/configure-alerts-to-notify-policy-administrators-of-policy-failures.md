---
title: Configurer des alertes afin d’informer les administrateurs de stratégie en cas d’échec de stratégie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, configure alerts
ms.assetid: e8e60159-d5b0-49d5-91f3-af8e9cb994c1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9eb84ced3bb6313dd5920deaf479925556f08fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695576"
---
# <a name="configure-alerts-to-notify-policy-administrators-of-policy-failures"></a><span data-ttu-id="02c71-102">Configurer des alertes afin d'informer les administrateurs de stratégie en cas d'échec de stratégie</span><span class="sxs-lookup"><span data-stu-id="02c71-102">Configure Alerts to Notify Policy Administrators of Policy Failures</span></span>
  <span data-ttu-id="02c71-103">Lorsque des stratégies de Gestion basée sur des stratégies sont exécutées dans l'un des trois modes d'évaluation automatisés, en cas de violation de stratégie, un message est écrit dans le journal des événements.</span><span class="sxs-lookup"><span data-stu-id="02c71-103">When Policy-Based Management policies are executed in one of the three automated evaluation modes, if a policy violation occurs, a message is written to the event log.</span></span> <span data-ttu-id="02c71-104">Pour être informé de l'écriture de ce message dans le journal des événements, vous pouvez créer une alerte afin de détecter le message et d'exécuter une action.</span><span class="sxs-lookup"><span data-stu-id="02c71-104">To be notified when this message is written to the event log, you can create an alert to detect the message and perform an action.</span></span> <span data-ttu-id="02c71-105">L'alerte doit détecter les messages comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="02c71-105">The alert should detect the messages as shown in the following table.</span></span>  
  
|<span data-ttu-id="02c71-106">Mode d'exécution</span><span class="sxs-lookup"><span data-stu-id="02c71-106">Execution mode</span></span>|<span data-ttu-id="02c71-107">Numéro de message</span><span class="sxs-lookup"><span data-stu-id="02c71-107">Message number</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="02c71-108">Sur modification - Empêcher</span><span class="sxs-lookup"><span data-stu-id="02c71-108">On change: prevent</span></span><br /><br /> <span data-ttu-id="02c71-109">(si automatique)</span><span class="sxs-lookup"><span data-stu-id="02c71-109">(if automatic)</span></span>|<span data-ttu-id="02c71-110">34050</span><span class="sxs-lookup"><span data-stu-id="02c71-110">34050</span></span>|  
|<span data-ttu-id="02c71-111">Sur modification - Empêcher</span><span class="sxs-lookup"><span data-stu-id="02c71-111">On change: prevent</span></span><br /><br /> <span data-ttu-id="02c71-112">(si À la demande)</span><span class="sxs-lookup"><span data-stu-id="02c71-112">(if On demand)</span></span>|<span data-ttu-id="02c71-113">34051</span><span class="sxs-lookup"><span data-stu-id="02c71-113">34051</span></span>|  
|<span data-ttu-id="02c71-114">Selon planification</span><span class="sxs-lookup"><span data-stu-id="02c71-114">On schedule</span></span>|<span data-ttu-id="02c71-115">34052</span><span class="sxs-lookup"><span data-stu-id="02c71-115">34052</span></span>|  
|<span data-ttu-id="02c71-116">Sur modification</span><span class="sxs-lookup"><span data-stu-id="02c71-116">On change</span></span>|<span data-ttu-id="02c71-117">34053</span><span class="sxs-lookup"><span data-stu-id="02c71-117">34053</span></span>|  
  
 <span data-ttu-id="02c71-118">Pour configurer une alerte en réponse aux messages d'erreur de la Gestion basée sur des stratégies, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="02c71-118">To set up an alert to respond to the Policy-Based Management error messages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="02c71-119">Créer un opérateur</span><span class="sxs-lookup"><span data-stu-id="02c71-119">Create an Operator</span></span>](../../ssms/agent/create-an-operator.md)  
  
-   [<span data-ttu-id="02c71-120">Créer une alerte utilisant un numéro d'erreur</span><span class="sxs-lookup"><span data-stu-id="02c71-120">Create an Alert Using an Error Number</span></span>](../../ssms/agent/create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="02c71-121">Affecter des alertes à un opérateur</span><span class="sxs-lookup"><span data-stu-id="02c71-121">Assign Alerts to an Operator</span></span>](../../ssms/agent/assign-alerts-to-an-operator.md)  
  
## <a name="permissions"></a><span data-ttu-id="02c71-122">Autorisations</span><span class="sxs-lookup"><span data-stu-id="02c71-122">Permissions</span></span>  
 <span data-ttu-id="02c71-123">Lorsque des stratégies sont évaluées à la demande, elles s'exécutent dans le contexte de sécurité de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02c71-123">When policies are evaluated on demand, they execute in the security context of the user.</span></span> <span data-ttu-id="02c71-124">Pour écrire dans le journal des erreurs, l'utilisateur doit posséder l'autorisation ALTER TRACE ou être membre du rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="02c71-124">To write to the error log, the user must have ALTER TRACE permissions or be a member of the sysadmin fixed server role.</span></span> <span data-ttu-id="02c71-125">Les stratégies évaluées par un utilisateur qui dispose de moins de privilèges n'écrivent pas dans le journal des événements et ne déclenchent pas d'alerte.</span><span class="sxs-lookup"><span data-stu-id="02c71-125">Policies that are evaluated by a user that has less privileges will not write to the event log, and will not fire an alert.</span></span>  
  
 <span data-ttu-id="02c71-126">Les modes d'exécution automatisés s'exécutent comme membre du rôle sysadmin.</span><span class="sxs-lookup"><span data-stu-id="02c71-126">The automated execution modes execute as a member of the sysadmin role.</span></span> <span data-ttu-id="02c71-127">Cela permet à la stratégie d'écrire dans le journal des erreurs et de déclencher une alerte.</span><span class="sxs-lookup"><span data-stu-id="02c71-127">This allows the policy to write to the error log and raise an alert.</span></span>  
  
## <a name="additional-considerations-about-alerts"></a><span data-ttu-id="02c71-128">Considérations supplémentaires relatives aux alertes</span><span class="sxs-lookup"><span data-stu-id="02c71-128">Additional Considerations About Alerts</span></span>  
 <span data-ttu-id="02c71-129">Tenez compte des considérations supplémentaires relatives aux alertes :</span><span class="sxs-lookup"><span data-stu-id="02c71-129">Be aware of the following additional considerations about alerts:</span></span>  
  
-   <span data-ttu-id="02c71-130">Des alertes sont déclenchées uniquement pour les stratégies activées.</span><span class="sxs-lookup"><span data-stu-id="02c71-130">Alerts are raised only for policies that are enabled.</span></span> <span data-ttu-id="02c71-131">Comme les stratégies **À la demande** ne peuvent pas être activées, aucune alerte n’est déclenchée pour les stratégies exécutées sur demande.</span><span class="sxs-lookup"><span data-stu-id="02c71-131">Because **On demand** policies cannot be enabled, alerts are not raised for policies that are executed on demand.</span></span>  
  
-   <span data-ttu-id="02c71-132">Si l'action que vous souhaitez effectuer inclut l'envoi d'un message électronique, vous devez configurer un compte de messagerie.</span><span class="sxs-lookup"><span data-stu-id="02c71-132">If the action you want to take includes sending an e-mail message, you must configure a mail account.</span></span> <span data-ttu-id="02c71-133">Nous vous recommandons d'utiliser la Messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="02c71-133">We recommend that you use Database Mail.</span></span> <span data-ttu-id="02c71-134">Pour plus d’informations sur la manière de configurer la messagerie de base de données, consultez [Créer un compte de messagerie de base de données](../database-mail/create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="02c71-134">For more information about how to set up Database Mail, see [Create a Database Mail Account](../database-mail/create-a-database-mail-account.md).</span></span>  
  
  
