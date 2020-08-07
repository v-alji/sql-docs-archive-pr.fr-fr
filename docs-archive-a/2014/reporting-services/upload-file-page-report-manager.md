---
title: Page Télécharger un fichier (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703744"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="00d2e-102">Page Télécharger un fichier (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="00d2e-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="00d2e-103">La page Télécharger un fichier vous permet de publier un fichier du système de fichiers dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00d2e-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="00d2e-104">Les fichiers téléchargés sont représentés comme des éléments dans l'arborescence des dossiers du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00d2e-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="00d2e-105">Les fichiers .rdl téléchargés sont publiés sur un serveur de rapports sous forme de rapport.</span><span class="sxs-lookup"><span data-stu-id="00d2e-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="00d2e-106">Les fichiers .smdl téléchargés sont publiés sous la forme de modèles de rapports s'ils contiennent des informations sur la vue de la source de données.</span><span class="sxs-lookup"><span data-stu-id="00d2e-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="00d2e-107">Si une référence de la vue de source de données est absente, une erreur se produit au cours du téléchargement.</span><span class="sxs-lookup"><span data-stu-id="00d2e-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="00d2e-108">Les informations de vue de source de données peuvent être manquantes si vous téléchargez un fichier. smdl à partir d’un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projet de modèle de rapport.</span><span class="sxs-lookup"><span data-stu-id="00d2e-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="00d2e-109">Dans les projets de modèles de rapports, les informations de la vue de source de données sont stockées dans un fichier distinct au lieu d'être incluses dans le fichier .smdl lui-même.</span><span class="sxs-lookup"><span data-stu-id="00d2e-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="00d2e-110">Les fichiers de modèles qui contiennent des informations sur la vue de source de données (et qui peuvent par conséquent être téléchargés) ont été précédemment publiés sur un serveur de rapports, puis enregistrés depuis le serveur dans un fichier du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="00d2e-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="00d2e-111">Si vous ouvrez la page Propriétés générales d'un modèle et cliquez sur **Modifier** pour ouvrir le modèle, vous pouvez enregistrer celui-ci dans un fichier, puis le télécharger sous la forme d'un nouveau modèle sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00d2e-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="00d2e-112">Le fichier .smdl que vous téléchargez ensuite contient toutes les informations nécessaires à la publication du modèle.</span><span class="sxs-lookup"><span data-stu-id="00d2e-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="00d2e-113">Tous les autres types de fichiers que vous téléchargez sont stockés comme des ressources.</span><span class="sxs-lookup"><span data-stu-id="00d2e-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="00d2e-114">Cela inclut les fichiers .rds qui contiennent des informations de connexion de la source de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="00d2e-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="00d2e-115">Le téléchargement d'un fichier .rds ne produit pas d'élément de source de données partagée sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00d2e-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="00d2e-116">Lorsque vous téléchargez un élément, il est placé dans le dossier actif.</span><span class="sxs-lookup"><span data-stu-id="00d2e-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="00d2e-117">Une fois le téléchargement terminé, vous pouvez déplacer l'élément vers un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="00d2e-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00d2e-118">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00d2e-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="00d2e-119">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="00d2e-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="00d2e-120">Navigation</span><span class="sxs-lookup"><span data-stu-id="00d2e-120">Navigation</span></span>  
 <span data-ttu-id="00d2e-121">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="00d2e-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="00d2e-122">Pour ouvrir la page Télécharger un fichier</span><span class="sxs-lookup"><span data-stu-id="00d2e-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="00d2e-123">Ouvrez le Gestionnaire de rapports et accédez au dossier dans lequel vous voulez télécharger un fichier.</span><span class="sxs-lookup"><span data-stu-id="00d2e-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="00d2e-124">Dans la barre d'outils, cliquez sur **Télécharger un fichier**.</span><span class="sxs-lookup"><span data-stu-id="00d2e-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00d2e-125">Options</span><span class="sxs-lookup"><span data-stu-id="00d2e-125">Options</span></span>  
 <span data-ttu-id="00d2e-126">**Fichier à télécharger**</span><span class="sxs-lookup"><span data-stu-id="00d2e-126">**File to Upload**</span></span>  
 <span data-ttu-id="00d2e-127">Affiche le chemin d'accès complet au fichier que vous copiez à partir du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="00d2e-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="00d2e-128">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="00d2e-128">**Browse**</span></span>  
 <span data-ttu-id="00d2e-129">Cliquez pour choisir un fichier dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="00d2e-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="00d2e-130">**Nom**</span><span class="sxs-lookup"><span data-stu-id="00d2e-130">**Name**</span></span>  
 <span data-ttu-id="00d2e-131">Tapez le nom du fichier tel qu'il apparaîtra dans l'espace de noms du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="00d2e-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="00d2e-132">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="00d2e-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="00d2e-133">Il peut également comporter des espaces et certains symboles.</span><span class="sxs-lookup"><span data-stu-id="00d2e-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="00d2e-134">N'utilisez pas les caractères ; ?</span><span class="sxs-lookup"><span data-stu-id="00d2e-134">Do not use the characters ; ?</span></span> <span data-ttu-id="00d2e-135">: \@ & = +, $ \* \< > | "ou/lorsque vous spécifiez un nom d’élément.</span><span class="sxs-lookup"><span data-stu-id="00d2e-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="00d2e-136">**Remplacer l'élément s'il existe**</span><span class="sxs-lookup"><span data-stu-id="00d2e-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="00d2e-137">Activez cette case à cocher si vous souhaitez remplacer un élément existant par une nouvelle version.</span><span class="sxs-lookup"><span data-stu-id="00d2e-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="00d2e-138">Pour remplacer une version existante, le nom du nouvel élément et celui de l'élément existant doivent être identiques.</span><span class="sxs-lookup"><span data-stu-id="00d2e-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00d2e-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00d2e-139">See Also</span></span>  
 <span data-ttu-id="00d2e-140">[Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="00d2e-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="00d2e-141">[Page contenu &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="00d2e-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="00d2e-142">[Aide (F1) Gestionnaire de rapports](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="00d2e-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="00d2e-143">Télécharger des fichiers dans un dossier</span><span class="sxs-lookup"><span data-stu-id="00d2e-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
