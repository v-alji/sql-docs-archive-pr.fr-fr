---
title: Méthode setStartMode, (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600701"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="fb16e-102">Méthode SetStartMode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="fb16e-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="fb16e-103">Modifie le mode de démarrage de l'instance de service.</span><span class="sxs-lookup"><span data-stu-id="fb16e-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb16e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fb16e-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="fb16e-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="fb16e-105">Parts</span></span>  
 <span data-ttu-id="fb16e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="fb16e-106">*object*</span></span>  
 <span data-ttu-id="fb16e-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="fb16e-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="fb16e-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fb16e-108">Parameters</span></span>  
 <span data-ttu-id="fb16e-109">*StartMode*</span><span class="sxs-lookup"><span data-stu-id="fb16e-109">*StartMode*</span></span>  
 <span data-ttu-id="fb16e-110">Valeur `uint32` qui spécifie le mode de démarrage de l'instance de service.</span><span class="sxs-lookup"><span data-stu-id="fb16e-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="fb16e-111">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="fb16e-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="fb16e-112">Valeur = 0.</span><span class="sxs-lookup"><span data-stu-id="fb16e-112">Value = 0.</span></span> <span data-ttu-id="fb16e-113">Boot - Le pilote de périphérique est démarré par le chargeur du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="fb16e-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="fb16e-114">Cette valeur est uniquement valide pour les services de pilote.</span><span class="sxs-lookup"><span data-stu-id="fb16e-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="fb16e-115">Valeur = 1.</span><span class="sxs-lookup"><span data-stu-id="fb16e-115">Value = 1.</span></span> <span data-ttu-id="fb16e-116">System - Le pilote de périphérique est démarré par la méthode `IoInitSystem`.</span><span class="sxs-lookup"><span data-stu-id="fb16e-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="fb16e-117">Cette valeur est uniquement valide pour les services de pilote.</span><span class="sxs-lookup"><span data-stu-id="fb16e-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="fb16e-118">Valeur = 2</span><span class="sxs-lookup"><span data-stu-id="fb16e-118">Value = 2.</span></span> <span data-ttu-id="fb16e-119">Automatic - Le service doit être démarré automatiquement par le Gestionnaire de contrôle des services lors du démarrage du système.</span><span class="sxs-lookup"><span data-stu-id="fb16e-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="fb16e-120">Valeur = 3.</span><span class="sxs-lookup"><span data-stu-id="fb16e-120">Value = 3.</span></span> <span data-ttu-id="fb16e-121">Manual - Le service doit être démarré par Computer Manager lorsqu'un processus appelle la méthode `StartService`.</span><span class="sxs-lookup"><span data-stu-id="fb16e-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="fb16e-122">Valeur = 4</span><span class="sxs-lookup"><span data-stu-id="fb16e-122">Value = 4.</span></span> <span data-ttu-id="fb16e-123">Disabled - Le service ne peut pas être démarré.</span><span class="sxs-lookup"><span data-stu-id="fb16e-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fb16e-124">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="fb16e-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="fb16e-125">Valeur `uint32` égale à 0 si le service a été correctement modifié ou égale à 1 si la demande n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="fb16e-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="fb16e-126">Tout autre nombre indique une erreur.</span><span class="sxs-lookup"><span data-stu-id="fb16e-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb16e-127">Notes</span><span class="sxs-lookup"><span data-stu-id="fb16e-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb16e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb16e-128">See Also</span></span>  
 <span data-ttu-id="fb16e-129">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb16e-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
