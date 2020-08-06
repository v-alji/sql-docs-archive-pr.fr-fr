---
title: Propriété StartMode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702555"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="4fa1b-102">Propriété StartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="4fa1b-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="4fa1b-103">Obtient le mode de démarrage du service.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa1b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4fa1b-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="4fa1b-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="4fa1b-105">Parts</span></span>  
 <span data-ttu-id="4fa1b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4fa1b-106">*object*</span></span>  
 <span data-ttu-id="4fa1b-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4fa1b-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="4fa1b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4fa1b-109">Valeur uint32 qui spécifie le mode du service.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="4fa1b-110">Il peut s'agir de l'une des valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="4fa1b-111">Démarrage</span><span class="sxs-lookup"><span data-stu-id="4fa1b-111">Boot</span></span>  
 <span data-ttu-id="4fa1b-112">Valeur = 0.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-112">Value = 0.</span></span> <span data-ttu-id="4fa1b-113">Le service est démarré par le chargeur du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-113">Service started by the operating system loader.</span></span> <span data-ttu-id="4fa1b-114">Cette option est uniquement valide pour les services de pilote.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="4fa1b-115">Système</span><span class="sxs-lookup"><span data-stu-id="4fa1b-115">System</span></span>  
 <span data-ttu-id="4fa1b-116">Valeur = 1.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-116">Value = 1.</span></span> <span data-ttu-id="4fa1b-117">Le service est démarré par la méthode `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="4fa1b-118">Cette option est uniquement valide pour les services de pilote.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="4fa1b-119">Automatique</span><span class="sxs-lookup"><span data-stu-id="4fa1b-119">Automatic</span></span>  
 <span data-ttu-id="4fa1b-120">Valeur = 2</span><span class="sxs-lookup"><span data-stu-id="4fa1b-120">Value = 2.</span></span> <span data-ttu-id="4fa1b-121">Le service doit être démarré automatiquement par le Gestionnaire de contrôle des services lors du démarrage du système.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="4fa1b-122">Manuel</span><span class="sxs-lookup"><span data-stu-id="4fa1b-122">Manual</span></span>  
 <span data-ttu-id="4fa1b-123">Valeur = 3.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-123">Value = 3.</span></span> <span data-ttu-id="4fa1b-124">Le service doit être démarré par Computer Manager lorsqu'un processus appelle la méthode `StartService`.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="4fa1b-125">Désactivé</span><span class="sxs-lookup"><span data-stu-id="4fa1b-125">Disabled</span></span>  
 <span data-ttu-id="4fa1b-126">Valeur = 4</span><span class="sxs-lookup"><span data-stu-id="4fa1b-126">Value = 4.</span></span> <span data-ttu-id="4fa1b-127">Le service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="4fa1b-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fa1b-128">Notes</span><span class="sxs-lookup"><span data-stu-id="4fa1b-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa1b-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4fa1b-129">See Also</span></span>  
 <span data-ttu-id="4fa1b-130">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4fa1b-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
