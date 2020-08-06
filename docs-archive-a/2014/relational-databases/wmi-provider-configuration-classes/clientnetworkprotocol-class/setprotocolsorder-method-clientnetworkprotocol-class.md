---
title: Méthode SetProtocolsOrder, (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614445"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="882d4-102">Méthode SetProtocolsOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="882d4-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="882d4-103">Modifie l'ordre de la liste de protocoles.</span><span class="sxs-lookup"><span data-stu-id="882d4-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882d4-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="882d4-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="882d4-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="882d4-105">Parts</span></span>  
 <span data-ttu-id="882d4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="882d4-106">*object*</span></span>  
 <span data-ttu-id="882d4-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="882d4-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="882d4-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="882d4-108">Parameters</span></span>  
  
|<span data-ttu-id="882d4-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="882d4-109">Parameter</span></span>|<span data-ttu-id="882d4-110">Description</span><span class="sxs-lookup"><span data-stu-id="882d4-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="882d4-111">*ProtocolOrderList*</span><span class="sxs-lookup"><span data-stu-id="882d4-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="882d4-112">Tableau string[] qui répertorie les protocoles réseau clients dans le nouvel ordre.</span><span class="sxs-lookup"><span data-stu-id="882d4-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="882d4-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="882d4-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="882d4-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="882d4-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="882d4-115">Notes</span><span class="sxs-lookup"><span data-stu-id="882d4-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="882d4-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="882d4-116">See Also</span></span>  
 <span data-ttu-id="882d4-117">[Configurer des protocoles clients](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="882d4-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="882d4-118">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="882d4-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
