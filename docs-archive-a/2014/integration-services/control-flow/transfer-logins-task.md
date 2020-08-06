---
title: Transférer des connexions, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.f1
helpviewer_keywords:
- Transfer Logins task [Integration Services]
ms.assetid: 1df60fd6-c019-405d-8155-c330dbac2cc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d42d39b6cc7c2f350e3e3adc774be23934981369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600166"
---
# <a name="transfer-logins-task"></a><span data-ttu-id="6dc47-102">Tâche de transfert de connexions</span><span class="sxs-lookup"><span data-stu-id="6dc47-102">Transfer Logins Task</span></span>
  <span data-ttu-id="6dc47-103">La tâche de transfert de connexions transfère une ou plusieurs connexions entre des instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dc47-103">The Transfer Logins task transfers one or more logins between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="transfer-logins-between-instances-of-sql-server"></a><span data-ttu-id="6dc47-104">Transférer des connexions entre des instances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6dc47-104">Transfer Logins Between Instances of SQL Server</span></span>  
 <span data-ttu-id="6dc47-105">La tâche de transfert de connexions prend en charge une source et une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dc47-105">The Transfer Logins task supports a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source and destination.</span></span>  
  
## <a name="events"></a><span data-ttu-id="6dc47-106">Événements</span><span class="sxs-lookup"><span data-stu-id="6dc47-106">Events</span></span>  
 <span data-ttu-id="6dc47-107">La tâche génère un événement d'information qui indique le nombre de connexions transférées et un événement d'avertissement quand une connexion est remplacée.</span><span class="sxs-lookup"><span data-stu-id="6dc47-107">The task raises an information event that reports the number of logins transferred and a warning event when a login is overwritten.</span></span>  
  
 <span data-ttu-id="6dc47-108">La tâche de transfert des connexions n'indique pas les stades intermédiaires de l'avancement du transfert des connexions : elle signale la tâche comme réalisée à 0 % ou à 100 %.</span><span class="sxs-lookup"><span data-stu-id="6dc47-108">The Transfer Logins task does not report incremental progress of the login transfer; it reports only 0% and 100 % completion.</span></span>  
  
## <a name="execution-value"></a><span data-ttu-id="6dc47-109">Valeur d'exécution</span><span class="sxs-lookup"><span data-stu-id="6dc47-109">Execution Value</span></span>  
 <span data-ttu-id="6dc47-110">La valeur d'exécution, définie dans la propriété `ExecutionValue` de la tâche, renvoie le nombre de connexions transférées.</span><span class="sxs-lookup"><span data-stu-id="6dc47-110">The execution value, defined in the `ExecutionValue` property of the task, returns the number of logins transferred.</span></span> <span data-ttu-id="6dc47-111">En affectant une variable définie par l'utilisateur à la propriété `ExecValueVariable` de la tâche de transfert de connexions, les informations sur le transfert des connexions peuvent être rendues disponibles pour d'autres objets du package.</span><span class="sxs-lookup"><span data-stu-id="6dc47-111">By assigning a user-defined variable to the `ExecValueVariable` property of the Transfer Logins task, information about the login transfer can be made available to other objects in the package.</span></span> <span data-ttu-id="6dc47-112">Pour plus d’informations, consultez [Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) et [Utiliser des variables dans des packages](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6dc47-112">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>  
  
## <a name="log-entries"></a><span data-ttu-id="6dc47-113">Entrées du journal</span><span class="sxs-lookup"><span data-stu-id="6dc47-113">Log Entries</span></span>  
 <span data-ttu-id="6dc47-114">La tâche de transfert des connexions comporte les entrées du journal personnalisées suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc47-114">The Transfer Logins task includes the following custom log entries:</span></span>  
  
-   <span data-ttu-id="6dc47-115">TransferLoginsTaskStarTransferringObjects   Cette entrée du journal indique que le transfert a commencé.</span><span class="sxs-lookup"><span data-stu-id="6dc47-115">TransferLoginsTaskStarTransferringObjects    This log entry reports the transfer has started.</span></span> <span data-ttu-id="6dc47-116">L'entrée du journal inclut l'heure de début.</span><span class="sxs-lookup"><span data-stu-id="6dc47-116">The log entry includes the start time.</span></span>  
  
-   <span data-ttu-id="6dc47-117">TransferLoginsTaskFinishedTransferringObjects   Cette entrée du journal indique que le transfert est terminé.</span><span class="sxs-lookup"><span data-stu-id="6dc47-117">TransferLoginsTaskFinishedTransferringObjects   This log entry reports the transfer has completed.</span></span> <span data-ttu-id="6dc47-118">L'entrée du journal inclut l'heure de fin.</span><span class="sxs-lookup"><span data-stu-id="6dc47-118">The log entry includes the end time.</span></span>  
  
 <span data-ttu-id="6dc47-119">En outre, une entrée de journal pour l'événement `OnInformation` indique le nombre de connexions qui ont été transférées et une entrée de journal pour l'événement `OnWarning` est générée pour chaque connexion remplacée à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="6dc47-119">In addition, a log entry for the `OnInformation` event reports the number of logins that were transferred, and a log entry for the `OnWarning` event is written for each login on the destination that is overwritten.</span></span>  
  
## <a name="security-and-permissions"></a><span data-ttu-id="6dc47-120">Sécurité et autorisations</span><span class="sxs-lookup"><span data-stu-id="6dc47-120">Security and Permissions</span></span>  
 <span data-ttu-id="6dc47-121">Pour parcourir les connexions sur le serveur source et créer des connexions sur le serveur de destination, l'utilisateur doit être un membre du rôle de serveur sysadmin sur les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="6dc47-121">To browse logins on the source server and to create logins on the destination server, the user must be a member of the sysadmin server role on both servers.</span></span>  
  
## <a name="configuration-of-the-transfer-logins-task"></a><span data-ttu-id="6dc47-122">Configuration de la tâche de transfert des connexions</span><span class="sxs-lookup"><span data-stu-id="6dc47-122">Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="6dc47-123">La tâche de transfert de connexions peut être configurée pour transférer toutes les connexions, seulement les connexions spécifiées ou toutes les connexions ayant accès à une base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="6dc47-123">The Transfer Logins task can be configured to transfer all logins, only specified logins, or all logins that have access to specified databases only.</span></span> <span data-ttu-id="6dc47-124">La connexion sa ne peut pas être transférée.</span><span class="sxs-lookup"><span data-stu-id="6dc47-124">The sa login cannot be transferred.</span></span> <span data-ttu-id="6dc47-125">La connexion sa peut être renommée ; cependant, la connexion sa renommée ne peut pas être transférée non plus.</span><span class="sxs-lookup"><span data-stu-id="6dc47-125">The sa login may be renamed; however, the renamed sa login cannot be transferred either.</span></span>  
  
 <span data-ttu-id="6dc47-126">Vous pouvez également indiquer si la tâche copie les identificateurs de sécurité (SID) associés aux connexions.</span><span class="sxs-lookup"><span data-stu-id="6dc47-126">You can also indicate whether the task copies the security identifiers (SIDs) associated with the logins.</span></span> <span data-ttu-id="6dc47-127">Si la tâche de transfert des connexions est utilisée en conjonction avec la tâche de transfert des bases de données, les SID doivent être copiés à l'emplacement de destination ; si ce n'est pas le cas, les connexions transférées ne sont pas reconnues par la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="6dc47-127">If the Transfer Logins task is used in conjunction with the Transfer Database task the SIDs must be copied to the destination; otherwise, the transferred logins are not recognized by the destination database.</span></span>  
  
 <span data-ttu-id="6dc47-128">À l'emplacement de destination, les connexions transférées sont désactivées et des mots de passe aléatoires leur sont affectés.</span><span class="sxs-lookup"><span data-stu-id="6dc47-128">At the destination, the transferred logins are disabled and assigned random passwords.</span></span> <span data-ttu-id="6dc47-129">Un membre du rôle sysadmin sur le serveur de destination doit modifier les mots de passe et activer les connexions avant que ces dernières puissent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="6dc47-129">A member of the sysadmin role on the destination server must change the passwords and enable the logins before the logins can be used.</span></span>  
  
 <span data-ttu-id="6dc47-130">Les connexions à transférer peuvent déjà exister à l'emplacement de destination.</span><span class="sxs-lookup"><span data-stu-id="6dc47-130">The logins to be transferred may already exist on the destination.</span></span> <span data-ttu-id="6dc47-131">La tâche de transfert des connexions peut être configurée pour traiter les connexions existantes de différentes manières :</span><span class="sxs-lookup"><span data-stu-id="6dc47-131">The Transfer Logins task can be configured to handle existing logins in the following ways:</span></span>  
  
-   <span data-ttu-id="6dc47-132">Remplacer les connexions existantes</span><span class="sxs-lookup"><span data-stu-id="6dc47-132">Overwrite existing logins.</span></span>  
  
-   <span data-ttu-id="6dc47-133">Provoquer l'échec de la tâche lorsque des connexions dupliquées existent.</span><span class="sxs-lookup"><span data-stu-id="6dc47-133">Fail the task when duplicate logins exist.</span></span>  
  
-   <span data-ttu-id="6dc47-134">Ignorer les connexions dupliquées</span><span class="sxs-lookup"><span data-stu-id="6dc47-134">Skip duplicate logins.</span></span>  
  
 <span data-ttu-id="6dc47-135">À l'exécution, la tâche de transfert des connexions se connecte aux serveurs source et destination en utilisant deux gestionnaires de connexions SMO.</span><span class="sxs-lookup"><span data-stu-id="6dc47-135">At run time, the Transfer Logins task connects to the source and destination servers by using two SMO connection managers.</span></span> <span data-ttu-id="6dc47-136">Les gestionnaires de connexions SMO sont configurés indépendamment de la tâche de transfert des connexions, puis référencés dans celle-ci.</span><span class="sxs-lookup"><span data-stu-id="6dc47-136">The SMO connection managers are configured separately from the Transfer Logins task, and then referenced in the Transfer Logins task.</span></span> <span data-ttu-id="6dc47-137">Les gestionnaires de connexions SMO spécifient le serveur et le mode d'authentification à utiliser lors de l'accès au serveur.</span><span class="sxs-lookup"><span data-stu-id="6dc47-137">The SMO connection managers specify the server and the authentication mode to use when accessing the server.</span></span> <span data-ttu-id="6dc47-138">Pour plus d'informations, consultez [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6dc47-138">For more information, see [SMO Connection Manager](../connection-manager/smo-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6dc47-139">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="6dc47-139">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="6dc47-140">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6dc47-140">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="6dc47-141">Éditeur de tâche de transfert de connexions &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="6dc47-141">Transfer Logins Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="6dc47-142">Éditeur de tâche de transfert de connexions &#40;page Connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="6dc47-142">Transfer Logins Task Editor &#40;Logins Page&#41;</span></span>](../transfer-logins-task-editor-logins-page.md)  
  
-   [<span data-ttu-id="6dc47-143">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="6dc47-143">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="6dc47-144">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="6dc47-144">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="6dc47-145">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="6dc47-145">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-transfer-logins-task"></a><span data-ttu-id="6dc47-146">Configuration de la tâche de transfert des connexions par programme</span><span class="sxs-lookup"><span data-stu-id="6dc47-146">Programmatic Configuration of the Transfer Logins Task</span></span>  
 <span data-ttu-id="6dc47-147">Pour plus d'informations sur la définition par programme de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="6dc47-147">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.TransferLoginsTask.TransferLoginsTask>  
  
  
