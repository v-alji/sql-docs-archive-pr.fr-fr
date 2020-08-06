---
title: Activer le mode création DirectQuery (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 71fc7ebd-2e86-4a76-994b-66d3a57bcc9b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ccd2dc88f447e78f6558565a89accc341eac37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610872"
---
# <a name="enable-directquery-design-mode-ssas-tabular"></a><span data-ttu-id="4c554-102">Activer le mode Création DirectQuery (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="4c554-102">Enable DirectQuery Design Mode (SSAS Tabular)</span></span>
  <span data-ttu-id="4c554-103">Pour créer un modèle en mode DirectQuery, vous devez d'abord modifier l'environnement au moment de la conception afin qu'il prenne en charge l'utilisateur du mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="4c554-103">To create a model in DirectQuery mode, you must first change the design-time environment so that it supports the user of DirectQuery mode.</span></span> <span data-ttu-id="4c554-104">Dans ce cas, le concepteur effectue également les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c554-104">When you do so, the designer will also do the following:</span></span>  
  
-   <span data-ttu-id="4c554-105">Il active l'utilisation des propriétés de déploiement DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="4c554-105">Enable the use of the DirectQuery deployment properties.</span></span>  
  
-   <span data-ttu-id="4c554-106">Il modifie la base de données de l'espace de travail de façon à ce qu'elle s'exécute en mode hybride qui utilise le cache pour la conception.</span><span class="sxs-lookup"><span data-stu-id="4c554-106">Change the workspace database to run in a hybrid mode that uses the cache for designing.</span></span> <span data-ttu-id="4c554-107">Lorsque vous déployez réellement le modèle, la valeur de mode spécifiée dans les propriétés de déploiement du projet est rétablie.</span><span class="sxs-lookup"><span data-stu-id="4c554-107">When you actually deploy the model, the mode will be changed back to whatever value you specified in the project deployment properties.</span></span>  
  
-   <span data-ttu-id="4c554-108">Il désactive les fonctionnalités de création qui ne sont pas compatibles avec le mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="4c554-108">Disable design features that are incompatible with DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="4c554-109">Il valide le modèle existant.</span><span class="sxs-lookup"><span data-stu-id="4c554-109">Validate the existing model.</span></span>  
  
 <span data-ttu-id="4c554-110">Cette procédure explique comment activer le mode DirectQuery dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="4c554-110">This procedure describes how to enable DirectQuery mode in the designer.</span></span>  
  
### <a name="to-enable-use-of-directquery-in-a-model"></a><span data-ttu-id="4c554-111">Pour activer l'utilisation de DirectQuery dans un modèle</span><span class="sxs-lookup"><span data-stu-id="4c554-111">To enable use of DirectQuery in a model</span></span>  
  
1.  <span data-ttu-id="4c554-112">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le fichier solution.</span><span class="sxs-lookup"><span data-stu-id="4c554-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the solution file.</span></span>  
  
2.  <span data-ttu-id="4c554-113">Dans l'Explorateur d'objets, double-cliquez sur le fichier Model.bim.</span><span class="sxs-lookup"><span data-stu-id="4c554-113">In Object Explorer, double-click the Model.bim file.</span></span>  
  
3.  <span data-ttu-id="4c554-114">Dans le volet **Propriétés** , affectez à la propriété **DirectQueryMode**la valeur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="4c554-114">In the **Properties** pane, change the property, **DirectQueryMode**, to **On**.</span></span>  
  
4.  <span data-ttu-id="4c554-115">En cas de erreurs, dans Visual Studio, ouvrez la **Liste d'erreurs** et résolvez tous les problèmes qui empêcheraient le modèle de basculer en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="4c554-115">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being switched to DirectQuery mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c554-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c554-116">See Also</span></span>  
 [<span data-ttu-id="4c554-117">Mode DirectQuery &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="4c554-117">DirectQuery Mode &#40;SSAS Tabular&#41;</span></span>](directquery-mode-ssas-tabular.md)  
  
  
