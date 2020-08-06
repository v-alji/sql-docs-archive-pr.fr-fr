---
title: 'Étape 1 : Création d’un projet Integration Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f14521b5-941e-443b-8f5e-385f98e37fbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d6d16d7febcdecb01eb7a93167c2a18d225a9c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605596"
---
# <a name="step-1-creating-a-new-integration-services-project"></a><span data-ttu-id="ad302-102">Étape 1 : Création d’un nouveau projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="ad302-102">Step 1: Creating a New Integration Services Project</span></span>
  <span data-ttu-id="ad302-103">La première étape de la création d'un package dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] consiste à créer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad302-103">The first step in creating a package in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is to create an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="ad302-104">Ce projet comprend les modèles des objets (sources de données, vues de source de données et packages) que vous utilisez dans une solution de transformation de données.</span><span class="sxs-lookup"><span data-stu-id="ad302-104">This project includes the templates for the objects - data sources, data source views, and packages - that you use in a data transformation solution.</span></span>  
  
 <span data-ttu-id="ad302-105">Les packages que vous allez créer dans ce didacticiel [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] interprètent les valeurs des données de paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="ad302-105">The packages that you will create in this [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial interpret the values of locale-sensitive data.</span></span> <span data-ttu-id="ad302-106">Si votre ordinateur n'est pas configuré pour l'utilisation du paramètre Anglais (États-Unis), vous devez définir des propriétés supplémentaires dans le package.</span><span class="sxs-lookup"><span data-stu-id="ad302-106">If your computer is not configured to use the regional option English (United States), you need to set additional properties in the package.</span></span> <span data-ttu-id="ad302-107">Les packages que vous utilisez dans les leçons 2 à 5 sont copiés à partir du package créé dans la leçon 1 ; vous n'avez pas besoin de mettre à jour les propriétés des paramètres régionaux dans les packages copiés.</span><span class="sxs-lookup"><span data-stu-id="ad302-107">The packages that you use in lessons 2 through 5 are copied from the package created in lesson 1, and you need not update locale-sensitive properties in the copied packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ad302-108">Ce didacticiel nécessite Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="ad302-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
>   
>  <span data-ttu-id="ad302-109">Pour plus d’informations sur l’installation de SQL Server Data Tools, consultez [Télécharger SSDT (SQL Server Data Tools)](https://msdn.microsoft.com/data/hh297027).</span><span class="sxs-lookup"><span data-stu-id="ad302-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://msdn.microsoft.com/data/hh297027).</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="ad302-110">Pour créer un nouveau projet Integration Services</span><span class="sxs-lookup"><span data-stu-id="ad302-110">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="ad302-111">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, puis sur **Microsoft SQL Server**et cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ad302-111">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, and click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="ad302-112">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet** pour créer un projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad302-112">On the **File** menu, point to **New**, and click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="ad302-113">Dans la boîte de dialogue **Nouveau projet** , développez le nœud **Business Intelligence** sous **Modèles installés**, puis sélectionnez **Projet Integration Services** dans le volet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="ad302-113">In the **New Project** dialog box, expand the **Business Intelligence** node under **Installed Templates**, and select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="ad302-114">Dans la zone **Nom** , remplacez le nom par défaut par **SSIS Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="ad302-114">In the **Name** box, change the default name to **SSIS Tutorial**.</span></span> <span data-ttu-id="ad302-115">Vous pouvez éventuellement désactiver la case à cocher **Créer le répertoire pour la solution** .</span><span class="sxs-lookup"><span data-stu-id="ad302-115">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="ad302-116">Acceptez l'emplacement par défaut ou cliquez sur **Parcourir** pour rechercher et accéder au dossier que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ad302-116">Accept the default location, or click **Browse** to browse to locate the folder you want to use.</span></span> <span data-ttu-id="ad302-117">Dans la boîte de dialogue **Emplacement du projet** , cliquez sur le dossier, puis sur **Sélectionner le dossier**.</span><span class="sxs-lookup"><span data-stu-id="ad302-117">In the **Project Location** dialog box, click the folder and click **Select Folder**.</span></span>  
  
6.  <span data-ttu-id="ad302-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad302-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="ad302-119">Par défaut, un package vide nommé **Package.dtsx**est créé et ajouté à votre projet sous Packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="ad302-119">By default, an empty package, titled **Package.dtsx**, will be created and added to your project under SSIS Packages.</span></span>  
  
7.  <span data-ttu-id="ad302-120">Dans la barre d’outils de **l’Explorateur de solutions** , cliquez avec le bouton droit sur **Package.dtsx**, choisissez **Renommer**, puis attribuez au package par défaut le nom **Lesson 1.dtsx**.</span><span class="sxs-lookup"><span data-stu-id="ad302-120">In **Solution Explorer** toolbar, right-click **Package.dtsx**, click **Rename**, and rename the default package to **Lesson 1.dtsx**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ad302-121">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="ad302-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ad302-122">Étape 2 : Ajout et configuration d’un Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="ad302-122">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
  
