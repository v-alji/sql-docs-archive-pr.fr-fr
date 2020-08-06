---
title: 'Leçon 6 : ajouter un contrôle ReportViewer à l’application | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613832"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="82673-102">Leçon 6 : Ajouter un contrôle ReportViewer à l'application</span><span class="sxs-lookup"><span data-stu-id="82673-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="82673-103">Après avoir conçu le rapport enfant à l'aide de l'Assistant Rapport, l'étape suivante consiste à ajouter un contrôle ReportViewer à l'application de site Web.</span><span class="sxs-lookup"><span data-stu-id="82673-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="82673-104">Pour ajouter un contrôle ReportViewer à l'application</span><span class="sxs-lookup"><span data-stu-id="82673-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="82673-105">Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur **Default.aspx**, puis sélectionnez **Concepteur de vues**.</span><span class="sxs-lookup"><span data-stu-id="82673-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="82673-106">Dans le groupe **Extensions AJAX** de la fenêtre **Boîte à outils** , faites glisser un contrôle **ScriptManager** vers l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="82673-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="82673-107">Depuis le groupe **Création de rapports** , faites glisser un contrôle **ReportViewer** vers l'aire de conception sous le contrôle **ScriptManager** .</span><span class="sxs-lookup"><span data-stu-id="82673-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="82673-108">Ouvrez la fenêtre **Tâches ReportViewer** en cliquant sur la flèche située dans le coin supérieur droit du contrôle **ReportViewer** .</span><span class="sxs-lookup"><span data-stu-id="82673-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="82673-109">Dans la zone **Choisir un rapport** , sélectionnez le rapport parent que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="82673-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="82673-110">Lorsque vous sélectionnez un rapport, les instances de sources de données utilisées dans le rapport sont créées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="82673-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="82673-111">Le code est généré pour instancier chaque objet DataTable (et son conteneur [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="82673-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="82673-112">Un contrôle [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) est ajouté à l’aire de conception, correspondant à chaque source de données utilisée dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="82673-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="82673-113">Ce contrôle de source de données est configuré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="82673-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="82673-114">Si vous utilisez Microsoft Visual Studio 2012, assurez-vous que le contrôle ObjectDataSource est lié à DataSet1 qui est complet avec l’espace de noms du projet, si le nom complet est répertorié dans la zone de liste déroulante **choisir votre objet métier** (par exemple, ProjectNamespace. DataSet1TableAdapters. ProductTableAdapter).</span><span class="sxs-lookup"><span data-stu-id="82673-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="82673-115">Pour accéder à la zone de liste, cliquez avec le bouton droit sur ObjectDataSource, puis sélectionnez **Configurer la source de données**.</span><span class="sxs-lookup"><span data-stu-id="82673-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="82673-116">Dans le menu Générer, cliquez sur Générer le site Web.</span><span class="sxs-lookup"><span data-stu-id="82673-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="82673-117">Le rapport est compilé et toutes les erreurs, comme une erreur de syntaxe dans une expression de rapport, apparaissent dans la zone **Liste d'erreurs** .</span><span class="sxs-lookup"><span data-stu-id="82673-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="82673-118">Cliquez sur **Liste d'erreurs** en bas de la fenêtre de Visual Studio pour afficher la zone **Liste d'erreurs** .</span><span class="sxs-lookup"><span data-stu-id="82673-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="82673-119">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="82673-119">Next Task</span></span>  
 <span data-ttu-id="82673-120">Vous venez d'ajouter un contrôle ReportViewer dans l'application de site Web.</span><span class="sxs-lookup"><span data-stu-id="82673-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="82673-121">Vous allez à présent ajouter une action d'extraction dans le rapport parent.</span><span class="sxs-lookup"><span data-stu-id="82673-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
