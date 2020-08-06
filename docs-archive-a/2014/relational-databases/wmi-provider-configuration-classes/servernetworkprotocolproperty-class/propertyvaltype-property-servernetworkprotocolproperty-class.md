---
title: Propriété PropertyValType (classe ServerNetworkProtocolProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707315"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="f2d93-102">Propriété PropertyValType (classe ServerNetworkProtocolProperty)</span><span class="sxs-lookup"><span data-stu-id="f2d93-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="f2d93-103">Obtient le type de données de la valeur stockée dans la propriété référencée.</span><span class="sxs-lookup"><span data-stu-id="f2d93-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d93-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f2d93-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="f2d93-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="f2d93-105">Parts</span></span>  
 <span data-ttu-id="f2d93-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f2d93-106">*object*</span></span>  
 <span data-ttu-id="f2d93-107">A [classe ServerNetworkProtocolProperty](servernetworkprotocolproperty-class.md) qui représente un attribut du protocole réseau sur l'instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2d93-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f2d93-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f2d93-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f2d93-109">Valeur `uint32` qui spécifie le type de données de la valeur de la propriété.</span><span class="sxs-lookup"><span data-stu-id="f2d93-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="f2d93-110">Elle retourne 0 pour une valeur de chaîne et 1 pour un type numérique.</span><span class="sxs-lookup"><span data-stu-id="f2d93-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2d93-111">Notes</span><span class="sxs-lookup"><span data-stu-id="f2d93-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d93-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2d93-112">See Also</span></span>  
 <span data-ttu-id="f2d93-113">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f2d93-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
