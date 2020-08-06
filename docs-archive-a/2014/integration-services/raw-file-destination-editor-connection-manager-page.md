---
title: Éditeur de destination de fichier brut (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696952"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="333a4-102">Éditeur de destination de fichier brut (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="333a4-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="333a4-103">Utilisez l'Éditeur de destination de fichier brut pour configurer la destination de fichier brut et écrire des données brutes dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="333a4-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="333a4-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="333a4-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="333a4-105">Ouvrir l’éditeur de destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="333a4-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="333a4-106">Définir les options de l’onglet Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="333a4-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="333a4-107">Définir les options de l'onglet Colonnes</span><span class="sxs-lookup"><span data-stu-id="333a4-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a> <span data-ttu-id="333a4-108">Ouvrir l'Éditeur de destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="333a4-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="333a4-109">Ajoutez la destination de fichier brut à un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333a4-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="333a4-110">Cliquez avec le bouton droit sur le composant, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="333a4-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="333a4-111">Définir les options de l'onglet Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="333a4-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="333a4-112">**Mode d’accès**</span><span class="sxs-lookup"><span data-stu-id="333a4-112">**Access mode**</span></span>  
 <span data-ttu-id="333a4-113">Sélectionnez la façon dont le nom de fichier est spécifié.</span><span class="sxs-lookup"><span data-stu-id="333a4-113">Select how the file name is specified.</span></span> <span data-ttu-id="333a4-114">Sélectionnez **Nom de fichier** pour entrer directement le nom de fichier et le chemin d'accès, ou bien **Nom de fichier à partir d'une variable** pour spécifier une variable qui contient le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="333a4-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="333a4-115">**Nom de fichier** ou **Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="333a4-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="333a4-116">Entrez le nom et le chemin d'accès du fichier brut, ou sélectionnez la variable contenant le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="333a4-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="333a4-117">**Option d'écriture**</span><span class="sxs-lookup"><span data-stu-id="333a4-117">**Write option**</span></span>  
 <span data-ttu-id="333a4-118">Sélectionnez la méthode utilisée pour créer le fichier et y écrire.</span><span class="sxs-lookup"><span data-stu-id="333a4-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="333a4-119">**Générer le fichier brut initial**</span><span class="sxs-lookup"><span data-stu-id="333a4-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="333a4-120">Cliquez sur le bouton pour générer un fichier brut vide qui contient uniquement les colonnes (fichier réservé aux métadonnées), sans avoir à exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="333a4-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="333a4-121">Le fichier contient les colonnes sélectionnées à la page **Colonnes** de la boîte de dialogue **Éditeur de destination de fichier brut**.</span><span class="sxs-lookup"><span data-stu-id="333a4-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="333a4-122">Vous pouvez faire pointer la source de fichier brut vers ce fichier réservé aux métadonnées.</span><span class="sxs-lookup"><span data-stu-id="333a4-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="333a4-123">Lorsque vous cliquez sur **Générer le fichier brut initial**, un message s'affiche.</span><span class="sxs-lookup"><span data-stu-id="333a4-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="333a4-124">Cliquez sur **OK** pour commencer la création du fichier.</span><span class="sxs-lookup"><span data-stu-id="333a4-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="333a4-125">Cliquez sur **Annuler** pour sélectionner une autre liste de colonnes sur la page **Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="333a4-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="333a4-126">Définir les options de l’onglet colonnes</span><span class="sxs-lookup"><span data-stu-id="333a4-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="333a4-127">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="333a4-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="333a4-128">Sélectionnez une ou plusieurs colonnes d'entrée pour écrire dans le fichier brut.</span><span class="sxs-lookup"><span data-stu-id="333a4-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="333a4-129">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="333a4-129">**Input Column**</span></span>  
 <span data-ttu-id="333a4-130">Une colonne d’entrée est automatiquement ajoutée à cette table quand vous la sélectionnez sous **Colonnes d’entrée disponibles**. Vous pouvez également sélectionner directement la colonne d’entrée dans cette table.</span><span class="sxs-lookup"><span data-stu-id="333a4-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="333a4-131">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="333a4-131">**Output Alias**</span></span>  
 <span data-ttu-id="333a4-132">Spécifiez un autre nom pour la colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="333a4-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333a4-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="333a4-133">See Also</span></span>  
 [<span data-ttu-id="333a4-134">Destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="333a4-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
