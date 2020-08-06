---
title: Mettre à jour une ressource (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605066"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="a3927-102">mise à jour d'une ressource (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="a3927-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="a3927-103">Vous pouvez mettre à jour une ressource en la remplaçant par une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="a3927-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="a3927-104">Les ressources sont des éléments stockés sur un serveur de rapports qui tirent leur contenu des fichiers que vous téléchargez.</span><span class="sxs-lookup"><span data-stu-id="a3927-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="a3927-105">Vous pouvez remplacer une ressource existante en important du contenu de fichier inédit ou différent dans la ressource existante.</span><span class="sxs-lookup"><span data-stu-id="a3927-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="a3927-106">La mise à jour d'une ressource permet d'actualiser du contenu tout en préservant les propriétés existantes et les paramètres de sécurité définis sur la ressource.</span><span class="sxs-lookup"><span data-stu-id="a3927-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="a3927-107">Pour mettre à jour une ressource</span><span class="sxs-lookup"><span data-stu-id="a3927-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="a3927-108">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a3927-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="a3927-109">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'à la ressource à mettre à jour ou effectuez une recherche pour la localiser.</span><span class="sxs-lookup"><span data-stu-id="a3927-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="a3927-110">Cliquez sur la ressource pour l’ouvrir dans la page **Vue** .</span><span class="sxs-lookup"><span data-stu-id="a3927-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="a3927-111">Cliquez sur **Propriétés** pour ouvrir la page de propriétés **Général** .</span><span class="sxs-lookup"><span data-stu-id="a3927-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="a3927-112">Cliquez sur **Remplacer** pour ouvrir la page **Importer une ressource** .</span><span class="sxs-lookup"><span data-stu-id="a3927-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="a3927-113">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="a3927-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="a3927-114">Sélectionnez le fichier que vous voulez substituer à la ressource actuelle.</span><span class="sxs-lookup"><span data-stu-id="a3927-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="a3927-115">Vous pouvez utiliser une version mise à jour du fichier de ressources ou spécifier un fichier avec un nom ou un type de fichier différent.</span><span class="sxs-lookup"><span data-stu-id="a3927-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="a3927-116">Cliquez sur **OK** pour charger le fichier de ressources, fermez la page **Importer une ressource** et enregistrez les modifications sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a3927-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="a3927-117">Si la ressource en cours de mise à jour contient une image utilisée dans un rapport, vous devez actualiser le rapport pour afficher l'image mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a3927-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3927-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3927-118">See Also</span></span>  
 <span data-ttu-id="a3927-119">[Page contenu &#40;Gestionnaire de rapports&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a3927-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="a3927-120">[Page charger un fichier &#40;Gestionnaire de rapports&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a3927-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="a3927-121">[Charger des fichiers dans un dossier](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="a3927-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="a3927-122">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="a3927-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
