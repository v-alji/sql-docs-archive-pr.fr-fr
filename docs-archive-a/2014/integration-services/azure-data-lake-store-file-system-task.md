---
title: Système de fichiers Azure Data Lake Store, tâche | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611251"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="709c1-102">Système de fichiers Azure Data Lake Store, tâche</span><span class="sxs-lookup"><span data-stu-id="709c1-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="709c1-103">La **tâche de système de fichiers Azure Data Lake Store** permet aux utilisateurs d’effectuer diverses opérations de système de fichiers sur [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span><span class="sxs-lookup"><span data-stu-id="709c1-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="709c1-104">Pour ajouter une tâche de système de fichiers Azure Data Lake Store à un package, faites-la glisser depuis la boîte à outils SSIS vers la zone de conception.</span><span class="sxs-lookup"><span data-stu-id="709c1-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="709c1-105">Double-cliquez ensuite sur la tâche, ou cliquez avec le bouton droit sur la tâche et sélectionnez **modifier**pour ouvrir la boîte de dialogue Éditeur de tâche.</span><span class="sxs-lookup"><span data-stu-id="709c1-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="709c1-106">La propriété **Opération** indique l’opération de système de fichiers à réaliser.</span><span class="sxs-lookup"><span data-stu-id="709c1-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="709c1-107">Les opérations suivantes sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="709c1-107">The following operations are supported.</span></span>

* <span data-ttu-id="709c1-108">**CopyToADLS :** charger des fichiers dans ADLS.</span><span class="sxs-lookup"><span data-stu-id="709c1-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="709c1-109">**CopyFromADLS :** télécharger des fichiers depuis ADLS.</span><span class="sxs-lookup"><span data-stu-id="709c1-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="709c1-110">Pour toute opération, vous devez spécifier un gestionnaire de connexions Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="709c1-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="709c1-111">Voici les descriptions des propriétés spécifiques à chaque opération.</span><span class="sxs-lookup"><span data-stu-id="709c1-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="709c1-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="709c1-112">CopyToADLS</span></span>

* <span data-ttu-id="709c1-113">**LocalDirectory :** Spécifie le répertoire source qui contient les fichiers à charger.</span><span class="sxs-lookup"><span data-stu-id="709c1-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="709c1-114">**FileNamePattern :** spécifie un filtre de nom de fichier pour les fichiers sources.</span><span class="sxs-lookup"><span data-stu-id="709c1-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="709c1-115">Seuls les fichiers dont le nom correspond au modèle spécifié seront téléchargés.</span><span class="sxs-lookup"><span data-stu-id="709c1-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="709c1-116">Les caractères génériques `*` et `?` sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="709c1-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="709c1-117">**SearchRecursively :** indique si des fichiers à charger doivent être recherchés de manière récursive dans le répertoire source.</span><span class="sxs-lookup"><span data-stu-id="709c1-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="709c1-118">**AzureDataLakeDirectory :** spécifie le répertoire de destination ADLS dans lequel charger les fichiers.</span><span class="sxs-lookup"><span data-stu-id="709c1-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="709c1-119">**FileExpiry :** Spécifie une date et une heure d’expiration pour les fichiers téléchargés sur ADLS, ou laissez cette propriété vide pour indiquer que les fichiers n’expirent jamais.</span><span class="sxs-lookup"><span data-stu-id="709c1-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="709c1-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="709c1-120">CopyFromADLS</span></span>

* <span data-ttu-id="709c1-121">**AzureDataLakeDirectory :** spécifie le répertoire source ADLS qui contient les fichiers à télécharger.</span><span class="sxs-lookup"><span data-stu-id="709c1-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="709c1-122">**SearchRecursively :** indique si des fichiers à télécharger doivent être recherchés de manière récursive dans le répertoire source.</span><span class="sxs-lookup"><span data-stu-id="709c1-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="709c1-123">**LocalDirectory :** spécifie le répertoire de destination dans lequel stocker les fichiers téléchargés.</span><span class="sxs-lookup"><span data-stu-id="709c1-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
