---
title: À propos du Moteur de base de données SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], installing
ms.assetid: d0876e7f-aa52-4dd7-bd5c-029e2ffded5f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 93e3d7a749fe6be47cc84d43509a6f378476b2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701544"
---
# <a name="about-the-sql-server-database-engine"></a><span data-ttu-id="b3ea3-102">À propos du moteur de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3ea3-102">About the SQL Server Database Engine</span></span>
  <span data-ttu-id="b3ea3-103">Le composant [!INCLUDE[ssDE](../../includes/ssde-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est le service de base pour le stockage, le traitement et la protection des données.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-103">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="b3ea3-104">Le [!INCLUDE[ssDE](../../includes/ssde-md.md)] fournit un accès contrôlé et un traitement transactionnel rapide qui répondent aux exigences des applications les plus gourmandes en termes de données dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications in your enterprise.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b3ea3-105">prend en charge jusqu’à 50 instances du [!INCLUDE[ssDE](../../includes/ssde-md.md)] sur un seul ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-105">supports up to 50 instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on a single computer.</span></span> <span data-ttu-id="b3ea3-106">Pour créer une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation par défaut, consultez [installer SQL Server 2014 à partir de l’assistant installation &#40;&#41;d' ](install-sql-server-from-the-installation-wizard-setup.md)installation.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-106">To create a typical [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation, see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
 <span data-ttu-id="b3ea3-107">**Important** Pour des installations locales, vous devez exécuter le programme d’installation en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-107">**Important** For local installations, you must run Setup as an administrator.</span></span> <span data-ttu-id="b3ea3-108">Si vous installez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d'un partage distant, vous devez utiliser un compte de domaine qui a les autorisations de lecture et d'exécution sur le partage distant.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-108">If you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a remote share, you must use a domain account that has read and execute permissions on the remote share.</span></span>  
  
 <span data-ttu-id="b3ea3-109">Les fonctionnalités suivantes sont installées quand vous sélectionnez **Moteur de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** dans la page Composants à installer de l’Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b3ea3-109">The following features are installed when you select **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Database Engine** on the Components to Install page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard:</span></span>  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   <span data-ttu-id="b3ea3-110">Réplication (composant facultatif)</span><span class="sxs-lookup"><span data-stu-id="b3ea3-110">Replication - is an optional component</span></span>  
  
-   <span data-ttu-id="b3ea3-111">Recherche en texte intégral (composant facultatif)</span><span class="sxs-lookup"><span data-stu-id="b3ea3-111">Full-Text Search - is an optional component</span></span>  
  
-   <span data-ttu-id="b3ea3-112">Data Quality Services est un composant facultatif</span><span class="sxs-lookup"><span data-stu-id="b3ea3-112">Data Quality Services - is an optional component</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3ea3-113">Dans cette version, le fait de cocher la case **Data Quality Services** au moment de l’installation n’installe pas le serveur Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="b3ea3-113">In this release, selecting the **Data Quality Services** check box in setup does not install the Data Quality Services (DQS) server.</span></span> <span data-ttu-id="b3ea3-114">Vous devrez procéder à des étapes supplémentaires après l'installation pour installer le serveur DQS.</span><span class="sxs-lookup"><span data-stu-id="b3ea3-114">You will have to perform additional steps post installation to install DQS server.</span></span> <span data-ttu-id="b3ea3-115">Pour plus d’informations, consultez [Installer Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="b3ea3-115">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
 <span data-ttu-id="b3ea3-116">Les fonctionnalités supplémentaires suivantes sont des options pour un grand nombre de scénarios utilisateur classiques :</span><span class="sxs-lookup"><span data-stu-id="b3ea3-116">The following additional features are options for many typical user scenarios:</span></span>  
  
-   <span data-ttu-id="b3ea3-117">Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="b3ea3-117">Data Quality Client</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
-   <span data-ttu-id="b3ea3-118">Composants de connectivité</span><span class="sxs-lookup"><span data-stu-id="b3ea3-118">Connectivity components</span></span>  
  
-   <span data-ttu-id="b3ea3-119">Modèles de programmation</span><span class="sxs-lookup"><span data-stu-id="b3ea3-119">Programming models</span></span>  
  
-   <span data-ttu-id="b3ea3-120">Outils d'administration</span><span class="sxs-lookup"><span data-stu-id="b3ea3-120">Management tools</span></span>  
  
-   [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]  
  
-   <span data-ttu-id="b3ea3-121">Composants de documentation</span><span class="sxs-lookup"><span data-stu-id="b3ea3-121">Documentation components</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3ea3-122">Par défaut, les exemples de bases de données et les exemples de code ne sont pas installés dans le cadre de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3ea3-122">By default, sample databases and sample code are not installed as part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="b3ea3-123">Pour installer les exemples de bases de données et les exemples de code, consultez le [site web CodePlex](https://go.microsoft.com/fwlink/?LinkId=87843).</span><span class="sxs-lookup"><span data-stu-id="b3ea3-123">To install sample databases and sample code, see the [CodePlex Web site](https://go.microsoft.com/fwlink/?LinkId=87843).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ea3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b3ea3-124">See Also</span></span>  
 <span data-ttu-id="b3ea3-125">[Fonctionnalités prises en charge par les éditions de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="b3ea3-125">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="b3ea3-126">[Éditions et composants de SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="b3ea3-126">[Editions and Components of SQL Server 2014](../../sql-server/editions-and-components-of-sql-server-2016.md) </span></span>  
 <span data-ttu-id="b3ea3-127">[Planification d'une installation SQL Server](../../sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="b3ea3-127">[Planning a SQL Server Installation](../../sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="b3ea3-128">[Solutions haute disponibilité &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b3ea3-128">[High Availability Solutions &#40;SQL Server&#41;](../../sql-server/failover-clusters/high-availability-solutions-sql-server.md) </span></span>  
 [<span data-ttu-id="b3ea3-129">Effectuez une mise à niveau vers SQL Server 2014 à l’aide de l’Assistant Installation &#40;le programme d’installation&#41;</span><span class="sxs-lookup"><span data-stu-id="b3ea3-129">Upgrade to SQL Server 2014 Using the Installation Wizard &#40;Setup&#41;</span></span>](upgrade-sql-server-using-the-installation-wizard-setup.md)  
  
  
