---
title: Méthode GetNextOrderValue, (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615059"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="21c4b-102">Méthode GetNextOrderValue (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="21c4b-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="21c4b-103">Sélectionne le protocole qui figure à l'emplacement suivant dans la liste de protocoles.</span><span class="sxs-lookup"><span data-stu-id="21c4b-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c4b-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="21c4b-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="21c4b-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="21c4b-105">Parts</span></span>  
 <span data-ttu-id="21c4b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="21c4b-106">*object*</span></span>  
 <span data-ttu-id="21c4b-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21c4b-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="21c4b-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="21c4b-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="21c4b-109">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="21c4b-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21c4b-110">Notes</span><span class="sxs-lookup"><span data-stu-id="21c4b-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c4b-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21c4b-111">See Also</span></span>  
 <span data-ttu-id="21c4b-112">[Configurer des protocoles clients](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="21c4b-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="21c4b-113">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="21c4b-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
