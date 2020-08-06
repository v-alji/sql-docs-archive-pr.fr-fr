---
title: Méthode SetDisable (classe ServerNetworkProtocolIPAddress) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696631"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="d9e38-102">Méthode SetDisable (classe ServerNetworkProtocolIPAddress)</span><span class="sxs-lookup"><span data-stu-id="d9e38-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="d9e38-103">Désactive l'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="d9e38-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e38-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d9e38-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d9e38-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="d9e38-105">Parts</span></span>  
 <span data-ttu-id="d9e38-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d9e38-106">*object*</span></span>  
 <span data-ttu-id="d9e38-107">Objet [ServerNetworkProtocolIPAdress Class] ServerNetworkProtocolIPAddress-class.md) qui représente une adresse IP pour le protocole réseau sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9e38-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d9e38-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="d9e38-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d9e38-109">Valeur uint32 égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="d9e38-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9e38-110">Notes</span><span class="sxs-lookup"><span data-stu-id="d9e38-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e38-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d9e38-111">See Also</span></span>  
 <span data-ttu-id="d9e38-112">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d9e38-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
