---
title: Méthode SetServiceAccount, (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696552"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="1dbda-102">Méthode SetServiceAccount (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="1dbda-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="1dbda-103">Tente de modifier le nom d'utilisateur et le mot de passe sous lesquels l'instance du service s'exécute.</span><span class="sxs-lookup"><span data-stu-id="1dbda-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dbda-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1dbda-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1dbda-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="1dbda-105">Parts</span></span>  
 <span data-ttu-id="1dbda-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1dbda-106">*object*</span></span>  
 <span data-ttu-id="1dbda-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="1dbda-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1dbda-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1dbda-108">Parameters</span></span>  
 <span data-ttu-id="1dbda-109">*ServiceStartName*</span><span class="sxs-lookup"><span data-stu-id="1dbda-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="1dbda-110">Valeur de chaîne qui spécifie le nom de compte sous lequel le service s'exécute.</span><span class="sxs-lookup"><span data-stu-id="1dbda-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="1dbda-111">En fonction du type de service, le nom de compte peut se présenter sous la forme DomainName\Username.</span><span class="sxs-lookup"><span data-stu-id="1dbda-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="1dbda-112">Lorsqu'il s'exécute, le processus du service sera connecté à l'aide de l'une des deux formes suivantes :</span><span class="sxs-lookup"><span data-stu-id="1dbda-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="1dbda-113">si le compte appartient au domaine intégré, \Username peut être spécifié ;</span><span class="sxs-lookup"><span data-stu-id="1dbda-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="1dbda-114">Si NULL est spécifié, le service est connecté en tant que compte **LocalSystem** .</span><span class="sxs-lookup"><span data-stu-id="1dbda-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="1dbda-115">Pour les pilotes au niveau du noyau ou du système, *StartName* contient le nom d’objet du pilote, \FileSystem\Rdr ou \Driver\Xns, que le système d’e/s utilise pour charger le pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="1dbda-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="1dbda-116">Si la valeur NULL est spécifiée, le pilote s'exécute avec un nom d'objet par défaut créé par le système d'E/S en fonction du nom du service, par exemple DWDOM\Admin.</span><span class="sxs-lookup"><span data-stu-id="1dbda-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="1dbda-117">*ServiceStartPassword*</span><span class="sxs-lookup"><span data-stu-id="1dbda-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="1dbda-118">Valeur de chaîne qui spécifie le mot de passe pour le nom de compte dans le paramètre *StartName* .</span><span class="sxs-lookup"><span data-stu-id="1dbda-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="1dbda-119">Spécifiez NULL si vous ne modifiez pas le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="1dbda-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="1dbda-120">Spécifiez une chaîne vide si le service ne possède pas de mot de passe.</span><span class="sxs-lookup"><span data-stu-id="1dbda-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1dbda-121">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="1dbda-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="1dbda-122">Valeur `uint32` égale à 0 si le service a été correctement modifié ou égale à 1 si la demande n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1dbda-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="1dbda-123">Tout autre nombre indique une erreur.</span><span class="sxs-lookup"><span data-stu-id="1dbda-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dbda-124">Notes</span><span class="sxs-lookup"><span data-stu-id="1dbda-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dbda-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1dbda-125">See Also</span></span>  
 <span data-ttu-id="1dbda-126">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1dbda-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
