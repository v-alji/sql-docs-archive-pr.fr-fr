---
title: Informations de référence sur l’interface utilisateur de la boîte de dialogue Exporter le package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710759"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="5fe60-102">Référence de l'interface utilisateur de la boîte de dialogue Exporter un package</span><span class="sxs-lookup"><span data-stu-id="5fe60-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="5fe60-103">Utilisez la boîte de dialogue **Exporter un package** , disponible dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], pour exporter un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] vers un autre emplacement et éventuellement modifier son niveau de protection.</span><span class="sxs-lookup"><span data-stu-id="5fe60-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5fe60-104">Options</span><span class="sxs-lookup"><span data-stu-id="5fe60-104">Options</span></span>  
 <span data-ttu-id="5fe60-105">**Emplacement du package**</span><span class="sxs-lookup"><span data-stu-id="5fe60-105">**Package location**</span></span>  
 <span data-ttu-id="5fe60-106">Sélectionnez le type de stockage vers lequel exporter le package.</span><span class="sxs-lookup"><span data-stu-id="5fe60-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="5fe60-107">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="5fe60-107">The following options are available:</span></span>  
  
 <span data-ttu-id="5fe60-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5fe60-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="5fe60-109">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="5fe60-109">**File System**</span></span>  
  
 <span data-ttu-id="5fe60-110">**Magasin de packages SSIS**</span><span class="sxs-lookup"><span data-stu-id="5fe60-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="5fe60-111">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="5fe60-111">**Server**</span></span>  
 <span data-ttu-id="5fe60-112">Tapez le nom d’un serveur ou sélectionnez-en un dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5fe60-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="5fe60-113">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="5fe60-113">**Authentication**</span></span>  
 <span data-ttu-id="5fe60-114">Sélectionnez l'authentification Windows ou l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5fe60-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="5fe60-115">Cette option est disponible uniquement si l’emplacement de stockage est [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5fe60-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5fe60-116">Dans la mesure du possible, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="5fe60-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="5fe60-117">**Type d’authentification**</span><span class="sxs-lookup"><span data-stu-id="5fe60-117">**Authentication type**</span></span>  
 <span data-ttu-id="5fe60-118">Sélectionnez un type d'authentification.</span><span class="sxs-lookup"><span data-stu-id="5fe60-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="5fe60-119">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="5fe60-119">**User name**</span></span>  
 <span data-ttu-id="5fe60-120">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un nom d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5fe60-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="5fe60-121">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="5fe60-121">**Password**</span></span>  
 <span data-ttu-id="5fe60-122">Si vous utilisez l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , entrez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="5fe60-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="5fe60-123">**Chemin d'accès au package**</span><span class="sxs-lookup"><span data-stu-id="5fe60-123">**Package path**</span></span>  
 <span data-ttu-id="5fe60-124">Tapez le chemin du package ou cliquez sur le bouton Parcourir **(...)** pour rechercher le dossier dans lequel stocker le package.</span><span class="sxs-lookup"><span data-stu-id="5fe60-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="5fe60-125">**Niveau de protection**</span><span class="sxs-lookup"><span data-stu-id="5fe60-125">**Protection level**</span></span>  
 <span data-ttu-id="5fe60-126">Cliquez sur le bouton Parcourir **(...)** et mettez à jour le niveau de protection dans la boîte de dialogue **Niveau de protection du package**.</span><span class="sxs-lookup"><span data-stu-id="5fe60-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="5fe60-127">Pour plus d’informations, consultez [Boîte de dialogue Niveau de protection du package](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="5fe60-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe60-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5fe60-128">See Also</span></span>  
 <span data-ttu-id="5fe60-129">[Enregistrer une copie du package](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="5fe60-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="5fe60-130">[Référence de l’interface utilisateur de la boîte de dialogue Importer un package](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5fe60-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="5fe60-131">[Enregistrer les packages](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="5fe60-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="5fe60-132">Importer et exporter des packages &#40;service SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5fe60-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
