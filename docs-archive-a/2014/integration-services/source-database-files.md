---
title: Fichiers de base de données source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709703"
---
# <a name="source-database-files"></a><span data-ttu-id="46137-102">Fichiers de la base de données source</span><span class="sxs-lookup"><span data-stu-id="46137-102">Source database files</span></span>
  <span data-ttu-id="46137-103">Utilisez la boîte de dialogue **Fichiers de la base de données source** pour afficher le nom et l'emplacement des fichiers de la base de données sur le serveur source ou pour spécifier un emplacement de partage de fichiers réseau pour la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="46137-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="46137-104">Pour plus d’informations sur cette tâche, consultez [Tâche de transfert de bases de données](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="46137-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="46137-105">Pour remplir cette boîte de dialogue avec le nom et l'emplacement des fichiers de base de données sur le serveur source, spécifiez d'abord **SourceConnection** et **SourceDatabaseName** dans la page **Bases de données** de la boîte de dialogue **Éditeur de tâche de transfert de bases de données** .</span><span class="sxs-lookup"><span data-stu-id="46137-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="46137-106">Options</span><span class="sxs-lookup"><span data-stu-id="46137-106">Options</span></span>  
 <span data-ttu-id="46137-107">**Source File**</span><span class="sxs-lookup"><span data-stu-id="46137-107">**Source File**</span></span>  
 <span data-ttu-id="46137-108">Nom des fichiers de base de données sur le serveur source qui seront transférés.</span><span class="sxs-lookup"><span data-stu-id="46137-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="46137-109">Le**Fichier source** est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="46137-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="46137-110">**Dossier source**</span><span class="sxs-lookup"><span data-stu-id="46137-110">**Source Folder**</span></span>  
 <span data-ttu-id="46137-111">Dossier du serveur source où se trouvent les fichiers de base de données à transférer.</span><span class="sxs-lookup"><span data-stu-id="46137-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="46137-112">Le**Dossier source** est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="46137-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="46137-113">**Partage de fichiers réseau**</span><span class="sxs-lookup"><span data-stu-id="46137-113">**Network File Share**</span></span>  
 <span data-ttu-id="46137-114">Dossier réseau partagé du serveur source à partir duquel les fichiers de base de données seront transférés.</span><span class="sxs-lookup"><span data-stu-id="46137-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="46137-115">Utilisez le **Partage de fichiers réseau** lors du transfert d'une base de données en mode hors connexion en spécifiant **DatabaseOffline** pour **Méthode** dans la page **Bases de données** de la boîte de dialogue **Éditeur de tâche de transfert de bases de données** .</span><span class="sxs-lookup"><span data-stu-id="46137-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="46137-116">Entrez l’emplacement du partage de fichiers réseau ou cliquez sur le bouton Parcourir **(...)** pour le rechercher.</span><span class="sxs-lookup"><span data-stu-id="46137-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="46137-117">Lors du transfert d'une base de données en mode hors connexion, les fichiers de base de données sont copiés dans l'emplacement du **Partage de fichiers réseau** sur le serveur source avant d'être transférés sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="46137-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46137-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46137-118">See Also</span></span>  
 <span data-ttu-id="46137-119">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="46137-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="46137-120">[Éditeur de tâche de transfert de bases de données &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="46137-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="46137-121">Éditeur de tâche de transfert de bases de données &#40;page Bases de données&#41;</span><span class="sxs-lookup"><span data-stu-id="46137-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
