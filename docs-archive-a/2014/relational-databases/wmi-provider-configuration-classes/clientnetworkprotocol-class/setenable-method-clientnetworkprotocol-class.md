---
title: Méthode SetEnable (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a66c756a-1311-4f4a-8088-818f8ed90056
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dfba695506dd04ded82083b85bfbb751913fbcbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613852"
---
# <a name="setenable-method-clientnetworkprotocol-class"></a><span data-ttu-id="f865f-102">Méthode SetEnable (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="f865f-102">SetEnable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="f865f-103">Active le protocole réseau client spécifié par la configuration des [protocoles clients](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="f865f-103">Enables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f865f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f865f-104">Syntax</span></span>  
  
```  
  
object  
.SetEnableMethod()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f865f-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="f865f-105">Parts</span></span>  
 <span data-ttu-id="f865f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f865f-106">*object*</span></span>  
 <span data-ttu-id="f865f-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f865f-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f865f-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f865f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f865f-109">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="f865f-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f865f-110">Notes</span><span class="sxs-lookup"><span data-stu-id="f865f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f865f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f865f-111">See Also</span></span>  
 [<span data-ttu-id="f865f-112">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="f865f-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
