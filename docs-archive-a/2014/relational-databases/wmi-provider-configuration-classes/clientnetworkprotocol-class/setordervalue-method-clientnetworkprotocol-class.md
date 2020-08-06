---
title: Méthode SetOrderValue (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614449"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="850e6-102">Méthode SetOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="850e6-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="850e6-103">Sélectionne le protocole avec la valeur d'ordre spécifiée dans la liste de protocoles du client.</span><span class="sxs-lookup"><span data-stu-id="850e6-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="850e6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="850e6-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="850e6-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="850e6-105">Parts</span></span>  
 <span data-ttu-id="850e6-106">*object*</span><span class="sxs-lookup"><span data-stu-id="850e6-106">*object*</span></span>  
 <span data-ttu-id="850e6-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="850e6-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="850e6-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="850e6-108">Parameters</span></span>  
  
|<span data-ttu-id="850e6-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="850e6-109">Parameter</span></span>|<span data-ttu-id="850e6-110">Description</span><span class="sxs-lookup"><span data-stu-id="850e6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="850e6-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="850e6-111">*OrderValue*</span></span>|<span data-ttu-id="850e6-112">Valeur u`int32` qui définit la valeur d'ordre.</span><span class="sxs-lookup"><span data-stu-id="850e6-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="850e6-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="850e6-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="850e6-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="850e6-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="850e6-115">Notes</span><span class="sxs-lookup"><span data-stu-id="850e6-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="850e6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="850e6-116">See Also</span></span>  
 [<span data-ttu-id="850e6-117">Propriétés de protocoles clients (onglet Ordre)</span><span class="sxs-lookup"><span data-stu-id="850e6-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
