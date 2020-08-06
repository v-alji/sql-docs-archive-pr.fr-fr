---
title: Propriété ExitCode (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ExitCode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ExitCode property
ms.assetid: e6b8bff2-946f-4abe-bd50-1f7bb11fdddf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f7f5414afd8507a1fc9c592d6b8226692e9683a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603329"
---
# <a name="exitcode-property-sqlservice-class"></a><span data-ttu-id="91668-102">Propriété ExitCode (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="91668-102">ExitCode Property (SqlService Class)</span></span>
  <span data-ttu-id="91668-103">Obtient ou définit le code d'erreur [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 qui définit les problèmes rencontrés lors du démarrage et de l'arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="91668-103">Gets or sets the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 error code that defines problems encountered when starting and stopping the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91668-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="91668-104">Syntax</span></span>  
  
```  
  
object  
.ExitCode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="91668-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="91668-105">Parts</span></span>  
 <span data-ttu-id="91668-106">*object*</span><span class="sxs-lookup"><span data-stu-id="91668-106">*object*</span></span>  
 <span data-ttu-id="91668-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="91668-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="91668-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="91668-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="91668-109">Valeur `uint32` qui spécifie le code de sortie.</span><span class="sxs-lookup"><span data-stu-id="91668-109">A `uint32` value that specifies the exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91668-110">Notes</span><span class="sxs-lookup"><span data-stu-id="91668-110">Remarks</span></span>  
 <span data-ttu-id="91668-111">Cette propriété a la valeur ERROR_SERVICE_SPECIFIC_ERROR (1066) lorsque l'erreur est spécifique au service représenté par cette classe.</span><span class="sxs-lookup"><span data-stu-id="91668-111">This property is set to ERROR_SERVICE_SPECIFIC_ERROR (1066) when the error is unique to the service represented by this class.</span></span> <span data-ttu-id="91668-112">Le service attribue la valeur NO_ERROR lors de d'exécution, et à nouveau lors d'une fin normale.</span><span class="sxs-lookup"><span data-stu-id="91668-112">The service sets this value to NO_ERROR when running, and again upon normal termination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91668-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91668-113">See Also</span></span>  
 <span data-ttu-id="91668-114">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="91668-114">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
