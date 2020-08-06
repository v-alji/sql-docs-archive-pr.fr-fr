---
title: 'Étape 3 : Ajout et configuration d’un gestionnaire de connexions OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605592"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="1e18c-102">Étape 3 : Ajout et configuration d’un Gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="1e18c-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="1e18c-103">La tâche qui suit l'ajout du Gestionnaire de connexions de fichiers plats pour la connexion à la source de données, consiste à ajouter un Gestionnaire de connexions OLE DB pour la connexion à la destination.</span><span class="sxs-lookup"><span data-stu-id="1e18c-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="1e18c-104">Un Gestionnaire de connexions OLE DB permet à un package d’extraire ou de charger des données dans une source de données compatible OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1e18c-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="1e18c-105">Au moyen du Gestionnaire de connexions OLE DB, vous pouvez spécifier le serveur, la méthode d'authentification et la base de données par défaut pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="1e18c-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="1e18c-106">Au cours de cette leçon, vous allez créer un Gestionnaire de connexions OLE DB qui utilise l’authentification Windows pour la connexion à l’instance locale de **AdventureWorksDB2012**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="1e18c-107">Le Gestionnaire de connexions OLE DB que vous créez sera également référencé par d'autres composants que vous créerez ultérieurement au cours de ce didacticiel, tels que la transformation de recherche et la destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1e18c-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="1e18c-108">Pour ajouter et configurer un Gestionnaire de connexions OLE DB au package SSIS</span><span class="sxs-lookup"><span data-stu-id="1e18c-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="1e18c-109">Cliquez avec le bouton droit dans la zone **Gestionnaires de connexions** et choisissez **Nouvelle connexion OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="1e18c-110">Dans la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="1e18c-111">Dans la zone **Nom du serveur**, entrez **localhost**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="1e18c-112">Lorsque vous spécifiez « localhost » comme nom de serveur, le gestionnaire de connexions se connecte à l'instance par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="1e18c-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="1e18c-113">Pour utiliser une instance distante de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], remplacez « localhost » par le nom du serveur auquel vous souhaitez établir la connexion.</span><span class="sxs-lookup"><span data-stu-id="1e18c-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="1e18c-114">Dans le groupe **Connexion au serveur** , vérifiez que l’option **Utiliser l’authentification Windows** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e18c-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="1e18c-115">Dans le groupe **se connecter à une base de données** , dans la zone **Sélectionner ou entrer un nom de base de données** , tapez ou sélectionnez `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="1e18c-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="1e18c-116">Cliquez sur **Tester la connexion** pour vérifier si les paramètres de connexion que vous avez spécifiés sont valides.</span><span class="sxs-lookup"><span data-stu-id="1e18c-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="1e18c-117">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="1e18c-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1e18c-119">Dans le volet **Connexions de données** de la boîte de dialogue **Configurer le Gestionnaire de connexions OLE DB** , vérifiez que **localhost.AdventureWorksDW2012** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="1e18c-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="1e18c-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e18c-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1e18c-121">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="1e18c-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1e18c-122">Étape 4 : Ajout d’une tâche de flux de données au package</span><span class="sxs-lookup"><span data-stu-id="1e18c-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="1e18c-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e18c-123">See Also</span></span>  
 [<span data-ttu-id="1e18c-124">Gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="1e18c-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
