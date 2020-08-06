---
title: Définir des points d’arrêt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.setbreakpoints.f1
helpviewer_keywords:
- Set Breakpoints dialog box
ms.assetid: 876e61b7-875c-43f4-bbce-d7eeb90f6730
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8115fcd845ee5ff415d13aa4fe36230234e33ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706319"
---
# <a name="set-breakpoints"></a><span data-ttu-id="9be28-102">Définir des points d’arrêt</span><span class="sxs-lookup"><span data-stu-id="9be28-102">Set Breakpoints</span></span>
  <span data-ttu-id="9be28-103">Utilisez la boîte de dialogue **Définir des points d'arrêt** pour spécifier les événements pour lesquels activer des points d'arrêt et pour gérer le contrôle du point d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9be28-103">Use the **Set Breakpoints** dialog box to specify the events on which to enable breakpoints and to control the behavior of the breakpoint.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9be28-104">Options</span><span class="sxs-lookup"><span data-stu-id="9be28-104">Options</span></span>  
 <span data-ttu-id="9be28-105">**Activé**</span><span class="sxs-lookup"><span data-stu-id="9be28-105">**Enabled**</span></span>  
 <span data-ttu-id="9be28-106">Sélectionnez cette option pour activer un point d'arrêt sur un événement.</span><span class="sxs-lookup"><span data-stu-id="9be28-106">Select to enable a breakpoint on an event.</span></span>  
  
 <span data-ttu-id="9be28-107">**Break Condition**</span><span class="sxs-lookup"><span data-stu-id="9be28-107">**Break Condition**</span></span>  
 <span data-ttu-id="9be28-108">Affichez la liste des événements disponibles sur lesquels définir des points d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="9be28-108">View a list of available events on which to set breakpoints.</span></span>  
  
 <span data-ttu-id="9be28-109">**Hit Count Type**</span><span class="sxs-lookup"><span data-stu-id="9be28-109">**Hit Count Type**</span></span>  
 <span data-ttu-id="9be28-110">Spécifiez le moment où le point d'arrêt entre en vigueur.</span><span class="sxs-lookup"><span data-stu-id="9be28-110">Specify when the breakpoint takes effect.</span></span>  
  
|<span data-ttu-id="9be28-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="9be28-111">Value</span></span>|<span data-ttu-id="9be28-112">Description</span><span class="sxs-lookup"><span data-stu-id="9be28-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9be28-113">**Toujours**</span><span class="sxs-lookup"><span data-stu-id="9be28-113">**Always**</span></span>|<span data-ttu-id="9be28-114">L'exécution est toujours suspendue lorsque le point d'arrêt est atteint.</span><span class="sxs-lookup"><span data-stu-id="9be28-114">Execution is always suspended when the breakpoint is hit.</span></span>|  
|<span data-ttu-id="9be28-115">**Égal au nombre d'accès**</span><span class="sxs-lookup"><span data-stu-id="9be28-115">**Hit count equals**</span></span>|<span data-ttu-id="9be28-116">L'exécution est suspendue lorsque le nombre de fois où s'est produit le point d'arrêt est égal au nombre d'accès.</span><span class="sxs-lookup"><span data-stu-id="9be28-116">Execution is suspended when the number of times the breakpoint has occurred is equal to the hit count.</span></span>|  
|<span data-ttu-id="9be28-117">**Supérieur ou égal au nombre d'accès**</span><span class="sxs-lookup"><span data-stu-id="9be28-117">**Hit greater or equal**</span></span>|<span data-ttu-id="9be28-118">L'exécution est suspendue lorsque le nombre de fois où s'est produit le point d'arrêt est supérieur ou égal au nombre d'accès.</span><span class="sxs-lookup"><span data-stu-id="9be28-118">Execution is suspended when the number of times the breakpoint has occurred is equal to or greater than the hit count.</span></span>|  
|<span data-ttu-id="9be28-119">**Multiple du nombre d'accès**</span><span class="sxs-lookup"><span data-stu-id="9be28-119">**Hit count multiple**</span></span>|<span data-ttu-id="9be28-120">L'exécution est suspendue lorsqu'un multiple du nombre d'accès est atteint.</span><span class="sxs-lookup"><span data-stu-id="9be28-120">Execution is suspended when a multiple of the hit count occurs.</span></span> <span data-ttu-id="9be28-121">Par exemple, si vous définissez cette option sur 5, l'exécution est suspendue une fois toutes les cinq fois.</span><span class="sxs-lookup"><span data-stu-id="9be28-121">For example, if you set this option to 5, execution is suspended every fifth time.</span></span>|  
  
 <span data-ttu-id="9be28-122">**Nombre d'accès**</span><span class="sxs-lookup"><span data-stu-id="9be28-122">**Hit Count**</span></span>  
 <span data-ttu-id="9be28-123">Spécifiez le nombre d'accès à partir duquel déclencher un arrêt.</span><span class="sxs-lookup"><span data-stu-id="9be28-123">Specify the number of hits at which to trigger a break.</span></span> <span data-ttu-id="9be28-124">Cette option n'est pas disponible si le point d'arrêt est constamment en vigueur.</span><span class="sxs-lookup"><span data-stu-id="9be28-124">This option is not available if the breakpoint is always in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be28-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9be28-125">See Also</span></span>  
 [<span data-ttu-id="9be28-126">Débogage du flux de contrôle</span><span class="sxs-lookup"><span data-stu-id="9be28-126">Debugging Control Flow</span></span>](../../../integration-services/troubleshooting/debugging-control-flow.md)  
  
  
