---
title: Éditeur de destination de fichier brut (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationcolumns.f1
ms.assetid: 37f61d0b-1269-42ee-94ab-011cbaac63e9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a89d8ca46805a23fd03465ed40428081499dccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696955"
---
# <a name="raw-file-destination-editor-columns-page"></a><span data-ttu-id="25704-102">Éditeur de destination de fichier brut (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="25704-102">Raw File Destination Editor (Columns Page)</span></span>
  <span data-ttu-id="25704-103">Utilisez l'Éditeur de destination de fichier brut pour configurer la destination de fichier brut et écrire des données brutes dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="25704-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="25704-104">**Que voulez-vous faire ?**</span><span class="sxs-lookup"><span data-stu-id="25704-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="25704-105">Ouvrir l’éditeur de destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="25704-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="25704-106">Définir les options de l’onglet Gestionnaire de connexions</span><span class="sxs-lookup"><span data-stu-id="25704-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="25704-107">Définir les options de l'onglet Colonnes</span><span class="sxs-lookup"><span data-stu-id="25704-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a> <span data-ttu-id="25704-108">Ouvrir l'Éditeur de destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="25704-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="25704-109">Ajoutez la destination de fichier brut à un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25704-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="25704-110">Cliquez avec le bouton droit sur le composant, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="25704-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="25704-111">Définir les options de l'onglet Gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="25704-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="25704-112">**Mode d’accès**</span><span class="sxs-lookup"><span data-stu-id="25704-112">**Access mode**</span></span>  
 <span data-ttu-id="25704-113">Sélectionnez la façon dont le nom de fichier est spécifié.</span><span class="sxs-lookup"><span data-stu-id="25704-113">Select how the file name is specified.</span></span> <span data-ttu-id="25704-114">Sélectionnez **Nom de fichier** pour entrer directement le nom de fichier et le chemin d'accès, ou bien **Nom de fichier à partir d'une variable** pour spécifier une variable qui contient le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="25704-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="25704-115">**Nom de fichier** ou **Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="25704-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="25704-116">Entrez le nom et le chemin d'accès du fichier brut, ou sélectionnez la variable contenant le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="25704-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="25704-117">**Option d'écriture**</span><span class="sxs-lookup"><span data-stu-id="25704-117">**Write option**</span></span>  
 <span data-ttu-id="25704-118">Sélectionnez la méthode utilisée pour créer le fichier et y écrire.</span><span class="sxs-lookup"><span data-stu-id="25704-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="25704-119">**Générer le fichier brut initial**</span><span class="sxs-lookup"><span data-stu-id="25704-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="25704-120">Cliquez sur le bouton pour générer un fichier brut vide qui contient uniquement les colonnes (fichier réservé aux métadonnées), sans avoir à exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="25704-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="25704-121">Vous pouvez faire pointer la source de fichier brut vers le fichier réservé aux métadonnées.</span><span class="sxs-lookup"><span data-stu-id="25704-121">You can point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="25704-122">Lorsque vous cliquez sur le bouton, la liste des colonnes s'affiche.</span><span class="sxs-lookup"><span data-stu-id="25704-122">When you click the button, a list of the columns appears.</span></span> <span data-ttu-id="25704-123">Vous pouvez cliquer sur Annuler et modifier les colonnes, ou vous pouvez cliquer sur OK pour continuer à créer le fichier.</span><span class="sxs-lookup"><span data-stu-id="25704-123">You can click cancel and modify the columns or click OK to proceed with creating the file.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="25704-124">Définir les options de l’onglet colonnes</span><span class="sxs-lookup"><span data-stu-id="25704-124">Set options on the Columns tab</span></span>  
 <span data-ttu-id="25704-125">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="25704-125">**Available Input Columns**</span></span>  
 <span data-ttu-id="25704-126">Sélectionnez une ou plusieurs colonnes d'entrée pour écrire dans le fichier brut.</span><span class="sxs-lookup"><span data-stu-id="25704-126">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="25704-127">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="25704-127">**Input Column**</span></span>  
 <span data-ttu-id="25704-128">Une colonne d’entrée est automatiquement ajoutée à cette table quand vous la sélectionnez sous **Colonnes d’entrée disponibles**. Vous pouvez également sélectionner directement la colonne d’entrée dans cette table.</span><span class="sxs-lookup"><span data-stu-id="25704-128">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="25704-129">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="25704-129">**Output Alias**</span></span>  
 <span data-ttu-id="25704-130">Spécifiez un autre nom pour la colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="25704-130">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25704-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25704-131">See Also</span></span>  
 [<span data-ttu-id="25704-132">Destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="25704-132">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
