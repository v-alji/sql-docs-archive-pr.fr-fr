---
title: Spécifier une version comme étant la dernière version | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], latest version
- latest file version specified
- file versions [SQL Server]
ms.assetid: 407dffb1-3ecf-461e-835d-124781f26ee7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: dafe4f757e33a5db63340c3d3cc7c9151871d438
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601066"
---
# <a name="specify-a-version-as-the-latest-version"></a><span data-ttu-id="ab94b-102">Désigner une version comme étant la dernière version</span><span class="sxs-lookup"><span data-stu-id="ab94b-102">Specify a Version as the Latest Version</span></span>
  <span data-ttu-id="ab94b-103">Lorsque vous archivez un fichier dans le contrôle de code source, la version que vous archivez devient la dernière version. Les utilisateurs qui extraient ou récupèrent la dernière version reçoivent des copies locales du tout dernier élément archivé.</span><span class="sxs-lookup"><span data-stu-id="ab94b-103">When you check a file into source control, the version you check in becomes the latest version; users who check out or retrieve the latest version receive local copies of the item most recently checked in.</span></span>  
  
 <span data-ttu-id="ab94b-104">Dans certains cas, vous pouvez toutefois souhaiter désigner une version antérieure d'un élément comme étant la dernière version.</span><span class="sxs-lookup"><span data-stu-id="ab94b-104">However, in some situations, you may want to designate an earlier version of an item as the latest version.</span></span> <span data-ttu-id="ab94b-105">Par exemple, vous effectuez l'extraction d'un fichier, vous le modifiez, vous l'archivez,</span><span class="sxs-lookup"><span data-stu-id="ab94b-105">For example, you check out a file, modify the file, and then check the file in.</span></span> <span data-ttu-id="ab94b-106">puis vous décidez d'ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="ab94b-106">You later decide to discard your modifications.</span></span> <span data-ttu-id="ab94b-107">Comme vous avez archivé l'élément, il est alors inutile d'annuler l'extraction d'origine.</span><span class="sxs-lookup"><span data-stu-id="ab94b-107">Because you have checked in the item, undoing your original checkout is not an option.</span></span> <span data-ttu-id="ab94b-108">Vous pouvez dans ce cas désigner la version extraite à l'origine comme étant la dernière version de l'élément.</span><span class="sxs-lookup"><span data-stu-id="ab94b-108">In this situation, you can designate the version you originally checked out as the latest version of the item.</span></span>  
  
 <span data-ttu-id="ab94b-109">Vous pouvez désigner une version comme étant la dernière version en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab94b-109">You can designate the latest version by:</span></span>  
  
-   <span data-ttu-id="ab94b-110">**Épinglage d’une version**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-110">**Pinning a version**.</span></span> <span data-ttu-id="ab94b-111">Lorsque vous mettez une version de fichier en attente, les versions ultérieures à la version en attente ne sont pas supprimées.</span><span class="sxs-lookup"><span data-stu-id="ab94b-111">When you pin a file version, versions that are more recent than the pinned version are not deleted.</span></span> <span data-ttu-id="ab94b-112">Vous pouvez par ailleurs annuler la mise en attente d'un fichier préalablement définie.</span><span class="sxs-lookup"><span data-stu-id="ab94b-112">In addition, you can unpin a file that you have previously pinned.</span></span> <span data-ttu-id="ab94b-113">Lorsque vous effectuez cette opération, la toute dernière version archivée du fichier devient la dernière version.</span><span class="sxs-lookup"><span data-stu-id="ab94b-113">When you do this, the most recently checked in version of the file becomes the latest version.</span></span> <span data-ttu-id="ab94b-114">Vous ne pouvez toutefois pas extraire un fichier en attente.</span><span class="sxs-lookup"><span data-stu-id="ab94b-114">However, you cannot check out a pinned file.</span></span>  
  
-   <span data-ttu-id="ab94b-115">**Restauration d’une version spécifiée**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-115">**Rolling back to a specified version**.</span></span> <span data-ttu-id="ab94b-116">Lorsque vous restaurez une version, toutes les versions ultérieures à la version que vous avez restaurée sont supprimées du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="ab94b-116">When you roll back to a version, all versions more recent than the one to which you have rolled back are deleted from source control.</span></span> <span data-ttu-id="ab94b-117">Vous pouvez alors extraire la dernière version restante.</span><span class="sxs-lookup"><span data-stu-id="ab94b-117">You can then check out the latest remaining version.</span></span>  
  
### <a name="to-pin-a-version"></a><span data-ttu-id="ab94b-118">Pour mettre une version en attente</span><span class="sxs-lookup"><span data-stu-id="ab94b-118">To pin a version</span></span>  
  
1.  <span data-ttu-id="ab94b-119">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], ouvrez la solution.</span><span class="sxs-lookup"><span data-stu-id="ab94b-119">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="ab94b-120">Dans l'Explorateur de solutions, sélectionnez le fichier que vous souhaitez désigner comme étant la dernière version.</span><span class="sxs-lookup"><span data-stu-id="ab94b-120">In Solution Explorer, select the file that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="ab94b-121">Dans le menu **fichier** , pointez sur **contrôle de code source** , puis cliquez sur **ViewHistory**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-121">On the **File** menu, point to **Source Control** and click **ViewHistory**.</span></span>  
  
4.  <span data-ttu-id="ab94b-122">Dans la boîte **de dialogue historique de** \<file> , sélectionnez la version que vous souhaitez spécifier comme la plus récente, puis cliquez sur **épingler**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-122">In the **History of** \<file> dialog box, select the version that you want to specify as the latest, and click **Pin**.</span></span>  
  
     <span data-ttu-id="ab94b-123">Un symbole de mise en attente s'affiche à côté de la version sélectionnée, indiquant qu'il s'agit de la version en cours du fichier.</span><span class="sxs-lookup"><span data-stu-id="ab94b-123">A pin symbol appears next to the version you have selected, indicating that it is the current file version.</span></span> <span data-ttu-id="ab94b-124">En cas de chargement d'une version différente dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], le système vous demande de recharger le fichier.</span><span class="sxs-lookup"><span data-stu-id="ab94b-124">If you have a different version loaded in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you are prompted to reload the file.</span></span>  
  
### <a name="to-roll-back-to-a-version"></a><span data-ttu-id="ab94b-125">Pour restaurer une version</span><span class="sxs-lookup"><span data-stu-id="ab94b-125">To roll back to a version</span></span>  
  
1.  <span data-ttu-id="ab94b-126">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], ouvrez la solution.</span><span class="sxs-lookup"><span data-stu-id="ab94b-126">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the solution.</span></span>  
  
2.  <span data-ttu-id="ab94b-127">Dans l'Explorateur de solutions, sélectionnez l'élément que vous souhaitez désigner comme étant la dernière version.</span><span class="sxs-lookup"><span data-stu-id="ab94b-127">In Solution Explorer, select the item that you want to specify as the latest version.</span></span>  
  
3.  <span data-ttu-id="ab94b-128">Dans le menu **fichier** , pointez sur **contrôle de code source** , puis cliquez sur **historique**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-128">On the **File** menu, point to **Source Control** and click **History**.</span></span>  
  
4.  <span data-ttu-id="ab94b-129">Dans la boîte de dialogue **options d’historique** , cliquez sur **OK** pour afficher la boîte **de dialogue historique du fichier** .</span><span class="sxs-lookup"><span data-stu-id="ab94b-129">In the **History Options** dialog box, click **OK** to display the **History of File** dialog box.</span></span>  
  
5.  <span data-ttu-id="ab94b-130">Dans la zone **historique du fichier** , sélectionnez la version que vous souhaitez spécifier comme version la plus récente, puis cliquez sur **restaurer**.</span><span class="sxs-lookup"><span data-stu-id="ab94b-130">In the **History of File** box, select the version you want to specify as the latest version, and click **Rollback**.</span></span>  
  
     <span data-ttu-id="ab94b-131">Un message, vous notifiant que toutes les versions ultérieures à la version que vous avez sélectionnée seront supprimées, s'affiche.</span><span class="sxs-lookup"><span data-stu-id="ab94b-131">A message appears notifying you that all versions subsequent to the one you have selected will be deleted.</span></span>  
  
6.  <span data-ttu-id="ab94b-132">Cliquez sur **Oui** pour revenir à la version sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ab94b-132">Click **Yes** to roll back to the selected version.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab94b-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab94b-133">See Also</span></span>  
 <span data-ttu-id="ab94b-134">[Gérer les archivages](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="ab94b-134">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="ab94b-135">Archiver des fichiers</span><span class="sxs-lookup"><span data-stu-id="ab94b-135">Check In Files</span></span>](../../2014/database-engine/check-in-files.md)  
  
  
