---
title: Éditeur de tâche de transfert de procédures stockées de Master (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.general.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: fa1abd4c-e2be-427f-be53-860e49c97227
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a25a5c9c6ed3802e21ac522e94163ce5fb9e8c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703116"
---
# <a name="transfer-master-stored-procedures-task-editor-general-page"></a><span data-ttu-id="725f8-102">Éditeur de tâche de transfert de procédures stockées de master (page Général)</span><span class="sxs-lookup"><span data-stu-id="725f8-102">Transfer Master Stored Procedures Task Editor (General Page)</span></span>
  <span data-ttu-id="725f8-103">Utilisez la page **Général** de la boîte de dialogue **Éditeur de tâche de transfert de procédures stockées de master** pour nommer et décrire la tâche de transfert de procédures stockées de master.</span><span class="sxs-lookup"><span data-stu-id="725f8-103">Use the **General** page of the **Transfer Master Stored Procedures Task Editor** dialog box to name and describe the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="725f8-104">Pour plus d'informations sur cette tâche, consultez [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="725f8-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="725f8-105">Cette tâche transfère seulement les procédures stockées définies par l’utilisateur appartenant à **dbo** d’une base de données **MASTER** sur le serveur source vers une base de données **MASTER** sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="725f8-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="725f8-106">Les utilisateurs doivent disposer de l’autorisation Créer une procédure dans la base de données **MASTER** du serveur de destination ou être membres du rôle serveur fixe **sysadmin** sur le serveur de destination pour y créer des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="725f8-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="725f8-107">Options</span><span class="sxs-lookup"><span data-stu-id="725f8-107">Options</span></span>  
 <span data-ttu-id="725f8-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="725f8-108">**Name**</span></span>  
 <span data-ttu-id="725f8-109">Donnez un nom unique à la tâche de transfert de procédures stockées de master.</span><span class="sxs-lookup"><span data-stu-id="725f8-109">Type a unique name for the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="725f8-110">Ce nom sert d'étiquette à l'icône de la tâche.</span><span class="sxs-lookup"><span data-stu-id="725f8-110">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="725f8-111">Les noms de tâche doivent être uniques dans un package.</span><span class="sxs-lookup"><span data-stu-id="725f8-111">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="725f8-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="725f8-112">**Description**</span></span>  
 <span data-ttu-id="725f8-113">Entrez une description de la tâche de transfert de procédures stockées de master.</span><span class="sxs-lookup"><span data-stu-id="725f8-113">Type a description of the Transfer Master Stored Procedures task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="725f8-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="725f8-114">See Also</span></span>  
 <span data-ttu-id="725f8-115">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="725f8-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="725f8-116">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="725f8-116">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="725f8-117">[Éditeur de tâche de transfert de procédures stockées de Master &#40;page procédures stockées&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span><span class="sxs-lookup"><span data-stu-id="725f8-117">[Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span></span>  
 [<span data-ttu-id="725f8-118">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="725f8-118">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
