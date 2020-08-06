---
title: Ajouter un rapport personnalisé à Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599767"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="8f828-102">Ajouter un rapport personnalisé à Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f828-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="8f828-103">Cette rubrique explique comment créer un simple rapport [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enregistré comme fichier .rdl, puis ajouter ce fichier à [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en tant que rapport personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8f828-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="8f828-104">permet de créer un large choix de rapports élaborés.</span><span class="sxs-lookup"><span data-stu-id="8f828-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="8f828-105">Pour que vous puissiez créer un rapport en suivant cette rubrique, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8f828-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="8f828-106">Vous n'avez pas besoin d'installer [!INCLUDE[ssRS](../../includes/ssrs.md)] sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter un rapport personnalisé à l'aide de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f828-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="8f828-107">Pour créer un rapport simple enregistré en tant que fichier .rdl</span><span class="sxs-lookup"><span data-stu-id="8f828-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="8f828-108">Cliquez sur **Démarrer**, pointez sur **Programmes**, puis sur **Microsoft SQL Server**, puis cliquez sur **Outils de données SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8f828-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="8f828-109">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="8f828-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="8f828-110">Dans la liste **Types de projets** , cliquez sur **Projets Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="8f828-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="8f828-111">Dans la liste **Modèles** , cliquez sur **Assistant Projet Report Server**.</span><span class="sxs-lookup"><span data-stu-id="8f828-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="8f828-112">Dans la zone **Nom**, tapez **ConnectionsReport**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f828-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="8f828-113">Dans la page **Assistant Rapport** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8f828-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="8f828-114">Dans la page **Sélectionner la source de données** , dans la zone Nom, entrez un nom de connexion à votre [!INCLUDE[ssDE](../../includes/ssde-md.md)], puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="8f828-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="8f828-115">Dans la boîte de dialogue **Propriétés de connexion** , dans la zone de texte **Nom du serveur** , tapez le nom de votre instance de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f828-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="8f828-116">Dans la zone **Sélectionner ou entrer un nom de base de données** , tapez le nom de l’une de vos bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], comme [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f828-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="8f828-117">Dans la page **Sélectionner la source de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8f828-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="8f828-118">Dans la page **Concevoir la requête** , dans la zone **Chaîne de requête** , tapez l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante qui répertorie les connexions en cours à votre [!INCLUDE[ssDE](../../includes/ssde-md.md)], puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8f828-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="8f828-119">La zone Chaîne de requête de l'Assistant Rapport n'accepte pas les paramètres de rapport.</span><span class="sxs-lookup"><span data-stu-id="8f828-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="8f828-120">Les rapports personnalisés plus complexes doivent être créés manuellement.</span><span class="sxs-lookup"><span data-stu-id="8f828-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="8f828-121">Dans la page **Sélectionner le type de rapport** , sélectionnez **Tabulaire**, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8f828-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="8f828-122">Dans la page **Fin de l’Assistant** , dans la zone **Nom du rapport** , tapez **ConnectionsReport**, puis cliquez sur **Terminer** pour créer et enregistrer le rapport.</span><span class="sxs-lookup"><span data-stu-id="8f828-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="8f828-123">Fermez [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f828-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="8f828-124">Copiez **ConnectionsReport.rdl** dans un dossier que vous avez créé sur votre serveur de bases de données pour les rapports personnalisés.</span><span class="sxs-lookup"><span data-stu-id="8f828-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="8f828-125">Pour ajouter un rapport à Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f828-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="8f828-126">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , cliquez avec le bouton droit sur un nœud dans l’Explorateur d’objets, pointez sur **rapports**, puis cliquez sur **rapports personnalisés**.</span><span class="sxs-lookup"><span data-stu-id="8f828-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="8f828-127">Dans la boîte de dialogue **Ouvrir un fichier** , recherchez le dossier des rapports personnalisés, sélectionnez le fichier **ConnectionsReport.rdl** , puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="8f828-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="8f828-128">Quand un nouveau rapport personnalisé est ouvert pour la première fois à partir d’un nœud de l’Explorateur d’objets, il vient s’ajouter à la liste des derniers fichiers utilisés sous **Rapports personnalisés** dans le menu contextuel de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="8f828-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="8f828-129">Un rapport standard s’affiche aussi dans la liste des derniers rapports utilisés sous **Rapports personnalisés**quand vous l’ouvrez pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="8f828-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="8f828-130">En cas de suppression d'un fichier de rapport personnalisé, lorsque l'élément est à nouveau sélectionné, une invite apparaît et propose de supprimer l'élément de la liste des derniers fichiers utilisés.</span><span class="sxs-lookup"><span data-stu-id="8f828-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="8f828-131">Pour modifier le nombre de fichiers dévoilés dans la liste des derniers fichiers utilisés, cliquez sur **Options** dans le menu **Outils** , développez le dossier **Environnement** , puis cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="8f828-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="8f828-132">Ajustez le nombre de fichiers dans la **liste des derniers fichiers utilisés**.</span><span class="sxs-lookup"><span data-stu-id="8f828-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f828-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8f828-133">See Also</span></span>  
 <span data-ttu-id="8f828-134">[Rapports personnalisés dans Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="8f828-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="8f828-135">[Utiliser des rapports personnalisés avec les propriétés de nœud de l’Explorateur d’objets](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8f828-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="8f828-136">[Annuler la suppression des avertissements d’exécution de rapports personnalisés](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="8f828-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="8f828-137">Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f828-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
