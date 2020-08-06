---
title: Gestionnaire de connexions de fichiers | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- files [Integration Services]
- connection managers [Integration Services], File
- connections [Integration Services], files
- File connection manager
ms.assetid: 019078bc-44ee-4975-9169-0f9a89e3f3be
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cebb5438003c6b14c547d14012ff1bc1175a706d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706620"
---
# <a name="file-connection-manager"></a><span data-ttu-id="f4ca7-102">Gestionnaire de connexions de fichiers</span><span class="sxs-lookup"><span data-stu-id="f4ca7-102">File Connection Manager</span></span>
  <span data-ttu-id="f4ca7-103">Un gestionnaire de connexions de fichiers permet à un package de référencer un fichier ou dossier existant ou de créer un fichier ou dossier au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-103">A File connection manager enables a package to reference an existing file or folder, or to create a file or folder at run time.</span></span> <span data-ttu-id="f4ca7-104">Par exemple, vous pouvez référencer un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-104">For example, you can reference an Excel file.</span></span> <span data-ttu-id="f4ca7-105">Certains composants de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilisent les informations figurant dans les fichiers pour réaliser leur travail.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-105">Certain components in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] use information in files to perform their work.</span></span> <span data-ttu-id="f4ca7-106">Par exemple, une tâche d'exécution SQL peut référencer un fichier contenant les instructions SQL exécutées par la tâche.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-106">For example, an Execute SQL task can reference a file that contains the SQL statements that the task executes.</span></span> <span data-ttu-id="f4ca7-107">D'autres composants exécutent des opérations sur les fichiers.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-107">Other components perform operations on files.</span></span> <span data-ttu-id="f4ca7-108">Par exemple, la tâche de système de fichiers peut référencer un fichier pour le copier à un nouvel emplacement.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-108">For example, the File System task can reference a file to copy it to a new location.</span></span>  
  
## <a name="usage-types-of-the-file-connection-manager"></a><span data-ttu-id="f4ca7-109">Types d'utilisations du gestionnaire de connexions de fichiers</span><span class="sxs-lookup"><span data-stu-id="f4ca7-109">Usage Types of the File Connection Manager</span></span>  
 <span data-ttu-id="f4ca7-110">La propriété `FileUsageType` du gestionnaire de connexions de fichiers spécifie la manière dont la connexion de fichiers est utilisée.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-110">The `FileUsageType` property of the File connection manager specifies how the file connection is used.</span></span> <span data-ttu-id="f4ca7-111">Le gestionnaire de connexions de fichiers peut créer un fichier, créer un dossier, utiliser un fichier existant ou utiliser un dossier existant.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-111">The File connection manager can create a file, create a folder, use an existing file, or use an existing folder.</span></span>  
  
 <span data-ttu-id="f4ca7-112">Le tableau qui suit énumère les valeurs de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-112">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="f4ca7-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="f4ca7-113">Value</span></span>|<span data-ttu-id="f4ca7-114">Description</span><span class="sxs-lookup"><span data-stu-id="f4ca7-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="f4ca7-115">Le gestionnaire de connexions de fichiers utilise un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-115">File connection manager uses an existing file.</span></span>|  
|`1`|<span data-ttu-id="f4ca7-116">Le gestionnaire de connexions de fichiers crée un fichier.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-116">File connection manager creates a file.</span></span>|  
|`2`|<span data-ttu-id="f4ca7-117">Le gestionnaire de connexions de fichiers utilise un dossier existant.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-117">File connection manager uses an existing folder.</span></span>|  
|`3`|<span data-ttu-id="f4ca7-118">Le gestionnaire de connexions de fichiers crée un dossier.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-118">File connection manager creates a folder.</span></span>|  
  
## <a name="multiple-file-or-folder-connections"></a><span data-ttu-id="f4ca7-119">Connexions de fichiers ou de dossiers multiples</span><span class="sxs-lookup"><span data-stu-id="f4ca7-119">Multiple File or Folder Connections</span></span>  
 <span data-ttu-id="f4ca7-120">Le gestionnaire de connexions de fichiers peut référencer un seul fichier ou dossier.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-120">The File connection manager can reference only one file or folder.</span></span> <span data-ttu-id="f4ca7-121">Pour référencer plusieurs fichiers ou dossiers, utilisez un gestionnaire de connexions de fichiers multiples au lieu du gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-121">To reference multiple files or folders, use a Multiple Files connection manager instead of a File connection manager.</span></span> <span data-ttu-id="f4ca7-122">Pour plus d’informations, consultez [Gestionnaire de connexions de fichiers multiples](multiple-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f4ca7-122">For more information, see [Multiple Files Connection Manager](multiple-files-connection-manager.md).</span></span>  
  
## <a name="configuration-of-the-file-connection-manager"></a><span data-ttu-id="f4ca7-123">Configuration du gestionnaire de connexions de fichiers</span><span class="sxs-lookup"><span data-stu-id="f4ca7-123">Configuration of the File Connection Manager</span></span>  
 <span data-ttu-id="f4ca7-124">Lorsque vous ajoutez un gestionnaire de connexions de fichiers à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion de fichiers au moment de l'exécution, définit les propriétés de la connexion de fichiers et ajoute la connexion de fichiers à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-124">When you add a File connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a File connection at run time, sets the File connection properties, and adds the File connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="f4ca7-125">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `FILE`.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-125">The `ConnectionManagerType` property of the connection manager is set to `FILE`.</span></span>  
  
 <span data-ttu-id="f4ca7-126">Vous pouvez configurer un gestionnaire de connexions de fichiers de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="f4ca7-126">You can configure a File connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="f4ca7-127">Spécifiez le type d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-127">Specify the usage type.</span></span>  
  
-   <span data-ttu-id="f4ca7-128">Spécifiez un fichier ou un dossier.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-128">Specify a file or folder.</span></span>  
  
 <span data-ttu-id="f4ca7-129">Vous pouvez définir la propriété ConnectionString du gestionnaire de connexions de fichiers en spécifiant une expression dans la fenêtre Propriétés de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4ca7-129">You can set the ConnectionString property for the File connection manager by specifying an expression in the Properties window of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="f4ca7-130">Toutefois, pour éviter une erreur de validation lorsque vous utilisez une expression pour spécifier le fichier ou le dossier, dans l' **éditeur du gestionnaire de connexions de fichiers**, pour **fichier/dossier**, ajoutez un chemin d’accès de fichier ou de dossier.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-130">However, to avoid a validation error when you use an expression to specify the file or folder, in the **File Connection Manager Editor**, for **File/Folder**, add a file or folder path.</span></span>  
  
 <span data-ttu-id="f4ca7-131">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="f4ca7-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f4ca7-132">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Éditeur du gestionnaire de connexions de fichiers](../file-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f4ca7-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [File Connection Manager Editor](../file-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="f4ca7-133">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="f4ca7-133">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
