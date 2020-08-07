---
title: Copier un package dans SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], copying
- copying packages
- regenerating package GUID
- updating package properties
ms.assetid: 03edc659-e76d-48c0-a749-5f1899b6b507
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bd6ed4dd66ee4755181f5df6f3c1b5466b3f26b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610792"
---
# <a name="copy-a-package-in-sql-server-data-tools"></a><span data-ttu-id="43d28-102">Copier un package dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="43d28-102">Copy a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="43d28-103">Cette rubrique explique comment créer un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en copiant un package existant, et comment mettre à jour les propriétés `Name` et `GUID` du nouveau package.</span><span class="sxs-lookup"><span data-stu-id="43d28-103">This topic describes how to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package by copying an existing package, and how to update the `Name` and `GUID` properties of the new package.</span></span>  
  
### <a name="to-copy-a-package"></a><span data-ttu-id="43d28-104">Pour copier un package</span><span class="sxs-lookup"><span data-stu-id="43d28-104">To copy a package</span></span>  
  
1.  <span data-ttu-id="43d28-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package que vous voulez copier.</span><span class="sxs-lookup"><span data-stu-id="43d28-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to copy.</span></span>  
  
2.  <span data-ttu-id="43d28-106">Dans l'Explorateur de solutions, double-cliquez sur le package.</span><span class="sxs-lookup"><span data-stu-id="43d28-106">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="43d28-107">Vérifiez soit que le package à copier est sélectionné dans l'Explorateur de solutions, soit que l'onglet du concepteur SSIS qui contient le package est l'onglet actif.</span><span class="sxs-lookup"><span data-stu-id="43d28-107">Verify either the package to copy is selected in Solution Explorer or the tab in SSIS Designer that contains the package is the active tab</span></span>  
  
4.  <span data-ttu-id="43d28-108">Dans le menu **Fichier** , cliquez sur **Enregistrer \<package name> sous**.</span><span class="sxs-lookup"><span data-stu-id="43d28-108">On the **File** menu, click **Save \<package name> As**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43d28-109">Le package doit être ouvert dans le concepteur SSIS pour que l’option **Enregistrer sous** apparaisse dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="43d28-109">The package must be opened in SSIS Designer before the **Save As** option appears on the **File** menu.</span></span>  
  
5.  <span data-ttu-id="43d28-110">Le cas échéant, accédez à un autre dossier.</span><span class="sxs-lookup"><span data-stu-id="43d28-110">Optionally, browse to a different folder.</span></span>  
  
6.  <span data-ttu-id="43d28-111">Mettez à jour le nom du fichier de package.</span><span class="sxs-lookup"><span data-stu-id="43d28-111">Update the name of the package file.</span></span> <span data-ttu-id="43d28-112">Veillez à conserver l'extension de fichier .dtsx.</span><span class="sxs-lookup"><span data-stu-id="43d28-112">Make sure that you retain the .dtsx file extension.</span></span>  
  
7.  <span data-ttu-id="43d28-113">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="43d28-113">Click **Save**.</span></span>  
  
8.  <span data-ttu-id="43d28-114">À l'invite, déterminez si vous voulez mettre à jour le nom de l'objet de package afin qu'il corresponde au nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="43d28-114">At the prompt, choose whether to update the name of the package object to match the file name.</span></span> <span data-ttu-id="43d28-115">Si vous cliquez sur **Oui**, la `Name` propriété du package est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="43d28-115">If you click **Yes**, the `Name` property of the package is updated.</span></span> <span data-ttu-id="43d28-116">Le nouveau package est ajouté au projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et ouvert dans le concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43d28-116">The new package is added to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
9. <span data-ttu-id="43d28-117">Le cas échéant, cliquez sur l’arrière-plan de l’onglet **Flux de contrôle** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="43d28-117">Optionally, click in the background of the **Control Flow** tab, and the click **Properties**.</span></span>  
  
10. <span data-ttu-id="43d28-118">Dans la fenêtre Propriétés, cliquez sur la valeur de la propriété ID, puis cliquez sur **\<Generate New ID>** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="43d28-118">In the Properties window, click the value of the ID property, and then in the drop-down list click **\<Generate New ID>**.</span></span>  
  
11. <span data-ttu-id="43d28-119">Dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés** pour enregistrer le nouveau package.</span><span class="sxs-lookup"><span data-stu-id="43d28-119">On the **File** menu, click **Save Selected Items** to save the new package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d28-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43d28-120">See Also</span></span>  
 <span data-ttu-id="43d28-121">[Enregistrer une copie d'un package](../../2014/integration-services/save-a-copy-of-a-package.md) </span><span class="sxs-lookup"><span data-stu-id="43d28-121">[Save a Copy of a Package](../../2014/integration-services/save-a-copy-of-a-package.md) </span></span>  
 <span data-ttu-id="43d28-122">[Créer des packages dans SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span><span class="sxs-lookup"><span data-stu-id="43d28-122">[Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) </span></span>  
 [<span data-ttu-id="43d28-123">Packages Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="43d28-123">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
