---
title: Éditeur du gestionnaire de connexions de fichiers | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileconnectionmanager.f1
helpviewer_keywords:
- File Connection Manager Editor
ms.assetid: 051c48e5-3d86-49af-b554-ff62e3de3622
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f3261b836d4800787fc078b05b15e469d3c200d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613013"
---
# <a name="file-connection-manager-editor"></a><span data-ttu-id="1379b-102">Éditeur du gestionnaire de connexions de fichiers</span><span class="sxs-lookup"><span data-stu-id="1379b-102">File Connection Manager Editor</span></span>
  <span data-ttu-id="1379b-103">Utilisez la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers** pour spécifier les propriétés à utiliser pour se connecter à un fichier ou à un dossier.</span><span class="sxs-lookup"><span data-stu-id="1379b-103">Use the **File Connection Manager Editor** dialog box to specify the properties used to connect to a file or a folder.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1379b-104">Vous pouvez définir la propriété ConnectionString du gestionnaire de connexions de fichiers en spécifiant une expression dans la fenêtre Propriétés de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1379b-104">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="1379b-105">Toutefois, pour éviter une erreur de validation lorsque vous utilisez une expression pour spécifier le fichier ou le dossier, dans l' **éditeur du gestionnaire de connexions de fichiers**, pour **fichier/dossier**, ajoutez un chemin d’accès de fichier ou de dossier.</span><span class="sxs-lookup"><span data-stu-id="1379b-105">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="1379b-106">Pour en savoir plus sur le gestionnaire de connexions de fichiers, consultez [File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="1379b-106">To learn more about the File connection manager, see [File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1379b-107">Options</span><span class="sxs-lookup"><span data-stu-id="1379b-107">Options</span></span>  
 <span data-ttu-id="1379b-108">**Type d'utilisation**</span><span class="sxs-lookup"><span data-stu-id="1379b-108">**Usage Type**</span></span>  
 <span data-ttu-id="1379b-109">Indiquez si le **Gestionnaire de connexions de fichiers** se connecte à un fichier ou dossier existant ou s’il crée un nouveau fichier ou dossier.</span><span class="sxs-lookup"><span data-stu-id="1379b-109">Specify whether the **File Connection Manager** connects to an existing file or folder or creates a new file or folder.</span></span>  
  
|<span data-ttu-id="1379b-110">Valeur</span><span class="sxs-lookup"><span data-stu-id="1379b-110">Value</span></span>|<span data-ttu-id="1379b-111">Description</span><span class="sxs-lookup"><span data-stu-id="1379b-111">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1379b-112">Créer un fichier</span><span class="sxs-lookup"><span data-stu-id="1379b-112">Create file</span></span>|<span data-ttu-id="1379b-113">Crée un nouveau fichier au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="1379b-113">Create a new file at run time.</span></span>|  
|<span data-ttu-id="1379b-114">Fichier existant</span><span class="sxs-lookup"><span data-stu-id="1379b-114">Existing file</span></span>|<span data-ttu-id="1379b-115">Utilise un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="1379b-115">Use an existing file.</span></span>|  
|<span data-ttu-id="1379b-116">Créer un dossier</span><span class="sxs-lookup"><span data-stu-id="1379b-116">Create folder</span></span>|<span data-ttu-id="1379b-117">Crée un nouveau dossier au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="1379b-117">Create a new folder at run time.</span></span>|  
|<span data-ttu-id="1379b-118">Dossier existant</span><span class="sxs-lookup"><span data-stu-id="1379b-118">Existing folder</span></span>|<span data-ttu-id="1379b-119">Utilise un dossier existant.</span><span class="sxs-lookup"><span data-stu-id="1379b-119">Use an existing folder.</span></span>|  
  
 <span data-ttu-id="1379b-120">**Fichier / Dossier**</span><span class="sxs-lookup"><span data-stu-id="1379b-120">**File / Folder**</span></span>  
 <span data-ttu-id="1379b-121">Si **Fichier**, spécifiez le fichier à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1379b-121">If **File**, specify the file to use.</span></span>  
  
 <span data-ttu-id="1379b-122">Si **Dossier**, spécifiez le dossier à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1379b-122">If **Folder**, specify the folder to use.</span></span>  
  
 <span data-ttu-id="1379b-123">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="1379b-123">**Browse**</span></span>  
 <span data-ttu-id="1379b-124">Sélectionnez le fichier ou le dossier à l’aide de la boîte de dialogue **Sélectionner un fichier** ou **Rechercher un dossier** .</span><span class="sxs-lookup"><span data-stu-id="1379b-124">Select the file or folder by using the **Select File** or **Browse for Folder** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1379b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1379b-125">See Also</span></span>  
 [<span data-ttu-id="1379b-126">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="1379b-126">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
