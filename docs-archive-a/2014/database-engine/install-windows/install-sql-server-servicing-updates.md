---
title: Installer les mises à jour de maintenance de SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 7d6c962b-c8d0-49f7-a2ac-00ad8dca930a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace0fd187386d9a9d96e82f61d1efaa254f08c6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697115"
---
# <a name="install-sql-server-2014-servicing-updates"></a><span data-ttu-id="7bed7-102">Installer des mises à jour de maintenance de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7bed7-102">Install SQL Server 2014 Servicing Updates</span></span>
  <span data-ttu-id="7bed7-103">Cette rubrique fournit des informations sur l'installation des mises à jour de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bed7-103">This topic provides information about installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7bed7-104">Cette section aborde les sujets suivants :</span><span class="sxs-lookup"><span data-stu-id="7bed7-104">This section provides information about the following:</span></span>  
  
-   <span data-ttu-id="7bed7-105">Installation des mises à jour de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pendant une nouvelle installation</span><span class="sxs-lookup"><span data-stu-id="7bed7-105">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] during a new installation</span></span>  
  
-   <span data-ttu-id="7bed7-106">Installation des mises à jour de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] après qu'il a déjà été installé.</span><span class="sxs-lookup"><span data-stu-id="7bed7-106">Installing updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed.</span></span>  
  
 <span data-ttu-id="7bed7-107">Il est recommandé que les clients évaluent et installent les dernières mises à jour de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en temps voulu pour s'assurer que les systèmes sont à jour avec des mises à jour de sécurité les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="7bed7-107">We recommend that customers evaluate and install latest [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates in a timely manner to make sure that systems are up-to-date with the most recent security updates.</span></span>  
  
## <a name="installing-updates-for-sscurrent-during-a-new-installation"></a><span data-ttu-id="7bed7-108">Installation des mises à jour de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pendant une nouvelle installation</span><span class="sxs-lookup"><span data-stu-id="7bed7-108">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] During a New Installation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7bed7-109">intègre les dernières mises à jour du produit avec l'installation principale, de sorte que le produit principal et les mises à jour applicables sont installés en même temps.</span><span class="sxs-lookup"><span data-stu-id="7bed7-109">setup integrates the latest product updates with the main product installation so that the main product and its applicable updates are installed at the same time.</span></span> <span data-ttu-id="7bed7-110">La mise à jour du produit peut rechercher les mises à jour applicables à partir de :</span><span class="sxs-lookup"><span data-stu-id="7bed7-110">Product Update can search for the applicable updates from:</span></span>  
  
-   [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7bed7-111">Update</span><span class="sxs-lookup"><span data-stu-id="7bed7-111">Update</span></span>  
  
-   <span data-ttu-id="7bed7-112">Windows Server Update Services (WSUS)</span><span class="sxs-lookup"><span data-stu-id="7bed7-112">Windows Server Update Services (WSUS)</span></span>  
  
-   <span data-ttu-id="7bed7-113">Un dossier local</span><span class="sxs-lookup"><span data-stu-id="7bed7-113">A local folder</span></span>  
  
-   <span data-ttu-id="7bed7-114">Un partage de réseau</span><span class="sxs-lookup"><span data-stu-id="7bed7-114">A network share</span></span>  
  
 <span data-ttu-id="7bed7-115">Une fois que le programme d'installation a détecté les versions les plus récentes des mises à jour applicables, il les télécharge et les intègre dans le processus d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cours.</span><span class="sxs-lookup"><span data-stu-id="7bed7-115">After Setup finds the latest versions of the applicable updates, it downloads and integrates them with the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup process.</span></span> <span data-ttu-id="7bed7-116">La fonctionnalité de mise à jour du produit peut inclure une mise à jour, un Service Pack, ou un Service Pack et la mise à jour cumulative.</span><span class="sxs-lookup"><span data-stu-id="7bed7-116">Product Update can include a cumulative update, service pack, or service pack plus cumulative update.</span></span> <span data-ttu-id="7bed7-117">La fonctionnalité de mise à jour du produit est une extension de la [fonctionnalité Slipstream](https://go.microsoft.com/fwlink/?LinkId=219945) qui était disponible dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span><span class="sxs-lookup"><span data-stu-id="7bed7-117">Product Update functionality is an extension of the [Slipstream Functionality](https://go.microsoft.com/fwlink/?LinkId=219945) that was available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] PCU1.</span></span>  
  
## <a name="installing-updates-for-sscurrent-after-it-has-already-been-installed"></a><span data-ttu-id="7bed7-118">Installation des mises à jour de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] après qu'il a déjà été installé</span><span class="sxs-lookup"><span data-stu-id="7bed7-118">Installing Updates for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after it has already been installed</span></span>  
 <span data-ttu-id="7bed7-119">Sur une instance installée de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , nous vous recommandons d’appliquer toutes les mises à jour disponibles : mises en production générales de distribution (GDR-sécurité/mises à jour critiques), service packs (SP), ainsi que la dernière mise à jour cumulative disponible (Cu).</span><span class="sxs-lookup"><span data-stu-id="7bed7-119">On an installed instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you apply all available updates: General Distribution Releases (GDR - security/critical updates), Service Packs (SP), as well as the latest available Cumulative Update (CU).</span></span>  
  
 <span data-ttu-id="7bed7-120">Selon le type de version de maintenance, SQL Server mises à jour sont disponibles via Microsoft Update (MU), le centre de téléchargement Microsoft et/ou le serveur de correctifs du support technique.</span><span class="sxs-lookup"><span data-stu-id="7bed7-120">Depending on the type of servicing release, SQL Server updates are available via Microsoft Update (MU), the Microsoft Download Center, and/or the Customer Support Services hotfix Server.</span></span> <span data-ttu-id="7bed7-121">Les mises à jour critiques et de sécurité pour SQL Server sont fournies automatiquement par Microsoft Update (pour pouvoir consulter ces mises à jour, vous devez vous abonner à MU via Windows Update dans le panneau de configuration).</span><span class="sxs-lookup"><span data-stu-id="7bed7-121">Security and Critical updates for SQL Server are automatically provided by Microsoft Update (to be able to see these updates you need to opt-in to MU through Windows Update in Control panel).</span></span> <span data-ttu-id="7bed7-122">Les service packs sont disponibles sur MU comme téléchargements facultatifs/importants, ainsi que dans le centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="7bed7-122">Service Packs are available on MU as Optional/Important downloads as well as the Download Center.</span></span> <span data-ttu-id="7bed7-123">Les mises à jour cumulatives sont disponibles sur le serveur de téléchargement de correctifs Microsoft fourni dans les Articles de la base de connaissances CU.</span><span class="sxs-lookup"><span data-stu-id="7bed7-123">Cumulative updates are available on the Microsoft hotfix download server provided in CU Knowledge Base articles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bed7-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7bed7-124">See Also</span></span>  
 <span data-ttu-id="7bed7-125">[Installer SQL Server 2014 à partir de l’Assistant Installation &#40;le programme d’installation&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7bed7-125">[Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md) </span></span>  
 <span data-ttu-id="7bed7-126">[Installation des mises à jour à partir de l’invite de commandes](installing-updates-from-the-command-prompt.md) [Ajout de fonctionnalités à une Instance de SQL Server 2014 &#40;le programme d’installation&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span><span class="sxs-lookup"><span data-stu-id="7bed7-126">[Installing updates from the command prompt](installing-updates-from-the-command-prompt.md) [Add Features to an Instance of SQL Server 2014 &#40;Setup&#41;](add-features-to-an-instance-of-sql-server-setup.md) </span></span>  
 [<span data-ttu-id="7bed7-127">Ignorer une installation de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7bed7-127">Drop a SQL Server 2014 Installation</span></span>](repair-a-failed-sql-server-installation.md)  
  
  
