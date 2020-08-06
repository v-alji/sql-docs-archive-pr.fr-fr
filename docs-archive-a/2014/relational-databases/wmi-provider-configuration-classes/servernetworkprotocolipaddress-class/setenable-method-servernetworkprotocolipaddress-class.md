---
title: Méthode SetEnable (classe ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5be9c30acacaedba320fd68363e531b178918271
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610984"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="a7d81-102">Méthode SetEnable (classe ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="a7d81-102">SetEnable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="a7d81-103">Active l'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="a7d81-103">Enables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7d81-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a7d81-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="a7d81-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="a7d81-105">Parts</span></span>  
 <span data-ttu-id="a7d81-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a7d81-106">*object*</span></span>  
 <span data-ttu-id="a7d81-107">A [classe ServerNetworkProtocolIPAdress](servernetworkprotocolipaddress-class.md) qui représente une adresse IP pour le protocole réseau sur l'instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7d81-107">A [ServerNetworkProtocolIPAdress Class](servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a7d81-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a7d81-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a7d81-109">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="a7d81-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7d81-110">Notes</span><span class="sxs-lookup"><span data-stu-id="a7d81-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d81-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7d81-111">See Also</span></span>  
 <span data-ttu-id="a7d81-112">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a7d81-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
