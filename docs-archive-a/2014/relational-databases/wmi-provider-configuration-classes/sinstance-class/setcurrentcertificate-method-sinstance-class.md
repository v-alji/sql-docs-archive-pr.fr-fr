---
title: Méthode SetCurrentCertificate (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 7349fb87-b973-4160-a2be-cab73abf5b31
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 44e65ab30659cacca09e63a94a1f3596a182dda5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696595"
---
# <a name="setcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="19414-102">Méthode SetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="19414-102">SetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="19414-103">Définit le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="19414-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19414-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="19414-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="19414-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="19414-105">Parts</span></span>  
 <span data-ttu-id="19414-106">*object*</span><span class="sxs-lookup"><span data-stu-id="19414-106">*object*</span></span>  
 <span data-ttu-id="19414-107">Objet de [classe SInstance](sinstance-class.md) qui représente le paramètre du serveur sur une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19414-107">An [SInstance Class](sinstance-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="19414-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="19414-108">Parameters</span></span>  
  
|<span data-ttu-id="19414-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="19414-109">Parameter</span></span>|<span data-ttu-id="19414-110">Description</span><span class="sxs-lookup"><span data-stu-id="19414-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19414-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="19414-111">*SHA*</span></span>|<span data-ttu-id="19414-112">Valeur de chaîne qui spécifie le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="19414-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="19414-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="19414-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="19414-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="19414-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19414-115">Notes</span><span class="sxs-lookup"><span data-stu-id="19414-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19414-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19414-116">See Also</span></span>  
 <span data-ttu-id="19414-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="19414-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
