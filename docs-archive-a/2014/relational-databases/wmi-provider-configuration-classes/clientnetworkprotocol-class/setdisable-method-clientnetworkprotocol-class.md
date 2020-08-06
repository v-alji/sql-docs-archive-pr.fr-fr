---
title: Méthode SetDisable (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: bce69ab9-ea5b-43fd-8114-08b1b5890755
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bad312f1f7c7e9540acdaf3dd46df78b953d4ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615054"
---
# <a name="setdisable-method-clientnetworkprotocol-class"></a><span data-ttu-id="4bcdb-102">Méthode SetDisable (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="4bcdb-102">SetDisable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="4bcdb-103">Désactive le protocole réseau client spécifié par la [Configuration des protocoles clients](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="4bcdb-103">Disables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bcdb-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4bcdb-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4bcdb-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="4bcdb-105">Parts</span></span>  
 <span data-ttu-id="4bcdb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4bcdb-106">*object*</span></span>  
 <span data-ttu-id="4bcdb-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4bcdb-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4bcdb-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="4bcdb-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4bcdb-109">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="4bcdb-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bcdb-110">Notes</span><span class="sxs-lookup"><span data-stu-id="4bcdb-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcdb-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bcdb-111">See Also</span></span>  
 [<span data-ttu-id="4bcdb-112">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="4bcdb-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
