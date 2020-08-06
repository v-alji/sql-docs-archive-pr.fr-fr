---
title: Ajouter des solutions au contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding solutions
- solutions [SQL Server Management Studio], adding
ms.assetid: b9e36569-616d-4e47-9140-0978a9bfe923
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1c72949fd8257332a36af52ab287ed326eed5274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698532"
---
# <a name="add-solutions-to-source-control"></a><span data-ttu-id="b507e-102">Ajouter des solutions au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="b507e-102">Add Solutions to Source Control</span></span>
  <span data-ttu-id="b507e-103">Lorsque vous ajoutez une solution au contrôle de code source, vous souhaitez la plupart du temps ajouter l'ensemble de la solution avec tous les projets qu'elle comporte.</span><span class="sxs-lookup"><span data-stu-id="b507e-103">When you add a solution to source control, you usually want to add the entire solution and all the projects it contains.</span></span> <span data-ttu-id="b507e-104">Vous pouvez utiliser [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour ajouter une solution au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="b507e-104">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to add a solution to source control.</span></span>  
  
 <span data-ttu-id="b507e-105">Un projet [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] se trouve entièrement sur votre disque local.</span><span class="sxs-lookup"><span data-stu-id="b507e-105">A [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] project resides completely on your local disk.</span></span> <span data-ttu-id="b507e-106">Vous modifiez, enregistrez et créez localement les projets.</span><span class="sxs-lookup"><span data-stu-id="b507e-106">You edit, save, and build projects locally.</span></span> <span data-ttu-id="b507e-107">Après avoir ajouté le projet au contrôle de code source, vous pouvez utiliser la commande **extraire** pour extraire les fichiers du projet du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="b507e-107">After adding the project to source control, you can use the **Check Out** command to check the project's files out of source control.</span></span>  
  
### <a name="to-add-a-solution-to-source-control"></a><span data-ttu-id="b507e-108">Pour ajouter une solution au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="b507e-108">To add a solution to source control</span></span>  
  
1.  <span data-ttu-id="b507e-109">Dans l'Explorateur de solutions, sélectionnez la solution que vous souhaitez ajouter.</span><span class="sxs-lookup"><span data-stu-id="b507e-109">In Solution Explorer, select the solution you want to add.</span></span>  
  
2.  <span data-ttu-id="b507e-110">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **Ajouter la solution au contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="b507e-110">On the **File** menu, point to **Source Control**, and then click **Add Solution to Source Control**.</span></span>  
  
3.  <span data-ttu-id="b507e-111">Si vous y êtes invité, connectez-vous à votre fournisseur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="b507e-111">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="b507e-112">La boîte **de dialogue Ajouter au projet SourceSafe** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="b507e-112">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="b507e-113">Le nom de votre projet s’affiche dans la zone **projet** .</span><span class="sxs-lookup"><span data-stu-id="b507e-113">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="b507e-114">Dans la liste des **dossiers** , ouvrez le dossier dans lequel vous souhaitez placer votre projet.</span><span class="sxs-lookup"><span data-stu-id="b507e-114">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="b507e-115">Vous pouvez également cliquer sur **créer** pour créer un dossier avec le nom affiché dans la zone **projet** .</span><span class="sxs-lookup"><span data-stu-id="b507e-115">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b507e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b507e-116">See Also</span></span>  
 <span data-ttu-id="b507e-117">[Ajouter des solutions et des projets au contrôle de code source](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="b507e-117">[Add Solutions and Projects to Source Control](../../2014/database-engine/add-solutions-and-projects-to-source-control.md) </span></span>  
 [<span data-ttu-id="b507e-118">Ajouter des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="b507e-118">Add Projects to Source Control</span></span>](../../2014/database-engine/add-projects-to-source-control.md)  
  
  
