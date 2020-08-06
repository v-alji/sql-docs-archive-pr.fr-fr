---
title: Éditeur de tâche de transfert de procédures stockées de Master (page procédures stockées) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703112"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="ef57f-102">Éditeur de tâche de transfert de procédures stockées de master (page Procédures stockées)</span><span class="sxs-lookup"><span data-stu-id="ef57f-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="ef57f-103">La page **Procédures stockées** de la boîte de dialogue **Éditeur de tâche de transfert de procédures stockées de master** permet de spécifier les propriétés de copie d’une ou plusieurs procédures stockées définies par l’utilisateur de la base de données **MASTER** d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vers une base de données **MASTER** d’une autre instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef57f-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ef57f-104">Pour plus d'informations sur cette tâche, consultez [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="ef57f-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef57f-105">Cette tâche transfère seulement les procédures stockées définies par l’utilisateur appartenant à **dbo** d’une base de données **MASTER** sur le serveur source vers une base de données **MASTER** sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="ef57f-106">Les utilisateurs doivent disposer de l’autorisation Créer une procédure dans la base de données **MASTER** du serveur de destination ou être membres du rôle serveur fixe **sysadmin** sur le serveur de destination pour y créer des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="ef57f-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef57f-107">Options</span><span class="sxs-lookup"><span data-stu-id="ef57f-107">Options</span></span>  
 <span data-ttu-id="ef57f-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="ef57f-108">**SourceConnection**</span></span>  
 <span data-ttu-id="ef57f-109">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="ef57f-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="ef57f-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="ef57f-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="ef57f-111">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="ef57f-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="ef57f-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="ef57f-113">Sélectionnez la façon dont la tâche doit traiter les procédures stockées définies par l’utilisateur qui existent déjà sous le même nom dans la base de données **MASTER** du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="ef57f-114">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="ef57f-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="ef57f-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="ef57f-115">Value</span></span>|<span data-ttu-id="ef57f-116">Description</span><span class="sxs-lookup"><span data-stu-id="ef57f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef57f-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="ef57f-117">**FailTask**</span></span>|<span data-ttu-id="ef57f-118">La tâche échoue si des procédures stockées du même nom existent déjà dans la base de données **MASTER** du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="ef57f-119">**Remplacer**</span><span class="sxs-lookup"><span data-stu-id="ef57f-119">**Overwrite**</span></span>|<span data-ttu-id="ef57f-120">La tâche remplace les procédures stockées du même nom dans la base de données **MASTER** du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="ef57f-121">**Skip**</span><span class="sxs-lookup"><span data-stu-id="ef57f-121">**Skip**</span></span>|<span data-ttu-id="ef57f-122">La tâche ignore les procédures stockées qui existent sous le même nom dans la base de données **MASTER** du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="ef57f-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="ef57f-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="ef57f-124">Indiquez si toutes les procédures stockées définies par l’utilisateur dans la base de données **MASTER** sur le serveur source doivent être copiées sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="ef57f-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="ef57f-125">Value</span></span>|<span data-ttu-id="ef57f-126">Description</span><span class="sxs-lookup"><span data-stu-id="ef57f-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef57f-127">**True**</span><span class="sxs-lookup"><span data-stu-id="ef57f-127">**True**</span></span>|<span data-ttu-id="ef57f-128">Copie toutes les procédures stockées définies par l’utilisateur dans la base de données **MASTER** .</span><span class="sxs-lookup"><span data-stu-id="ef57f-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="ef57f-129">**False**</span><span class="sxs-lookup"><span data-stu-id="ef57f-129">**False**</span></span>|<span data-ttu-id="ef57f-130">Copie uniquement les procédures stockées spécifiées.</span><span class="sxs-lookup"><span data-stu-id="ef57f-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="ef57f-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="ef57f-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="ef57f-132">Sélectionnez les procédures stockées définies par l’utilisateur dans la base de données **MASTER** du serveur source qui doivent être copiées dans la base de données **MASTER** de destination.</span><span class="sxs-lookup"><span data-stu-id="ef57f-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="ef57f-133">Cette option est disponible uniquement lorsque **TransferAllStoredProcedures** a la valeur **False**.</span><span class="sxs-lookup"><span data-stu-id="ef57f-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef57f-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef57f-134">See Also</span></span>  
 <span data-ttu-id="ef57f-135">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ef57f-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ef57f-136">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="ef57f-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="ef57f-137">[Éditeur de tâche de transfert de procédures stockées de Master &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="ef57f-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="ef57f-138">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="ef57f-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="ef57f-139">Gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="ef57f-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
