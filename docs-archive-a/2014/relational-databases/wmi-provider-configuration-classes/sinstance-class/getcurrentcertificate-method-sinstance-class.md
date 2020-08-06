---
title: Méthode GetCurrentCertificate, (classe SInstance) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 9d2b72df-cb21-414a-abef-917f13d4de62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 47838190e3791e01f8482e3fb064a9dca3a764af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615050"
---
# <a name="getcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="121a9-102">Méthode GetCurrentCertificate (classe SInstance)</span><span class="sxs-lookup"><span data-stu-id="121a9-102">GetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="121a9-103">Obtient le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="121a9-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="121a9-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="121a9-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="121a9-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="121a9-105">Parts</span></span>  
 <span data-ttu-id="121a9-106">*object*</span><span class="sxs-lookup"><span data-stu-id="121a9-106">*object*</span></span>  
 <span data-ttu-id="121a9-107">Objet de [classe SInstance](sinstance-class.md) qui représente les paramètres du serveur sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="121a9-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="121a9-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="121a9-108">Parameters</span></span>  
  
|<span data-ttu-id="121a9-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="121a9-109">Parameter</span></span>|<span data-ttu-id="121a9-110">Description</span><span class="sxs-lookup"><span data-stu-id="121a9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="121a9-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="121a9-111">*SHA*</span></span>|<span data-ttu-id="121a9-112">Valeur d'objet de chaîne (paramètre de sortie) qui spécifie le certificat de sécurité actuel une fois la méthode terminée.</span><span class="sxs-lookup"><span data-stu-id="121a9-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="121a9-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="121a9-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="121a9-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="121a9-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="121a9-115">Notes</span><span class="sxs-lookup"><span data-stu-id="121a9-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121a9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="121a9-116">See Also</span></span>  
 <span data-ttu-id="121a9-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="121a9-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
