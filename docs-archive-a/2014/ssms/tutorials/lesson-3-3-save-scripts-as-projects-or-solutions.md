---
title: Enregistrer des scripts sous forme de projets ou de solutions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702228"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="b7e68-102">Enregistrer des scripts sous forme de projets ou de solutions</span><span class="sxs-lookup"><span data-stu-id="b7e68-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="b7e68-103">Les développeurs familiarisés avec [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio seront heureux de pouvoir utiliser l'Explorateur de solutions dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7e68-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b7e68-104">Les scripts sur lesquels votre activité est basée peuvent être groupés en projets de scripts et ces projets être gérés ensemble sous la forme d'une solution.</span><span class="sxs-lookup"><span data-stu-id="b7e68-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="b7e68-105">Lorsque les scripts sont placés dans des projets de scripts et des solutions, il est possible de les ouvrir en groupe ou de les enregistrer ensemble dans un produit de contrôle du code source tel que Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="b7e68-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="b7e68-106">Les projets de scripts contiennent les informations de connexion pour que les scripts puissent s'exécuter correctement et peuvent inclure des fichiers non script tels que des fichiers texte.</span><span class="sxs-lookup"><span data-stu-id="b7e68-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="b7e68-107">Au cours de l'exercice pratique suivant, vous allez créer un script court qui interroge la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , et qui est placé dans un projet de scripts et une solution.</span><span class="sxs-lookup"><span data-stu-id="b7e68-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="b7e68-108">Utilisation des projets de scripts et des solutions</span><span class="sxs-lookup"><span data-stu-id="b7e68-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="b7e68-109">Pour créer un projet de scripts et une solution</span><span class="sxs-lookup"><span data-stu-id="b7e68-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="b7e68-110">Ouvrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]et établissez une connexion à un serveur avec l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="b7e68-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="b7e68-111">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="b7e68-112">La boîte de dialogue **Nouveau projet** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="b7e68-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b7e68-113">Dans la zone de texte **Nom** , tapez **StatusCheck**, cliquez sur **Scripts SQL Server** dans **Modèles**, puis cliquez sur **OK** pour ouvrir une nouvelle solution et un projet de scripts.</span><span class="sxs-lookup"><span data-stu-id="b7e68-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="b7e68-114">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Connexions**et choisissez **Nouvelle connexion**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="b7e68-115">La boîte de dialogue **Se connecter au serveur** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b7e68-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="b7e68-116">Dans la zone de liste **Nom du serveur** , tapez le nom de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="b7e68-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="b7e68-117">Cliquez sur **Options**, puis sur l’onglet **Propriétés de connexions** .</span><span class="sxs-lookup"><span data-stu-id="b7e68-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="b7e68-118">Dans la zone **Se connecter à la base de données** , parcourez le serveur, sélectionnez la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="b7e68-119">Les données de connexion concernant la base de données sont ajoutées au projet.</span><span class="sxs-lookup"><span data-stu-id="b7e68-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="b7e68-120">Si la fenêtre des propriétés ne s'affiche pas, sélectionnez la nouvelle connexion dans l'Explorateur de solutions et appuyez sur F4.</span><span class="sxs-lookup"><span data-stu-id="b7e68-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="b7e68-121">Les propriétés de la connexion s’affichent et présentent les informations relatives à la connexion concernant la **Base de données initiale** qui est [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7e68-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="b7e68-122">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur la connexion, puis cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="b7e68-123">Une nouvelle requête nommée **SQLQuery1.sql** est créée, connectée à la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sur votre serveur et ajoutée à votre projet de scripts.</span><span class="sxs-lookup"><span data-stu-id="b7e68-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="b7e68-124">Dans l'Éditeur de requête, tapez la requête suivante pour déterminer le nombre de bons de commande pour lesquels les dates d'échéance sont antérieures aux dates de début.</span><span class="sxs-lookup"><span data-stu-id="b7e68-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="b7e68-125">(Vous pouvez copier et coller le code à partir de la fenêtre du didacticiel.)</span><span class="sxs-lookup"><span data-stu-id="b7e68-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7e68-126">Si vous avez besoin de davantage d'espace pour taper votre requête, appuyez sur Maj+Alt+Entrée pour afficher un plein écran.</span><span class="sxs-lookup"><span data-stu-id="b7e68-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="b7e68-127">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **SQLQuery1**et choisissez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="b7e68-128">Tapez **Check ordres de validation. SQL** comme nouveau nom de la requête, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="b7e68-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="b7e68-129">Pour enregistrer votre solution et votre projet de scripts, dans le menu **Fichier** , cliquez sur **Enregistrer tout**.</span><span class="sxs-lookup"><span data-stu-id="b7e68-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b7e68-130">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="b7e68-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b7e68-131">Résumé : Solutions et projets de script</span><span class="sxs-lookup"><span data-stu-id="b7e68-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  
