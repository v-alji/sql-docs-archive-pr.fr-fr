---
title: 'Tâche 3 (facultatif) : examen des vues d’abonnement | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3f1d3eb7-2baa-4215-b040-0b41e3d10740
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 35cf0c246ab778b46a2ceaa2b6ff6fad02d0b670
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601839"
---
# <a name="task-3-optional-reviewing-the-subscription-views"></a><span data-ttu-id="028a1-102">Tâche 3 (facultatif) : Examiner les vues d’abonnement</span><span class="sxs-lookup"><span data-stu-id="028a1-102">Task 3 (Optional): Reviewing the Subscription Views</span></span>
  <span data-ttu-id="028a1-103">Dans cette tâche, vous allez vérifier que les vues SQL sont créées à l'aide de SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="028a1-103">In this task, you confirm that the SQL views are created by using SQL Server Management Studio.</span></span>

1.  <span data-ttu-id="028a1-104">Lancez **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="028a1-104">Launch **SQL Server Management Studio**.</span></span> <span data-ttu-id="028a1-105">Cliquez sur le bouton **Démarrer** , sur **tous les programmes**, sur **Microsoft SQL Server 2012**, puis sur **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="028a1-105">Click the **Start** button, click **All Programs**, click **Microsoft SQL Server 2012**, and then click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="028a1-106">Dans la fenêtre **se connecter au serveur** , affectez à **type de serveur** la valeur **moteur de base de données**, tapez le nom du **serveur** (ou sélectionnez **(local)**, puis sélectionnez **authentification**appropriée, puis cliquez sur **se connecter**.</span><span class="sxs-lookup"><span data-stu-id="028a1-106">In the **Connect to Server** window, set **Server Type** to **Database Engine**, type the **server name** (or select **(local)**, and select appropriate **authentication**, and click **Connect**.</span></span>

3.  <span data-ttu-id="028a1-107">Dans le **volet Explorateur d’objets** , développez successivement **bases de données**, **MDS**, puis **vues**.</span><span class="sxs-lookup"><span data-stu-id="028a1-107">In the **Object Explorer** pane, expand **Databases**, expand **MDS**, and then expand **Views**.</span></span>

4.  <span data-ttu-id="028a1-108">Vérifiez que le MDM est visible \*\*. \*\*Affichage des fournisseurs dans la liste.</span><span class="sxs-lookup"><span data-stu-id="028a1-108">Confirm that you see the **mdm.Suppliers** view in the list.</span></span>

     <span data-ttu-id="028a1-109">![SQL Server Management Studio - Vue mdm.Suppliers](../../2014/tutorials/media/et-reviewingthesubscriptionviews.jpg "SQL Server Management Studio - Vue mdm.Suppliers")</span><span class="sxs-lookup"><span data-stu-id="028a1-109">![SQL Server Management Studio - mdm.Suppliers View](../../2014/tutorials/media/et-reviewingthesubscriptionviews.jpg "SQL Server Management Studio - mdm.Suppliers View")</span></span>

## <a name="next-step"></a><span data-ttu-id="028a1-110">étape suivante</span><span class="sxs-lookup"><span data-stu-id="028a1-110">Next Step</span></span>
 [<span data-ttu-id="028a1-111">Tâche 4 : Création d’un projet SSIS à l’aide de SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="028a1-111">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>](../../2014/tutorials/task-4-creating-an-ssis-project-using-sql-server-data-tools.md)