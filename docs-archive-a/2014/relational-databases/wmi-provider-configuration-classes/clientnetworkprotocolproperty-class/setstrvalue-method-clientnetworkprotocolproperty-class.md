---
title: Méthode SetStrValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 4ff80124-6e2e-4d96-a692-57c17b53c55e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f3c23eebdbe948e1b77c47ef56a04691fa391938
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708123"
---
# <a name="setstrvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="3e87f-102">Méthode SetStrValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="3e87f-102">SetStrValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="3e87f-103">Définit la valeur de chaîne de la propriété actuelle référencée par la valeur de la [propriété PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="3e87f-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e87f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3e87f-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="3e87f-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="3e87f-105">Parts</span></span>  
 <span data-ttu-id="3e87f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="3e87f-106">*object*</span></span>  
 <span data-ttu-id="3e87f-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) qui représente un attribut du protocole réseau utilisé par le client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e87f-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="3e87f-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="3e87f-108">Parameters</span></span>  
  
|<span data-ttu-id="3e87f-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="3e87f-109">Parameter</span></span>|<span data-ttu-id="3e87f-110">Description</span><span class="sxs-lookup"><span data-stu-id="3e87f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e87f-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="3e87f-111">*StrValue*</span></span>|<span data-ttu-id="3e87f-112">Valeur de chaîne qui spécifie la nouvelle valeur de la propriété actuelle.</span><span class="sxs-lookup"><span data-stu-id="3e87f-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3e87f-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="3e87f-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="3e87f-114">Valeur uint32 égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="3e87f-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e87f-115">Notes</span><span class="sxs-lookup"><span data-stu-id="3e87f-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e87f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e87f-116">See Also</span></span>  
 [<span data-ttu-id="3e87f-117">Configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="3e87f-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
