---
title: Propriété ErrorControl (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706312"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="c640a-102">Propriété ErrorControl (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="c640a-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="c640a-103">Obtient ou définit la gravité de l'erreur si le service ne peut pas démarrer au démarrage.</span><span class="sxs-lookup"><span data-stu-id="c640a-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c640a-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c640a-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c640a-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="c640a-105">Parts</span></span>  
 <span data-ttu-id="c640a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c640a-106">*object*</span></span>  
 <span data-ttu-id="c640a-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="c640a-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c640a-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c640a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c640a-109">Valeur de chaîne qui spécifie la gravité de l'erreur signalée si le service échoue au démarrage.</span><span class="sxs-lookup"><span data-stu-id="c640a-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="c640a-110">Le tableau suivant répertorie les valeurs possibles.</span><span class="sxs-lookup"><span data-stu-id="c640a-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="c640a-111">Ignorer</span><span class="sxs-lookup"><span data-stu-id="c640a-111">Ignore</span></span>  
 <span data-ttu-id="c640a-112">L'utilisateur n'est pas notifié.</span><span class="sxs-lookup"><span data-stu-id="c640a-112">User is not notified.</span></span>  
  
 <span data-ttu-id="c640a-113">Normal</span><span class="sxs-lookup"><span data-stu-id="c640a-113">Normal</span></span>  
 <span data-ttu-id="c640a-114">L'utilisateur est notifié.</span><span class="sxs-lookup"><span data-stu-id="c640a-114">User is notified.</span></span>  
  
 <span data-ttu-id="c640a-115">Severe</span><span class="sxs-lookup"><span data-stu-id="c640a-115">Severe</span></span>  
 <span data-ttu-id="c640a-116">Le système est redémarré avec la dernière bonne configuration connue.</span><span class="sxs-lookup"><span data-stu-id="c640a-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="c640a-117">Critique</span><span class="sxs-lookup"><span data-stu-id="c640a-117">Critical</span></span>  
 <span data-ttu-id="c640a-118">Le système tente de redémarrer avec une bonne configuration.</span><span class="sxs-lookup"><span data-stu-id="c640a-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="c640a-119">Unknown</span><span class="sxs-lookup"><span data-stu-id="c640a-119">Unknown</span></span>  
 <span data-ttu-id="c640a-120">La gravité est inconnue.</span><span class="sxs-lookup"><span data-stu-id="c640a-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c640a-121">Notes</span><span class="sxs-lookup"><span data-stu-id="c640a-121">Remarks</span></span>  
 <span data-ttu-id="c640a-122">La valeur indique l'action prise par le programme de démarrage en cas d'échec.</span><span class="sxs-lookup"><span data-stu-id="c640a-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="c640a-123">Toutes les erreurs sont journalisées par le système informatique.</span><span class="sxs-lookup"><span data-stu-id="c640a-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c640a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c640a-124">See Also</span></span>  
 <span data-ttu-id="c640a-125">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c640a-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
