---
title: Définition d’une source de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600306"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="5b43a-102">Définition d'une source de données</span><span class="sxs-lookup"><span data-stu-id="5b43a-102">Defining a Data Source</span></span>
  <span data-ttu-id="5b43a-103">Après avoir créé un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , vous commencez généralement par définir une ou plusieurs sources de données à utiliser dans ce projet.</span><span class="sxs-lookup"><span data-stu-id="5b43a-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="5b43a-104">Lorsque vous définissez une source de données, vous définissez les informations de la chaîne de connexion qui seront utilisées pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="5b43a-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="5b43a-105">Pour plus d’informations, consultez [Créer une source de données &#40;SSAS Multidimensionnel&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="5b43a-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="5b43a-106">Au cours de la tâche suivante, vous allez définir la base de données exemple AdventureWorksDWSQLServer2012 comme source de données pour le projet Didacticiel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b43a-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="5b43a-107">Si cette base de données est située sur votre ordinateur local dans le cadre de ce didacticiel, sachez que les bases de données sources sont généralement hébergées sur un ou plusieurs ordinateurs distants.</span><span class="sxs-lookup"><span data-stu-id="5b43a-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="5b43a-108">Pour définir une nouvelle source de données</span><span class="sxs-lookup"><span data-stu-id="5b43a-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="5b43a-109">Dans l’explorateur de solutions (à droite de la fenêtre de Microsoft Visual Studio), cliquez avec le bouton droit sur **Sources de données**, puis cliquez sur **Nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="5b43a-110">Sur la page Bienvenue dans l' **Assistant source de données** de l' **Assistant source de données**, cliquez sur **suivant** pour ouvrir la page **Sélectionner la méthode de définition de la connexion** .</span><span class="sxs-lookup"><span data-stu-id="5b43a-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="5b43a-111">Dans la page **Sélectionner la méthode de définition de la connexion** , vous pouvez définir une source de données basée sur une nouvelle connexion, sur une connexion existante ou sur un objet de source de données défini précédemment.</span><span class="sxs-lookup"><span data-stu-id="5b43a-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="5b43a-112">Au cours de ce didacticiel, vous allez définir une source de données basée sur une nouvelle connexion.</span><span class="sxs-lookup"><span data-stu-id="5b43a-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="5b43a-113">Vérifiez que l’option **Créer une source de données basée sur une connexion existante ou nouvelle** est sélectionnée, puis cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="5b43a-114">Dans la boîte de dialogue **Gestionnaire de connexions** vous définissez les propriétés de connexion de la source de données.</span><span class="sxs-lookup"><span data-stu-id="5b43a-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="5b43a-115">Dans la zone de liste **Fournisseur** , vérifiez que **Native OLE DB\SQL Server Native Client 11.0** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5b43a-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="5b43a-116">prend également en charge d’autres fournisseurs, affichés dans la liste **Fournisseur** .</span><span class="sxs-lookup"><span data-stu-id="5b43a-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="5b43a-117">Dans la zone de texte **nom du serveur** , tapez `localhost` .</span><span class="sxs-lookup"><span data-stu-id="5b43a-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="5b43a-118">Pour vous connecter à une instance nommée sur votre ordinateur local, tapez \*\*localhost \\<nom \> \*\*de l’instance.</span><span class="sxs-lookup"><span data-stu-id="5b43a-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="5b43a-119">Pour se connecter à l'ordinateur spécifique au lieu de l'ordinateur local, tapez le nom d'ordinateur ou l'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="5b43a-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="5b43a-120">Vérifiez que l’option **Utiliser l’authentification Windows** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b43a-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="5b43a-121">Dans la liste **Sélectionner ou entrer un nom de base de données** , sélectionnez **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="5b43a-122">Cliquez sur **Tester la connexion** pour tester la connexion à la base de données.</span><span class="sxs-lookup"><span data-stu-id="5b43a-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="5b43a-123">Cliquez sur **OK**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="5b43a-124">Dans la page **Informations d’emprunt d’identité** de l’Assistant, vous pouvez définir les informations d’identification de sécurité que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] doit utiliser pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="5b43a-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="5b43a-125">L'emprunt d'identité affecte le compte Windows utilisé pour la connexion à la source de données lorsque l'authentification Windows est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5b43a-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="5b43a-126">ne prend pas en charge l’emprunt d’identité pour le traitement des objets OLAP.</span><span class="sxs-lookup"><span data-stu-id="5b43a-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="5b43a-127">Sélectionnez **Utiliser le compte de service**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="5b43a-128">Dans la page **Fin de l’Assistant** , acceptez le nom par défaut **Adventure Works DW 2012**et cliquez sur **Terminer** pour créer la source de données.</span><span class="sxs-lookup"><span data-stu-id="5b43a-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b43a-129">Pour modifier les propriétés d’une source de données après qu’elle a été créée, double-cliquez sur cette source de données dans le dossier **Sources de données** pour en afficher les propriétés dans le **Concepteur de source de données**.</span><span class="sxs-lookup"><span data-stu-id="5b43a-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="5b43a-130">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="5b43a-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="5b43a-131">Définition d'une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="5b43a-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="5b43a-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b43a-132">See Also</span></span>  
 [<span data-ttu-id="5b43a-133">Créer une source de données &#40;SSAS Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="5b43a-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  
