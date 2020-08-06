---
title: Gestionnaire de connexions de fichiers multiples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- folders [Integration Services], connections
- files [Integration Services], connections
- Multiple Files connection manager
- connection managers [Integration Services], Multiple Files
- connections [Integration Services], files
- multiple file connections
ms.assetid: 10bdc56e-c5cd-4ddb-b2f7-375fe57fe8b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9ebd45aa4f0794d98be6a79125bf1874913d491
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613091"
---
# <a name="multiple-files-connection-manager"></a><span data-ttu-id="4b1ff-102">Gestionnaire de connexions de fichiers multiples</span><span class="sxs-lookup"><span data-stu-id="4b1ff-102">Multiple Files Connection Manager</span></span>
  <span data-ttu-id="4b1ff-103">Un gestionnaire de connexions de fichiers multiples permet à un package de référencer des fichiers et dossiers existants ou de créer des fichiers ou dossiers au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-103">A Multiple Files connection manager enables a package to reference existing files and folders, or to create files and folders at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4b1ff-104">Les tâches et composants de flux de données de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] n'utilisent pas le gestionnaire de connexions de fichiers multiples.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-104">The built-in tasks and data flow components in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] do not use the Multiple Files connection manager.</span></span> <span data-ttu-id="4b1ff-105">Toutefois, vous pouvez utiliser ce gestionnaire de connexions dans la tâche de script ou le composant Script.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-105">However, you can use this connection manager in the Script task or Script component.</span></span> <span data-ttu-id="4b1ff-106">Pour plus d’informations sur l’utilisation des gestionnaires de connexions avec la tâche de script, consultez [Connexion à des sources de données dans la tâche de script](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-106">For information about how to use connection managers in the Script task, see [Connecting to Data Sources in the Script Task](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md).</span></span> <span data-ttu-id="4b1ff-107">Pour plus d’informations sur l’utilisation des gestionnaires de connexions dans le composant script, consultez [connexion à des sources de données dans le composant Script] (. /extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-107">For information about how to use connection managers in the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md.</span></span>  
  
## <a name="usage-types-of-the-multiple-files-connection-manager"></a><span data-ttu-id="4b1ff-108">Types d'utilisations du gestionnaire de connexions de fichiers multiples</span><span class="sxs-lookup"><span data-stu-id="4b1ff-108">Usage Types of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="4b1ff-109">La propriété `FileUsageType` du gestionnaire de connexions de fichiers multiples indique la manière dont la connexion est utilisée.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-109">The `FileUsageType` property of the Multiple Files connection manager specifies how the connection is used.</span></span> <span data-ttu-id="4b1ff-110">Le gestionnaire de connexions de fichiers multiples permet de créer des fichiers, de créer des dossiers, d'utiliser des fichiers existants et d'utiliser des dossiers existants.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-110">The Multiple Files connection manager can create files, create folders, use existing files, and use existing folders.</span></span>  
  
 <span data-ttu-id="4b1ff-111">Le tableau qui suit énumère les valeurs de `FileUsageType`.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-111">The following table lists the values of `FileUsageType`.</span></span>  
  
|<span data-ttu-id="4b1ff-112">Valeur</span><span class="sxs-lookup"><span data-stu-id="4b1ff-112">Value</span></span>|<span data-ttu-id="4b1ff-113">Description</span><span class="sxs-lookup"><span data-stu-id="4b1ff-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b1ff-114">**0**</span><span class="sxs-lookup"><span data-stu-id="4b1ff-114">**0**</span></span>|<span data-ttu-id="4b1ff-115">Le gestionnaire de connexions de fichiers multiples utilise un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-115">Multiple Files connection manager uses an existing file.</span></span>|  
|<span data-ttu-id="4b1ff-116">**1**</span><span class="sxs-lookup"><span data-stu-id="4b1ff-116">**1**</span></span>|<span data-ttu-id="4b1ff-117">Le gestionnaire de connexions de fichiers multiples crée un fichier.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-117">Multiple Files connection manager creates a file.</span></span>|  
|<span data-ttu-id="4b1ff-118">**2**</span><span class="sxs-lookup"><span data-stu-id="4b1ff-118">**2**</span></span>|<span data-ttu-id="4b1ff-119">Le gestionnaire de connexions de fichiers multiples utilise un dossier existant.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-119">Multiple Files connection manager uses an existing folder.</span></span>|  
|<span data-ttu-id="4b1ff-120">**3**</span><span class="sxs-lookup"><span data-stu-id="4b1ff-120">**3**</span></span>|<span data-ttu-id="4b1ff-121">Le gestionnaire de connexions de fichiers multiples crée un dossier.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-121">Multiple Files connection manager creates a folder.</span></span>|  
  
## <a name="configuration-of-the-multiple-files-connection-manager"></a><span data-ttu-id="4b1ff-122">Configuration du gestionnaire de connexions de fichiers multiples</span><span class="sxs-lookup"><span data-stu-id="4b1ff-122">Configuration of the Multiple Files Connection Manager</span></span>  
 <span data-ttu-id="4b1ff-123">Lorsque vous ajoutez un gestionnaire de connexions de fichiers multiples à un package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crée un gestionnaire de connexions qui sera converti en connexion de fichiers multiples au moment de l'exécution, définit les propriétés de la connexion de fichiers multiples et ajoute la connexion de fichiers multiples à la collection `Connections` du package.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-123">When you add a Multiple Files connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a Multiple Files connection at run time, sets the Multiple Files connection properties, and adds the Multiple Files connection to the `Connections` collection of the package.</span></span>  
  
 <span data-ttu-id="4b1ff-124">La propriété `ConnectionManagerType` du gestionnaire de connexions a pour valeur `MULTIFILE`.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-124">The `ConnectionManagerType` property of the connection manager is set to `MULTIFILE`.</span></span>  
  
 <span data-ttu-id="4b1ff-125">Vous pouvez configurer un gestionnaire de connexions de fichiers multiples de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="4b1ff-125">You can configure a Multiple Files connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4b1ff-126">Spécifiez le type d'utilisation des fichiers et des dossiers.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-126">Specify the usage type of files and folders.</span></span>  
  
-   <span data-ttu-id="4b1ff-127">Spécifiez les fichiers et les dossiers.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-127">Specify files and folders.</span></span>  
  
-   <span data-ttu-id="4b1ff-128">Si vous utilisez plusieurs fichiers ou dossiers, indiquez l'ordre d'accès des fichiers et dossiers.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-128">If using multiple files or folders, specify the order in which the files and folders are accessed.</span></span>  
  
 <span data-ttu-id="4b1ff-129">Si le gestionnaire de connexions de fichiers multiples référence plusieurs fichiers et dossiers, les chemins d'accès aux fichiers et dossiers sont séparés par une barre verticale (|).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-129">If the Multiple Files connection manager references multiple files and folders, the paths of the files and folders are separated by the pipe (|) character.</span></span> <span data-ttu-id="4b1ff-130">La propriété `ConnectionString` du gestionnaire de connexions utilise le format suivant :</span><span class="sxs-lookup"><span data-stu-id="4b1ff-130">The `ConnectionString` property of the connection manager has the following format:</span></span>  
  
 \<*path*>|\<*path*>  
  
 <span data-ttu-id="4b1ff-131">Vous pouvez également spécifier plusieurs fichiers ou dossiers en utilisant des caractères génériques.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-131">You can also specify multiple files or folders using wildcard characters.</span></span> <span data-ttu-id="4b1ff-132">Par exemple, pour référencer tous les fichiers texte sur le lecteur C, la valeur de la `ConnectionString` propriété peut être définie sur C : \\ \*. txt.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-132">For example, to reference all the text files on the C drive, the value of the `ConnectionString` property can be set to C:\\*.txt.</span></span>  
  
 <span data-ttu-id="4b1ff-133">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="4b1ff-133">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4b1ff-134">Pour plus d’informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , consultez [Référence de l’interface utilisateur de la boîte de dialogue Ajouter un gestionnaire de connexions de fichiers](add-file-connection-manager-dialog-box-ui-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Add File Connection Manager Dialog Box UI Reference](add-file-connection-manager-dialog-box-ui-reference.md).</span></span>  
  
 <span data-ttu-id="4b1ff-135">Pour plus d’informations sur la configuration d’un gestionnaire de connexions par programmation, consultez <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> et [Ajout de connexions par programme](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4b1ff-135">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
