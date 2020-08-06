---
title: Installer SQL Server 2014 sur Server Core | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697144"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="fcf78-102">Installer SQL Server 2014 sur Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="fcf78-103">Vous pouvez installer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur une installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="fcf78-104">Cette rubrique fournit des détails spécifiques à l'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="fcf78-105">L'option d'installation de Server Core pour le système d'exploitation [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] offre l'environnement minimal requis pour l'exécution de certains rôles de serveurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fcf78-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="fcf78-106">Cela permet de réduire les besoins en maintenance et gestion et l'exposition aux attaques de ces rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="fcf78-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="fcf78-107">Pour plus d’informations sur Server Core implémenté sur [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] , consultez [Server Core pour Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="fcf78-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="fcf78-108">Pour plus d’informations sur Server Core implémenté sur [!INCLUDE[win8srv](../../includes/win8srv-md.md)], consultez [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="fcf78-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fcf78-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fcf78-109">Prerequisites</span></span>  
  
|<span data-ttu-id="fcf78-110">Condition requise</span><span class="sxs-lookup"><span data-stu-id="fcf78-110">Requirement</span></span>|<span data-ttu-id="fcf78-111">Procédure d'installation</span><span class="sxs-lookup"><span data-stu-id="fcf78-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="fcf78-112">2.0 SP2</span><span class="sxs-lookup"><span data-stu-id="fcf78-112">2.0 SP2</span></span>|<span data-ttu-id="fcf78-113">Inclus dans l'installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 et de [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="fcf78-114">S'il n'est pas activé, le programme d'installation l'active par défaut.</span><span class="sxs-lookup"><span data-stu-id="fcf78-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="fcf78-115">Il n'est pas possible d'exécuter les versions 2.0, 3.0 et 3.5 côte à côte sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fcf78-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="fcf78-116">Lorsque vous installez le .NET Framework 3.5 SP1, vous obtenez les couches 2.0 et 3.0 automatiquement.</span><span class="sxs-lookup"><span data-stu-id="fcf78-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="fcf78-117">Profil 3.5 SP1 complet</span><span class="sxs-lookup"><span data-stu-id="fcf78-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="fcf78-118">Inclus dans l'installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="fcf78-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="fcf78-119">S'il n'est pas activé, le programme d'installation l'active par défaut.</span><span class="sxs-lookup"><span data-stu-id="fcf78-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="fcf78-120">Sur un ordinateur disposant du système d'exploitation Windows Server, vous devez télécharger et installer le .NET Framework 3.5 SP1 avant d'exécuter le programme d'installation, pour installer les composants qui dépendent du NET 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="fcf78-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="fcf78-121">Pour plus d’informations sur les recommandations et des conseils sur l’acquisition et l’activation de .NET Framework 3,5 dans [!INCLUDE[win8srv](../../includes/win8srv-md.md)] , consultez Considérations sur le [déploiement de Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="fcf78-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="fcf78-122">Profil 4 Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-122">4 Server Core Profile</span></span>|<span data-ttu-id="fcf78-123">Pour toutes les éditions de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sauf [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], le programme d'installation installe le profil 4 Server Core [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] comme condition préalable.</span><span class="sxs-lookup"><span data-stu-id="fcf78-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="fcf78-124">Pour [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] , téléchargez le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Profil 4 Server Core à partir de [Microsoft .NET Framework 4 (programme d’installation autonome) pour Server Core](https://www.microsoft.com/download/details.aspx?id=17718) ( https://www.microsoft.com/download/details.aspx?id=17718) et installez-le avant de procéder à l’installation.</span><span class="sxs-lookup"><span data-stu-id="fcf78-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="fcf78-125">Windows Installer 4.5</span><span class="sxs-lookup"><span data-stu-id="fcf78-125">Windows Installer 4.5</span></span>|<span data-ttu-id="fcf78-126">Inclus dans l'installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 et de [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="fcf78-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="fcf78-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="fcf78-128">Inclus dans l'installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 et de [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="fcf78-129">Fonctionnalités prises en charge</span><span class="sxs-lookup"><span data-stu-id="fcf78-129">Supported Features</span></span>  
 <span data-ttu-id="fcf78-130">Utilisez le tableau suivant pour rechercher les fonctionnalités prises en charge dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur une installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 et [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="fcf78-131">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="fcf78-131">Feature</span></span>|<span data-ttu-id="fcf78-132">Prise en charge</span><span class="sxs-lookup"><span data-stu-id="fcf78-132">Supported</span></span>|  
|-------------|---------------|  
|<span data-ttu-id="fcf78-133">du[!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-133">[!INCLUDE[ssDE](../../includes/ssde-md.md)] Services</span></span>|<span data-ttu-id="fcf78-134">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-134">Yes</span></span>|  
|<span data-ttu-id="fcf78-135">Réplication[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication</span></span>|<span data-ttu-id="fcf78-136">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-136">Yes</span></span>|  
|<span data-ttu-id="fcf78-137">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="fcf78-137">Full Text Search</span></span>|<span data-ttu-id="fcf78-138">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="fcf78-139">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="fcf78-140">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-140">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fcf78-141">Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="fcf78-141">Data Tools (SSDT)</span></span>|<span data-ttu-id="fcf78-142">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-142">No</span></span>|  
|<span data-ttu-id="fcf78-143">Connectivité des outils clients</span><span class="sxs-lookup"><span data-stu-id="fcf78-143">Client Tools Connectivity</span></span>|<span data-ttu-id="fcf78-144">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-144">Yes</span></span>|  
|<span data-ttu-id="fcf78-145">Serveur de Integration Services<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="fcf78-146">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-146">Yes</span></span>|  
|<span data-ttu-id="fcf78-147">Compatibilité descendante des outils clients</span><span class="sxs-lookup"><span data-stu-id="fcf78-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="fcf78-148">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-148">No</span></span>|  
|<span data-ttu-id="fcf78-149">Kit de développement logiciel (SDK) des outils clients</span><span class="sxs-lookup"><span data-stu-id="fcf78-149">Client Tools SDK</span></span>|<span data-ttu-id="fcf78-150">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-150">No</span></span>|  
|<span data-ttu-id="fcf78-151">Documentation en ligne[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-151">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="fcf78-152">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-152">No</span></span>|  
|<span data-ttu-id="fcf78-153">Outils de gestion - Base</span><span class="sxs-lookup"><span data-stu-id="fcf78-153">Management Tools - Basic</span></span>|<span data-ttu-id="fcf78-154">Distant uniquement<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="fcf78-155">Outils de gestion - Complet</span><span class="sxs-lookup"><span data-stu-id="fcf78-155">Management Tools - Complete</span></span>|<span data-ttu-id="fcf78-156">Distant uniquement<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="fcf78-157">Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="fcf78-157">Distributed Replay Controller</span></span>|<span data-ttu-id="fcf78-158">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-158">No</span></span>|  
|<span data-ttu-id="fcf78-159">Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="fcf78-159">Distributed Replay Client</span></span>|<span data-ttu-id="fcf78-160">Distant uniquement<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="fcf78-161">Kit de développement logiciel (SDK) de l'option Connectivité client de SQL</span><span class="sxs-lookup"><span data-stu-id="fcf78-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="fcf78-162">Oui</span><span class="sxs-lookup"><span data-stu-id="fcf78-162">Yes</span></span>|  
|<span data-ttu-id="fcf78-163">Microsoft Sync Framework</span><span class="sxs-lookup"><span data-stu-id="fcf78-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="fcf78-164">Oui<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="fcf78-165">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="fcf78-166">Non</span><span class="sxs-lookup"><span data-stu-id="fcf78-166">No</span></span>|  
  
 <span data-ttu-id="fcf78-167"><sup>[1]</sup> Pour plus d’informations sur le nouveau serveur de Integration Services et ses fonctionnalités dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , consultez [Integration Services &#40;serveur de&#41; SSIS](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="fcf78-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="fcf78-168"><sup>[2]</sup> L’installation de ces fonctionnalités sur Server Core n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fcf78-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="fcf78-169">Ces composants peuvent être installés sur un serveur autre que [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core et être connectés aux services de [!INCLUDE[ssDE](../../includes/ssde-md.md)] installés sur Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="fcf78-170"><sup>[3]</sup> Microsoft Sync Framework n’est pas inclus dans le [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] package d’installation.</span><span class="sxs-lookup"><span data-stu-id="fcf78-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="fcf78-171">Vous pouvez télécharger la version appropriée de Sync Framework à partir de ce [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/?LinkId=221788) ( https://go.microsoft.com/fwlink/?LinkId=221788) page et l’installer sur un ordinateur qui exécute l’installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf78-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="fcf78-172">Matrice de scénario prise en charge</span><span class="sxs-lookup"><span data-stu-id="fcf78-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="fcf78-173">Le tableau suivant indique la matrice de scénario prise en charge pour l'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur une installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 et [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcf78-174">Éditions de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-174">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editions</span></span>|<span data-ttu-id="fcf78-175">Toutes les [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] éditions 64 bits<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="fcf78-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|<span data-ttu-id="fcf78-176">Langue de[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-176">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language</span></span>|<span data-ttu-id="fcf78-177">Toutes les langues</span><span class="sxs-lookup"><span data-stu-id="fcf78-177">All languages</span></span>|  
|<span data-ttu-id="fcf78-178">Langage[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur le langage du système d'exploitation/paramètres régionaux (combinaison)</span><span class="sxs-lookup"><span data-stu-id="fcf78-178">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language on OS language/locale (combination)</span></span>|<span data-ttu-id="fcf78-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows JPN (japonais)</span><span class="sxs-lookup"><span data-stu-id="fcf78-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows GER (allemand)</span><span class="sxs-lookup"><span data-stu-id="fcf78-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows CHS (chinois-Chine)</span><span class="sxs-lookup"><span data-stu-id="fcf78-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows ARA (Arabe (Arabie-Saoudite))</span><span class="sxs-lookup"><span data-stu-id="fcf78-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows THA (thaïlandais)</span><span class="sxs-lookup"><span data-stu-id="fcf78-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows TRK (turque)</span><span class="sxs-lookup"><span data-stu-id="fcf78-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows pt-PT (portugais Portugal)</span><span class="sxs-lookup"><span data-stu-id="fcf78-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="fcf78-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Windows ENG (anglais)</span><span class="sxs-lookup"><span data-stu-id="fcf78-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="fcf78-187">Édition Windows</span><span class="sxs-lookup"><span data-stu-id="fcf78-187">Windows edition</span></span>|[!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="fcf78-188">64-bit x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="fcf78-188">64-bit x64 Datacenter</span></span><br /><br /> [!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="fcf78-189">64-bit x64 Standard</span><span class="sxs-lookup"><span data-stu-id="fcf78-189">64-bit x64 Standard</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="fcf78-190">SP1 64-bit x64 Data Center Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-190">SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="fcf78-191">SP1 64-bit x64 Enterprise Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-191">SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="fcf78-192">SP1 64-bit x64 Standard Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-192">SP1 64-bit x64 Standard Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="fcf78-193">SP1 64-bit x64 Web Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-193">SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="fcf78-194"><sup>[1]</sup> L’installation de la version 32 bits des [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] éditions de n’est pas prise en charge sur Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="fcf78-195">Mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fcf78-195">Upgrading</span></span>  
 <span data-ttu-id="fcf78-196">Sur les installations Server Core, la mise à niveau depuis [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] vers [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fcf78-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="fcf78-197">Installation</span><span class="sxs-lookup"><span data-stu-id="fcf78-197">Installation</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="fcf78-198">ne prend pas en charge l'installation avec l'Assistant d'installation sur le système d'exploitation de Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-198">does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="fcf78-199">Lors de l'installation sous Server Core, le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge le mode silencieux complet via le paramètre /Q ou le mode silencieux simple via le paramètre /QS.</span><span class="sxs-lookup"><span data-stu-id="fcf78-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="fcf78-200">Pour plus d’informations, consultez [Installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="fcf78-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="fcf78-201">ne peut pas être installé côte à côte avec des versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un ordinateur qui exécute [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-201">cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="fcf78-202">Indépendamment de la méthode d'installation, vous êtes invité à confirmer l'acceptation des termes de la licence de logiciel en tant que personne physique ou pour le compte d'une entité, sauf si votre utilisation du logiciel est régie par un accord distinct, tel qu'un accord de concession de licence en volume de [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou un accord tiers avec un éditeur de logiciels ou un fabricant OEM.</span><span class="sxs-lookup"><span data-stu-id="fcf78-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="fcf78-203">Les termes du contrat de licence sont affichés afin que vous puissiez les consulter et les accepter dans l'interface utilisateur du programme d'installation.</span><span class="sxs-lookup"><span data-stu-id="fcf78-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="fcf78-204">Les installations sans assistance (à l'aide du paramètre /Q ou /QS) doivent inclure le paramètre /IACCEPTSQLSERVERLICENSETERMS.</span><span class="sxs-lookup"><span data-stu-id="fcf78-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="fcf78-205">Vous pouvez consulter les termes du contrat de licence séparément sur la page [Termes du contrat de licence logiciel Microsoft](https://go.microsoft.com/fwlink/?LinkId=148209).</span><span class="sxs-lookup"><span data-stu-id="fcf78-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcf78-206">Selon la façon dont vous avez reçu le logiciel (par exemple, via le programme de licence en volume [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), votre utilisation du logiciel peut être soumise à des termes et conditions supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="fcf78-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="fcf78-207">Pour installer des fonctionnalités spécifiques, utilisez le paramètre /FEATURES et spécifiez la fonctionnalité parent ou les valeurs de fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="fcf78-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="fcf78-208">Pour plus d'informations sur les paramètres de fonctionnalités et leur utilisation, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="fcf78-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="fcf78-209">Paramètres de fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="fcf78-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="fcf78-210">Paramètre de fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="fcf78-210">Feature parameter</span></span>|<span data-ttu-id="fcf78-211">Description</span><span class="sxs-lookup"><span data-stu-id="fcf78-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="fcf78-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="fcf78-212">SQLENGINE</span></span>|<span data-ttu-id="fcf78-213">Installe uniquement [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="fcf78-214">RÉPLICATION</span><span class="sxs-lookup"><span data-stu-id="fcf78-214">REPLICATION</span></span>|<span data-ttu-id="fcf78-215">Installe le composant Replication avec le [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="fcf78-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="fcf78-216">FULLTEXT</span></span>|<span data-ttu-id="fcf78-217">Installe le composant FullText avec [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="fcf78-218">AS</span><span class="sxs-lookup"><span data-stu-id="fcf78-218">AS</span></span>|<span data-ttu-id="fcf78-219">Installe tous les composants [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf78-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="fcf78-220">IS</span><span class="sxs-lookup"><span data-stu-id="fcf78-220">IS</span></span>|<span data-ttu-id="fcf78-221">Installe tous les composants [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf78-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="fcf78-222">CONN</span><span class="sxs-lookup"><span data-stu-id="fcf78-222">CONN</span></span>|<span data-ttu-id="fcf78-223">Installe les composants de connectivité.</span><span class="sxs-lookup"><span data-stu-id="fcf78-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="fcf78-224">Consultez les exemples suivants de l'utilisation de paramètres de fonctionnalités :</span><span class="sxs-lookup"><span data-stu-id="fcf78-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="fcf78-225">Paramètre et valeurs</span><span class="sxs-lookup"><span data-stu-id="fcf78-225">Parameter and values</span></span>|<span data-ttu-id="fcf78-226">Description</span><span class="sxs-lookup"><span data-stu-id="fcf78-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="fcf78-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fcf78-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="fcf78-228">Installe uniquement [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="fcf78-229">/FEATURES=SQLEngine,FullText</span><span class="sxs-lookup"><span data-stu-id="fcf78-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="fcf78-230">Installe le [!INCLUDE[ssDE](../../includes/ssde-md.md)] et la recherche en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="fcf78-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="fcf78-231">/FEATURES=SQLEngine,Conn</span><span class="sxs-lookup"><span data-stu-id="fcf78-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="fcf78-232">Installe les [!INCLUDE[ssDE](../../includes/ssde-md.md)] et composants de connectivité.</span><span class="sxs-lookup"><span data-stu-id="fcf78-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="fcf78-233">/FEATURES=SQLEngine,AS,IS,Conn</span><span class="sxs-lookup"><span data-stu-id="fcf78-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="fcf78-234">Installe les [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]et composants de connectivité.</span><span class="sxs-lookup"><span data-stu-id="fcf78-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="fcf78-235">Options d'installation</span><span class="sxs-lookup"><span data-stu-id="fcf78-235">Installation Options</span></span>  
 <span data-ttu-id="fcf78-236">L'installation prend en charge les options d'installation suivantes lors de l'installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur un système d'exploitation Server Core :</span><span class="sxs-lookup"><span data-stu-id="fcf78-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="fcf78-237">**Installation à partir de la ligne de commande**</span><span class="sxs-lookup"><span data-stu-id="fcf78-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="fcf78-238">Pour installer des fonctionnalités spécifiques à l'aide de l'option d'installation de l'invite de commande, utilisez le paramètre /FEATURES et spécifiez la fonctionnalité parent ou les valeurs de fonctionnalités répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="fcf78-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="fcf78-239">Voici un exemple d'utilisation des paramètres de la ligne de commande :</span><span class="sxs-lookup"><span data-stu-id="fcf78-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="fcf78-240">**Installation à l’aide du fichier de configuration**</span><span class="sxs-lookup"><span data-stu-id="fcf78-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="fcf78-241">Le programme d'installation prend en charge l'utilisation du fichier de configuration uniquement via l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="fcf78-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="fcf78-242">Le fichier de configuration est un fichier texte avec une structure de base d'un paramètre (paire nom/valeur) et d'un commentaire descriptif.</span><span class="sxs-lookup"><span data-stu-id="fcf78-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="fcf78-243">Le fichier de configuration spécifié à l'invite de commande doit avoir une extension de nom de fichier .INI.</span><span class="sxs-lookup"><span data-stu-id="fcf78-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="fcf78-244">Consultez les exemples suivants de ConfigurationFile.INI :</span><span class="sxs-lookup"><span data-stu-id="fcf78-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="fcf78-245">Installation de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="fcf78-246">L’exemple suivant montre comment installer une nouvelle instance autonome qui inclut le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fcf78-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="fcf78-247">Installation des composants de connectivité</span><span class="sxs-lookup"><span data-stu-id="fcf78-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="fcf78-248">L'exemple suivant montre comment installer les composants de connectivité :</span><span class="sxs-lookup"><span data-stu-id="fcf78-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="fcf78-249">Installation de toutes les fonctionnalités prises en charge</span><span class="sxs-lookup"><span data-stu-id="fcf78-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="fcf78-250">L'exemple suivant montre comment installer toutes les fonctionnalités prises en charge de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sur Server Core :</span><span class="sxs-lookup"><span data-stu-id="fcf78-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="fcf78-251">Les exemples suivants montrent comment lancer l’installation à l’aide d’un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="fcf78-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="fcf78-252">Fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="fcf78-252">Configuration file</span></span>  
  
         <span data-ttu-id="fcf78-253">Voici quelques exemples qui illustrent l’utilisation du fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="fcf78-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="fcf78-254">Pour spécifier le fichier de configuration à l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="fcf78-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="fcf78-255">Pour spécifier des mots de passe à l'invite de commandes plutôt que dans le fichier de configuration :</span><span class="sxs-lookup"><span data-stu-id="fcf78-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="fcf78-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="fcf78-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="fcf78-257">Si vous le fichier DefaultSetup.ini figure dans les dossiers \x86 et \x64 au niveau de la racine du média source [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ouvrez le fichier DefaultSetup.ini, puis ajoutez le paramètre *Features* au fichier.</span><span class="sxs-lookup"><span data-stu-id="fcf78-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="fcf78-258">Si le fichier DefaultSetup.ini n'existe pas, vous pouvez le créer et le copier dans les dossiers \x86 et \x64 au niveau de la racine du média source [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fcf78-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="fcf78-259">Configuration de l'accès à distance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécutant sur Server Core</span><span class="sxs-lookup"><span data-stu-id="fcf78-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="fcf78-260">Effectuez les actions décrites ci-dessous pour configurer l'accès à distance d'une instance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] qui s'exécute sur une installation Server Core de [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="fcf78-261">Activer les connexions distantes sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="fcf78-262">Pour activer les connexions distantes, utilisez SQLCMD.exe localement et exécutez les instructions suivantes sur l'instance de Server Core :</span><span class="sxs-lookup"><span data-stu-id="fcf78-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="fcf78-263">Activer et démarrer le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="fcf78-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="fcf78-264">Par défaut, le service Browser est désactivé.</span><span class="sxs-lookup"><span data-stu-id="fcf78-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="fcf78-265">Si elle est désactivée sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécutant sur Server Core, exécutez la commande suivante à partir de l'invite de commandes pour l'activer :</span><span class="sxs-lookup"><span data-stu-id="fcf78-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="fcf78-266">Après activation, exécutez la commande suivante à partir de l'invite de commandes pour démarrer le service :</span><span class="sxs-lookup"><span data-stu-id="fcf78-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="fcf78-267">Créer des exceptions dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="fcf78-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="fcf78-268">Pour créer des exceptions pour l’accès à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le Pare-feu Windows, suivez les étapes spécifiées dans [Configurer le Pare-feu Windows pour autoriser l’accès à SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="fcf78-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="fcf78-269">Activer TCP/IP sur l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf78-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="fcf78-270">Le protocole TCP/IP peut être activé via Windows PowerShell pour une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur Server Core.</span><span class="sxs-lookup"><span data-stu-id="fcf78-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="fcf78-271">Procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fcf78-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="fcf78-272">Sur un ordinateur qui exécute [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, lancez le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="fcf78-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="fcf78-273">Dans l'onglet **Applications** , cliquez sur **Nouvelle tâche**.</span><span class="sxs-lookup"><span data-stu-id="fcf78-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="fcf78-274">Dans la boîte de dialogue **Créer une nouvelle tâche** , tapez **sqlps.exe** dans le champ **Ouvrir** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcf78-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="fcf78-275">La fenêtre \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="fcf78-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="fcf78-276">Dans la fenêtre **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell**, exécutez le script suivant pour activer le protocole TCP/IP :</span><span class="sxs-lookup"><span data-stu-id="fcf78-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="fcf78-277">Désinstallation</span><span class="sxs-lookup"><span data-stu-id="fcf78-277">Uninstallation</span></span>  
 <span data-ttu-id="fcf78-278">Après avoir ouvert une session sur un ordinateur qui exécute [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 ou [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, vous disposez d'un environnement de bureau limité avec une invite de commandes d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="fcf78-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="fcf78-279">Vous pouvez utiliser cette invite de commandes pour lancer la désinstallation d'une instance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="fcf78-280">Pour désinstaller une instance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], lancez la désinstallation à partir de l'invite de commandes en mode silencieux complet à l'aide du paramètre /Q ou en mode silencieux simple à l'aide du paramètre /QS.</span><span class="sxs-lookup"><span data-stu-id="fcf78-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="fcf78-281">Le paramètre /QS indique la progression via l'interface utilisateur, mais n'accepte aucune entrée.</span><span class="sxs-lookup"><span data-stu-id="fcf78-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="fcf78-282">/Q s'exécute en mode silencieux sans interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fcf78-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="fcf78-283">Pour désinstaller une instance existante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="fcf78-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="fcf78-284">Pour supprimer une instance nommée, spécifiez le nom de l'instance au lieu de « MSSQLSERVER » dans l'exemple précédent.</span><span class="sxs-lookup"><span data-stu-id="fcf78-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="fcf78-285">Si vous fermez accidentellement l'invite de commandes, vous pouvez démarrer une nouvelle invite de commandes en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="fcf78-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="fcf78-286">Appuyez sur Ctrl+Shift+Esc pour afficher le Gestionnaire des tâches.</span><span class="sxs-lookup"><span data-stu-id="fcf78-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="fcf78-287">Dans l'onglet **Applications** , cliquez sur **Nouvelle tâche**.</span><span class="sxs-lookup"><span data-stu-id="fcf78-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="fcf78-288">Dans la boîte de dialogue **Créer une nouvelle tâche** , tapez **cmd** dans le champ **Ouvrir** , [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fcf78-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf78-289">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcf78-289">See Also</span></span>  
 <span data-ttu-id="fcf78-290">[Installer SQL Server 2014 à l’aide d’un fichier de configuration](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="fcf78-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="fcf78-291">[Installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="fcf78-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="fcf78-292">[Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="fcf78-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="fcf78-293">[Guide de Prise en main de l’option d’installation minimale](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="fcf78-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="fcf78-294">[Configuration d’une installation Server Core : vue d’ensemble](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="fcf78-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="fcf78-295">[Applets de commande de cluster de basculement dans Windows PowerShell listées par tâche](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="fcf78-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="fcf78-296">Mappage des commandes Cluster.exe aux applets de commande Windows PowerShell pour les clusters de basculement</span><span class="sxs-lookup"><span data-stu-id="fcf78-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
