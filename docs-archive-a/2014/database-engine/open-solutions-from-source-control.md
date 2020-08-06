---
title: Ouvrir des solutions à partir du contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- opening solutions
- solutions [SQL Server Management Studio], opening
ms.assetid: a96a1f0d-0183-4587-a3b0-4598309cbdd2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 808a4851bcc1f51690b2ba924a859bcccf9a6adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613604"
---
# <a name="open-solutions-from-source-control"></a><span data-ttu-id="2be66-102">Ouvrir des solutions à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="2be66-102">Open Solutions from Source Control</span></span>
  <span data-ttu-id="2be66-103">Vous pouvez utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour ouvrir des solutions directement à partir du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="2be66-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open solutions directly from source control.</span></span> <span data-ttu-id="2be66-104">Lorsque vous effectuez cette opération, l'environnement Studio crée une copie de la toute dernière version des fichiers solutions à l'emplacement que vous avez spécifié.</span><span class="sxs-lookup"><span data-stu-id="2be66-104">When you do this, the Studio environment creates a copy of the latest version of the solution files at the location you specify.</span></span>  
  
 <span data-ttu-id="2be66-105">Si aucune copie locale de la solution ne figure sur votre disque local, vous devez ouvrir le projet à partir du contrôle de code source avant de pouvoir utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour extraire la solution ou récupérer les fichiers solutions.</span><span class="sxs-lookup"><span data-stu-id="2be66-105">If a local copy of the solution does not exist on your local disk, you must open the project from source control before you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out the solution or retrieve solution files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2be66-106">Si vous disposez déjà d'une copie locale de la solution dont vous procédez à l'ouverture à partir du contrôle de code source, le système vous demande de remplacer la copie locale.</span><span class="sxs-lookup"><span data-stu-id="2be66-106">If you already have a local copy of the solution you are opening from source control, you are prompted to overwrite the local copy.</span></span>  
  
### <a name="to-open-a-solution-from-source-control"></a><span data-ttu-id="2be66-107">Pour ouvrir une solution à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="2be66-107">To open a solution from source control</span></span>  
  
1.  <span data-ttu-id="2be66-108">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **ouvrir à partir du contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="2be66-108">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="2be66-109">Si le système vous le demande, connectez-vous à [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="2be66-109">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="2be66-110">Dans la boîte de dialogue **créer un projet local à partir de SourceSafe** , sélectionnez le dossier qui contient la solution que vous souhaitez ouvrir, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be66-110">In the **Create local project from SourceSafe** dialog box, select the folder that contains the solution you want to open, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="2be66-111">Si un dossier de travail de la solution existe déjà sur votre lecteur de disque local, la zone **créer un nouveau projet dans le dossier** change pour identifier le répertoire local.</span><span class="sxs-lookup"><span data-stu-id="2be66-111">If a working folder for the solution already exists on your local disk drive, the **Create a new project in the folder** box changes to identify the local directory.</span></span> <span data-ttu-id="2be66-112">En l'absence de dossier de travail pour la solution en question, vous pouvez indiquer le dossier local dans lequel vous souhaitez ouvrir la solution ou encore naviguer jusqu'à lui.</span><span class="sxs-lookup"><span data-stu-id="2be66-112">If no working folder for the solution exists, you can type or browse to the local directory in which the solution should be opened.</span></span>  
  
5.  <span data-ttu-id="2be66-113">Dans la boîte de dialogue **ouvrir une solution** , sélectionnez le fichier solution, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be66-113">In the **Open Solution** dialog box, select the solution file, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be66-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2be66-114">See Also</span></span>  
 [<span data-ttu-id="2be66-115">Ouvrir des projets à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="2be66-115">Open Projects from Source Control</span></span>](../../2014/database-engine/open-projects-from-source-control.md)  
  
  
