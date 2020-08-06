---
title: 'Leçon 9 : générer et exécuter l’application | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f52d3f3a-0b09-4b34-9112-0b3655271587
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 068deb075f0f60dde634ac29f6f8f934448dc6a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601955"
---
# <a name="lesson-9-build-and-run-the-application"></a><span data-ttu-id="fd086-102">Lesson 9: Build and Run the Application</span><span class="sxs-lookup"><span data-stu-id="fd086-102">Lesson 9: Build and Run the Application</span></span>
  <span data-ttu-id="fd086-103">Après avoir créé un filtre de données pour la table de données, l'étape suivante consiste à générer et à exécuter l'application de site Web.</span><span class="sxs-lookup"><span data-stu-id="fd086-103">After you create a data filter for the data table, your next step is to build and run the website application.</span></span>

### <a name="to-build-and-run-the-application"></a><span data-ttu-id="fd086-104">Pour générer et exécuter l'application</span><span class="sxs-lookup"><span data-stu-id="fd086-104">To build and run the application</span></span>

1.  <span data-ttu-id="fd086-105">Appuyez sur **CTRL+F5** pour exécuter la page Default.aspx sans débogage, ou appuyez sur F5 pour exécuter la page avec débogage.</span><span class="sxs-lookup"><span data-stu-id="fd086-105">Press **CTRL+F5** to run the Default.aspx page without debugging, or press F5 to run the page with debugging.</span></span>

     <span data-ttu-id="fd086-106">Dans le cadre du processus de génération, le rapport est compilé et toutes les erreurs trouvées (comme une erreur de syntaxe dans une expression utilisée dans le rapport) sont ajoutées à la **Liste des tâches** située au bas de la fenêtre de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd086-106">As part of the build process, the report is compiled and any errors found (such as a syntax error in an expression used in the report) are added to the **Task List** that is located at the bottom of the Visual Studio window.</span></span>

     <span data-ttu-id="fd086-107">La page Web apparaît dans le navigateur.</span><span class="sxs-lookup"><span data-stu-id="fd086-107">The webpage appears in the browser.</span></span> <span data-ttu-id="fd086-108">Le contrôle ReportViewer affiche le rapport.</span><span class="sxs-lookup"><span data-stu-id="fd086-108">The ReportViewer control displays the report.</span></span> <span data-ttu-id="fd086-109">Vous pouvez utiliser la barre d'outils pour parcourir le rapport, effectuer un zoom et exporter le rapport vers Excel.</span><span class="sxs-lookup"><span data-stu-id="fd086-109">You can use the toolbar to browse through the report, zoom, and export the report to Excel.</span></span>

2.  <span data-ttu-id="fd086-110">Pointez la souris sur l'une des lignes sous la colonne **Nom** .</span><span class="sxs-lookup"><span data-stu-id="fd086-110">Hover the mouse over any of the rows under **Name** column.</span></span> <span data-ttu-id="fd086-111">Le curseur de la souris affiche le symbole de main.</span><span class="sxs-lookup"><span data-stu-id="fd086-111">The mouse cursor will display a Hand symbol.</span></span>

3.  <span data-ttu-id="fd086-112">Cliquez sur une valeur dans la colonne **Nom** .</span><span class="sxs-lookup"><span data-stu-id="fd086-112">Click a value in the **Name** column.</span></span> <span data-ttu-id="fd086-113">Le rapport enfant s'affiche avec les données filtrées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="fd086-113">The child report is shown with the corresponding filtered data.</span></span>

4.  <span data-ttu-id="fd086-114">Cliquez sur l'icône **Revenir au rapport parent**, dans la barre d'outils de **ReportViewer** pour revenir au rapport **Parent** .</span><span class="sxs-lookup"><span data-stu-id="fd086-114">Click the icon, **Go back to parent report**, in the **ReportViewer** tool bar to navigate back to the **Parent** report.</span></span>

     <span data-ttu-id="fd086-115">![extraction SSRS à l’aide de ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "extraction SSRS à l’aide de ReportViewer")</span><span class="sxs-lookup"><span data-stu-id="fd086-115">![ssrs drill through using ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "ssrs drill through using ReportViewer")</span></span>

5.  <span data-ttu-id="fd086-116">Fermez le navigateur.</span><span class="sxs-lookup"><span data-stu-id="fd086-116">Close the browser to exit.</span></span>


