---
title: Décompresser un package DAC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614632"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="8fcf7-102">Décompresser un package DAC</span><span class="sxs-lookup"><span data-stu-id="8fcf7-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="8fcf7-103">Utilisez la boîte de dialogue Décompresser une application de la couche Données pour décompresser les scripts et les fichiers d'un package d'application de la couche Données (DAC).</span><span class="sxs-lookup"><span data-stu-id="8fcf7-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="8fcf7-104">Les scripts et les fichiers sont placés dans un dossier où ils peuvent être examinés avant que le package soit utilisé pour déployer la DAC dans un système de production.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="8fcf7-105">Le contenu d'une DAC peut également être comparé avec le contenu d'un autre package décompressé dans un autre dossier.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="8fcf7-106">**Avant de commencer :**  [Sécurité](#Security)</span><span class="sxs-lookup"><span data-stu-id="8fcf7-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="8fcf7-107">**Pour décompresser une DAC, à l’aide de la**  [boîte de dialogue Décompresser une application de la couche Données](#UnpackDACDial), [Examen du contenu d’un package DAC](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="8fcf7-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8fcf7-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="8fcf7-108">Security</span></span>  
 <span data-ttu-id="8fcf7-109">Nous vous recommandons de ne pas déployer un package DAC provenant de sources inconnues ou non approuvées.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="8fcf7-110">Ces DAC peuvent contenir du code malveillant susceptible d'exécuter un code [!INCLUDE[tsql](../../includes/tsql-md.md)] indésirable ou de provoquer des erreurs en modifiant le schéma.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="8fcf7-111">Avant d'utiliser une DAC provenant d'une source inconnue ou non approuvée, déployez-la sur une instance de test isolée du [!INCLUDE[ssDE](../../includes/ssde-md.md)], décompressez la DAC et examinez le code, par exemple les procédures stockées ou autre code défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="8fcf7-112">Boîte de dialogue Décompresser une application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="8fcf7-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="8fcf7-113">**Pour décompresser un fichier de package DAC**</span><span class="sxs-lookup"><span data-stu-id="8fcf7-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="8fcf7-114">Dans l’ **Explorateur Windows**, accédez à l’emplacement d’un fichier de package DAC (.dacpac).</span><span class="sxs-lookup"><span data-stu-id="8fcf7-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="8fcf7-115">Utilisez l'une des deux méthodes suivantes pour ouvrir la boîte de dialogue Décompresser une application de la couche Données :</span><span class="sxs-lookup"><span data-stu-id="8fcf7-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="8fcf7-116">Cliquez avec le bouton droit sur le fichier de package DAC (.dacpac), puis sélectionnez **Décompresser**.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="8fcf7-117">Double-cliquez sur le fichier de package DAC.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="8fcf7-118">Renseignez les boîtes de dialogue :</span><span class="sxs-lookup"><span data-stu-id="8fcf7-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="8fcf7-119">Décompresser un fichier de package DAC Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fcf7-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="8fcf7-120">Rechercher un dossier</span><span class="sxs-lookup"><span data-stu-id="8fcf7-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="8fcf7-121">Décompresser un fichier de package DAC Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fcf7-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="8fcf7-122">Utilisez cette page pour spécifier le dossier de destination dans lequel placer les fichiers non compressés, puis exécuter l'opération de décompression.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="8fcf7-123">**Les fichiers seront décompressés dans ce dossier :** - Spécifiez le chemin complet du dossier pour les fichiers non compressés.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="8fcf7-124">Si le dossier existe et que vous connaissez le chemin d'accès complet, tapez le chemin d'accès dans la zone.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="8fcf7-125">Autrement, cliquez sur le bouton **Parcourir** pour accéder à un dossier ou créer un dossier.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="8fcf7-126">**Parcourir** - Ouvre la page **Rechercher un dossier** où vous pouvez choisir un dossier en parcourant la hiérarchie des fichiers ou créer un dossier.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="8fcf7-127">**Décompresser** - Démarre l’opération de décompression.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="8fcf7-128">**Annuler** - Ferme la boîte de dialogue sans décompresser le package DAC.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="8fcf7-129">Rechercher un dossier</span><span class="sxs-lookup"><span data-stu-id="8fcf7-129">Browse for Folder</span></span>  
 <span data-ttu-id="8fcf7-130">Utilisez cette page pour choisir le dossier de destination pour l'opération de décompression.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="8fcf7-131">Vous pouvez également créer un dossier.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="8fcf7-132">**Liste de dossiers** - Affiche la hiérarchie des fichiers de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="8fcf7-133">Développez les nœuds pour accéder au dossier dans lequel décompresser le package DAC.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="8fcf7-134">Cliquez sur le dossier, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="8fcf7-135">**Créer un nouveau dossier** - Ouvre un dialogue dans lequel vous pouvez spécifier le nom d’un nouveau dossier qui sera créé dans le dossier actuellement sélectionné dans l’arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="8fcf7-136">**OK** - Place le chemin du dossier que vous avez sélectionné dans la zone **Les fichiers seront décompressés dans ce dossier** de la page **Décompresser un fichier de package DAC** et vous ramène à cette page.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="8fcf7-137">**Annuler** - Ferme la boîte de dialogue sans sélectionner de dossier.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="8fcf7-138">Examen du contenu d'un package DAC</span><span class="sxs-lookup"><span data-stu-id="8fcf7-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="8fcf7-139">Après avoir décompressé le package, vous pouvez examiner les fichiers produits par la boîte de dialogue **Décompresser une application de la couche Données** .</span><span class="sxs-lookup"><span data-stu-id="8fcf7-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="8fcf7-140">La boîte de dialogue génère les fichiers suivants dans le dossier de destination sélectionné :</span><span class="sxs-lookup"><span data-stu-id="8fcf7-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="8fcf7-141">un script Transact-SQL qui contient les instructions pour la création des objets définis dans la DAC ;</span><span class="sxs-lookup"><span data-stu-id="8fcf7-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="8fcf7-142">Le nom de fichier est *DACName*.sql, où *DACName* correspond au nom de la DAC.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="8fcf7-143">tous les fichiers XML du package ;</span><span class="sxs-lookup"><span data-stu-id="8fcf7-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="8fcf7-144">tous les fichiers de la section Fichiers supplémentaires de la DAC, tels que les fichiers de pré-déploiement ou de post-déploiement de la DAC.</span><span class="sxs-lookup"><span data-stu-id="8fcf7-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="8fcf7-145">Pour plus d’informations, consultez [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="8fcf7-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fcf7-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fcf7-146">See Also</span></span>  
 <span data-ttu-id="8fcf7-147">[Applications de la couche Données](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="8fcf7-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="8fcf7-148">[Déployer une application de la couche Données](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="8fcf7-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="8fcf7-149">Mettre à niveau une application de la couche Données</span><span class="sxs-lookup"><span data-stu-id="8fcf7-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
