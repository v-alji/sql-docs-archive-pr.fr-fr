---
title: Enregistrer une copie du package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706587"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="1eca0-102">Enregistrer une copie du package</span><span class="sxs-lookup"><span data-stu-id="1eca0-102">Save Copy of Package</span></span>
  <span data-ttu-id="1eca0-103">La boîte de dialogue **Enregistrer une copie du package** , accessible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], permet d’enregistrer la copie d’un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] vers un emplacement différent et éventuellement de modifier le niveau de protection du package.</span><span class="sxs-lookup"><span data-stu-id="1eca0-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1eca0-104">Options</span><span class="sxs-lookup"><span data-stu-id="1eca0-104">Options</span></span>  
 <span data-ttu-id="1eca0-105">**Emplacement du package**</span><span class="sxs-lookup"><span data-stu-id="1eca0-105">**Package location**</span></span>  
 <span data-ttu-id="1eca0-106">Sélectionnez le type d'emplacement de stockage dans lequel enregistrer la copie du package.</span><span class="sxs-lookup"><span data-stu-id="1eca0-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="1eca0-107">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="1eca0-107">The following options are available:</span></span>  
  
 <span data-ttu-id="1eca0-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="1eca0-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="1eca0-109">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="1eca0-109">**File System**</span></span>  
  
 <span data-ttu-id="1eca0-110">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="1eca0-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="1eca0-111">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="1eca0-111">**Server**</span></span>  
 <span data-ttu-id="1eca0-112">Tapez le nom d’un serveur ou sélectionnez-en un dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1eca0-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="1eca0-113">Cette option est disponible uniquement si l’emplacement de stockage est **SQL Server** ou **Magasin de packages SSIS**.</span><span class="sxs-lookup"><span data-stu-id="1eca0-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="1eca0-114">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="1eca0-114">**Authentication**</span></span>  
 <span data-ttu-id="1eca0-115">Sélectionnez l'authentification Windows ou l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1eca0-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="1eca0-116">Cette option est disponible uniquement si l’emplacement de stockage est [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1eca0-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1eca0-117">À chaque fois que possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1eca0-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="1eca0-118">**Type d’authentification**</span><span class="sxs-lookup"><span data-stu-id="1eca0-118">**Authentication type**</span></span>  
 <span data-ttu-id="1eca0-119">Sélectionnez un type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="1eca0-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="1eca0-120">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="1eca0-120">**User name**</span></span>  
 <span data-ttu-id="1eca0-121">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1eca0-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="1eca0-122">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="1eca0-122">**Password**</span></span>  
 <span data-ttu-id="1eca0-123">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="1eca0-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="1eca0-124">**Chemin d'accès au package**</span><span class="sxs-lookup"><span data-stu-id="1eca0-124">**Package path**</span></span>  
 <span data-ttu-id="1eca0-125">Tapez le chemin d’accès au package ou cliquez sur le bouton Parcourir **(...)** et recherchez le dossier dans lequel stocker le package.</span><span class="sxs-lookup"><span data-stu-id="1eca0-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="1eca0-126">**Niveau de protection**</span><span class="sxs-lookup"><span data-stu-id="1eca0-126">**Protection level**</span></span>  
 <span data-ttu-id="1eca0-127">Cliquez sur le bouton Parcourir **(...)** et mettez à jour le niveau de protection dans la boîte de dialogue **niveau de protection du package** .</span><span class="sxs-lookup"><span data-stu-id="1eca0-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="1eca0-128">Pour plus d’informations, consultez [Boîte de dialogue Niveau de protection du package](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="1eca0-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eca0-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1eca0-129">See Also</span></span>  
 <span data-ttu-id="1eca0-130">[Référence de l’interface utilisateur de la boîte de dialogue Importer un package](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1eca0-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="1eca0-131">[Référence de l’interface utilisateur de la boîte de dialogue Exporter le package](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1eca0-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="1eca0-132">[Enregistrer les packages](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="1eca0-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="1eca0-133">Importer et exporter des packages &#40;service SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1eca0-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
