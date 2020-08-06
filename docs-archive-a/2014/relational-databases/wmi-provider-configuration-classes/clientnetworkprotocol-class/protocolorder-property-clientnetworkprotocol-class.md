---
title: Propriété ProtocolOrder, (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614450"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="79a20-102">Propriété ProtocolOrder (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="79a20-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="79a20-103">Obtient le numéro d'ordre du protocole réseau client actuellement référencé tel que spécifié par la [méthode SetOrderValue (classe ClientNetworkProtocol)](clientnetworkprotocol-class.md) .</span><span class="sxs-lookup"><span data-stu-id="79a20-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a20-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="79a20-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="79a20-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="79a20-105">Parts</span></span>  
 <span data-ttu-id="79a20-106">*object*</span><span class="sxs-lookup"><span data-stu-id="79a20-106">*object*</span></span>  
 <span data-ttu-id="79a20-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79a20-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="79a20-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="79a20-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="79a20-109">Valeur `uint32` qui spécifie le numéro d'ordre du protocole réseau client actuellement référencé en tant que jeu par la méthode `OrderValue`.</span><span class="sxs-lookup"><span data-stu-id="79a20-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="79a20-110">Si le protocole réseau client est désactivé, cette valeur sera égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="79a20-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a20-111">Notes</span><span class="sxs-lookup"><span data-stu-id="79a20-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a20-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79a20-112">See Also</span></span>  
 <span data-ttu-id="79a20-113">[Configurer des protocoles clients](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="79a20-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="79a20-114">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="79a20-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
