---
title: Méthode SetCurrentCertificate (classe SecurityCertificate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603351"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="cf18f-102">Méthode SetCurrentCertificate (classe SecurityCertificate)</span><span class="sxs-lookup"><span data-stu-id="cf18f-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="cf18f-103">Définit le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="cf18f-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf18f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="cf18f-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="cf18f-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="cf18f-105">Parts</span></span>  
 <span data-ttu-id="cf18f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="cf18f-106">*object*</span></span>  
 <span data-ttu-id="cf18f-107">Objet [SecurityCertificate Class] SecurityCertificate-class.md) qui représente un certificat de sécurité.</span><span class="sxs-lookup"><span data-stu-id="cf18f-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="cf18f-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="cf18f-108">Parameters</span></span>  
  
|<span data-ttu-id="cf18f-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="cf18f-109">Parameter</span></span>|<span data-ttu-id="cf18f-110">Description</span><span class="sxs-lookup"><span data-stu-id="cf18f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf18f-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="cf18f-111">*SHA*</span></span>|<span data-ttu-id="cf18f-112">Valeur de chaîne qui spécifie l'empreinte numérique de l'algorithme de hachage sécurisé (SHA) pour le certificat de sécurité requis.</span><span class="sxs-lookup"><span data-stu-id="cf18f-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="cf18f-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="cf18f-113">*SQLInstance*</span></span>|<span data-ttu-id="cf18f-114">Valeur de chaîne qui spécifie l'instance pour laquelle le certificat est requis.</span><span class="sxs-lookup"><span data-stu-id="cf18f-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="cf18f-115">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="cf18f-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="cf18f-116">Valeur uint32 égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="cf18f-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf18f-117">Notes</span><span class="sxs-lookup"><span data-stu-id="cf18f-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf18f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf18f-118">See Also</span></span>  
 <span data-ttu-id="cf18f-119">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="cf18f-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
