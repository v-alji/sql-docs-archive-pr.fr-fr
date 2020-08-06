---
title: Méthode SetServiceAccountPassword, (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccountPassword Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccountPassword method
ms.assetid: e577a1ac-985c-4799-bb38-9393efc3def2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7a83a6d3686b2ec2df98ae79b4c9d3347f621ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696555"
---
# <a name="setserviceaccountpassword-method-sqlservice-class"></a><span data-ttu-id="b1c5e-102">Méthode SetServiceAccountPassword (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="b1c5e-102">SetServiceAccountPassword Method (SqlService Class)</span></span>
  <span data-ttu-id="b1c5e-103">Modifie le mot de passe pour le compte sous lequel le service référencé s'exécute.</span><span class="sxs-lookup"><span data-stu-id="b1c5e-103">Modifies the password for the account that the referenced service runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c5e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b1c5e-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccountPassword(  
AccountOldPassword , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b1c5e-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="b1c5e-105">Parts</span></span>  
 <span data-ttu-id="b1c5e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b1c5e-106">*object*</span></span>  
 <span data-ttu-id="b1c5e-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="b1c5e-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="b1c5e-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b1c5e-108">Parameters</span></span>  
 <span data-ttu-id="b1c5e-109">*AccountOldPassword*</span><span class="sxs-lookup"><span data-stu-id="b1c5e-109">*AccountOldPassword*</span></span>  
 <span data-ttu-id="b1c5e-110">Valeur de chaîne qui spécifie le mot de passe existant pour le compte.</span><span class="sxs-lookup"><span data-stu-id="b1c5e-110">A string value that specifies the existing password for the account.</span></span>  
  
 <span data-ttu-id="b1c5e-111">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="b1c5e-111">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="b1c5e-112">Valeur de chaîne qui spécifie le nouveau mot de passe pour le compte.</span><span class="sxs-lookup"><span data-stu-id="b1c5e-112">A string value that specifies the new password for the account.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b1c5e-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b1c5e-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="b1c5e-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="b1c5e-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1c5e-115">Notes</span><span class="sxs-lookup"><span data-stu-id="b1c5e-115">Remarks</span></span>  
  
