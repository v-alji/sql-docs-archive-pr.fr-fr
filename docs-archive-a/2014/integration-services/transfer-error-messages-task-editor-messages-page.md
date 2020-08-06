---
title: Éditeur de tâche de transfert de messages d’erreur (page messages) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615208"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="3eb9e-102">Éditeur de tâche de transfert de messages d'erreur (page Messages)</span><span class="sxs-lookup"><span data-stu-id="3eb9e-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="3eb9e-103">Utilisez la page **Messages** de la boîte de dialogue **Éditeur de tâche de transfert de messages d’erreur** pour spécifier les propriétés de copie d’un ou plusieurs messages d’erreur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] définis par l’utilisateur d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] à une autre.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="3eb9e-104">Pour plus d'informations sur cette tâche, consultez [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="3eb9e-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3eb9e-105">Options</span><span class="sxs-lookup"><span data-stu-id="3eb9e-105">Options</span></span>  
 <span data-ttu-id="3eb9e-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-106">**SourceConnection**</span></span>  
 <span data-ttu-id="3eb9e-107">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="3eb9e-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="3eb9e-109">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="3eb9e-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="3eb9e-111">Déterminez si la tâche doit remplacer les messages d'erreur définis par l'utilisateur existants, ignorer les messages existants ou échouer si des messages d'erreur du même nom existent déjà sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="3eb9e-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="3eb9e-113">Déterminez si la tâche doit copier du serveur source au serveur de destination tous les messages définis par l'utilisateur ou seulement ceux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="3eb9e-114">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="3eb9e-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="3eb9e-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="3eb9e-115">Value</span></span>|<span data-ttu-id="3eb9e-116">Description</span><span class="sxs-lookup"><span data-stu-id="3eb9e-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3eb9e-117">**True**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-117">**True**</span></span>|<span data-ttu-id="3eb9e-118">Copie tous les messages définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="3eb9e-119">**False**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-119">**False**</span></span>|<span data-ttu-id="3eb9e-120">Copie uniquement les messages définis par l'utilisateur spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="3eb9e-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="3eb9e-122">Cliquez sur le bouton Parcourir **(...)** pour sélectionner les messages d’erreur à copier.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eb9e-123">Vous devez spécifier **SourceConnection** avant de pouvoir sélectionner les messages d’erreur à copier.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="3eb9e-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="3eb9e-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="3eb9e-125">Cliquez sur le bouton Parcourir **(...)** pour sélectionner les langues pour lesquelles copier les messages d’erreur définis par l’utilisateur sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="3eb9e-126">Une version us_english (page de codes 1033) du message doit exister sur le serveur de destination avant de pouvoir transférer vers ce serveur d'autres versions de langue du message.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3eb9e-127">Vous devez spécifier **SourceConnection** avant de pouvoir sélectionner les messages d’erreur à copier.</span><span class="sxs-lookup"><span data-stu-id="3eb9e-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb9e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3eb9e-128">See Also</span></span>  
 <span data-ttu-id="3eb9e-129">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3eb9e-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3eb9e-130">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="3eb9e-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="3eb9e-131">[Éditeur de tâche de transfert de messages d’erreur &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="3eb9e-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="3eb9e-132">[Gestionnaire de connexions SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3eb9e-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="3eb9e-133">[Éditeur de tâche de transfert de messages d’erreur &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="3eb9e-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="3eb9e-134">Gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="3eb9e-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
