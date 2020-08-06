---
title: Méthode SetFlag (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697632"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="69544-102">Méthode SetFlag (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="69544-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="69544-103">Définit l'indicateur de la propriété référencée.</span><span class="sxs-lookup"><span data-stu-id="69544-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69544-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="69544-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="69544-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="69544-105">Parts</span></span>  
 <span data-ttu-id="69544-106">*object*</span><span class="sxs-lookup"><span data-stu-id="69544-106">*object*</span></span>  
 <span data-ttu-id="69544-107">Objet [ServerNetworkProtocolProperty Class] ServerNetworkProtocolProperty-class.md) qui représente un attribut du protocole réseau sur l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69544-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="69544-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="69544-108">Parameters</span></span>  
  
|<span data-ttu-id="69544-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="69544-109">Parameter</span></span>|<span data-ttu-id="69544-110">Description</span><span class="sxs-lookup"><span data-stu-id="69544-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69544-111">*BoolValue*</span><span class="sxs-lookup"><span data-stu-id="69544-111">*BoolValue*</span></span>|<span data-ttu-id="69544-112">Valeur booléenne qui spécifie la nouvelle valeur de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="69544-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="69544-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="69544-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="69544-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="69544-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69544-115">Notes</span><span class="sxs-lookup"><span data-stu-id="69544-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69544-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69544-116">See Also</span></span>  
 <span data-ttu-id="69544-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="69544-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
