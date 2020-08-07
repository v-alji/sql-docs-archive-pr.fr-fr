---
title: 'Leçon 1 : création du projet client du service Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703543"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="a0644-102">Leçon 1 : Création du projet client du service web</span><span class="sxs-lookup"><span data-stu-id="a0644-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="a0644-103">Dans cette procédure pas à pas, vous allez créer une application console simple qui accède au service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="a0644-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="a0644-104">Il est supposé que vous utilisez [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] pour le développement.</span><span class="sxs-lookup"><span data-stu-id="a0644-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="a0644-105">Pour créer une application console</span><span class="sxs-lookup"><span data-stu-id="a0644-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="a0644-106">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet** pour ouvrir la boîte de dialogue **Nouveau projet** .</span><span class="sxs-lookup"><span data-stu-id="a0644-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="a0644-107">Dans le volet gauche, sous **Modèles installés**, cliquez sur le nœud **Visual Basic** ou **Visual C#** , puis sélectionnez une catégorie de types de projets dans la liste développée.</span><span class="sxs-lookup"><span data-stu-id="a0644-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="a0644-108">Choisissez le type de projet **Application console** .</span><span class="sxs-lookup"><span data-stu-id="a0644-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="a0644-109">Dans la zone **Nom** , tapez le nom de votre projet.</span><span class="sxs-lookup"><span data-stu-id="a0644-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="a0644-110">Tapez le nom `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="a0644-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="a0644-111">Dans la zone **emplacement** , entrez le chemin d’accès à l’emplacement où vous souhaitez enregistrer votre projet ou cliquez sur **Parcourir** pour naviguer jusqu’au dossier.</span><span class="sxs-lookup"><span data-stu-id="a0644-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="a0644-112">Une vue réduite de votre projet s’affiche dans Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="a0644-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="a0644-113">Dans l'Explorateur de solutions, développez le nœud du projet.</span><span class="sxs-lookup"><span data-stu-id="a0644-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="a0644-114">Un fichier avec le nom par défaut Program.cs (Module1. vb pour [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) a été ajouté à votre projet.</span><span class="sxs-lookup"><span data-stu-id="a0644-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0644-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0644-115">See Also</span></span>  
 <span data-ttu-id="a0644-116">[Leçon 2 : ajout d’une référence Web](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a0644-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="a0644-117">Accès au service Web Report Server à l’aide de Visual Basic ou du didacticiel Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a0644-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
