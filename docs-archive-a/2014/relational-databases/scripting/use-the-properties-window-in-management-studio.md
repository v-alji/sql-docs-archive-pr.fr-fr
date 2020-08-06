---
title: Utiliser la fenêtre Propriétés dans Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613953"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="43ced-102">Utiliser la fenêtre Propriétés dans Management Studio</span><span class="sxs-lookup"><span data-stu-id="43ced-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="43ced-103">La fenêtre Propriétés décrit l'état d'un élément dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], tel qu'une connexion ou un opérateur Showplan, et fournit des informations sur les objets de base de données tels que les tables, les vues et les concepteurs.</span><span class="sxs-lookup"><span data-stu-id="43ced-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="43ced-104">Vous pouvez également utiliser la fenêtre Propriétés pour afficher les propriétés de la connexion active.</span><span class="sxs-lookup"><span data-stu-id="43ced-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="43ced-105">La plupart des propriétés sont en lecture seule dans la fenêtre Propriétés. Toutefois, elles peuvent être modifiées à d'autres emplacements dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43ced-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="43ced-106">Par exemple, la propriété Database d'une requête est en lecture seule dans la fenêtre Propriétés mais elle peut être modifiée dans la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="43ced-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="43ced-107">Pour afficher des propriétés dans la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="43ced-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="43ced-108">Si la fenêtre Propriétés n'est pas visible, cliquez sur **Fenêtre Propriétés** dans le menu **Affichage** ou appuyez sur F4.</span><span class="sxs-lookup"><span data-stu-id="43ced-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="43ced-109">Activez l'objet dont vous souhaitez afficher les propriétés.</span><span class="sxs-lookup"><span data-stu-id="43ced-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="43ced-110">Recherchez une propriété spécifique dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="43ced-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="43ced-111">Pour afficher les propriétés de connexion d'une fenêtre de requête</span><span class="sxs-lookup"><span data-stu-id="43ced-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="43ced-112">Si la fenêtre Propriétés n'est pas visible, cliquez sur **Fenêtre Propriétés** dans le menu **Affichage** ou appuyez sur F4.</span><span class="sxs-lookup"><span data-stu-id="43ced-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="43ced-113">Dans la fenêtre Propriétés, vous pouvez voir toutes les propriétés de connexion.</span><span class="sxs-lookup"><span data-stu-id="43ced-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="43ced-114">Pour afficher les propriétés d'un opérateur Showplan</span><span class="sxs-lookup"><span data-stu-id="43ced-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="43ced-115">Dans le menu **Requête** , cliquez sur **Inclure le plan d'exécution réel**.</span><span class="sxs-lookup"><span data-stu-id="43ced-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="43ced-116">Dans l'Éditeur de requête SQL, tapez une requête, puis exécutez-la.</span><span class="sxs-lookup"><span data-stu-id="43ced-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="43ced-117">Si la fenêtre Propriétés n'est pas visible, cliquez sur **Fenêtre Propriétés** dans le menu **Affichage** ou appuyez sur F4.</span><span class="sxs-lookup"><span data-stu-id="43ced-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="43ced-118">Sous l'onglet **Plan d'exécution** de l'Éditeur de requête SQL, cliquez sur les icônes des opérateurs pour afficher des informations sur ces derniers dans la fenêtre Propriétés.</span><span class="sxs-lookup"><span data-stu-id="43ced-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ced-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43ced-119">See Also</span></span>  
 [<span data-ttu-id="43ced-120">Fenêtre Propriétés &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="43ced-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
