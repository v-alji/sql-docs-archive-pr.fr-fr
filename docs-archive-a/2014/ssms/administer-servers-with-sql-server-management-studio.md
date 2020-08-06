---
title: Administrer des serveurs à l’aide de SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705923"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="13cba-102">Administrer des serveurs à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="13cba-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="13cba-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]est un client administratif intégré et riche conçu pour répondre aux [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] exigences de gestion des serveurs de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="13cba-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="13cba-104">Dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], les tâches d'administration sont effectuées à l'aide de l'Explorateur d'objets qui vous permet de vous connecter à n'importe quel serveur de la famille des produits [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et de parcourir son contenu sous forme graphique.</span><span class="sxs-lookup"><span data-stu-id="13cba-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="13cba-105">Un serveur peut être une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)], d'[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ou d'[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cba-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="13cba-106">Les composants outil de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] comprennent les serveurs inscrits, l'Explorateur d'objets, l'Explorateur de solutions, l'Explorateur de modèles, la page Détails de l'Explorateur d'objets et la fenêtre de document.</span><span class="sxs-lookup"><span data-stu-id="13cba-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="13cba-107">Pour afficher un outil, dans le menu **Affichage** , cliquez sur le nom de l’outil.</span><span class="sxs-lookup"><span data-stu-id="13cba-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="13cba-108">Pour afficher l’outil Éditeur de requête, cliquez sur le bouton **Nouvelle requête** de la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="13cba-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="13cba-109">Par défaut, le trafic réseau entre [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] et [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] n'est pas chiffré.</span><span class="sxs-lookup"><span data-stu-id="13cba-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="13cba-110">N'utilisez pas de données sensibles (notamment des mots de passe) dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , à moins que vous n'ayez établi une connexion chiffrée.</span><span class="sxs-lookup"><span data-stu-id="13cba-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="13cba-111">Pour plus d’informations, consultez [Activer des connexions chiffrées dans le moteur de base de données &#40;Gestionnaire de configuration SQL Server&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="13cba-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="13cba-112">Utilisez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="13cba-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="13cba-113">Inscrire des serveurs</span><span class="sxs-lookup"><span data-stu-id="13cba-113">Register servers.</span></span>  
  
-   <span data-ttu-id="13cba-114">vous connecter à une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)], de [!INCLUDE[ssAS](../includes/ssas-md.md)], de [!INCLUDE[ssRS](../includes/ssrs.md)] ou de [!INCLUDE[ssIS](../includes/ssis-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="13cba-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="13cba-115">Configurer les propriétés du serveur</span><span class="sxs-lookup"><span data-stu-id="13cba-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="13cba-116">Gérer la base de données et les objets [!INCLUDE[ssAS](../includes/ssas-md.md)] tels que les cubes, les dimensions et les assemblys</span><span class="sxs-lookup"><span data-stu-id="13cba-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="13cba-117">Créer des objets tels que des bases de données, des tables, des cubes, des utilisateurs de base de données et des connexions</span><span class="sxs-lookup"><span data-stu-id="13cba-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="13cba-118">Gérer les fichiers et les groupes de fichiers</span><span class="sxs-lookup"><span data-stu-id="13cba-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="13cba-119">Attacher ou détacher les bases de données</span><span class="sxs-lookup"><span data-stu-id="13cba-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="13cba-120">Lancer des outils de script</span><span class="sxs-lookup"><span data-stu-id="13cba-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="13cba-121">Gérer la sécurité</span><span class="sxs-lookup"><span data-stu-id="13cba-121">Manage security.</span></span>  
  
-   <span data-ttu-id="13cba-122">Afficher les journaux système</span><span class="sxs-lookup"><span data-stu-id="13cba-122">View system logs.</span></span>  
  
-   <span data-ttu-id="13cba-123">Surveiller l'activité actuelle</span><span class="sxs-lookup"><span data-stu-id="13cba-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="13cba-124">Configurer la réplication</span><span class="sxs-lookup"><span data-stu-id="13cba-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="13cba-125">Gérer les index de texte intégral</span><span class="sxs-lookup"><span data-stu-id="13cba-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="13cba-126">Pour démarrer et arrêter [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , utilisez le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="13cba-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cba-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13cba-127">See Also</span></span>  
 <span data-ttu-id="13cba-128">[Utiliser SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="13cba-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="13cba-129">Afficher ou modifier des propriétés de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="13cba-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
