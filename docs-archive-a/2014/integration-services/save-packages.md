---
title: Enregistrer des packages | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 17c1de2c-637f-45c2-a148-79294bae0af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 102e2c3eab001c230722bf3485d6ea9731aa99a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706584"
---
# <a name="save-packages"></a><span data-ttu-id="97642-102">Enregistrer des packages</span><span class="sxs-lookup"><span data-stu-id="97642-102">Save Packages</span></span>
  <span data-ttu-id="97642-103">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , vous créez des packages à l’aide du concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] et vous les enregistrez dans le système de fichiers sous forme de fichiers XML (fichiers .dtsx).</span><span class="sxs-lookup"><span data-stu-id="97642-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] you build packages by using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and save the packages to the file system as XML files (.dtsx files).</span></span> <span data-ttu-id="97642-104">Vous pouvez également enregistrer des copies du fichier XML des packages dans la base de données msdb dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou dans le magasin de packages.</span><span class="sxs-lookup"><span data-stu-id="97642-104">You can also save copies of the package XML file to the msdb database in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="97642-105">Le magasin de packages représente les dossiers de l’emplacement du système de fichiers gérés par le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97642-105">The package store represents the folders in the file system location that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
 <span data-ttu-id="97642-106">Si vous enregistrez un package dans le système de fichiers, vous pouvez utiliser par la suite le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pour importer le package dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou dans le magasin de packages.</span><span class="sxs-lookup"><span data-stu-id="97642-106">If you save a package to the file system, you can later use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service to import the package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="97642-107">Pour plus d’informations, consultez [Importer et exporter des packages &#40;Service SSIS&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="97642-107">For more information, see [Import and Export Packages &#40;SSIS Service&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span></span>  
  
 <span data-ttu-id="97642-108">Vous pouvez également utiliser un utilitaire d’invite de commandes, **dtutil**, pour copier un package entre le système de fichiers et msdb.</span><span class="sxs-lookup"><span data-stu-id="97642-108">You can also use a command prompt utility, **dtutil**, to copy a package between the file system and msdb.</span></span> <span data-ttu-id="97642-109">Pour plus d’informations, consultez [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="97642-109">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-save-a-package"></a><span data-ttu-id="97642-110">Pour enregistrer un package</span><span class="sxs-lookup"><span data-stu-id="97642-110">To save a package</span></span>  
  
-   [<span data-ttu-id="97642-111">Enregistrer un package dans le système de fichiers</span><span class="sxs-lookup"><span data-stu-id="97642-111">Save a Package to the File System</span></span>](../../2014/integration-services/save-a-package-to-the-file-system.md)  
  
-   [<span data-ttu-id="97642-112">Enregistrer une copie d’un package</span><span class="sxs-lookup"><span data-stu-id="97642-112">Save a Copy of a Package</span></span>](../../2014/integration-services/save-a-copy-of-a-package.md)  
  
  
