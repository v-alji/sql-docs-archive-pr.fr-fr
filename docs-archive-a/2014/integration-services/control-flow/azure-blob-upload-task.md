---
title: Chargement d’objets blob Azure, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697072"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="af7fe-102">Tâche de chargement d’objets blob Azure</span><span class="sxs-lookup"><span data-stu-id="af7fe-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="af7fe-103">La tâche de chargement d’objets blob Azure permet à un package SSIS de charger des fichiers sur un stockage d’objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="af7fe-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="af7fe-104">Pour ajouter une **tâche de chargement d’objets blob Azure**, faites-la glisser vers le concepteur SSIS, double-cliquez dessus ou cliquez dessus avec le bouton droit, puis cliquez sur **Modifier** pour afficher la boîte de dialogue de **l’Éditeur de tâche de chargement d’objets blob Azure** .</span><span class="sxs-lookup"><span data-stu-id="af7fe-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="af7fe-105">Le tableau suivant décrit les champs de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="af7fe-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="af7fe-106">**Champ**</span><span class="sxs-lookup"><span data-stu-id="af7fe-106">**Field**</span></span>|<span data-ttu-id="af7fe-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="af7fe-107">**Description**</span></span>|  
|<span data-ttu-id="af7fe-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="af7fe-108">AzureStorageConnection</span></span>|<span data-ttu-id="af7fe-109">Spécifiez un gestionnaire de connexions Azure Storage existant ou créez-en un qui fait référence à un compte Azure Storage et pointe vers l’emplacement où les fichiers d’objets blob sont hébergés.</span><span class="sxs-lookup"><span data-stu-id="af7fe-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="af7fe-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="af7fe-110">BlobContainer</span></span>|<span data-ttu-id="af7fe-111">Spécifie le nom du conteneur d’objets blob qui contiendra les fichiers chargés en tant qu’objets blob.</span><span class="sxs-lookup"><span data-stu-id="af7fe-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="af7fe-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="af7fe-112">BlobDirectory</span></span>|<span data-ttu-id="af7fe-113">Spécifie le répertoire d’objets blob dans lequel le fichier chargé sera stocké en tant qu’objet blob de bloc.</span><span class="sxs-lookup"><span data-stu-id="af7fe-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="af7fe-114">Le répertoire d’objet blob est une structure hiérarchique virtuelle.</span><span class="sxs-lookup"><span data-stu-id="af7fe-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="af7fe-115">Si l’objet blob existe déjà, il sera remplacé.</span><span class="sxs-lookup"><span data-stu-id="af7fe-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="af7fe-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="af7fe-116">LocalDirectory</span></span>|<span data-ttu-id="af7fe-117">Spécifie le répertoire local qui contient les fichiers à charger.</span><span class="sxs-lookup"><span data-stu-id="af7fe-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="af7fe-118">FileName</span><span class="sxs-lookup"><span data-stu-id="af7fe-118">FileName</span></span>|<span data-ttu-id="af7fe-119">Spécifie un filtre de nom pour sélectionner des fichiers obéissant à un schéma de nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="af7fe-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="af7fe-120">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="af7fe-120">E.g.</span></span> <span data-ttu-id="af7fe-121">MySheet\*.xls\* inclut les fichiers MySheet001.xls et MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="af7fe-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="af7fe-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="af7fe-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="af7fe-123">Spécifie une plage de temps pour appliquer un filtre.</span><span class="sxs-lookup"><span data-stu-id="af7fe-123">Specifies a time range filter.</span></span> <span data-ttu-id="af7fe-124">Les fichiers modifiés après **TimeRangeFrom** et avant **TimeRangeTo** seront inclus.</span><span class="sxs-lookup"><span data-stu-id="af7fe-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
