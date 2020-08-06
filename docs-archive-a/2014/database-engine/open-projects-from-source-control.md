---
title: Ouvrir des projets à partir du contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613606"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="13232-102">Ouvrir des projets à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="13232-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="13232-103">Vous pouvez utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour ouvrir des projets directement à partir du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="13232-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="13232-104">Lorsque vous effectuez cette opération, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] récupère la dernière version du projet et la copie sur votre disque local.</span><span class="sxs-lookup"><span data-stu-id="13232-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="13232-105">L'environnement [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] crée également automatiquement une solution pour le projet.</span><span class="sxs-lookup"><span data-stu-id="13232-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="13232-106">Une fois un projet ouvert à partir du contrôle de code source, vous pouvez extraire et modifier des fichiers projet.</span><span class="sxs-lookup"><span data-stu-id="13232-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="13232-107">La procédure qui suit ne doit être utilisée qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="13232-107">The following procedure should only be used once.</span></span> <span data-ttu-id="13232-108">Ensuite, vous devez ouvrir le projet comme n’importe quel autre projet (en cliquant sur **fichier**, **ouvrir**, puis **projet**).</span><span class="sxs-lookup"><span data-stu-id="13232-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="13232-109">Pour ouvrir un projet à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="13232-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="13232-110">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **ouvrir à partir du contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="13232-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="13232-111">Si le système vous le demande, connectez-vous à [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="13232-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="13232-112">Dans la boîte de dialogue **créer un projet local à partir de SourceSafe** , ouvrez le dossier qui contient le projet à ouvrir.</span><span class="sxs-lookup"><span data-stu-id="13232-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="13232-113">La zone **créer un nouveau projet dans le dossier** change pour identifier le répertoire local dans lequel le projet sera créé.</span><span class="sxs-lookup"><span data-stu-id="13232-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="13232-114">Si vous souhaitez placer le projet dans un autre répertoire, tapez le chemin d’accès au répertoire ou utilisez le bouton **Parcourir** pour localiser le répertoire sur votre disque local.</span><span class="sxs-lookup"><span data-stu-id="13232-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="13232-115">Dans la **zone créer un nouveau projet dans le dossier**, vérifiez que le dossier approprié est affiché, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="13232-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="13232-116">Dans la boîte de dialogue **ouvrir une solution** , sélectionnez le projet que vous souhaitez ouvrir, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="13232-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13232-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13232-117">See Also</span></span>  
 <span data-ttu-id="13232-118">[Ouvrir des solutions et des projets à partir du contrôle de code source](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="13232-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="13232-119">Ouvrir des solutions à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="13232-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
