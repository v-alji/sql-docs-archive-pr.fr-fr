---
title: Autorisations d’accès aux dossiers et aux fichiers (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699935"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="c233b-102">Autorisations d'accès aux dossiers et aux fichiers (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c233b-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="c233b-103">Lorsque vous installez [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], des dossiers et des fichiers sont installés dans le système de fichiers dans le chemin d’installation que vous spécifiez pour les fonctionnalités partagées [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c233b-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="c233b-104">Si vous utilisez le chemin d’installation par défaut pour les [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] fonctionnalités partagées, le chemin d’installation de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] est *lecteur*: \program Files\Microsoft SQL Server\120\Master Data Services.</span><span class="sxs-lookup"><span data-stu-id="c233b-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="c233b-105">Vous pouvez modifier le chemin d’installation des fonctionnalités partagées, mais tenez compte des autorisations héritées du dossier parent et des autorisations définies explicitement pour [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c233b-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="c233b-106">Autorisations héritées</span><span class="sxs-lookup"><span data-stu-id="c233b-106">Inherited Permissions</span></span>  
 <span data-ttu-id="c233b-107">Le dossier **Microsoft SQL Server** , le dossier **Master Data Services** et la plupart des sous-dossiers et des fichiers héritent les autorisations du dossier parent spécifié lors de l’exécution du programme d’installation de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c233b-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="c233b-108">Si vous choisissez l’emplacement d’installation par défaut, le dossier parent duquel les autorisations sont héritées est *lecteur*:\Program Files.</span><span class="sxs-lookup"><span data-stu-id="c233b-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="c233b-109">Le tableau suivant décrit les autorisations par défaut du dossier **Program Files**.</span><span class="sxs-lookup"><span data-stu-id="c233b-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c233b-110">Si vous modifiez les autorisations par défaut du dossier **Program Files**, ou si vous choisissez un emplacement d’installation différent, les dossiers et les fichiers [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] héritent les autorisations de leur dossier parent et, par conséquent, les autorisations peuvent différer de celles décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c233b-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="c233b-111">Autorisations par défaut du dossier Program Files</span><span class="sxs-lookup"><span data-stu-id="c233b-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="c233b-112">Nom de groupe ou de compte</span><span class="sxs-lookup"><span data-stu-id="c233b-112">Group or account name</span></span>|<span data-ttu-id="c233b-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c233b-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="c233b-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="c233b-114">CREATOR OWNER</span></span>|<span data-ttu-id="c233b-115">Autorisations spéciales</span><span class="sxs-lookup"><span data-stu-id="c233b-115">Special permissions</span></span>|  
|<span data-ttu-id="c233b-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="c233b-116">SYSTEM</span></span>|<span data-ttu-id="c233b-117">Autorisations spéciales</span><span class="sxs-lookup"><span data-stu-id="c233b-117">Special permissions</span></span>|  
|<span data-ttu-id="c233b-118">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="c233b-118">Administrators</span></span>|<span data-ttu-id="c233b-119">Autorisations spéciales</span><span class="sxs-lookup"><span data-stu-id="c233b-119">Special permissions</span></span>|  
|<span data-ttu-id="c233b-120">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c233b-120">Users</span></span>|<span data-ttu-id="c233b-121">Lire & exécuter, répertorier le contenu des dossiers, lire</span><span class="sxs-lookup"><span data-stu-id="c233b-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="c233b-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="c233b-122">TrustedInstaller</span></span>|<span data-ttu-id="c233b-123">Répertorier le contenu des dossiers, autorisations spéciales</span><span class="sxs-lookup"><span data-stu-id="c233b-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="c233b-124">Autorisations explicites</span><span class="sxs-lookup"><span data-stu-id="c233b-124">Explicit Permissions</span></span>  
 <span data-ttu-id="c233b-125">Le dossier **MDSTempDir** et le fichier [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config (dans le dossier **WebApplication** ) n’héritent pas des autorisations.</span><span class="sxs-lookup"><span data-stu-id="c233b-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="c233b-126">Ils ont des autorisations définies explicitement lorsque vous installez [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], indépendamment du chemin d'installation que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="c233b-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="c233b-127">Ne modifiez pas ces autorisations.</span><span class="sxs-lookup"><span data-stu-id="c233b-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="c233b-128">Autorisations MDSTempDir</span><span class="sxs-lookup"><span data-stu-id="c233b-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="c233b-129">Nom de groupe ou de compte</span><span class="sxs-lookup"><span data-stu-id="c233b-129">Group or account name</span></span>|<span data-ttu-id="c233b-130">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c233b-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="c233b-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="c233b-131">SYSTEM</span></span>|<span data-ttu-id="c233b-132">Modifier, lire & exécuter, répertorier le contenu des dossiers, lire, écrire</span><span class="sxs-lookup"><span data-stu-id="c233b-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="c233b-133">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="c233b-133">Administrators</span></span>|<span data-ttu-id="c233b-134">Modifier, lire & exécuter, répertorier le contenu des dossiers, lire, écrire</span><span class="sxs-lookup"><span data-stu-id="c233b-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="c233b-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="c233b-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="c233b-136">Modifier, lire & exécuter, répertorier le contenu des dossiers, lire, écrire</span><span class="sxs-lookup"><span data-stu-id="c233b-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="c233b-137">Autorisations Web.config</span><span class="sxs-lookup"><span data-stu-id="c233b-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="c233b-138">Nom de groupe ou de compte</span><span class="sxs-lookup"><span data-stu-id="c233b-138">Group or account name</span></span>|<span data-ttu-id="c233b-139">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c233b-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="c233b-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="c233b-140">SYSTEM</span></span>|<span data-ttu-id="c233b-141">Contrôle total, modifier, lire & exécuter, lire, écrire</span><span class="sxs-lookup"><span data-stu-id="c233b-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="c233b-142">Administrateurs</span><span class="sxs-lookup"><span data-stu-id="c233b-142">Administrators</span></span>|<span data-ttu-id="c233b-143">Contrôle total, modifier, lire & exécuter, lire, écrire</span><span class="sxs-lookup"><span data-stu-id="c233b-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="c233b-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="c233b-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="c233b-145">Lire & exécuter, lire</span><span class="sxs-lookup"><span data-stu-id="c233b-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="c233b-146">Pour plus d’informations sur le contenu de le fichier [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config, consultez [Référence de configuration web &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c233b-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c233b-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c233b-147">See Also</span></span>  
 [<span data-ttu-id="c233b-148">Installer Master Data Services</span><span class="sxs-lookup"><span data-stu-id="c233b-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
