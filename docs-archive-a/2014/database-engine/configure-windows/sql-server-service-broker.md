---
title: SQL Server Service Broker | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SSBQUEUEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBREMSVCBINDPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBMSGTYPEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBROUTEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBCONTRACTPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBSERVICEPROPERTIES.GENERAL.F1
- SQL12.SWB.SSBPRIORITYPROPERTIES.GENERAL.F1
helpviewer_keywords:
- Broker See Service Broker
- SQL Server Service Broker
- Service Broker
ms.assetid: 8b8b3b57-fd46-44de-9a4e-e3a8e3999c1e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3d3877dd8311e0fe5b65bd4b1e7f9c40fbd84751
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707832"
---
# <a name="sql-server-service-broker"></a><span data-ttu-id="7db03-102">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="7db03-102">SQL Server Service Broker</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="7db03-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)]fournit la prise en charge native des applications de messagerie et de mise en file d’attente dans le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7db03-103">[!INCLUDE[ssSB](../../includes/sssb-md.md)] provides native support for messaging and queuing applications in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="7db03-104">Cette opération permet aux développeurs de créer plus facilement des applications perfectionnées qui utilisent des composants de [!INCLUDE[ssDE](../../includes/ssde-md.md)] pour la communication entre des bases de données disparates.</span><span class="sxs-lookup"><span data-stu-id="7db03-104">This makes it easier for developers to create sophisticated applications that use the [!INCLUDE[ssDE](../../includes/ssde-md.md)] components to communicate between disparate databases.</span></span> <span data-ttu-id="7db03-105">Les développeurs peuvent utiliser [!INCLUDE[ssSB](../../includes/sssb-md.md)] pour créer facilement des applications fiables et distribuées.</span><span class="sxs-lookup"><span data-stu-id="7db03-105">Developers can use [!INCLUDE[ssSB](../../includes/sssb-md.md)] to easily build distributed and reliable applications.</span></span>  
  
 <span data-ttu-id="7db03-106">Les développeurs d'applications qui utilisent [!INCLUDE[ssSB](../../includes/sssb-md.md)] peuvent distribuer les charges de données sur plusieurs bases de données sans développer des mécanismes de messagerie et de communication complexes.</span><span class="sxs-lookup"><span data-stu-id="7db03-106">Application developers who use [!INCLUDE[ssSB](../../includes/sssb-md.md)] can distribute data workloads across several databases without programming complex communication and messaging internals.</span></span> <span data-ttu-id="7db03-107">Il est ainsi possible de réduire le travail de développement et de test puisque [!INCLUDE[ssSB](../../includes/sssb-md.md)] gère les chemins de communication dans le contexte d'une conversation.</span><span class="sxs-lookup"><span data-stu-id="7db03-107">This reduces development and test work because [!INCLUDE[ssSB](../../includes/sssb-md.md)] handles the communication paths in the context of a conversation.</span></span> <span data-ttu-id="7db03-108">Les performances sont aussi meilleures.</span><span class="sxs-lookup"><span data-stu-id="7db03-108">It also improves performance.</span></span> <span data-ttu-id="7db03-109">Par exemple, les bases de données frontales prenant en charge les sites Web peuvent enregistrer des informations et mettre des tâches intensives en file d'attente dans des bases de données principales.</span><span class="sxs-lookup"><span data-stu-id="7db03-109">For example, front-end databases supporting Web sites can record information and send process intensive tasks to queue in back-end databases.</span></span> [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="7db03-110">garantit que toutes les tâches sont gérées dans le contexte des transactions afin d’assurer une fiabilité et une cohérence techniques.</span><span class="sxs-lookup"><span data-stu-id="7db03-110">ensures that all tasks are managed in the context of transactions to assure reliability and technical consistency.</span></span>  
  
## <a name="where-is-the-documentation-for-service-broker"></a><span data-ttu-id="7db03-111">Emplacement de la documentation de Service Broker</span><span class="sxs-lookup"><span data-stu-id="7db03-111">Where is the documentation for Service Broker?</span></span>  
 <span data-ttu-id="7db03-112">La documentation de référence pour [!INCLUDE[ssSB](../../includes/sssb-md.md)] est incluse dans la documentation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7db03-112">The reference documentation for [!INCLUDE[ssSB](../../includes/sssb-md.md)] is included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation.</span></span> <span data-ttu-id="7db03-113">Cette documentation de référence comprend les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="7db03-113">This reference documentation includes the following sections:</span></span>  
  
-   <span data-ttu-id="7db03-114">[Instructions DDL &#40;Data Definition Language &#41; &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) pour les instructions CREATE, ALTER et DROP</span><span class="sxs-lookup"><span data-stu-id="7db03-114">[Data Definition Language &#40;DDL&#41; Statements &#40;Transact-SQL&#41;](/sql/odbc/reference/develop-app/ddl-statements) for CREATE, ALTER, and DROP statements</span></span>  
  
-   [<span data-ttu-id="7db03-115">Affichages catalogue relatifs à Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7db03-115">Service Broker Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/service-broker-catalog-views-transact-sql)  
  
-   [<span data-ttu-id="7db03-116">Vues de gestion dynamique liées à Service Broker &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7db03-116">Service Broker Related Dynamic Management Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/service-broker-related-dynamic-management-views-transact-sql)  
  
-   [<span data-ttu-id="7db03-117">Utilitaire ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="7db03-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](../../tools/ssbdiagnose/ssbdiagnose-utility-service-broker.md)  
  
 <span data-ttu-id="7db03-118">Consultez la [documentation précédemment publiée](https://go.microsoft.com/fwlink/?LinkId=231312) pour les concepts [!INCLUDE[ssSB](../../includes/sssb-md.md)] et pour les tâches de gestion et de développement.</span><span class="sxs-lookup"><span data-stu-id="7db03-118">See the [previously published documentation](https://go.microsoft.com/fwlink/?LinkId=231312) for [!INCLUDE[ssSB](../../includes/sssb-md.md)] concepts and for development and management tasks.</span></span> <span data-ttu-id="7db03-119">Cette documentation n'est pas reproduite dans la documentation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] en raison de quelques modifications apportées dans [!INCLUDE[ssSB](../../includes/sssb-md.md)] dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7db03-119">This documentation is not reproduced in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] documentation due to the small number of changes in [!INCLUDE[ssSB](../../includes/sssb-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="whats-new-in-service-broker"></a><span data-ttu-id="7db03-120">Nouveautés dans Service Broker</span><span class="sxs-lookup"><span data-stu-id="7db03-120">What's new in Service Broker</span></span>  
 <span data-ttu-id="7db03-121">Aucune modification importante n'a été introduite dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7db03-121">No significant changes are introduced in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  <span data-ttu-id="7db03-122">Les modifications suivantes ont été introduites dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7db03-122">The following changes were introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
### <a name="messages-can-be-sent-to-multiple-target-services-multicast"></a><span data-ttu-id="7db03-123">Les messages peuvent être envoyés à des services cibles (multidiffusion).</span><span class="sxs-lookup"><span data-stu-id="7db03-123">Messages can be sent to multiple target services (multicast)</span></span>  
 <span data-ttu-id="7db03-124">La syntaxe de l’instruction [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) a été étendue pour permettre la multidiffusion au moyen de la prise en charge de plusieurs descripteurs de conversation.</span><span class="sxs-lookup"><span data-stu-id="7db03-124">The syntax of the [SEND &#40;Transact-SQL&#41;](/sql/t-sql/statements/send-transact-sql) statement has been extended to enable multicast by supporting multiple conversation handles.</span></span>  
  
### <a name="queues-expose-the-message-enqueued-time"></a><span data-ttu-id="7db03-125">Les files d'attente exposent le temps d'empilement des messages.</span><span class="sxs-lookup"><span data-stu-id="7db03-125">Queues expose the message enqueued time</span></span>  
 <span data-ttu-id="7db03-126">Les files d’attente ont une nouvelle colonne, **message_enqueue_time**, qui indique depuis combien de temps un message est dans la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="7db03-126">Queues have a new column, **message_enqueue_time**, that shows how long a message has been in the queue.</span></span>  
  
### <a name="poison-message-handling-can-be-disabled"></a><span data-ttu-id="7db03-127">La gestion des messages incohérents peut être désactivée</span><span class="sxs-lookup"><span data-stu-id="7db03-127">Poison message handling can be disabled</span></span>  
 <span data-ttu-id="7db03-128">Les instructions [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) et [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) ont désormais la possibilité d’activer ou désactiver la gestion des messages incohérents en ajoutant la clause `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span><span class="sxs-lookup"><span data-stu-id="7db03-128">The [CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) and [ALTER QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-queue-transact-sql) statements now have the ability to enable or disable poison message handling by adding the clause, `POISON_MESSAGE_HANDLING (STATUS = ON | OFF)`.</span></span> <span data-ttu-id="7db03-129">L’affichage catalogue **sys.service_queues** comprend maintenant la colonne **is_poison_message_handling_enabled** pour indiquer si le message incohérent est activé ou désactivé.</span><span class="sxs-lookup"><span data-stu-id="7db03-129">The catalog view **sys.service_queues** now has the column **is_poison_message_handling_enabled** to indicate whether poison message is enabled or disabled.</span></span>  
  
### <a name="alwayson-support-in-service-broker"></a><span data-ttu-id="7db03-130">Prise en charge d'AlwaysOn dans Service Broker</span><span class="sxs-lookup"><span data-stu-id="7db03-130">AlwaysOn support in Service Broker</span></span>  
 <span data-ttu-id="7db03-131">Pour plus d’informations, consultez [Service Broker avec les groupes de disponibilité Always On &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7db03-131">For more information, see [Service Broker with AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/service-broker-with-always-on-availability-groups-sql-server.md).</span></span>  
  
  
