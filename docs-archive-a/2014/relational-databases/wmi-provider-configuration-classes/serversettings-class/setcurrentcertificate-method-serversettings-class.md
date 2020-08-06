---
title: Méthode SetCurrentCertificate (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: f9c6e172-11be-42de-b19b-a5b3436e84da
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7071937a7d7e601597fe008187448bb16a5a15ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699342"
---
# <a name="setcurrentcertificate-method-serversettings-class"></a><span data-ttu-id="ad945-102">Méthode SetCurrentCertificate (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="ad945-102">SetCurrentCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="ad945-103">Définit le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="ad945-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad945-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ad945-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ad945-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="ad945-105">Parts</span></span>  
 <span data-ttu-id="ad945-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ad945-106">*object*</span></span>  
 <span data-ttu-id="ad945-107">Objet [ServerSettings Class] ServerSettings-class.md) qui représente le paramètre du serveur sur une instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad945-107">A [ServerSettings Class]serversettings-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ad945-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ad945-108">Parameters</span></span>  
  
|<span data-ttu-id="ad945-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="ad945-109">Parameter</span></span>|<span data-ttu-id="ad945-110">Description</span><span class="sxs-lookup"><span data-stu-id="ad945-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad945-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="ad945-111">*SHA*</span></span>|<span data-ttu-id="ad945-112">Valeur de chaîne qui spécifie le certificat de sécurité actuel.</span><span class="sxs-lookup"><span data-stu-id="ad945-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ad945-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="ad945-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ad945-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="ad945-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad945-115">Notes</span><span class="sxs-lookup"><span data-stu-id="ad945-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad945-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad945-116">See Also</span></span>  
 <span data-ttu-id="ad945-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ad945-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
