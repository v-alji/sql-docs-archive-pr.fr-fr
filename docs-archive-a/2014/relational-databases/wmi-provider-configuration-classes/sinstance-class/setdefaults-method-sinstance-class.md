---
title: Méthode SetDefaults (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696591"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="2afda-102">Méthode SetDefaults (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="2afda-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="2afda-103">Définit toutes les valeurs par défaut de l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec l’option permettant de remplacer les données existantes.</span><span class="sxs-lookup"><span data-stu-id="2afda-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2afda-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2afda-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="2afda-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="2afda-105">Parts</span></span>  
 <span data-ttu-id="2afda-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2afda-106">*object*</span></span>  
 <span data-ttu-id="2afda-107">Objet de [classe SInstance](sinstance-class.md) qui représente une instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="2afda-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2afda-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="2afda-108">Parameters</span></span>  
  
|<span data-ttu-id="2afda-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="2afda-109">Parameter</span></span>|<span data-ttu-id="2afda-110">Description</span><span class="sxs-lookup"><span data-stu-id="2afda-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2afda-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="2afda-111">*OverwriteAll*</span></span>|<span data-ttu-id="2afda-112">Valeur booléenne qui spécifie s'il faut remplacer la valeur existante sur l'instance du client [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : `true` si les données existantes sont remplacées ou `false` si les données existantes ne sont pas remplacées.</span><span class="sxs-lookup"><span data-stu-id="2afda-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2afda-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="2afda-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="2afda-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="2afda-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2afda-115">Notes</span><span class="sxs-lookup"><span data-stu-id="2afda-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afda-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2afda-116">See Also</span></span>  
 <span data-ttu-id="2afda-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2afda-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
