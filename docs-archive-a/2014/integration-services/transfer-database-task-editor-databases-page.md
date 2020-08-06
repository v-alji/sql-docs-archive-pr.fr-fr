---
title: Éditeur de tâche de transfert de bases de données (page bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.database.f1
helpviewer_keywords:
- Transfer Database Task Editor
ms.assetid: ccdb74d0-4bea-420c-a726-2e0eb8957e0a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df4452e28a32463a7825e9c64cfd053f98c53ee8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694643"
---
# <a name="transfer-database-task-editor-databases-page"></a><span data-ttu-id="a10b1-102">Éditeur de tâche de transfert de bases de données (page Bases de données)</span><span class="sxs-lookup"><span data-stu-id="a10b1-102">Transfer Database Task Editor (Databases Page)</span></span>
  <span data-ttu-id="a10b1-103">Utilisez la page **Bases de données** de la boîte de dialogue **Éditeur de tâche de transfert de bases de données** pour spécifier les propriétés des bases de données source et de destination concernées par la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="a10b1-103">Use the **Databases** page of the **Transfer Database Task Editor** dialog box to specify properties for the source and destination databases involved in the Transfer Database task.</span></span> <span data-ttu-id="a10b1-104">La tâche de transfert de bases de données copie ou déplace une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] entre deux instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a10b1-104">The Transfer Database task copies or moves a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database between two instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a10b1-105">Cette tâche peut également servir à copier une base de données sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="a10b1-105">This task can also be used to copy a database within the same server.</span></span> <span data-ttu-id="a10b1-106">Pour plus d’informations sur cette tâche, consultez [Tâche de transfert de bases de données](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="a10b1-106">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a10b1-107">Options</span><span class="sxs-lookup"><span data-stu-id="a10b1-107">Options</span></span>  
 <span data-ttu-id="a10b1-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="a10b1-108">**SourceConnection**</span></span>  
 <span data-ttu-id="a10b1-109">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="a10b1-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="a10b1-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="a10b1-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="a10b1-111">Sélectionnez un gestionnaire de connexion SMO dans la liste ou cliquez sur **\<New connection...>** pour créer une connexion au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="a10b1-112">**DestinationDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a10b1-112">**DestinationDatabaseName**</span></span>  
 <span data-ttu-id="a10b1-113">Spécifiez le nom de la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-113">Specify the name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database on the destination server.</span></span>  
  
 <span data-ttu-id="a10b1-114">Pour remplir automatiquement ce champ avec le nom de la base de données source, spécifiez d’abord **SourceConnection** et **SourceDatabaseName** .</span><span class="sxs-lookup"><span data-stu-id="a10b1-114">To automatically populate this field with the source database name, specify the **SourceConnection** and **SourceDatabaseName** first.</span></span>  
  
 <span data-ttu-id="a10b1-115">Pour renommer la base de données sur le serveur de destination, tapez son nouveau nom dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="a10b1-115">To rename the database on the destination server, type the new name in this field.</span></span>  
  
 <span data-ttu-id="a10b1-116">**DestinationDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="a10b1-116">**DestinationDatabaseFiles**</span></span>  
 <span data-ttu-id="a10b1-117">Spécifiez le nom et l'emplacement des fichiers de base de données sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-117">Specifies the names and locations of the database files on the destination server.</span></span>  
  
 <span data-ttu-id="a10b1-118">Pour remplir automatiquement ce champ avec le nom de la base de données source, spécifiez d’abord **SourceConnection**, **SourceDatabaseName**et **SourceDatabaseFiles** .</span><span class="sxs-lookup"><span data-stu-id="a10b1-118">To automatically populate this field with the source database file names and locations, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first.</span></span>  
  
 <span data-ttu-id="a10b1-119">Pour renommer les fichiers de base de données ou pour spécifier les nouveaux emplacements sur le serveur de destination, remplissez ce champ avec les informations sur la base de données source, puis cliquez sur le bouton Parcourir.</span><span class="sxs-lookup"><span data-stu-id="a10b1-119">To rename the database files or to specify the new locations on the destination server, populate this field with the source database information, and then click the browse button.</span></span> <span data-ttu-id="a10b1-120">Dans la boîte de dialogue **Fichiers de la base de données de destination** , modifiez **Fichier de destination**, **Dossier de destination**ou **Partage de fichiers réseau**.</span><span class="sxs-lookup"><span data-stu-id="a10b1-120">In the **Destination database files** dialog box, edit the **Destination File**, **Destination Folder**, or **Network File Share**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a10b1-121">Si vous trouvez l’emplacement des fichiers de la base de données à l’aide du bouton Parcourir, l’emplacement des fichiers est entré en utilisant la notation de lecteur local : par exemple, c:\\.</span><span class="sxs-lookup"><span data-stu-id="a10b1-121">If you locate the database files by using the browse button, the file location is entered using the local drive notation: for example, c:\\.</span></span> <span data-ttu-id="a10b1-122">Vous devez remplacer cette notation par la notation de partage réseau, qui comporte le nom de l'ordinateur et le nom du partage.</span><span class="sxs-lookup"><span data-stu-id="a10b1-122">You must replace this with the network share notation, including the computer name and share name.</span></span> <span data-ttu-id="a10b1-123">Si le partage administratif par défaut est utilisé, vous devez utiliser la notation $ et disposer d'un accès administratif au partage.</span><span class="sxs-lookup"><span data-stu-id="a10b1-123">If the default administrative share is used, you must use the $ notation, and have administrative access to the share.</span></span>  
  
 <span data-ttu-id="a10b1-124">**DestinationOverwrite**</span><span class="sxs-lookup"><span data-stu-id="a10b1-124">**DestinationOverwrite**</span></span>  
 <span data-ttu-id="a10b1-125">Spécifiez si la base de données sur le serveur de destination peut être remplacée.</span><span class="sxs-lookup"><span data-stu-id="a10b1-125">Specify whether the database on the destination server can be overwritten.</span></span>  
  
 <span data-ttu-id="a10b1-126">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="a10b1-126">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a10b1-127">Valeur</span><span class="sxs-lookup"><span data-stu-id="a10b1-127">Value</span></span>|<span data-ttu-id="a10b1-128">Description</span><span class="sxs-lookup"><span data-stu-id="a10b1-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a10b1-129">**True**</span><span class="sxs-lookup"><span data-stu-id="a10b1-129">**True**</span></span>|<span data-ttu-id="a10b1-130">Remplace la base de données du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-130">Overwrite destination server database.</span></span>|  
|<span data-ttu-id="a10b1-131">**False**</span><span class="sxs-lookup"><span data-stu-id="a10b1-131">**False**</span></span>|<span data-ttu-id="a10b1-132">Ne remplace pas la base de données du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-132">Do not overwrite destination server database.</span></span>|  
  
> [!CAUTION]  
>  <span data-ttu-id="a10b1-133">Les données de la base de données du serveur de destination seront remplacées si vous spécifiez **True** pour **DestinationOverwrite**, ce qui peut provoquer la perte de données.</span><span class="sxs-lookup"><span data-stu-id="a10b1-133">The data in the destination server database will be overwritten if you specify **True** for **DestinationOverwrite**, which may result in data loss.</span></span> <span data-ttu-id="a10b1-134">Pour l'éviter, sauvegardez la base de données du serveur de destination dans un autre emplacement avant d'exécuter la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="a10b1-134">To avoid this, back up the destination server database to another location before executing the Transfer Database task.</span></span>  
  
 <span data-ttu-id="a10b1-135">**Action**</span><span class="sxs-lookup"><span data-stu-id="a10b1-135">**Action**</span></span>  
 <span data-ttu-id="a10b1-136">Spécifiez si la tâche doit **Copier** ou **Déplacer** la base de données sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="a10b1-136">Specify whether the task will **Copy** or **Move** the database to the destination server.</span></span>  
  
 <span data-ttu-id="a10b1-137">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="a10b1-137">**Method**</span></span>  
 <span data-ttu-id="a10b1-138">Spécifiez si la tâche est exécutée pendant que la base de données sur le serveur source est en ligne ou en mode hors connexion.</span><span class="sxs-lookup"><span data-stu-id="a10b1-138">Specify whether the task will be executed while the database on the source server is in online or offline mode.</span></span>  
  
 <span data-ttu-id="a10b1-139">Pour transférer une base de données en mode hors connexion, l’utilisateur qui exécute le package doit être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="a10b1-139">To transfer a database using offline mode, the user that runs the package must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="a10b1-140">Pour transférer une base de données en mode en ligne, l’utilisateur qui exécute le package doit être membre du rôle serveur fixe **sysadmin** ou propriétaire de la base de données sélectionnée (**dbo**).</span><span class="sxs-lookup"><span data-stu-id="a10b1-140">To transfer a database using the online mode, the user that runs the package must be a member of the **sysadmin** fixed server role, or the database owner (**dbo**) of the selected database.</span></span>  
  
 <span data-ttu-id="a10b1-141">**SourceDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a10b1-141">**SourceDatabaseName**</span></span>  
 <span data-ttu-id="a10b1-142">Sélectionnez le nom de la base de données à copier ou à déplacer.</span><span class="sxs-lookup"><span data-stu-id="a10b1-142">Select the name of the database to be copied or moved.</span></span>  
  
 <span data-ttu-id="a10b1-143">**SourceDatabaseFiles**</span><span class="sxs-lookup"><span data-stu-id="a10b1-143">**SourceDatabaseFiles**</span></span>  
 <span data-ttu-id="a10b1-144">Cliquez sur le bouton Parcourir pour sélectionner les fichiers de base de données.</span><span class="sxs-lookup"><span data-stu-id="a10b1-144">Click the browse button to select the database files.</span></span>  
  
 <span data-ttu-id="a10b1-145">**ReattachSourceDatabase**</span><span class="sxs-lookup"><span data-stu-id="a10b1-145">**ReattachSourceDatabase**</span></span>  
 <span data-ttu-id="a10b1-146">Spécifiez si la tâche va tenter de rattacher la base de données source en cas d'échec.</span><span class="sxs-lookup"><span data-stu-id="a10b1-146">Specify whether the task will attempt to reattach the source database if a failure occurs.</span></span>  
  
 <span data-ttu-id="a10b1-147">Cette propriété dispose des options répertoriées dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="a10b1-147">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a10b1-148">Valeur</span><span class="sxs-lookup"><span data-stu-id="a10b1-148">Value</span></span>|<span data-ttu-id="a10b1-149">Description</span><span class="sxs-lookup"><span data-stu-id="a10b1-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a10b1-150">**True**</span><span class="sxs-lookup"><span data-stu-id="a10b1-150">**True**</span></span>|<span data-ttu-id="a10b1-151">Rattache la base de données source.</span><span class="sxs-lookup"><span data-stu-id="a10b1-151">Reattach source database.</span></span>|  
|<span data-ttu-id="a10b1-152">**False**</span><span class="sxs-lookup"><span data-stu-id="a10b1-152">**False**</span></span>|<span data-ttu-id="a10b1-153">Ne rattache pas la base de données source.</span><span class="sxs-lookup"><span data-stu-id="a10b1-153">Do not reattach source database.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a10b1-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a10b1-154">See Also</span></span>  
 <span data-ttu-id="a10b1-155">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a10b1-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a10b1-156">[Tâches Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a10b1-156">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="a10b1-157">[Éditeur de tâche de transfert de bases de données &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a10b1-157">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a10b1-158">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a10b1-158">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="a10b1-159">Gestionnaire de connexions SMO</span><span class="sxs-lookup"><span data-stu-id="a10b1-159">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
