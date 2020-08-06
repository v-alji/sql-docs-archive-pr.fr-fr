---
title: 'Tâche 4 : création d’un projet SSIS à l’aide de SQL Server Data Tools | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 8603ea91-2ec4-40b6-8070-4f824332f5d3
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 07976dbd2c84b1385d79ce3f4ce4f616e0f706b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702175"
---
# <a name="task-4-creating-an-ssis-project-using-sql-server-data-tools"></a><span data-ttu-id="6f434-102">Tâche 4 : Création d’un projet SSIS à l’aide de SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="6f434-102">Task 4: Creating an SSIS Project using SQL Server Data Tools</span></span>
  <span data-ttu-id="6f434-103">Au cours de cette tâche, vous allez créer un projet SSIS à l’aide de **SQL Server Data Tools** pour automatiser le nettoyage et la correspondance des données des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="6f434-103">In this task, you create an SSIS project by using **SQL Server Data Tools** to automate cleansing and matching supplier data.</span></span>

1.  <span data-ttu-id="6f434-104">Lancez **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="6f434-104">Launch **SQL Server Data Tools**.</span></span> <span data-ttu-id="6f434-105">Cliquez sur Démarrer, pointez sur **tous les programmes**, développez **Microsoft SQL Server 2012**, puis cliquez sur **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="6f434-105">Click Start, point to **All Programs**, expand **Microsoft SQL Server 2012**, and click **SQL Server Data Tools**.</span></span>

2.  <span data-ttu-id="6f434-106">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet**.</span><span class="sxs-lookup"><span data-stu-id="6f434-106">On the **File** menu, point to **New**, and click **Project**.</span></span>

3.  <span data-ttu-id="6f434-107">Développez **Business Intelligence** dans le volet **modèles installés** , puis sélectionnez **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="6f434-107">Expand **Business Intelligence** in the **Installed Templates** pane, and select **Integration Services**.</span></span>

     <span data-ttu-id="6f434-108">![Visual Studio - Boîte de dialogue Nouveau projet](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - Boîte de dialogue Nouveau projet")</span><span class="sxs-lookup"><span data-stu-id="6f434-108">![Visual Studio - New Project Dialog Box](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-01.jpg "Visual Studio - New Project Dialog Box")</span></span>

4.  <span data-ttu-id="6f434-109">Sélectionnez **Integration Services projet** dans la **liste des types de projets**.</span><span class="sxs-lookup"><span data-stu-id="6f434-109">Select **Integration Services Project** in the **list of project types**.</span></span>

5.  <span data-ttu-id="6f434-110">Tapez **CleanseAndCurateSuppliers** pour **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f434-110">Type **CleanseAndCurateSuppliers** for **Name** and click **OK**.</span></span>

6.  <span data-ttu-id="6f434-111">Dans **Explorateur de solutions** fenêtre, cliquez avec le bouton droit sur **Package. dtsx** , puis sélectionnez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="6f434-111">In **Solution Explorer** window, right-click **Package.dtsx** and select **Rename**.</span></span> <span data-ttu-id="6f434-112">Si **Explorateur de solutions** fenêtre ne s’affiche pas, cliquez sur **affichage** dans la barre de menus et cliquez sur **Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="6f434-112">If you don't see **Solution Explorer** window, click **View** on the menu bar and click **Solution Explorer**.</span></span>

     <span data-ttu-id="6f434-113">![Package.dtsx - Menu Renommer](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Menu Renommer")</span><span class="sxs-lookup"><span data-stu-id="6f434-113">![Package.dtsx - Rename Menu](../../2014/tutorials/media/et-creatinganssisprojectusingsqlsdt-02.jpg "Package.dtsx - Rename Menu")</span></span>

7.  <span data-ttu-id="6f434-114">Tapez **CleanseAndCurate. dtsx** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="6f434-114">Type **CleanseAndCurate.dtsx** and press **ENTER**.</span></span> <span data-ttu-id="6f434-115">Assurez-vous que l' **extension** reste **. dtsx**.</span><span class="sxs-lookup"><span data-stu-id="6f434-115">Make sure that the **extension** remains **.dtsx**.</span></span>

## <a name="next-step"></a><span data-ttu-id="6f434-116">étape suivante</span><span class="sxs-lookup"><span data-stu-id="6f434-116">Next Step</span></span>
 [<span data-ttu-id="6f434-117">Tâche 5 : Ajout d’une tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="6f434-117">Task 5: Adding Data Flow Task</span></span>](task-5-adding-data-flow-task.md)


