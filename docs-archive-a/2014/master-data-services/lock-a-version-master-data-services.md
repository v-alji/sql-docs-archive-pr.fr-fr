---
title: Verrouiller une version (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706548"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="eb661-102">Verrouiller une version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="eb661-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="eb661-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], verrouillez une version d’un modèle pour empêcher que des modifications ne soient apportées aux membres du modèle et à leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="eb661-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb661-104">Lorsqu'une version est verrouillée, les administrateurs de modèle peuvent continuer à ajouter, modifier et supprimer des membres.</span><span class="sxs-lookup"><span data-stu-id="eb661-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="eb661-105">Les autres utilisateurs qui ont une autorisation sur le modèle peuvent consulter les membres uniquement.</span><span class="sxs-lookup"><span data-stu-id="eb661-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb661-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="eb661-106">Prerequisites</span></span>  
 <span data-ttu-id="eb661-107">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="eb661-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="eb661-108">Vous devez avoir l’autorisation d’accéder à la zone fonctionnelle **Gestion des versions** .</span><span class="sxs-lookup"><span data-stu-id="eb661-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="eb661-109">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="eb661-109">You must be a model administrator.</span></span> <span data-ttu-id="eb661-110">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="eb661-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="eb661-111">L’état de la version doit être **Ouvert**.</span><span class="sxs-lookup"><span data-stu-id="eb661-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="eb661-112">Pour verrouiller une version</span><span class="sxs-lookup"><span data-stu-id="eb661-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="eb661-113">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Gestion des versions**.</span><span class="sxs-lookup"><span data-stu-id="eb661-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="eb661-114">Dans la page **Gérer les versions** , sélectionnez la ligne de la version à verrouiller.</span><span class="sxs-lookup"><span data-stu-id="eb661-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="eb661-115">Cliquez sur **Verrouiller**.</span><span class="sxs-lookup"><span data-stu-id="eb661-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="eb661-116">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb661-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb661-117">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="eb661-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="eb661-118">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eb661-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="eb661-119">Activer une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eb661-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb661-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb661-120">See Also</span></span>  
 <span data-ttu-id="eb661-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="eb661-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="eb661-122">Déverrouiller une version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="eb661-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  
