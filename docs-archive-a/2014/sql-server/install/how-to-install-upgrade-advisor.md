---
title: 'Procédure : installer le conseiller de mise à niveau | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613800"
---
# <a name="how-to-install-upgrade-advisor"></a><span data-ttu-id="c7476-102">Procédure : installer le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="c7476-102">How to: Install Upgrade Advisor</span></span>
  <span data-ttu-id="c7476-103">Le Conseiller de mise à niveau prend en charge l'analyse distante de tous les composants pris en charge, à l'exception de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7476-103">Upgrade Advisor supports remote analysis of all supported components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="c7476-104">Si vous n'analysez pas d'instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez installer le Conseiller de mise à niveau sur n'importe quel ordinateur pouvant se connecter à vos instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7476-104">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to your instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c7476-105">Les composants requis du Conseiller de mise à niveau doivent également être installés sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c7476-105">The computer must also meet Upgrade Advisor prerequisites.</span></span> <span data-ttu-id="c7476-106">Si vous analysez des instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous devez installer le Conseiller de mise à niveau sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c7476-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="c7476-107">Pour plus d’informations, consultez [installation du conseiller de mise à niveau](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="c7476-107">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
### <a name="to-install-upgrade-advisor"></a><span data-ttu-id="c7476-108">Pour installer le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="c7476-108">To install Upgrade Advisor</span></span>  
  
1.  <span data-ttu-id="c7476-109">Démarrez l'installation en appliquant l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7476-109">Start the installation using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="c7476-110">Si vous effectuez l’installation à partir du [!INCLUDE[msCoName](../../includes/msconame-md.md)] site Web, cliquez sur le lien de **Téléchargement** , puis cliquez sur le bouton **exécuter** pour démarrer l’installation.</span><span class="sxs-lookup"><span data-stu-id="c7476-110">If you are installing from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Web site, click the **Download** link and then click the **Run** button to start the installation.</span></span>  
  
    -   <span data-ttu-id="c7476-111">Si vous effectuez l’installation à partir du support du produit, ouvrez le dossier **Redist** , ouvrez le dossier du **conseiller de mise à niveau** , puis double-cliquez sur **SQLUA.msi**.</span><span class="sxs-lookup"><span data-stu-id="c7476-111">If you are installing from the product media, open the **redist** folder, open the **Upgrade Advisor** folder, and then double-click **SQLUA.msi**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c7476-112">Le Conseiller de mise à niveau nécessite [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c7476-112">Upgrade Advisor requires the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4.</span></span> <span data-ttu-id="c7476-113">S'il n'est pas installé, ou si vous disposez d'une version préliminaire, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="c7476-113">If it is not installed, or if you have a pre-release version, an error message will appear.</span></span> <span data-ttu-id="c7476-114">Désinstallez toute version antérieure du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], puis installez la version la plus récente de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c7476-114">Uninstall any earlier version of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] and then install the latest version of .NET Framework 4.</span></span>  
    >   
    >  <span data-ttu-id="c7476-115">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom est un composant requis pour l’installation du [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] conseiller de mise à niveau et n’est pas installé par le programme d’installation du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c7476-115">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="c7476-116">Le programme d’installation vous demande de télécharger et d’installer le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom à partir du [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="c7476-116">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
2.  <span data-ttu-id="c7476-117">Sur la page Bienvenue dans le \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] programme d’installation du conseiller de mise à niveau\*\* , cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c7476-117">On the **Welcome to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor Setup** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c7476-118">Sur la page **contrat de licence** , lisez le contrat de licence.</span><span class="sxs-lookup"><span data-stu-id="c7476-118">On the **License Agreement** page, read the license agreement.</span></span> <span data-ttu-id="c7476-119">Si vous acceptez, sélectionnez **J’accepte le contrat de licence** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="c7476-119">If you agree, select **I accept the license agreement** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="c7476-120">Dans la page **informations d’inscription** , entrez votre nom et votre société.</span><span class="sxs-lookup"><span data-stu-id="c7476-120">On the **Registration Information** page, enter your name and company.</span></span>  
  
5.  <span data-ttu-id="c7476-121">Dans la page **sélection de fonctionnalités** , examinez la valeur **chemin d’installation** .</span><span class="sxs-lookup"><span data-stu-id="c7476-121">On the **Feature Selection** page, review the **Installation path** value.</span></span> <span data-ttu-id="c7476-122">Si nécessaire, utilisez le bouton **Parcourir** pour modifier l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="c7476-122">If necessary, use the **Browse** button to change the location.</span></span> <span data-ttu-id="c7476-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c7476-123">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c7476-124">Dans la page **prêt à installer le programme** , cliquez sur **installer** pour installer le conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c7476-124">On the **Ready to Install the Program** page, click **Install** to install Upgrade Advisor.</span></span>  
  
7.  <span data-ttu-id="c7476-125">Cliquez sur **Terminer** pour quitter l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="c7476-125">Click **Finish** to exit the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7476-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7476-126">See Also</span></span>  
 [<span data-ttu-id="c7476-127">Configuration requise par le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="c7476-127">Upgrade Advisor Prerequisites</span></span>](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
