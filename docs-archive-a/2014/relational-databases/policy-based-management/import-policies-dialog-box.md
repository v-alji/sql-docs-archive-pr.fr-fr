---
title: Importer des stratégies, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.importpolicy.f1
ms.assetid: 78ab5f6e-2f13-4788-937e-8892ef4e2345
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2601c21ea08d00bf77e9b97a5186f2d6d1200a10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601431"
---
# <a name="import-policies-dialog-box"></a><span data-ttu-id="94fbf-102">Boîte de dialogue Importer des stratégies</span><span class="sxs-lookup"><span data-stu-id="94fbf-102">Import Policies Dialog Box</span></span>
  <span data-ttu-id="94fbf-103">Utilisez cette boîte de dialogue pour importer une ou plusieurs stratégies (et leur condition référencée) enregistrées en tant que fichiers XML dans l'instance [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] active.</span><span class="sxs-lookup"><span data-stu-id="94fbf-103">Use this dialog box to import one or more policies (and their referenced condition) that are saved as XML files, into the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="94fbf-104">Options</span><span class="sxs-lookup"><span data-stu-id="94fbf-104">Options</span></span>  
 <span data-ttu-id="94fbf-105">**Fichiers à importer**</span><span class="sxs-lookup"><span data-stu-id="94fbf-105">**Files to import**</span></span>  
 <span data-ttu-id="94fbf-106">Pour importer une stratégie à partir d’un fichier XML, tapez le nom et le chemin du fichier ou utilisez le bouton d’exploration ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="94fbf-106">To import a policy from an XML file, type the path and name of the file or use the Browse (**...**) button.</span></span>  
  
 <span data-ttu-id="94fbf-107">**Remplacer les doublons avec les éléments importés**</span><span class="sxs-lookup"><span data-stu-id="94fbf-107">**Replace duplicates with items imported**</span></span>  
 <span data-ttu-id="94fbf-108">Sélectionnez cette option pour remplacer toute stratégie ou condition existante du même nom si elle existe déjà sur cette instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="94fbf-108">Select to overwrite any existing policy or condition of the same name if it already exists on this [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance.</span></span> <span data-ttu-id="94fbf-109">Une condition avec une stratégie dépendante ne peut pas être remplacée, à moins que la stratégie dépendante ne soit également remplacée.</span><span class="sxs-lookup"><span data-stu-id="94fbf-109">A condition with a dependent policy cannot be overwritten unless the dependent policy is also being overwritten.</span></span> <span data-ttu-id="94fbf-110">Si cette option n'est pas sélectionnée, une condition existante qui utilise la même expression de condition ne provoquera pas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="94fbf-110">If this option is not selected, an existing condition that is using the same condition expression will not cause an error.</span></span>  
  
 <span data-ttu-id="94fbf-111">**État de la stratégie**</span><span class="sxs-lookup"><span data-stu-id="94fbf-111">**Policy state**</span></span>  
 <span data-ttu-id="94fbf-112">Sélectionnez l'état que vous souhaitez attribuer à la stratégie importée :</span><span class="sxs-lookup"><span data-stu-id="94fbf-112">Select the state that you want for the imported policy:</span></span>  
  
-   <span data-ttu-id="94fbf-113">**Conserver l'état de la stratégie lors de l'importation**</span><span class="sxs-lookup"><span data-stu-id="94fbf-113">**Preserve policy state on import**</span></span>  
  
-   <span data-ttu-id="94fbf-114">**Activer toutes les stratégies lors de l'importation**</span><span class="sxs-lookup"><span data-stu-id="94fbf-114">**Enable all policies on import**</span></span>  
  
-   <span data-ttu-id="94fbf-115">**Désactiver toutes les stratégies lors de l'importation**</span><span class="sxs-lookup"><span data-stu-id="94fbf-115">**Disable all policies on import**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fbf-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94fbf-116">See Also</span></span>  
 <span data-ttu-id="94fbf-117">[Administrer des serveurs à l'aide de la Gestion basée sur des stratégies](administer-servers-by-using-policy-based-management.md) </span><span class="sxs-lookup"><span data-stu-id="94fbf-117">[Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md) </span></span>  
 <span data-ttu-id="94fbf-118">[Importer une stratégie de gestion basée sur des stratégies](import-a-policy-based-management-policy.md) </span><span class="sxs-lookup"><span data-stu-id="94fbf-118">[Import a Policy-Based Management Policy](import-a-policy-based-management-policy.md) </span></span>  
 [<span data-ttu-id="94fbf-119">Exporter une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="94fbf-119">Export a Policy-Based Management Policy</span></span>](export-a-policy-based-management-policy.md)  
  
  
