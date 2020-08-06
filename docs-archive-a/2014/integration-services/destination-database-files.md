---
title: Fichiers de base de données de destination | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613562"
---
# <a name="destination-database-files"></a><span data-ttu-id="f62ad-102">Fichiers de la base de données de destination</span><span class="sxs-lookup"><span data-stu-id="f62ad-102">Destination Database Files</span></span>
  <span data-ttu-id="f62ad-103">Utilisez la boîte de dialogue **Fichiers de la base de données de destination** pour afficher ou modifier le nom et l'emplacement des fichiers de la base de données sur le serveur de destination ou pour spécifier un emplacement de fichier réseau pour la tâche de transfert de bases de données.</span><span class="sxs-lookup"><span data-stu-id="f62ad-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="f62ad-104">Pour plus d’informations sur cette tâche, consultez [Tâche de transfert de bases de données](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="f62ad-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="f62ad-105">Pour remplir automatiquement cette boîte de dialogue avec le nom et l'emplacement des fichiers de base de données sur le serveur source, spécifiez d'abord **SourceConnection**, **SourceDatabaseName**et **SourceDatabaseFiles** dans la page **Bases de données** de la boîte de dialogue **Éditeur de tâche de transfert de bases de données** .</span><span class="sxs-lookup"><span data-stu-id="f62ad-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f62ad-106">Options</span><span class="sxs-lookup"><span data-stu-id="f62ad-106">Options</span></span>  
 <span data-ttu-id="f62ad-107">**Fichier de destination**</span><span class="sxs-lookup"><span data-stu-id="f62ad-107">**Destination File**</span></span>  
 <span data-ttu-id="f62ad-108">Nom des fichiers de la base de données transférés sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="f62ad-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="f62ad-109">Entrez le nom du fichier ou cliquez dessus pour le modifier.</span><span class="sxs-lookup"><span data-stu-id="f62ad-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="f62ad-110">**Dossier de destination**</span><span class="sxs-lookup"><span data-stu-id="f62ad-110">**Destination Folder**</span></span>  
 <span data-ttu-id="f62ad-111">Dossier du serveur de destination où les fichiers de la base de données seront transférés.</span><span class="sxs-lookup"><span data-stu-id="f62ad-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="f62ad-112">Entrez le chemin d'accès au dossier, cliquez dessus pour le modifier ou cliquez sur Parcourir pour rechercher le dossier dans lequel transférer les fichiers de la base de données sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="f62ad-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="f62ad-113">**Partage de fichiers réseau**</span><span class="sxs-lookup"><span data-stu-id="f62ad-113">**Network File Share**</span></span>  
 <span data-ttu-id="f62ad-114">Dossier réseau partagé du serveur de destination où les fichiers de la base de données seront transférés.</span><span class="sxs-lookup"><span data-stu-id="f62ad-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="f62ad-115">Utilisez le **Partage de fichiers réseau** lors du transfert d'une base de données en mode hors connexion en spécifiant **DatabaseOffline** pour **Méthode** dans la page **Bases de données** de la boîte de dialogue **Éditeur de tâche de transfert de bases de données** .</span><span class="sxs-lookup"><span data-stu-id="f62ad-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="f62ad-116">Entrez l'emplacement du partage de fichiers réseau ou cliquez sur le bouton Parcourir pour le rechercher.</span><span class="sxs-lookup"><span data-stu-id="f62ad-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="f62ad-117">Lors du transfert d'une base de données en mode hors connexion, les fichiers de base de données sont copiés dans l'emplacement du **Partage de fichiers réseau** avant d'être transférés dans l'emplacement **Dossier de destination** .</span><span class="sxs-lookup"><span data-stu-id="f62ad-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f62ad-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f62ad-118">See Also</span></span>  
 <span data-ttu-id="f62ad-119">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f62ad-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f62ad-120">[Éditeur de tâche de transfert de bases de données &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="f62ad-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="f62ad-121">Éditeur de tâche de transfert de bases de données &#40;page Bases de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f62ad-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
