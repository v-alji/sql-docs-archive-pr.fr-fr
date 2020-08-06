---
title: State, propriété (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702543"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="98e8c-102">Propriété State (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="98e8c-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="98e8c-103">Obtient ou définit l'état actuel du service.</span><span class="sxs-lookup"><span data-stu-id="98e8c-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e8c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="98e8c-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="98e8c-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="98e8c-105">Parts</span></span>  
 <span data-ttu-id="98e8c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="98e8c-106">*object*</span></span>  
 <span data-ttu-id="98e8c-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="98e8c-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="98e8c-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="98e8c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="98e8c-109">Valeur uint32 qui spécifie l'état du service.</span><span class="sxs-lookup"><span data-stu-id="98e8c-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="98e8c-110">Il peut s'agir de l'une des valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="98e8c-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="98e8c-111">1</span><span class="sxs-lookup"><span data-stu-id="98e8c-111">1</span></span>  
 <span data-ttu-id="98e8c-112">Arrêté.</span><span class="sxs-lookup"><span data-stu-id="98e8c-112">Stopped.</span></span> <span data-ttu-id="98e8c-113">Le service est arrêté.</span><span class="sxs-lookup"><span data-stu-id="98e8c-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="98e8c-114">2</span><span class="sxs-lookup"><span data-stu-id="98e8c-114">2</span></span>  
 <span data-ttu-id="98e8c-115">Démarrage en attente.</span><span class="sxs-lookup"><span data-stu-id="98e8c-115">Start Pending.</span></span> <span data-ttu-id="98e8c-116">Le service est en attente de démarrage.</span><span class="sxs-lookup"><span data-stu-id="98e8c-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="98e8c-117">3</span><span class="sxs-lookup"><span data-stu-id="98e8c-117">3</span></span>  
 <span data-ttu-id="98e8c-118">Arrêt en attente.</span><span class="sxs-lookup"><span data-stu-id="98e8c-118">Stop Pending.</span></span> <span data-ttu-id="98e8c-119">Le service est en attente d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="98e8c-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="98e8c-120">4</span><span class="sxs-lookup"><span data-stu-id="98e8c-120">4</span></span>  
 <span data-ttu-id="98e8c-121">En cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="98e8c-121">Running.</span></span> <span data-ttu-id="98e8c-122">Le service est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="98e8c-122">The service is running.</span></span>  
  
 <span data-ttu-id="98e8c-123">5</span><span class="sxs-lookup"><span data-stu-id="98e8c-123">5</span></span>  
 <span data-ttu-id="98e8c-124">Continuation en attente.</span><span class="sxs-lookup"><span data-stu-id="98e8c-124">Continue Pending.</span></span> <span data-ttu-id="98e8c-125">Le service est en attente de continuation.</span><span class="sxs-lookup"><span data-stu-id="98e8c-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="98e8c-126">6</span><span class="sxs-lookup"><span data-stu-id="98e8c-126">6</span></span>  
 <span data-ttu-id="98e8c-127">Pause en attente.</span><span class="sxs-lookup"><span data-stu-id="98e8c-127">Pause Pending.</span></span> <span data-ttu-id="98e8c-128">Le service est en attente de pause.</span><span class="sxs-lookup"><span data-stu-id="98e8c-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="98e8c-129">7</span><span class="sxs-lookup"><span data-stu-id="98e8c-129">7</span></span>  
 <span data-ttu-id="98e8c-130">Suspendu.</span><span class="sxs-lookup"><span data-stu-id="98e8c-130">Paused.</span></span> <span data-ttu-id="98e8c-131">Le service est suspendu.</span><span class="sxs-lookup"><span data-stu-id="98e8c-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98e8c-132">Notes</span><span class="sxs-lookup"><span data-stu-id="98e8c-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e8c-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98e8c-133">See Also</span></span>  
 <span data-ttu-id="98e8c-134">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="98e8c-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
