---
title: Méthode SetDisable (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 0ebbe0c5-07ad-4a76-a918-e379930adf71
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3176227aba4de1e5aca1be35ec1f071a15caa49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603345"
---
# <a name="setdisable-method-servernetworkprotocol-class"></a><span data-ttu-id="79ebd-102">Méthode SetDisable (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="79ebd-102">SetDisable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="79ebd-103">Désactive le protocole réseau serveur.</span><span class="sxs-lookup"><span data-stu-id="79ebd-103">Disables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79ebd-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="79ebd-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="79ebd-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="79ebd-105">Parts</span></span>  
 <span data-ttu-id="79ebd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="79ebd-106">*object*</span></span>  
 <span data-ttu-id="79ebd-107">Objet [ServerNetworkProtocol Class] ServerNetworkProtocol-class.md) qui représente le protocole réseau utilisé par l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79ebd-107">A [ServerNetworkProtocol Class]servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="79ebd-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="79ebd-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="79ebd-109">Valeur uint32 égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="79ebd-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79ebd-110">Notes</span><span class="sxs-lookup"><span data-stu-id="79ebd-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79ebd-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79ebd-111">See Also</span></span>  
 <span data-ttu-id="79ebd-112">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="79ebd-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
