---
title: Méthode RemoveCertificate (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 9ffdbc39-93f5-48fb-859a-86a3ad545827
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 00731fab5c4bdec61848df93829dd5013a7454f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696596"
---
# <a name="removecertificate-method-serversettings-class"></a><span data-ttu-id="ce67e-102">Méthode RemoveCertificate (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="ce67e-102">RemoveCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="ce67e-103">Supprime le certificat de sécurité actuel de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce67e-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce67e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ce67e-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ce67e-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="ce67e-105">Parts</span></span>  
 <span data-ttu-id="ce67e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ce67e-106">*object*</span></span>  
 <span data-ttu-id="ce67e-107">Objet de [classe ServerSettings](serversettings-class.md) qui représente les paramètres du serveur sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce67e-107">A [ServerSettings Class](serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ce67e-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="ce67e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ce67e-109">Valeur u`int32` égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="ce67e-109">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce67e-110">Notes</span><span class="sxs-lookup"><span data-stu-id="ce67e-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce67e-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce67e-111">See Also</span></span>  
 <span data-ttu-id="ce67e-112">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ce67e-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
