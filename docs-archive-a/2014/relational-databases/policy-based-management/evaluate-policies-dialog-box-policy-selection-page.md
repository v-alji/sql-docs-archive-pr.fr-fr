---
title: Boîte de dialogue Évaluer les stratégies, page Sélection de la stratégie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.runnow.f1
ms.assetid: 20075fbe-0b48-42c8-b747-690f1aa23dcf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f68a1ccc7873b6a05d2641ddaa87e8d5b0e5c6d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696719"
---
# <a name="evaluate-policies-dialog-box-policy-selection-page"></a><span data-ttu-id="ef2b7-102">Boîte de dialogue Évaluer les stratégies, page Sélectionner la stratégie</span><span class="sxs-lookup"><span data-stu-id="ef2b7-102">Evaluate Policies Dialog Box, Policy Selection Page</span></span>
  <span data-ttu-id="ef2b7-103">Utilisez cette boîte de dialogue pour évaluer les stratégies de la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-103">Use this dialog box to evaluate Policy-Based Management policies.</span></span> <span data-ttu-id="ef2b7-104">En sélectionnant la page **Résultats d'évaluation** , vous pouvez appliquer des stratégies aux éléments d'un jeu de cibles non conforme aux stratégies.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-104">By selecting the **Evaluation Results** page, you can apply policies to the items in a target set that do not comply with the policies.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef2b7-105">Options</span><span class="sxs-lookup"><span data-stu-id="ef2b7-105">Options</span></span>  
 <span data-ttu-id="ef2b7-106">**Source**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-106">**Source**</span></span>  
 <span data-ttu-id="ef2b7-107">Spécifie la source des stratégies.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-107">Specifies the source of the policies.</span></span> <span data-ttu-id="ef2b7-108">Pour modifier la source, cliquez sur le bouton Parcourir (**...**) pour ouvrir la boîte de dialogue **Sélectionner une source** .</span><span class="sxs-lookup"><span data-stu-id="ef2b7-108">To change the source, click the Browse (**...**) button to open the **Select Source** dialog box.</span></span>  
  
 <span data-ttu-id="ef2b7-109">**Fichiers**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-109">**Files**</span></span>  
 <span data-ttu-id="ef2b7-110">Tapez le chemin d’un fichier qui contient une stratégie de Gestion basée sur des stratégies, ou utilisez le bouton Parcourir (**...**) pour sélectionner le fichier.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-110">Type the path of a file that contains a Policy-Based Management policy, or use the Browse (**...**) button to select the file.</span></span>  
  
 <span data-ttu-id="ef2b7-111">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-111">**Server**</span></span>  
 <span data-ttu-id="ef2b7-112">Sélectionnez cette option pour vous connecter à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui contient la stratégie souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-112">Select to connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that contains the policy that you want.</span></span>  
  
 <span data-ttu-id="ef2b7-113">**Stratégies : Stratégie**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-113">**Policies: Policy**</span></span>  
 <span data-ttu-id="ef2b7-114">Cliquez sur cette option pour ouvrir la boîte de dialogue de la stratégie spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-114">Click to open the policy dialog box for the specified policy.</span></span>  
  
 <span data-ttu-id="ef2b7-115">**Stratégies : Catégorie**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-115">**Policies: Category**</span></span>  
 <span data-ttu-id="ef2b7-116">Indique la catégorie de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-116">The category of the policy.</span></span> <span data-ttu-id="ef2b7-117">Cette zone est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-117">This box is read-only.</span></span>  
  
 <span data-ttu-id="ef2b7-118">**Stratégies : Facette**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-118">**Policies: Facet**</span></span>  
 <span data-ttu-id="ef2b7-119">Indique la facette implémentée par la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-119">The facet implemented by the policy.</span></span> <span data-ttu-id="ef2b7-120">Cette zone est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-120">This box is read-only.</span></span>  
  
 <span data-ttu-id="ef2b7-121">**Évaluer**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-121">**Evaluate**</span></span>  
 <span data-ttu-id="ef2b7-122">Exécute la stratégie en mode d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-122">Runs the policy in evaluation mode.</span></span> <span data-ttu-id="ef2b7-123">Cela génère un rapport de conformité pour le jeu de cibles mais n'applique pas la conformité future et ne reconfigure pas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef2b7-123">This generates a compliance report for the target set but does not reconfigure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or enforce future compliance.</span></span>  
  
## <a name="possible-errors"></a><span data-ttu-id="ef2b7-124">Erreurs possibles</span><span class="sxs-lookup"><span data-stu-id="ef2b7-124">Possible Errors</span></span>  
  
-   <span data-ttu-id="ef2b7-125">**Aucune cible n'a été trouvée**</span><span class="sxs-lookup"><span data-stu-id="ef2b7-125">**No targets found**</span></span>  
  
     <span data-ttu-id="ef2b7-126">Le jeu de cibles peut être vide pour l'une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="ef2b7-126">The target set could be empty due to any of the following reasons:</span></span>  
  
    -   <span data-ttu-id="ef2b7-127">Il n'y a aucune cible sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du type spécifié par la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-127">There are no targets on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of the type specified by the policy.</span></span>  
  
    -   <span data-ttu-id="ef2b7-128">La restriction de serveur exclut peut-être l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui contient la cible.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-128">The server restriction might exclude the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains the target.</span></span>  
  
    -   <span data-ttu-id="ef2b7-129">Si la stratégie est sur un objet dans une base de données (par exemple une table, une vue ou un utilisateur), la base de données n'est peut-être pas abonnée à la catégorie de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-129">If the policy is on an object in a database (for example a table, view, or user) the database might not subscribe to the category of the policy.</span></span>  
  
    -   <span data-ttu-id="ef2b7-130">Le filtre de jeu de cibles exclut peut-être toutes les cibles sur cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef2b7-130">The target-set filter might exclude all targets on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="ef2b7-131">Le type du serveur cible est différent du type du serveur sur lequel la stratégie est évaluée.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-131">The target server type is different from the server type on which the policy is evaluated.</span></span> <span data-ttu-id="ef2b7-132">Par exemple, dans le [!INCLUDE[ssDE](../../includes/ssde-md.md)], si vous essayez d'évaluer une stratégie qui a été créée pour [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], vous recevez un jeu de cibles vide.</span><span class="sxs-lookup"><span data-stu-id="ef2b7-132">For example, in the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if you try to evaluate a policy that has been created for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you will receive an empty target set</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef2b7-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef2b7-133">See Also</span></span>  
 <span data-ttu-id="ef2b7-134">[Administrer des serveurs à l’aide de la gestion basée sur des stratégies](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="ef2b7-134">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 [<span data-ttu-id="ef2b7-135">Boîte de dialogue Évaluer les stratégies, page Résultats d'évaluation</span><span class="sxs-lookup"><span data-stu-id="ef2b7-135">Evaluate Policies Dialog Box, Evaluation Results Page</span></span>](evaluate-policies-dialog-box-evaluation-results-page.md)  
  
  
