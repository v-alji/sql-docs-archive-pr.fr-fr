---
title: Méthode StopService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StopService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StopService method
ms.assetid: ef8e1856-4930-417a-8f52-be470fd3f15c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 534db69b9c5474638ef5e893847f7d6b9bbb645d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702540"
---
# <a name="stopservice-method-sqlservice-class"></a><span data-ttu-id="80d51-102">Méthode StopService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="80d51-102">StopService Method (SqlService Class)</span></span>
  <span data-ttu-id="80d51-103">Tente de placer le service dans l'état arrêté.</span><span class="sxs-lookup"><span data-stu-id="80d51-103">Attempts to place the service in the stopped state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d51-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="80d51-104">Syntax</span></span>  
  
```  
  
object  
.StopService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="80d51-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="80d51-105">Parts</span></span>  
 <span data-ttu-id="80d51-106">*object*</span><span class="sxs-lookup"><span data-stu-id="80d51-106">*object*</span></span>  
 <span data-ttu-id="80d51-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="80d51-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="80d51-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="80d51-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="80d51-109">Valeur `uint32` égale à 0 si la demande `ResumeService` a été acceptée, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="80d51-109">A `uint32` value, which is 0 if the `ResumeService` request was accepted, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80d51-110">Notes</span><span class="sxs-lookup"><span data-stu-id="80d51-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d51-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80d51-111">See Also</span></span>  
 <span data-ttu-id="80d51-112">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="80d51-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
