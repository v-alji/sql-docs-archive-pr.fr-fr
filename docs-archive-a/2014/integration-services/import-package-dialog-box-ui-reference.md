---
title: Informations de référence sur l’interface utilisateur de la boîte de dialogue Importer le package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605644"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="e090c-102">Référence de l'interface utilisateur de la boîte de dialogue Importer un package</span><span class="sxs-lookup"><span data-stu-id="e090c-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="e090c-103">Utilisez la boîte de dialogue **Importer un package** , disponible dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], pour importer un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et pour définir ou modifier son niveau de protection.</span><span class="sxs-lookup"><span data-stu-id="e090c-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e090c-104">Options</span><span class="sxs-lookup"><span data-stu-id="e090c-104">Options</span></span>  
 <span data-ttu-id="e090c-105">**Emplacement du package**</span><span class="sxs-lookup"><span data-stu-id="e090c-105">**Package location**</span></span>  
 <span data-ttu-id="e090c-106">Sélectionnez le type d'emplacement de stockage dans lequel importer le package.</span><span class="sxs-lookup"><span data-stu-id="e090c-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="e090c-107">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="e090c-107">The following options are available:</span></span>  
  
 <span data-ttu-id="e090c-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e090c-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="e090c-109">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="e090c-109">**File System**</span></span>  
  
 <span data-ttu-id="e090c-110">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="e090c-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="e090c-111">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="e090c-111">**Server**</span></span>  
 <span data-ttu-id="e090c-112">Tapez le nom d’un serveur ou sélectionnez-en un dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e090c-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="e090c-113">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="e090c-113">**Authentication**</span></span>  
 <span data-ttu-id="e090c-114">Sélectionnez l'authentification Windows ou l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e090c-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="e090c-115">Cette option est disponible uniquement si l’emplacement de stockage est [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e090c-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e090c-116">Dans la mesure du possible, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="e090c-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="e090c-117">**Type d’authentification**</span><span class="sxs-lookup"><span data-stu-id="e090c-117">**Authentication type**</span></span>  
 <span data-ttu-id="e090c-118">Sélectionnez un type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="e090c-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="e090c-119">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="e090c-119">**User name**</span></span>  
 <span data-ttu-id="e090c-120">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e090c-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="e090c-121">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="e090c-121">**Password**</span></span>  
 <span data-ttu-id="e090c-122">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="e090c-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="e090c-123">**Chemin d'accès au package**</span><span class="sxs-lookup"><span data-stu-id="e090c-123">**Package path**</span></span>  
 <span data-ttu-id="e090c-124">Tapez le chemin du package ou cliquez sur le bouton Parcourir **(...)** pour rechercher le package.</span><span class="sxs-lookup"><span data-stu-id="e090c-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="e090c-125">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="e090c-125">**Package name**</span></span>  
 <span data-ttu-id="e090c-126">Éventuellement, renommez le package.</span><span class="sxs-lookup"><span data-stu-id="e090c-126">Optionally, rename the package.</span></span> <span data-ttu-id="e090c-127">Par défaut, son nom est celui du package à importer.</span><span class="sxs-lookup"><span data-stu-id="e090c-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="e090c-128">**Niveau de protection**</span><span class="sxs-lookup"><span data-stu-id="e090c-128">**Protection level**</span></span>  
 <span data-ttu-id="e090c-129">Cliquez sur le bouton Parcourir **(...)** et, dans la boîte de dialogue **Niveau de protection du package**, mettez à jour le niveau de protection.</span><span class="sxs-lookup"><span data-stu-id="e090c-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="e090c-130">Pour plus d’informations, consultez [Boîte de dialogue Niveau de protection du package](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="e090c-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e090c-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e090c-131">See Also</span></span>  
 <span data-ttu-id="e090c-132">[Enregistrer une copie du package](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="e090c-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="e090c-133">[Référence de l’interface utilisateur de la boîte de dialogue Exporter le package](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e090c-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="e090c-134">[Enregistrer les packages](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="e090c-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="e090c-135">Importer et exporter des packages &#40;service SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e090c-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
