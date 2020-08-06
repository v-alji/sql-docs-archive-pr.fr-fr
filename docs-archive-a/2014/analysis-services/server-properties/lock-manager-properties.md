---
title: Propriétés du gestionnaire de verrous | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710851"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="adfc3-102">Propriétés du gestionnaire de verrous</span><span class="sxs-lookup"><span data-stu-id="adfc3-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="adfc3-103">prend en charge les propriétés du serveur du gestionnaire de verrous répertoriées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="adfc3-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="adfc3-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="adfc3-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="adfc3-105">**S'applique à :** mode serveur multidimensionnel et tabulaire</span><span class="sxs-lookup"><span data-stu-id="adfc3-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="adfc3-106">Propriétés</span><span class="sxs-lookup"><span data-stu-id="adfc3-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="adfc3-107">Propriété dont la valeur est un entier 32 bits signé qui définit le délai d'expiration de verrouillage par défaut (en millisecondes) pour les demandes de verrous internes.</span><span class="sxs-lookup"><span data-stu-id="adfc3-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="adfc3-108">La valeur par défaut de cette propriété est -1, qui indique l'absence de délai d'expiration pour les demandes de verrous internes.</span><span class="sxs-lookup"><span data-stu-id="adfc3-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="adfc3-109">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adfc3-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="adfc3-110">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adfc3-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adfc3-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adfc3-111">See Also</span></span>  
 <span data-ttu-id="adfc3-112">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="adfc3-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="adfc3-113">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="adfc3-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
