---
title: Visionneuse de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610776"
---
# <a name="data-viewer"></a><span data-ttu-id="be00c-102">Visionneuse de données</span><span class="sxs-lookup"><span data-stu-id="be00c-102">Data Viewer</span></span>
  <span data-ttu-id="be00c-103">Si un chemin d'accès est configuré pour utiliser une visionneuse de données, la visionneuse affiche les données tampon par tampon à mesure qu'elles se déplacent entre deux composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="be00c-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be00c-104">Options</span><span class="sxs-lookup"><span data-stu-id="be00c-104">Options</span></span>  
 <span data-ttu-id="be00c-105">**Flèche verte**</span><span class="sxs-lookup"><span data-stu-id="be00c-105">**Green arrow**</span></span>  
 <span data-ttu-id="be00c-106">Cliquez sur cette option pour afficher les données du tampon suivant.</span><span class="sxs-lookup"><span data-stu-id="be00c-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="be00c-107">Si les données peuvent être déplacées dans un tampon unique, cette option n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="be00c-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="be00c-108">**Détacher**</span><span class="sxs-lookup"><span data-stu-id="be00c-108">**Detach**</span></span>  
 <span data-ttu-id="be00c-109">Détachez la visionneuse de données.</span><span class="sxs-lookup"><span data-stu-id="be00c-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="be00c-110">**Remarque** Le détachement d'une visionneuse de données ne la supprime pas.</span><span class="sxs-lookup"><span data-stu-id="be00c-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="be00c-111">Si la visionneuse de données est détachée, les données continuent de circuler sur le chemin mais les données de la visionneuse ne sont pas mises à jour pour refléter les données de chaque tampon.</span><span class="sxs-lookup"><span data-stu-id="be00c-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="be00c-112">**Attacher**</span><span class="sxs-lookup"><span data-stu-id="be00c-112">**Attach**</span></span>  
 <span data-ttu-id="be00c-113">Attachez une visionneuse de données.</span><span class="sxs-lookup"><span data-stu-id="be00c-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="be00c-114">**Remarque** Lorsque la visionneuse de données est attachée, elle affiche les informations de chaque tampon du flux de données, puis s'arrête.</span><span class="sxs-lookup"><span data-stu-id="be00c-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="be00c-115">Vous pouvez progresser dans les tampons à l'aide de la flèche verte.</span><span class="sxs-lookup"><span data-stu-id="be00c-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="be00c-116">**Copier les données**</span><span class="sxs-lookup"><span data-stu-id="be00c-116">**Copy Data**</span></span>  
 <span data-ttu-id="be00c-117">Copiez les données du tampon actuel dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="be00c-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be00c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be00c-118">See Also</span></span>  
 [<span data-ttu-id="be00c-119">Débogage d’un flux de données</span><span class="sxs-lookup"><span data-stu-id="be00c-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
