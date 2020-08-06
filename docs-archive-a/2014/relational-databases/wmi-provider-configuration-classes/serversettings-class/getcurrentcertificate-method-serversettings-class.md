---
title: Méthode GetCurrentCertificate, (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 450e33c6-91d4-420f-ab7c-1905111f5658
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b36a5fe7cd39da0f336d05fc4c450170fa21199d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696619"
---
# <a name="getcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="e0988-102">Méthode GetCurrentCertificate (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="e0988-102">GetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="e0988-103">Obtient le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="e0988-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0988-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e0988-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e0988-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="e0988-105">Parts</span></span>  
 <span data-ttu-id="e0988-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e0988-106">*object*</span></span>  
 <span data-ttu-id="e0988-107">Objet `ServerSettings` qui représente les paramètres du serveur sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0988-107">A `ServerSettings` object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e0988-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e0988-108">Parameters</span></span>  
  
|<span data-ttu-id="e0988-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="e0988-109">Parameter</span></span>|<span data-ttu-id="e0988-110">Description</span><span class="sxs-lookup"><span data-stu-id="e0988-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0988-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="e0988-111">*SHA*</span></span>|<span data-ttu-id="e0988-112">Valeur d'objet de chaîne (paramètre de sortie) qui spécifie le certificat de sécurité actuel une fois la méthode terminée.</span><span class="sxs-lookup"><span data-stu-id="e0988-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e0988-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="e0988-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e0988-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="e0988-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0988-115">Notes</span><span class="sxs-lookup"><span data-stu-id="e0988-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0988-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0988-116">See Also</span></span>  
 <span data-ttu-id="e0988-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e0988-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
