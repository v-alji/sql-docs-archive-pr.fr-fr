---
title: Propriétés personnalisées de la destination DataReader | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610774"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="27959-102">Propriétés personnalisées de la destination DataReader</span><span class="sxs-lookup"><span data-stu-id="27959-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="27959-103">La destination DataReader comporte à la fois des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="27959-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="27959-104">Le tableau suivant décrit les propriétés personnalisées de la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="27959-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="27959-105">Toutes les propriétés sont en lecture/écriture, à l'exception de `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="27959-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="27959-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="27959-106">Property name</span></span>|<span data-ttu-id="27959-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="27959-107">Data Type</span></span>|<span data-ttu-id="27959-108">Description</span><span class="sxs-lookup"><span data-stu-id="27959-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="27959-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="27959-109">DataReader</span></span>|<span data-ttu-id="27959-110">String</span><span class="sxs-lookup"><span data-stu-id="27959-110">String</span></span>|<span data-ttu-id="27959-111">Nom de classe de la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="27959-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="27959-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="27959-112">FailOnTimeout</span></span>|<span data-ttu-id="27959-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="27959-113">Boolean</span></span>|<span data-ttu-id="27959-114">Indique s'il faut faire échouer l'opération ou non lorsqu'un `ReadTimeout` se produit.</span><span class="sxs-lookup"><span data-stu-id="27959-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="27959-115">La valeur par défaut de cette propriété est **False**.</span><span class="sxs-lookup"><span data-stu-id="27959-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="27959-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="27959-116">ReadTimeout</span></span>|<span data-ttu-id="27959-117">Integer</span><span class="sxs-lookup"><span data-stu-id="27959-117">Integer</span></span>|<span data-ttu-id="27959-118">Nombre de millisecondes devant s'écouler avant l'expiration du délai d'attente.</span><span class="sxs-lookup"><span data-stu-id="27959-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="27959-119">La valeur par défaut de cette propriété est 30000 (30 secondes).</span><span class="sxs-lookup"><span data-stu-id="27959-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="27959-120">L'entrée et les colonnes d'entrée de la destination DataReader ne disposent pas de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="27959-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="27959-121">Pour plus d’informations, consultez [Destination DataReader](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="27959-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27959-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="27959-122">See Also</span></span>  
 [<span data-ttu-id="27959-123">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="27959-123">Common Properties</span></span>](../common-properties.md)  
  
  
