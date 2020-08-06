---
title: Télécharger des fichiers dans un dossier | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605065"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="1db3c-102">Télécharger des fichiers dans un dossier</span><span class="sxs-lookup"><span data-stu-id="1db3c-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="1db3c-103">Vous pouvez télécharger des fichiers à partir du système de fichiers, puis les stocker comme éléments gérés dans une base de données de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1db3c-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="1db3c-104">Ce qui se produit lorsque vous téléchargez un fichier dépend du type du fichier.</span><span class="sxs-lookup"><span data-stu-id="1db3c-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="1db3c-105">Le téléchargement d'un fichier .rdl équivaut à la publication d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="1db3c-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="1db3c-106">Le téléchargement de n'importe quel autre fichier l'ajoute à la base de données du serveur de rapports en tant qu'objet binaire unique.</span><span class="sxs-lookup"><span data-stu-id="1db3c-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="1db3c-107">Ces fichiers sont publiés sur un serveur de rapports en tant que ressource.</span><span class="sxs-lookup"><span data-stu-id="1db3c-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="1db3c-108">Les ressources peuvent être n'importe quel type de fichier.</span><span class="sxs-lookup"><span data-stu-id="1db3c-108">Resources can be any file type.</span></span> <span data-ttu-id="1db3c-109">Si l'extension de fichier correspond à un type MIME connu, une icône associée à ce type MIME est utilisée pour identifier le type de la ressource.</span><span class="sxs-lookup"><span data-stu-id="1db3c-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="1db3c-110">Sinon, une icône de fichier générique indique la présence d'une ressource.</span><span class="sxs-lookup"><span data-stu-id="1db3c-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="1db3c-111">Vous pouvez télécharger un fichier de source de données de rapports (.rds) pour créer une source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="1db3c-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="1db3c-112">Les fichiers .rds sont utilisables uniquement dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1db3c-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="1db3c-113">Ils ne peuvent en aucun cas fournir le contenu d'un élément de source de données partagée que vous définissez et gérez via le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="1db3c-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="1db3c-114">Outre le téléchargement, vous pouvez écrire un script qui crée une source de données partagée en se basant sur un fichier .rds.</span><span class="sxs-lookup"><span data-stu-id="1db3c-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="1db3c-115">La taille de fichier maximale des éléments téléchargés est déterminée par [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1db3c-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="1db3c-116">Par défaut, la taille maximale est de 4 mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="1db3c-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="1db3c-117">Sur un plan visuel, les fichiers que vous téléchargez dans une base de données de serveur de rapports s'affichent dans l'arborescence des dossiers avec les icônes suivantes.</span><span class="sxs-lookup"><span data-stu-id="1db3c-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="1db3c-118">Icône rapport ![icône](../media/hlp-16doc.gif "Icône Rapport") rapport</span><span class="sxs-lookup"><span data-stu-id="1db3c-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="1db3c-119">Icône ![de modèle icône](../media/model-icon.gif "Icône Modèle") de modèle de rapport</span><span class="sxs-lookup"><span data-stu-id="1db3c-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="1db3c-120">icône de ressource générique icône ![de ressource générique](../media/hlp-16file.gif "icône de ressource générique")</span><span class="sxs-lookup"><span data-stu-id="1db3c-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="1db3c-121">Lorsque vous téléchargez un fichier, il est toujours placé dans le dossier en cours de sélection.</span><span class="sxs-lookup"><span data-stu-id="1db3c-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="1db3c-122">Vous pouvez soit naviguer d'abord vers le dossier où l'élément sera stocké, soit télécharger un fichier puis le déplacer ultérieurement vers son emplacement définitif.</span><span class="sxs-lookup"><span data-stu-id="1db3c-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="1db3c-123">Pour télécharger un fichier, utilisez le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="1db3c-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="1db3c-124">Votre possibilité de télécharger des fichiers sur un serveur de rapports dépend des tâches incluses dans votre attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="1db3c-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="1db3c-125">Si vous utilisez la sécurité par défaut, les administrateurs locaux peuvent ajouter des éléments à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1db3c-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="1db3c-126">Si la fonctionnalité Mes rapports est activée, tout utilisateur disposant d'un dossier Mes rapports est autorisé à télécharger des éléments dans ce dossier.</span><span class="sxs-lookup"><span data-stu-id="1db3c-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="1db3c-127">Si vous utilisez des attributions de rôle personnalisées, l'attribution de rôle doit inclure les tâches prenant en charge la gestion de dossiers.</span><span class="sxs-lookup"><span data-stu-id="1db3c-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="1db3c-128">Action à réaliser</span><span class="sxs-lookup"><span data-stu-id="1db3c-128">To do this</span></span>|<span data-ttu-id="1db3c-129">Incluez ces tâches</span><span class="sxs-lookup"><span data-stu-id="1db3c-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="1db3c-130">Télécharger un fichier .rdl dans un dossier</span><span class="sxs-lookup"><span data-stu-id="1db3c-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="1db3c-131">Gérer les rapports</span><span class="sxs-lookup"><span data-stu-id="1db3c-131">Manage reports</span></span>|
|<span data-ttu-id="1db3c-132">Télécharger un fichier en tant qu'objet binaire</span><span class="sxs-lookup"><span data-stu-id="1db3c-132">Upload any file as a binary object</span></span>|<span data-ttu-id="1db3c-133">Gestion des ressources</span><span class="sxs-lookup"><span data-stu-id="1db3c-133">Manage resources</span></span>|
|<span data-ttu-id="1db3c-134">Afficher le contenu d'un dossier</span><span class="sxs-lookup"><span data-stu-id="1db3c-134">View the contents of a folder</span></span>|<span data-ttu-id="1db3c-135">Afficher les ressources, afficher les rapports</span><span class="sxs-lookup"><span data-stu-id="1db3c-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="1db3c-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1db3c-136">See Also</span></span>
 <span data-ttu-id="1db3c-137">[Gestionnaire de rapports &#40;&#41; en mode natif SSRS].. /report-manager-ssrs-native-mode.md) l’octroi d’autorisations sur [les tâches et les autorisations](../security/tasks-and-permissions.md) [du serveur de rapports en mode natif](../security/granting-permissions-on-a-native-mode-report-server.md) [charge un fichier ou un rapport &#40;gestionnaire de rapports&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="1db3c-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


