---
title: Téléchargement d’objets blob Azure, tâche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697075"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="0b5bf-102">Tâche de téléchargement d’objet blob Azure</span><span class="sxs-lookup"><span data-stu-id="0b5bf-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="0b5bf-103">La tâche de téléchargement d’objet blob Azure permet à un package SSIS de télécharger des fichiers à partir d’un stockage d’objets blob Azure.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="0b5bf-104">Pour ajouter une **tâche de téléchargement d’objet blob Azure**, faites-la glisser sur le concepteur SSIS, double-cliquez dessus ou cliquez dessus avec le bouton droit, puis cliquez sur **Modifier** pour afficher la boîte de dialogue **Éditeur de la tâche de téléchargement d’objet blob Azure** .</span><span class="sxs-lookup"><span data-stu-id="0b5bf-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0b5bf-105">Le tableau suivant décrit les champs de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b5bf-106">**Champ**</span><span class="sxs-lookup"><span data-stu-id="0b5bf-106">**Field**</span></span>|<span data-ttu-id="0b5bf-107">**Description**</span><span class="sxs-lookup"><span data-stu-id="0b5bf-107">**Description**</span></span>|  
|<span data-ttu-id="0b5bf-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="0b5bf-108">AzureStorageConnection</span></span>|<span data-ttu-id="0b5bf-109">Spécifiez un gestionnaire de connexions Azure Storage existant ou créez-en un qui fait référence à un compte Azure Storage et pointe vers l’emplacement où les fichiers d’objets blob sont hébergés.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="0b5bf-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="0b5bf-110">BlobContainer</span></span>|<span data-ttu-id="0b5bf-111">Spécifie le nom du conteneur d’objets blob qui contient les fichiers d’objets blob à télécharger.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="0b5bf-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="0b5bf-112">BlobDirectory</span></span>|<span data-ttu-id="0b5bf-113">Spécifie le répertoire d’objets blob qui contient les fichiers d’objets blob à télécharger.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="0b5bf-114">Le répertoire d’objet blob est une structure hiérarchique virtuelle.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="0b5bf-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="0b5bf-115">LocalDirectory</span></span>|<span data-ttu-id="0b5bf-116">Spécifie le répertoire local où les fichiers d’objets blob téléchargés seront stockés.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="0b5bf-117">FileName</span><span class="sxs-lookup"><span data-stu-id="0b5bf-117">FileName</span></span>|<span data-ttu-id="0b5bf-118">Spécifie un filtre de nom pour sélectionner des fichiers obéissant à un schéma de nom spécifié.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="0b5bf-119">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="0b5bf-119">E.g.</span></span> <span data-ttu-id="0b5bf-120">MySheet\*.xls\* inclut les fichiers MySheet001.xls et MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="0b5bf-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="0b5bf-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="0b5bf-122">Spécifie une plage de temps pour appliquer un filtre.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-122">Specifies a time range filter.</span></span> <span data-ttu-id="0b5bf-123">Les fichiers modifiés après **TimeRangeFrom** et avant **TimeRangeTo** seront inclus.</span><span class="sxs-lookup"><span data-stu-id="0b5bf-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
