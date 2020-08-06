---
title: SetValue, méthode (classe ClientSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696660"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="c9d3e-102">Méthode SetValue (classe ClientSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="c9d3e-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="c9d3e-103">Définit toutes les valeurs de l'indicateur référencé.</span><span class="sxs-lookup"><span data-stu-id="c9d3e-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d3e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c9d3e-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c9d3e-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="c9d3e-105">Parts</span></span>  
 <span data-ttu-id="c9d3e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c9d3e-106">*object*</span></span>  
 <span data-ttu-id="c9d3e-107">Objet de [classe ClientSettingsGeneralFlag](clientsettingsgeneralflag-class.md) qui représente un indicateur général pour les paramètres du serveur.</span><span class="sxs-lookup"><span data-stu-id="c9d3e-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c9d3e-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c9d3e-108">Parameters</span></span>  
  
|<span data-ttu-id="c9d3e-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="c9d3e-109">Parameter</span></span>|<span data-ttu-id="c9d3e-110">Description</span><span class="sxs-lookup"><span data-stu-id="c9d3e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9d3e-111">*Valeur*</span><span class="sxs-lookup"><span data-stu-id="c9d3e-111">*Value*</span></span>|<span data-ttu-id="c9d3e-112">Valeur booléenne qui spécifie la valeur de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="c9d3e-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c9d3e-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c9d3e-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="c9d3e-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="c9d3e-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9d3e-115">Notes</span><span class="sxs-lookup"><span data-stu-id="c9d3e-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d3e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9d3e-116">See Also</span></span>  
 [<span data-ttu-id="c9d3e-117">Configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="c9d3e-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
