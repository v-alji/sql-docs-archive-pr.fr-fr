---
title: Référence de l’interface utilisateur de la boîte de dialogue Ajouter un gestionnaire de connexions de fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnection.f1
helpviewer_keywords:
- Add File Connection Manager
ms.assetid: 9370bfb5-5993-4ad8-a9cd-2de53f320f34
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 044d8e2eaae9db17d7155cb354f8d009750f44d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706628"
---
# <a name="add-file-connection-manager-dialog-box-ui-reference"></a><span data-ttu-id="9a3d0-102">Référence de l'interface utilisateur de la boîte de dialogue Ajouter un gestionnaire de connexions de fichiers</span><span class="sxs-lookup"><span data-stu-id="9a3d0-102">Add File Connection Manager Dialog Box UI Reference</span></span>
  <span data-ttu-id="9a3d0-103">Utilisez la boîte de dialogue **Ajouter un gestionnaire de connexions de fichiers** pour définir une connexion à un groupe de fichiers ou dossiers.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-103">Use the **Add File Connection Manager** dialog box to define a connection to a group of files or folders.</span></span>  
  
 <span data-ttu-id="9a3d0-104">Pour en savoir plus sur le gestionnaire de connexions pour plusieurs fichiers, consultez [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9a3d0-104">To learn more about the Multiple Files connection manager, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a3d0-105">Les tâches et composants de flux de données de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'utilisent pas le gestionnaire de connexions de fichiers multiples.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-105">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="9a3d0-106">Toutefois, vous pouvez utiliser ce gestionnaire de connexions dans la tâche de script ou le composant Script.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-106">However, you can use this connection manager in the Script task or Script component.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a3d0-107">Options</span><span class="sxs-lookup"><span data-stu-id="9a3d0-107">Options</span></span>  
 <span data-ttu-id="9a3d0-108">**Type d’utilisation**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-108">**Usage type**</span></span>  
 <span data-ttu-id="9a3d0-109">Spécifiez le type de fichiers à utiliser avec le gestionnaire de connexions pour plusieurs fichiers.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-109">Specify the type of files to use for the multiple files connection manager.</span></span>  
  
|<span data-ttu-id="9a3d0-110">Valeur</span><span class="sxs-lookup"><span data-stu-id="9a3d0-110">Value</span></span>|<span data-ttu-id="9a3d0-111">Description</span><span class="sxs-lookup"><span data-stu-id="9a3d0-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a3d0-112">**Créer des fichiers**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-112">**Create files**</span></span>|<span data-ttu-id="9a3d0-113">Le gestionnaire de connexions va créer les fichiers.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-113">The connection manager will create the files.</span></span>|  
|<span data-ttu-id="9a3d0-114">**Fichiers existants**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-114">**Existing files**</span></span>|<span data-ttu-id="9a3d0-115">Le gestionnaire de connexions va utiliser des fichiers existants.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-115">The connection manager will use existing files.</span></span>|  
|<span data-ttu-id="9a3d0-116">**Créer des dossiers**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-116">**Create folders**</span></span>|<span data-ttu-id="9a3d0-117">Le gestionnaire de connexions va créer les dossiers.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-117">The connection manager will create the folders.</span></span>|  
|<span data-ttu-id="9a3d0-118">**Dossiers existants**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-118">**Existing folders**</span></span>|<span data-ttu-id="9a3d0-119">Le gestionnaire de connexions va utiliser des dossiers existants.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-119">The connection manager will use existing folders.</span></span>|  
  
 <span data-ttu-id="9a3d0-120">**Fichiers / Dossiers**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-120">**Files / Folders**</span></span>  
 <span data-ttu-id="9a3d0-121">Affichez les fichiers ou dossiers que vous avez ajoutés à l'aide des boutons décrits ci-après.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-121">View the files or folders that you have added by using the buttons described as follows.</span></span>  
  
 <span data-ttu-id="9a3d0-122">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-122">**Add**</span></span>  
 <span data-ttu-id="9a3d0-123">Ajoutez un fichier à l’aide de la boîte de dialogue **Sélectionner les fichiers** ou ajoutez un dossier à l’aide de la boîte de dialogue **Rechercher un dossier** .</span><span class="sxs-lookup"><span data-stu-id="9a3d0-123">Add a file by using the **Select Files** dialog box, or add a folder by using the **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="9a3d0-124">**Modifier**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-124">**Edit**</span></span>  
 <span data-ttu-id="9a3d0-125">Sélectionnez un fichier ou dossier, puis remplacez-le par un autre fichier ou dossier à l’aide de la boîte de dialogue **Sélectionner les fichiers** ou **Rechercher un dossier** .</span><span class="sxs-lookup"><span data-stu-id="9a3d0-125">Select a file or folder, and then replace it with a different file or folder by using the **Select Files** or **Browse for Folder** dialog box.</span></span>  
  
 <span data-ttu-id="9a3d0-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-126">**Remove**</span></span>  
 <span data-ttu-id="9a3d0-127">Sélectionnez un fichier ou dossier, puis supprimez-le de la liste à l’aide du bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="9a3d0-127">Select a file or folder, and then remove it from the list by using the **Remove** button.</span></span>  
  
 <span data-ttu-id="9a3d0-128">**Boutons de direction**</span><span class="sxs-lookup"><span data-stu-id="9a3d0-128">**Arrow buttons**</span></span>  
 <span data-ttu-id="9a3d0-129">Sélectionnez un fichier ou dossier, puis utilisez les boutons de direction pour le déplacer vers le haut ou vers le bas afin de spécifier l'ordre d'accès.</span><span class="sxs-lookup"><span data-stu-id="9a3d0-129">Select a file or folder, and then use the arrow buttons to move it up or down to specify the sequence of access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a3d0-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a3d0-130">See Also</span></span>  
 [<span data-ttu-id="9a3d0-131">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="9a3d0-131">Integration Services Error and Message Reference</span></span>](../integration-services-error-and-message-reference.md)  
  
  
