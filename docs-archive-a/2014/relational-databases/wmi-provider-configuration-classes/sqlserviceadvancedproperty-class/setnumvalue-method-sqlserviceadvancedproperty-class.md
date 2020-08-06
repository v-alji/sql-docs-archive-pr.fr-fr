---
title: Méthode SetNumValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumValue method
ms.assetid: a5e1056b-0b75-4ad6-99c1-89246010d815
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 01388855a27dcf14754f677a42c13f8d29cbaacc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702527"
---
# <a name="setnumvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="aad59-102">Méthode SetNumValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="aad59-102">SetNumValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="aad59-103">Définit la valeur numérique d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="aad59-103">Sets the numeric value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad59-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="aad59-104">Syntax</span></span>  
  
```  
  
object  
.SetNumValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="aad59-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="aad59-105">Parts</span></span>  
 <span data-ttu-id="aad59-106">*object*</span><span class="sxs-lookup"><span data-stu-id="aad59-106">*object*</span></span>  
 <span data-ttu-id="aad59-107">Objet de [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) qui représente une propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="aad59-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="aad59-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="aad59-108">Parameters</span></span>  
  
|<span data-ttu-id="aad59-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="aad59-109">Parameter</span></span>|<span data-ttu-id="aad59-110">Description</span><span class="sxs-lookup"><span data-stu-id="aad59-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aad59-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="aad59-111">*NumValue*</span></span>|<span data-ttu-id="aad59-112">Valeur `uint32` qui spécifie la valeur de la propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="aad59-112">A `uint32` value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="aad59-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="aad59-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="aad59-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="aad59-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aad59-115">Notes</span><span class="sxs-lookup"><span data-stu-id="aad59-115">Remarks</span></span>  
 <span data-ttu-id="aad59-116">Le type de valeur de la propriété doit être numérique pour permettre l'attribution d'une valeur numérique à la propriété.</span><span class="sxs-lookup"><span data-stu-id="aad59-116">The property value type must be numeric to be able to set the property to a numeric value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aad59-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aad59-117">See Also</span></span>  
 <span data-ttu-id="aad59-118">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="aad59-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
