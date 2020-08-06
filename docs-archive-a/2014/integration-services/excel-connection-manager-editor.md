---
title: Éditeur du gestionnaire de connexions Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelconnection.f1
helpviewer_keywords:
- Excel Connection Manager Editor
ms.assetid: 7ff097e4-cafb-4885-a898-05b2a46628c1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f66de13b710e5ccb577e6f2d67c215572e34767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610756"
---
# <a name="excel-connection-manager-editor"></a><span data-ttu-id="ed1a2-102">Éditeur du gestionnaire de connexions Excel</span><span class="sxs-lookup"><span data-stu-id="ed1a2-102">Excel Connection Manager Editor</span></span>
  <span data-ttu-id="ed1a2-103">La boîte de dialogue **Éditeur du gestionnaire de connexions Excel** vous permet d'ajouter une connexion à un classeur [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] existant ou nouveau.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-103">Use the **Excel Connection Manager Editor** dialog box to add a connection to an existing or a new [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook file.</span></span>  
  
 <span data-ttu-id="ed1a2-104">Pour en savoir plus sur le gestionnaire de connexions Excel, consultez [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ed1a2-104">To learn more about the Excel connection manager, see [Excel Connection Manager](connection-manager/excel-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed1a2-105">Vous ne pouvez pas vous connecter à un fichier Excel protégé par mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-105">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ed1a2-106">Options</span><span class="sxs-lookup"><span data-stu-id="ed1a2-106">Options</span></span>  
 <span data-ttu-id="ed1a2-107">**Chemin de fichier Excel**</span><span class="sxs-lookup"><span data-stu-id="ed1a2-107">**Excel file path**</span></span>  
 <span data-ttu-id="ed1a2-108">Tapez le chemin d'accès et le nom du fichier d'un classeur Excel (.xls) existant ou nouveau.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-108">Type the path and file name of an existing or a new Excel workbook file (.xls).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ed1a2-109">L' **éditeur de destination Excel** crée automatiquement le fichier Excel lorsque vous sélectionnez une **connexion Excel** qui pointe vers un fichier nouveau ou inexistant, puis cliquez sur **nouveau** pour **le nom de la feuille Excel**.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-109">The **Excel Destination Editor** automatically creates the Excel file when you select an **Excel Connection** that points to a new/non-existent file and then click **New** for **Name of the Excel Sheet**.</span></span>  
  
 <span data-ttu-id="ed1a2-110">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="ed1a2-110">**Browse**</span></span>  
 <span data-ttu-id="ed1a2-111">Utilisez la boîte de dialogue **ouvrir** pour accéder au dossier dans lequel se trouve le fichier Excel ou à l’emplacement où vous souhaitez créer le fichier.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-111">Use the **Open** dialog box to navigate to the folder in which the excel file exists or where you want to create the new file.</span></span>  
  
 <span data-ttu-id="ed1a2-112">**Version d’Excel**</span><span class="sxs-lookup"><span data-stu-id="ed1a2-112">**Excel version**</span></span>  
 <span data-ttu-id="ed1a2-113">Spécifiez la version de Microsoft Excel qui a été utilisée pour créer le fichier.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-113">Specify the version of Microsoft Excel that was used to create the file.</span></span>  
  
|<span data-ttu-id="ed1a2-114">Option</span><span class="sxs-lookup"><span data-stu-id="ed1a2-114">Option</span></span>|<span data-ttu-id="ed1a2-115">Description</span><span class="sxs-lookup"><span data-stu-id="ed1a2-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ed1a2-116">Excel 97-2003</span><span class="sxs-lookup"><span data-stu-id="ed1a2-116">Excel 97-2003</span></span>|<span data-ttu-id="ed1a2-117">Le fichier a été créé à l'aide d'Excel 97 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-117">File was created using Excel 97 or later.</span></span>|  
|<span data-ttu-id="ed1a2-118">Excel 3,0</span><span class="sxs-lookup"><span data-stu-id="ed1a2-118">Excel 3.0</span></span>|<span data-ttu-id="ed1a2-119">Le fichier a été créé à l’aide d’Excel 3,0.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-119">File was created using Excel 3.0.</span></span>|  
|<span data-ttu-id="ed1a2-120">Excel 4,0</span><span class="sxs-lookup"><span data-stu-id="ed1a2-120">Excel 4.0</span></span>|<span data-ttu-id="ed1a2-121">Le fichier a été créé à l'aide d'Excel 4.0.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-121">File was created using Excel 4.0.</span></span>|  
|<span data-ttu-id="ed1a2-122">Excel 5,0</span><span class="sxs-lookup"><span data-stu-id="ed1a2-122">Excel 5.0</span></span>|<span data-ttu-id="ed1a2-123">Le fichier a été créé à l'aide d'Excel 95 (7.0).</span><span class="sxs-lookup"><span data-stu-id="ed1a2-123">File was created using Excel 95 (7.0).</span></span>|  
  
 <span data-ttu-id="ed1a2-124">**La première ligne possède des noms de colonnes**</span><span class="sxs-lookup"><span data-stu-id="ed1a2-124">**First row has column names**</span></span>  
 <span data-ttu-id="ed1a2-125">Permet de spécifier si la première ligne de données dans la feuille de calcul sélectionnée contient les noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-125">Specify whether the first row of data in the selected worksheet contains column names.</span></span> <span data-ttu-id="ed1a2-126">La valeur par défaut de cette option est **True**.</span><span class="sxs-lookup"><span data-stu-id="ed1a2-126">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed1a2-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed1a2-127">See Also</span></span>  
 <span data-ttu-id="ed1a2-128">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ed1a2-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ed1a2-129">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="ed1a2-129">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
