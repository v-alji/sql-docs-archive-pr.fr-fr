---
title: Méthode SetNumericalValue (classe ClientNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba963bb14e46aaa3f098ae74cd7aca92019256e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604407"
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="72450-102">Méthode SetNumericalValue (classe ClientNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="72450-102">SetNumericalValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="72450-103">Définit la valeur numérique de la propriété actuelle référencée par la valeur de la [propriété PropertyIdx (classe ClientNetworkProtocolProperty)](clientnetworkprotocolproperty-class.md) .</span><span class="sxs-lookup"><span data-stu-id="72450-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72450-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="72450-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="72450-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="72450-105">Parts</span></span>  
 <span data-ttu-id="72450-106">*object*</span><span class="sxs-lookup"><span data-stu-id="72450-106">*object*</span></span>  
 <span data-ttu-id="72450-107">A [classe ClientNetworkProtocolProperty](clientnetworkprotocolproperty-class.md) qui représente un attribut du protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="72450-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="72450-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="72450-108">Parameters</span></span>  
  
|<span data-ttu-id="72450-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="72450-109">Parameter</span></span>|<span data-ttu-id="72450-110">Description</span><span class="sxs-lookup"><span data-stu-id="72450-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72450-111">*value*</span><span class="sxs-lookup"><span data-stu-id="72450-111">*value*</span></span>|<span data-ttu-id="72450-112">Valeur `uint32` qui spécifie la valeur numérique de la propriété référencée.</span><span class="sxs-lookup"><span data-stu-id="72450-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="72450-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="72450-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="72450-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="72450-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72450-115">Notes</span><span class="sxs-lookup"><span data-stu-id="72450-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72450-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72450-116">See Also</span></span>  
 [<span data-ttu-id="72450-117">Configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="72450-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
