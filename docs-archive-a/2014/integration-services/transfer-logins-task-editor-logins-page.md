---
title: Éditeur de tâche de transfert de connexions (page connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615200"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="0c27b-102">Éditeur de tâche de transfert de connexions (page Connexions)</span><span class="sxs-lookup"><span data-stu-id="0c27b-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="0c27b-103">Utilisez la page **Connexions** de la boîte de dialogue **Éditeur de tâche de transfert de connexions** pour spécifier les propriétés de copie d'une ou plusieurs connexions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] d'une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à une autre.</span><span class="sxs-lookup"><span data-stu-id="0c27b-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="0c27b-104">Pour plus d'informations sur cette tâche, consultez [Transfer Logins Task](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="0c27b-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0c27b-105">Lors de l'exécution de la tâche de transfert de connexions, les connexions sont créées sur le serveur de destination avec des mots de passe aléatoires qui sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="0c27b-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="0c27b-106">Pour utiliser ces connexions, un membre du rôle serveur fixe **sysadmin** doit changer les mots de passe et les activer.</span><span class="sxs-lookup"><span data-stu-id="0c27b-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="0c27b-107">La connexion **sa** ne peut pas être transférée.</span><span class="sxs-lookup"><span data-stu-id="0c27b-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c27b-108">Options</span><span class="sxs-lookup"><span data-stu-id="0c27b-108">Options</span></span>  
 <span data-ttu-id="0c27b-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="0c27b-109">**SourceConnection**</span></span>  
 <span data-ttu-id="0c27b-110">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="0c27b-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="0c27b-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="0c27b-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="0c27b-112">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="0c27b-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="0c27b-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="0c27b-114">Sélectionnez les connexions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à copier du serveur source au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="0c27b-115">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="0c27b-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="0c27b-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="0c27b-116">Value</span></span>|<span data-ttu-id="0c27b-117">Description</span><span class="sxs-lookup"><span data-stu-id="0c27b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c27b-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="0c27b-118">**AllLogins**</span></span>|<span data-ttu-id="0c27b-119">Toutes les connexions [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur le serveur source seront copiées sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="0c27b-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="0c27b-120">**SelectedLogins**</span></span>|<span data-ttu-id="0c27b-121">Seules les connexions spécifiées dans **LoginsList** seront copiées sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="0c27b-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="0c27b-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="0c27b-123">Toutes les connexions des bases de données spécifiées dans **DatabasesList** seront copiées sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="0c27b-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="0c27b-124">**LoginsList**</span></span>  
 <span data-ttu-id="0c27b-125">Sélectionnez les connexions sur le serveur source à copier sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="0c27b-126">Cette option est disponible uniquement lorsque **SelectedLogins** est sélectionné pour **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="0c27b-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="0c27b-127">**DatabasesList**</span></span>  
 <span data-ttu-id="0c27b-128">Sélectionnez les bases de données du serveur source qui contiennent les connexions à copier sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="0c27b-129">Cette option est disponible uniquement lorsque **AllLoginsFromSelectedDatabases** est sélectionné pour **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="0c27b-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="0c27b-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="0c27b-131">Sélectionnez la façon dont la tâche doit gérer les connexions de même nom que celles existant sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="0c27b-132">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="0c27b-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="0c27b-133">Valeur</span><span class="sxs-lookup"><span data-stu-id="0c27b-133">Value</span></span>|<span data-ttu-id="0c27b-134">Description</span><span class="sxs-lookup"><span data-stu-id="0c27b-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c27b-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="0c27b-135">**FailTask**</span></span>|<span data-ttu-id="0c27b-136">La tâche échoue si des connexions de même nom existent déjà sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="0c27b-137">**Remplacer**</span><span class="sxs-lookup"><span data-stu-id="0c27b-137">**Overwrite**</span></span>|<span data-ttu-id="0c27b-138">La tâche remplace les connexions de même nom sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="0c27b-139">**Skip**</span><span class="sxs-lookup"><span data-stu-id="0c27b-139">**Skip**</span></span>|<span data-ttu-id="0c27b-140">La tâche ignore les connexions de même nom qui existent sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="0c27b-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="0c27b-141">**CopySids**</span></span>  
 <span data-ttu-id="0c27b-142">Déterminez si les identificateurs de sécurité associés aux connexions doivent être copiés sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="0c27b-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="0c27b-143">**CopySids** doit prendre la valeur **True** si la tâche de transfert de connexions est utilisée en parallèle à la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="0c27b-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="0c27b-144">Dans le cas contraire, les connexions copiées ne seront pas reconnues par la base de données transférée.</span><span class="sxs-lookup"><span data-stu-id="0c27b-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c27b-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c27b-145">See Also</span></span>  
 <span data-ttu-id="0c27b-146">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="0c27b-147">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="0c27b-148">[Éditeur de tâche de transfert de connexions &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="0c27b-149">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="0c27b-150">[Gestionnaire de connexions SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="0c27b-151">[Mots de passe forts](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="0c27b-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="0c27b-152">Considérations sur la sécurité pour une installation SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c27b-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
