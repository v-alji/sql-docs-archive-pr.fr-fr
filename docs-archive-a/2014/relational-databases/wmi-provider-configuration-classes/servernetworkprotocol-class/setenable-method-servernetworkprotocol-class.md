---
title: Méthode SetEnable (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603343"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="81a25-102">Méthode SetEnable (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="81a25-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="81a25-103">Active le protocole réseau serveur.</span><span class="sxs-lookup"><span data-stu-id="81a25-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81a25-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="81a25-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="81a25-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="81a25-105">Parts</span></span>  
 <span data-ttu-id="81a25-106">*object*</span><span class="sxs-lookup"><span data-stu-id="81a25-106">*object*</span></span>  
 <span data-ttu-id="81a25-107">A [classe ServerNetworkProtocol](servernetworkprotocol-class.md) qui représente le protocole réseau utilisé par l'instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81a25-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="81a25-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="81a25-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="81a25-109">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="81a25-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81a25-110">Notes</span><span class="sxs-lookup"><span data-stu-id="81a25-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a25-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81a25-111">See Also</span></span>  
 <span data-ttu-id="81a25-112">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="81a25-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
