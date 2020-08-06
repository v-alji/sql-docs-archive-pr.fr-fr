---
title: Méthode GetCurrentCertificate, (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696636"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="c835c-102">Méthode GetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="c835c-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="c835c-103">Obtient le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="c835c-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c835c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c835c-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c835c-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="c835c-105">Parts</span></span>  
 <span data-ttu-id="c835c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c835c-106">*object*</span></span>  
 <span data-ttu-id="c835c-107">Objet de [classe SecurityCertificate](securitycertificate-class.md) qui représente un certificat de sécurité.</span><span class="sxs-lookup"><span data-stu-id="c835c-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c835c-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c835c-108">Parameters</span></span>  
  
|<span data-ttu-id="c835c-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="c835c-109">Parameter</span></span>|<span data-ttu-id="c835c-110">Description</span><span class="sxs-lookup"><span data-stu-id="c835c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c835c-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="c835c-111">*SHA*</span></span>|<span data-ttu-id="c835c-112">Valeur de chaîne (paramètre de sortie) qui spécifie l'empreinte numérique SHA du certificat de sécurité actuel une fois la méthode terminée.</span><span class="sxs-lookup"><span data-stu-id="c835c-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="c835c-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="c835c-113">*SQLInstance*</span></span>|<span data-ttu-id="c835c-114">Valeur de chaîne qui spécifie l'instance pour laquelle le certificat est requis.</span><span class="sxs-lookup"><span data-stu-id="c835c-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c835c-115">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c835c-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="c835c-116">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="c835c-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c835c-117">Notes</span><span class="sxs-lookup"><span data-stu-id="c835c-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c835c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c835c-118">See Also</span></span>  
 <span data-ttu-id="c835c-119">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c835c-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
