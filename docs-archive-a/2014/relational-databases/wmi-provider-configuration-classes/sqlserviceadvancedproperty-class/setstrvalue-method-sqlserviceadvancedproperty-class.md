---
title: Méthode SetStrValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702520"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="16d52-102">Méthode SetStrValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="16d52-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="16d52-103">Définit la valeur de chaîne d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="16d52-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d52-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="16d52-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="16d52-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="16d52-105">Parts</span></span>  
 <span data-ttu-id="16d52-106">*object*</span><span class="sxs-lookup"><span data-stu-id="16d52-106">*object*</span></span>  
 <span data-ttu-id="16d52-107">Objet de [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) qui représente une propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="16d52-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="16d52-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="16d52-108">Parameters</span></span>  
  
|<span data-ttu-id="16d52-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="16d52-109">Parameter</span></span>|<span data-ttu-id="16d52-110">Description</span><span class="sxs-lookup"><span data-stu-id="16d52-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16d52-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="16d52-111">*StrValue*</span></span>|<span data-ttu-id="16d52-112">Valeur de chaîne qui spécifie la valeur de la propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="16d52-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="16d52-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="16d52-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="16d52-114">Valeur uint32 égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="16d52-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d52-115">Notes</span><span class="sxs-lookup"><span data-stu-id="16d52-115">Remarks</span></span>  
 <span data-ttu-id="16d52-116">Le type de valeur de la propriété doit être *string* pour permettre l'attribution d'une valeur de chaîne à la propriété.</span><span class="sxs-lookup"><span data-stu-id="16d52-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16d52-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16d52-117">See Also</span></span>  
 <span data-ttu-id="16d52-118">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="16d52-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
