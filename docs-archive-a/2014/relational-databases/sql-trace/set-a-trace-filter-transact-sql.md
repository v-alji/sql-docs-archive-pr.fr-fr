---
title: Méthode SetBoolValue, (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SetBoolValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetBoolValue method
ms.assetid: 5252b439-fce5-446a-8e57-99e3054bee69
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0c7142d6f192e94e9850b3c1a8a9481dc15a222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697648"
---
# <a name="setboolvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="45e78-102">Méthode SetBoolValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="45e78-102">SetBoolValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="45e78-103">Définit la valeur booléenne d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="45e78-103">Sets the Boolean value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e78-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="45e78-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="45e78-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="45e78-105">Parts</span></span>  
 <span data-ttu-id="45e78-106">*object*</span><span class="sxs-lookup"><span data-stu-id="45e78-106">*object*</span></span>  
 <span data-ttu-id="45e78-107">Objet de [classe SqlServiceAdvancedProperty](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) qui représente une propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="45e78-107">A [SqlServiceAdvancedProperty Class](../wmi-provider-configuration-classes/sqlserviceadvancedproperty-class/sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="45e78-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="45e78-108">Parameters</span></span>  
  
|<span data-ttu-id="45e78-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="45e78-109">Parameter</span></span>|<span data-ttu-id="45e78-110">Description</span><span class="sxs-lookup"><span data-stu-id="45e78-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45e78-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="45e78-111">*BoolValue*</span></span>|<span data-ttu-id="45e78-112">Valeur booléenne qui spécifie la valeur de la propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="45e78-112">A Boolean value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="45e78-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="45e78-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="45e78-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="45e78-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45e78-115">Notes</span><span class="sxs-lookup"><span data-stu-id="45e78-115">Remarks</span></span>  
 <span data-ttu-id="45e78-116">Le type de valeur de la propriété doit être booléen pour permettre l'attribution d'une valeur booléenne à la propriété.</span><span class="sxs-lookup"><span data-stu-id="45e78-116">The property value type must be Boolean to set the property to a Boolean value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e78-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45e78-117">See Also</span></span>  
 <span data-ttu-id="45e78-118">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="45e78-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
