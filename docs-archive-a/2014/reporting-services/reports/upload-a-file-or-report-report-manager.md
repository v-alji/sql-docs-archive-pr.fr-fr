---
title: Télécharger un fichier ou un rapport (Gestionnaire de rapports) | Microsoft Docs
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
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602732"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="56b8d-102">Télécharger un fichier ou un rapport (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="56b8d-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="56b8d-103">Le Gestionnaire de rapports fournit une fonctionnalité de téléchargement qui vous permet d'ajouter des rapports, des modèles et d'autres fichiers à un serveur de rapports sans devoir publier ces éléments à partir d'une application cliente.</span><span class="sxs-lookup"><span data-stu-id="56b8d-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="56b8d-104">Les fichiers que vous téléchargez à partir du système de fichiers sont stockés en tant qu'éléments sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="56b8d-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="56b8d-105">Le type de fichier téléchargé détermine son mode de stockage :</span><span class="sxs-lookup"><span data-stu-id="56b8d-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="56b8d-106">Les fichiers .rdl sont stockés sous forme de rapports.</span><span class="sxs-lookup"><span data-stu-id="56b8d-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="56b8d-107">Les fichiers .smdl sont stockés sous forme de modèles de rapports.</span><span class="sxs-lookup"><span data-stu-id="56b8d-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="56b8d-108">Tous les autres fichiers, y compris les fichiers de sources de données partagées (.rds), sont téléchargés en tant que ressources.</span><span class="sxs-lookup"><span data-stu-id="56b8d-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="56b8d-109">Les ressources ne sont pas traitées par un serveur de rapports mais peuvent être affichées dans le Gestionnaire de rapports si le serveur de rapports prend en charge le type MIME du fichier.</span><span class="sxs-lookup"><span data-stu-id="56b8d-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="56b8d-110">Pour télécharger un fichier ou un rapport</span><span class="sxs-lookup"><span data-stu-id="56b8d-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="56b8d-111">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="56b8d-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="56b8d-112">Dans Gestionnaire de rapports, accédez à la page **contenu** .</span><span class="sxs-lookup"><span data-stu-id="56b8d-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="56b8d-113">Localisez le dossier auquel ajouter un élément.</span><span class="sxs-lookup"><span data-stu-id="56b8d-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="56b8d-114">Cliquez sur **Télécharger un fichier**.</span><span class="sxs-lookup"><span data-stu-id="56b8d-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="56b8d-115">Cliquez sur **Parcourir** pour sélectionner un fichier à charger sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="56b8d-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="56b8d-116">Vous pouvez télécharger un fichier de définition de rapport, une image, un document ou tout autre fichier que vous souhaitez rendre accessible sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="56b8d-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="56b8d-117">Tapez un nom pour le nouvel élément.</span><span class="sxs-lookup"><span data-stu-id="56b8d-117">Type a name for the new item.</span></span> <span data-ttu-id="56b8d-118">Ce nom peut comporter des espaces, mais il ne peut pas contenir les caractères réservés suivants : ; ?</span><span class="sxs-lookup"><span data-stu-id="56b8d-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="56b8d-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="56b8d-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="56b8d-120">Pour remplacer un élément existant par le nouveau, sélectionnez **Remplacer l’élément s’il existe**.</span><span class="sxs-lookup"><span data-stu-id="56b8d-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56b8d-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56b8d-121">See Also</span></span>  
 <span data-ttu-id="56b8d-122">[Créer, supprimer ou modifier une source de données partagée &#40;Gestionnaire de rapports&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56b8d-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="56b8d-123">[Page contenu &#40;Gestionnaire de rapports&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56b8d-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="56b8d-124">[Page charger un fichier &#40;Gestionnaire de rapports&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="56b8d-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="56b8d-125">Télécharger des fichiers dans un dossier</span><span class="sxs-lookup"><span data-stu-id="56b8d-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
