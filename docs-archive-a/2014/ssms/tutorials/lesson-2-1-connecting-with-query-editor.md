---
title: Connexion à l’aide de l’Éditeur de requête | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611462"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="2dd97-102">Connexion à l'aide de l'Éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="2dd97-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="2dd97-103">permet d'écrire du code ou de le modifier tout en étant déconnecté du serveur.</span><span class="sxs-lookup"><span data-stu-id="2dd97-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="2dd97-104">Cela peut s'avérer utile lorsque le serveur n'est pas disponible ou lorsque vous souhaitez limiter l'utilisation du serveur ou conserver les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="2dd97-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="2dd97-105">Vous pouvez également modifier la connexion de l'Éditeur de requête pour choisir une nouvelle instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sans ouvrir une nouvelle fenêtre de l'Éditeur de requête ou sans retaper du code.</span><span class="sxs-lookup"><span data-stu-id="2dd97-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="2dd97-106">Codage hors ligne</span><span class="sxs-lookup"><span data-stu-id="2dd97-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="2dd97-107">Pour écrire du code hors ligne puis se connecter à différents serveurs</span><span class="sxs-lookup"><span data-stu-id="2dd97-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="2dd97-108">Dans la barre d'outils [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , cliquez sur **Requête de moteur de base de données** pour ouvrir l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="2dd97-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="2dd97-109">Dans la boîte de dialogue **Se connecter au moteur de base de données** , cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="2dd97-110">L'Éditeur de requête s'ouvre et sa barre de titre indique que vous n'êtes pas connecté à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2dd97-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="2dd97-111">Dans le volet du code, tapez les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="2dd97-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="2dd97-112">À ce stade, vous pouvez vous connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en cliquant sur **Se connecter**, **Exécuter**, **Analyser**ou **Afficher le plan d’exécution estimé**. Toutes ces options sont disponibles à partir du menu **Requête** , de la barre d’outils de l’Éditeur de requête, ou du menu contextuel qui s’affiche quand vous cliquez avec le bouton droit dans la fenêtre de l’Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="2dd97-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="2dd97-113">Pour cet exercice, vous allez utiliser la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="2dd97-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="2dd97-114">Dans la barre d'outils, cliquez sur le bouton **Exécuter** pour ouvrir la boîte de dialogue **Se connecter au moteur de base de données** .</span><span class="sxs-lookup"><span data-stu-id="2dd97-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="2dd97-115">Dans la zone **Nom du serveur** , tapez le nom de votre serveur, puis cliquez sur **Options**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="2dd97-116">Dans la liste **Connexion à une base de données** de l'onglet **Propriétés de connexion** , parcourez le contenu du serveur pour sélectionner [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="2dd97-117">Pour ouvrir une autre fenêtre de l'Éditeur de requête avec la même connexion, dans la barre d'outils, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="2dd97-118">Pour changer les connexions, cliquez avec le bouton droit dans la fenêtre de l’Éditeur de requête, pointez sur **Connexion**, puis cliquez sur **Modifier la connexion**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="2dd97-119">Dans la boîte de dialogue **Connexion à SQL Server** , sélectionnez une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'il en existe une disponible, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="2dd97-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="2dd97-120">Cette nouvelle fonctionnalité de l'Éditeur de requête permet d'exécuter facilement le même code sur plusieurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="2dd97-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="2dd97-121">Cela peut s'avérer utile pour les actions de maintenance impliquant l'utilisation de serveurs similaires.</span><span class="sxs-lookup"><span data-stu-id="2dd97-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2dd97-122">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="2dd97-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2dd97-123">Ajout d'une mise en retrait</span><span class="sxs-lookup"><span data-stu-id="2dd97-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
