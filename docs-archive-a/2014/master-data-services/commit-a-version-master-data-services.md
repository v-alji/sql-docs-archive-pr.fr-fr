---
title: Activer une version (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699977"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="021f8-102">Activer une version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="021f8-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="021f8-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], activez une version d’un modèle pour empêcher que des modifications ne soient apportées aux membres du modèle et à leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="021f8-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="021f8-104">Les versions activées ne peuvent pas être déverrouillées.</span><span class="sxs-lookup"><span data-stu-id="021f8-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="021f8-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="021f8-105">Prerequisites</span></span>  
 <span data-ttu-id="021f8-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="021f8-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="021f8-107">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="021f8-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="021f8-108">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="021f8-108">You must be a model administrator.</span></span> <span data-ttu-id="021f8-109">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="021f8-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="021f8-110">L’état de la version doit être **Verrouillé**.</span><span class="sxs-lookup"><span data-stu-id="021f8-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="021f8-111">Pour plus d’informations, consultez [Verrouiller une version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="021f8-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="021f8-112">Tous les membres doivent avoir été validés correctement.</span><span class="sxs-lookup"><span data-stu-id="021f8-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="021f8-113">Pour activer une version</span><span class="sxs-lookup"><span data-stu-id="021f8-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="021f8-114">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="021f8-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="021f8-115">Dans la page **Gérer les versions** , dans la barre de menus, cliquez sur **Valider la version**.</span><span class="sxs-lookup"><span data-stu-id="021f8-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="021f8-116">Dans la page **Valider la version** , sélectionnez le modèle et la version à activer.</span><span class="sxs-lookup"><span data-stu-id="021f8-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="021f8-117">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="021f8-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="021f8-118">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="021f8-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="021f8-119">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="021f8-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="021f8-120">Créer un indicateur de version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="021f8-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="021f8-121">Affecter un indicateur à une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="021f8-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="021f8-122">Copier une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="021f8-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="021f8-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="021f8-123">See Also</span></span>  
 [<span data-ttu-id="021f8-124">Versions &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="021f8-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
