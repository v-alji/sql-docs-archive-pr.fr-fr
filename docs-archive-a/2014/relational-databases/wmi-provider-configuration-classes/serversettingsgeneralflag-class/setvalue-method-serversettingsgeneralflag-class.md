---
title: SetValue, méthode (classe ServerSettingsGeneralFlag) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710488"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="e7cc1-102">Méthode SetValue (classe ServerSettingsGeneralFlag)</span><span class="sxs-lookup"><span data-stu-id="e7cc1-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="e7cc1-103">Définit toutes les valeurs de l'indicateur référencé.</span><span class="sxs-lookup"><span data-stu-id="e7cc1-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7cc1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e7cc1-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e7cc1-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="e7cc1-105">Parts</span></span>  
 <span data-ttu-id="e7cc1-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e7cc1-106">*object*</span></span>  
 <span data-ttu-id="e7cc1-107">Objet de [classe ServerSettingsGeneralFlag](serversettingsgeneralflag-class.md) qui représente un indicateur général pour les paramètres du serveur.</span><span class="sxs-lookup"><span data-stu-id="e7cc1-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e7cc1-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e7cc1-108">Parameters</span></span>  
  
|<span data-ttu-id="e7cc1-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="e7cc1-109">Parameter</span></span>|<span data-ttu-id="e7cc1-110">Description</span><span class="sxs-lookup"><span data-stu-id="e7cc1-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7cc1-111">*Valeur*</span><span class="sxs-lookup"><span data-stu-id="e7cc1-111">*Value*</span></span>|<span data-ttu-id="e7cc1-112">Valeur booléenne qui spécifie la valeur de l'indicateur.</span><span class="sxs-lookup"><span data-stu-id="e7cc1-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e7cc1-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="e7cc1-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e7cc1-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="e7cc1-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7cc1-115">Notes</span><span class="sxs-lookup"><span data-stu-id="e7cc1-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7cc1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7cc1-116">See Also</span></span>  
 <span data-ttu-id="e7cc1-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e7cc1-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
