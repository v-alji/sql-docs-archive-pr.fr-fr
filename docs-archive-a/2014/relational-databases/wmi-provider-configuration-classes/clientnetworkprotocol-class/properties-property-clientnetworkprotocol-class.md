---
title: Propriété Properties (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615057"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="f6932-102">Propriété Properties (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="f6932-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="f6932-103">Obtient les propriétés associées au protocole réseau client actuel spécifié par [Configurer des protocoles clients](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="f6932-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6932-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f6932-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="f6932-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="f6932-105">Parts</span></span>  
 <span data-ttu-id="f6932-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f6932-106">*object*</span></span>  
 <span data-ttu-id="f6932-107">A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) qui représente le protocole réseau utilisé par le client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6932-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f6932-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f6932-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f6932-109">Tableau d’objets de [classe ClientNetworkProtocolProperty](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) qui représentent les propriétés prises en charge par le protocole réseau client actuel référencé par la `OrderValue` propriété.</span><span class="sxs-lookup"><span data-stu-id="f6932-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6932-110">Notes</span><span class="sxs-lookup"><span data-stu-id="f6932-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6932-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6932-111">See Also</span></span>  
 [<span data-ttu-id="f6932-112">Configuration des bibliothèques réseau et des protocoles réseau clients</span><span class="sxs-lookup"><span data-stu-id="f6932-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
