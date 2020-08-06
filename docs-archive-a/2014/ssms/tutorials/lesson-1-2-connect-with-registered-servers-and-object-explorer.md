---
title: Se connecter avec le composant Serveurs inscrits et l’Explorateur d’objets | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: d6b3911f-68b4-4483-831b-df89d6400add
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4bc75ad7f3682765dc102064a5621cd541ccd12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695183"
---
# <a name="connect-with-registered-servers-and-object-explorer"></a><span data-ttu-id="347b9-102">Connexion avec le composant Serveurs inscrits et l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="347b9-102">Connect with Registered Servers and Object Explorer</span></span>
  <span data-ttu-id="347b9-103">Ce didacticiel montre l'utilisation des serveurs inscrits et de l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="347b9-103">This tutorial demonstrates the use of Registered Servers and Object Explorer.</span></span>  
  
 <span data-ttu-id="347b9-104">Ce didacticiel utilise la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="347b9-104">This tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="347b9-105">Pour optimiser la sécurité, les exemples de bases de données ne sont pas installés par défaut.</span><span class="sxs-lookup"><span data-stu-id="347b9-105">To help enhance security, by default, the sample databases are not installed.</span></span> <span data-ttu-id="347b9-106">Pour plus d’informations, consultez [Installation d’exemples et d’exemples de bases de données SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="347b9-106">For more information, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="connecting-to-servers"></a><span data-ttu-id="347b9-107">Connexion à des serveurs</span><span class="sxs-lookup"><span data-stu-id="347b9-107">Connecting to Servers</span></span>  
 <span data-ttu-id="347b9-108">La barre d'outils du composant Serveurs inscrits comprend des boutons pour le [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]et [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-108">The toolbar of the Registered Servers component has buttons for the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="347b9-109">Vous pouvez inscrire un ou plusieurs de ces types de serveurs pour une administration plus aisée.</span><span class="sxs-lookup"><span data-stu-id="347b9-109">You can register one or more of these server types for convenient management.</span></span> <span data-ttu-id="347b9-110">Effectuez l'exercice ci-après pour inscrire la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="347b9-110">Try the following exercise to register the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
#### <a name="to-register-the-database"></a><span data-ttu-id="347b9-111">Pour enregistrer la base de données</span><span class="sxs-lookup"><span data-stu-id="347b9-111">To register the database</span></span>  
  
1.  <span data-ttu-id="347b9-112">Dans la barre d’outils Serveurs inscrits, cliquez sur **Moteur de base de données** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="347b9-112">On the Registered Servers toolbar, click **Database Engine** if you have to.</span></span> <span data-ttu-id="347b9-113">(Il se peut qu'il soit déjà sélectionné.)</span><span class="sxs-lookup"><span data-stu-id="347b9-113">(It may already be selected.)</span></span>  
  
2.  <span data-ttu-id="347b9-114">Développez **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="347b9-114">Expand **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="347b9-115">Cliquez avec le bouton droit sur **Groupes de serveurs locaux**, puis cliquez sur **Nouvelle inscription de serveur**.</span><span class="sxs-lookup"><span data-stu-id="347b9-115">Right-click **Local Server Groups**, and then click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="347b9-116">Dans la boîte de dialogue **Nouvelle inscription de serveur** , dans la zone de texte **Nom du serveur** , tapez le nom de votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-116">In the **New Server Registration** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="347b9-117">Dans la zone **Nom du serveur inscrit** , tapez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-117">In the **Registered server name** box, type [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
6.  <span data-ttu-id="347b9-118">Sous l’onglet **Propriétés de connexion** , dans la liste **se connecter à la base de données** , sélectionnez **\<Browse server...>** .</span><span class="sxs-lookup"><span data-stu-id="347b9-118">On the **Connection Properties** tab, in the **Connect to database** list, select **\<Browse server...>**.</span></span>  
  
7.  <span data-ttu-id="347b9-119">Dans la boîte de dialogue **Rechercher les bases de données** , cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="347b9-119">In the **Browse for Databases** dialog box, click **Yes**.</span></span>  
  
8.  <span data-ttu-id="347b9-120">Dans la boîte de dialogue **Rechercher une base de données sur le serveur** , sélectionnez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="347b9-120">In the **Browse Server for Database** dialog box, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
9. <span data-ttu-id="347b9-121">Cliquez sur **Tester**pour vérifier que le serveur a été inscrit correctement.</span><span class="sxs-lookup"><span data-stu-id="347b9-121">To verify that the server has been registered correctly, click **Test**.</span></span>  
  
10. <span data-ttu-id="347b9-122">Dans la boîte de dialogue **Nouvelle inscription de serveur** , cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="347b9-122">In the **New Server Registration** dialog box, click **Save**.</span></span>  
  
## <a name="connecting-with-object-explorer"></a><span data-ttu-id="347b9-123">Connexion avec l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="347b9-123">Connecting with Object Explorer</span></span>  
 <span data-ttu-id="347b9-124">Tout comme le composant Serveurs inscrits, l'Explorateur d'objets peut se connecter au [!INCLUDE[ssDE](../../includes/ssde-md.md)], à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]et à [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-124">Like Registered Servers, Object Explorer can connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
#### <a name="to-connect-with-object-explorer"></a><span data-ttu-id="347b9-125">Pour se connecter avec l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="347b9-125">To connect with Object Explorer</span></span>  
  
1.  <span data-ttu-id="347b9-126">Dans la barre d’outils de l’Explorateur d’objets, cliquez sur **Se connecter** pour dérouler la liste des types de connexions possibles, puis sélectionnez **Moteur de base de données**.</span><span class="sxs-lookup"><span data-stu-id="347b9-126">On the toolbar of Object Explorer, click **Connect** for a list of possible connection types, and then select **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="347b9-127">Dans la boîte de dialogue **Se connecter au serveur** , dans la zone de texte **Nom du serveur** , tapez le nom de votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-127">In the **Connect to Server** dialog box, in the **Server name** text box, type the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="347b9-128">Cliquez sur **Options** et parcourez la liste des choix.</span><span class="sxs-lookup"><span data-stu-id="347b9-128">Click **Options** and explore the choices.</span></span>  
  
4.  <span data-ttu-id="347b9-129">Cliquez sur **Se connecter**pour vous connecter au serveur.</span><span class="sxs-lookup"><span data-stu-id="347b9-129">To connect to the server, click **Connect**.</span></span> <span data-ttu-id="347b9-130">Si vous étiez déjà connecté, l'Explorateur d'objets s'affiche de nouveau et ce serveur est activé.</span><span class="sxs-lookup"><span data-stu-id="347b9-130">If you are already connected, this action just returns you to Object Explorer and sets the focus on that server.</span></span>  
  
     <span data-ttu-id="347b9-131">Avec l'Explorateur d'objets, vous pouvez administrer la sécurité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la réplication et la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="347b9-131">With Object Explorer you can administer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Security, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, Replication, and Database Mail.</span></span> <span data-ttu-id="347b9-132">L'Explorateur d'objets peut gérer uniquement certaines fonctionnalités de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]et [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-132">Object Explorer can only manage some of the features of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], and [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span></span> <span data-ttu-id="347b9-133">Chacun de ces composants disposent d'outils spécialisés supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="347b9-133">Each of those components has additional specialized tools.</span></span>  
  
5.  <span data-ttu-id="347b9-134">Dans l’Explorateur d’objets, développez le dossier **Bases de données** et sélectionnez [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="347b9-134">In Object Explorer, expand the **Databases** folder and select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
     <span data-ttu-id="347b9-135">Notez que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] présente les bases de données système dans un dossier séparé.</span><span class="sxs-lookup"><span data-stu-id="347b9-135">Notice that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] presents the system databases in a separate folder.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="347b9-136">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="347b9-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="347b9-137">Modifier la disposition d'environnement</span><span class="sxs-lookup"><span data-stu-id="347b9-137">Change the Environment Layout</span></span>](lesson-1-3-change-the-environment-layout.md)  
  
  
