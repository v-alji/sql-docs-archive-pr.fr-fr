---
title: Transférer les messages d’erreur, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.f1
helpviewer_keywords:
- Transfer Error Messages task [Integration Services]
ms.assetid: da702289-035a-4d14-bd74-04461fbfee1b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 952acc28a79fef7e7351c97400e05bc7ba5b9243
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600169"
---
# <a name="transfer-error-messages-task"></a><span data-ttu-id="32e37-102">Tâche de transfert de messages d'erreur</span><span class="sxs-lookup"><span data-stu-id="32e37-102">Transfer Error Messages Task</span></span>
  <span data-ttu-id="32e37-103">La tâche de transfert de messages d’erreur transfère un ou plusieurs messages d’erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] définis par l’utilisateur entre des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32e37-103">The Transfer Error Messages task transfers one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined error messages between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="32e37-104">Les messages définis par l'utilisateur sont des messages avec un identificateur supérieur ou égal à 50 000.</span><span class="sxs-lookup"><span data-stu-id="32e37-104">User-defined messages are messages with an identifier that is equal to or greater than 50000.</span></span> <span data-ttu-id="32e37-105">Les messages dont l'identificateur est inférieur à 50 000 sont des messages d'erreur système qui ne peuvent pas être transférés à l'aide de la tâche de transfert de messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="32e37-105">Messages with an identifier less than 50000 are system error messages, and cannot be transferred by using the Transfer Error Messages task.</span></span>  
  
 <span data-ttu-id="32e37-106">La tâche de transfert de messages d'erreur peut être configurée pour transférer tous les messages d'erreur ou uniquement les messages d'erreur spécifiés.</span><span class="sxs-lookup"><span data-stu-id="32e37-106">The Transfer Error Messages task can be configured to transfer all error messages, or only the specified error messages.</span></span> <span data-ttu-id="32e37-107">Les messages d'erreur définis par l'utilisateur peuvent être disponibles en différentes langues et la tâche peut être configurée pour ne transférer que les messages dans des langues sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="32e37-107">User-defined error messages may be available in a number of different languages and the task can be configured to transfer only messages in selected languages.</span></span> <span data-ttu-id="32e37-108">Une version us_english du message qui utilise la page de codes 1033 doit exister sur le serveur de destination avant que vous ne puissiez transférer d'autres versions linguistiques du message vers ce serveur.</span><span class="sxs-lookup"><span data-stu-id="32e37-108">A us_english version of the message that uses code page 1033 must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
 <span data-ttu-id="32e37-109">La table sysmessages dans la base de données master contient tous les messages d’erreur (système et définis par l’utilisateur) utilisés par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32e37-109">The sysmessages table in the master database contains all the error messages-both system and user-defined-that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses.</span></span>  
  
 <span data-ttu-id="32e37-110">Les messages définis par l'utilisateur à transférer peuvent déjà exister à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="32e37-110">The user-defined messages to be transferred may already exist on the destination.</span></span> <span data-ttu-id="32e37-111">Un message d'erreur est défini comme message d'erreur dupliqué si l'identificateur et la langue sont identiques.</span><span class="sxs-lookup"><span data-stu-id="32e37-111">An error message is defined as a duplicate error message if the identifier and the language are the same.</span></span> <span data-ttu-id="32e37-112">La tâche de transfert de messages d'erreur peut être configurée pour traiter les messages d'erreur existants de différentes manières :</span><span class="sxs-lookup"><span data-stu-id="32e37-112">The Transfer Error Messages task can be configured to handle existing error messages in the following ways:</span></span>  
  
-   <span data-ttu-id="32e37-113">Remplacer les messages d'erreur existants.</span><span class="sxs-lookup"><span data-stu-id="32e37-113">Overwrite existing error messages.</span></span>  
  
-   <span data-ttu-id="32e37-114">Provoquer l'échec de la tâche lorsque des messages dupliqués existent.</span><span class="sxs-lookup"><span data-stu-id="32e37-114">Fail the task when duplicate messages exist.</span></span>  
  
-   <span data-ttu-id="32e37-115">Ignorer les messages d'erreur dupliqués.</span><span class="sxs-lookup"><span data-stu-id="32e37-115">Skip duplicate error messages.</span></span>  
  
 <span data-ttu-id="32e37-116">À l'exécution, la tâche de transfert de messages d'erreur se connecte aux serveurs source et destination en utilisant un ou deux gestionnaires de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="32e37-116">At run time, the Transfer Error Messages task connects to the source and destination servers by using one or two SMO connection managers.</span></span> <span data-ttu-id="32e37-117">Le gestionnaire de connexions SMO est configuré indépendamment de la tâche de transfert de messages d'erreur, puis il est référencé dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="32e37-117">The SMO connection manager is configured separately from the Transfer Error Messages task, and then is referenced in the Transfer Error Messages task.</span></span> <span data-ttu-id="32e37-118">Le gestionnaire de connexions SMO spécifie le serveur et le mode d'authentification à utiliser lors de l'accès au serveur.</span><span class="sxs-lookup"><span data-stu-id="32e37-118">The SMO connection manager specifies the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="32e37-119">Pour plus d'informations, consultez [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="32e37-119">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="32e37-120">La tâche de transfert de messages d’erreur prend en charge une source et une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="32e37-120">The Transfer Error Messages task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span> <span data-ttu-id="32e37-121">Chacune des versions peut être utilisée indifféremment comme source ou comme destination.</span><span class="sxs-lookup"><span data-stu-id="32e37-121">There are no restrictions on which version to use as a source or destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="32e37-122">Événements</span><span class="sxs-lookup"><span data-stu-id="32e37-122">Events</span></span>  
 <span data-ttu-id="32e37-123">La tâche génère un événement d'information qui indique le nombre de messages d'erreur transférés.</span><span class="sxs-lookup"><span data-stu-id="32e37-123">The task raises an information event that reports the number of error messages that have been transferred.</span></span>  
  
 <span data-ttu-id="32e37-124">La tâche de transfert de messages d'erreur n'indique pas les stades intermédiaires de l'avancement du transfert des messages d'erreur : elle signale la tâche comme réalisée à 0 % ou à 100 %.</span><span class="sxs-lookup"><span data-stu-id="32e37-124">The Transfer Error Messages task does not report incremental progress of the error message transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="32e37-125">Valeur d'exécution</span><span class="sxs-lookup"><span data-stu-id="32e37-125">Execution Value</span></span>  
 <span data-ttu-id="32e37-126">La valeur d’exécution, définie dans la `ExecutionValue` propriété de la tâche, retourne le nombre de messages d’erreur qui ont été transférés.</span><span class="sxs-lookup"><span data-stu-id="32e37-126">The execution value, defined in the `ExecutionValue` property of the task, returns the number of error messages that have been transferred.</span></span> <span data-ttu-id="32e37-127">En affectant une variable définie par l'utilisateur à la propriété `ExecValueVariable` de la tâche de transfert de messages d'erreur, les informations sur le transfert de messages d'erreur peuvent être rendues disponibles aux autres objets du package.</span><span class="sxs-lookup"><span data-stu-id="32e37-127">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Error Message task, information about the error message transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="32e37-128">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="32e37-128">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="32e37-129">Entrées du journal</span><span class="sxs-lookup"><span data-stu-id="32e37-129">Log Entries</span></span>  
 <span data-ttu-id="32e37-130">La tâche de transfert de messages d'erreur comporte les entrées de journal personnalisées suivantes :</span><span class="sxs-lookup"><span data-stu-id="32e37-130">The Transfer Error Messages task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="32e37-131">TransferErrorMessagesTaskStartTransferringObjects    Cette entrée du journal indique que le transfert a commencé.</span><span class="sxs-lookup"><span data-stu-id="32e37-131">TransferErrorMessagesTaskStartTransferringObjects    This log entry reports that the transfer has started.</span></span> <span data-ttu-id="32e37-132">L'entrée du journal inclut l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="32e37-132">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="32e37-133">TransferErrorMessagesTaskFinishedTransferringObjects   Cette entrée du journal indique que le transfert est terminé.</span><span class="sxs-lookup"><span data-stu-id="32e37-133">TransferErrorMessagesTaskFinishedTransferringObjects   This log entry reports that the transfer has finished.</span></span> <span data-ttu-id="32e37-134">L'entrée du journal inclut l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="32e37-134">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="32e37-135">En outre, une entrée de journal pour l'événement `OnInformation` indique le nombre de messages d'erreur qui ont été transférés et une entrée de journal pour l'événement `OnWarning event` est générée pour chaque message d'erreur remplacé à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="32e37-135">In addition, a log entry for the `OnInformation` event reports the number of error messages that were transferred, and a log entry for the `OnWarning event` is written for each error message on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="32e37-136">Sécurité et autorisations</span><span class="sxs-lookup"><span data-stu-id="32e37-136">Security and Permissions</span></span>  
 <span data-ttu-id="32e37-137">Pour créer de nouveaux messages d'erreur, l'utilisateur qui exécute le package doit être un membre du rôle de serveur sysadmin ou serveradmin sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="32e37-137">To create new error messages, the user that runs the package must be a member of the sysadmin or serveradmin server role on the destination server.</span></span>  
  
## <a name="configuration-of-the-transfer-error-messages-task"></a><span data-ttu-id="32e37-138">Configuration de la tâche de transfert de messages d'erreur</span><span class="sxs-lookup"><span data-stu-id="32e37-138">Configuration of the Transfer Error Messages Task</span></span>  
 <span data-ttu-id="32e37-139">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="32e37-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="32e37-140">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="32e37-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="32e37-141">Éditeur de tâche de transfert de messages d’erreur &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="32e37-141">Transfer Error Messages Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="32e37-142">Éditeur de tâche de transfert de messages d’erreur &#40;page Messages&#41;</span><span class="sxs-lookup"><span data-stu-id="32e37-142">Transfer Error Messages Task Editor &#40;Messages Page&#41;</span></span>](../transfer-error-messages-task-editor-messages-page.md)  
  
-   [<span data-ttu-id="32e37-143">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="32e37-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="32e37-144">Pour plus d'informations sur la définition par programmation de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="32e37-144">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferErrorMessagesTask.TransferErrorMessagesTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="32e37-145">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="32e37-145">Related Tasks</span></span>  
 <span data-ttu-id="32e37-146">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="32e37-146">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="32e37-147">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="32e37-147">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="32e37-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32e37-148">See Also</span></span>  
 <span data-ttu-id="32e37-149">[Tâches Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="32e37-149">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="32e37-150">Flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="32e37-150">Control Flow</span></span>](control-flow.md)  
  
  
