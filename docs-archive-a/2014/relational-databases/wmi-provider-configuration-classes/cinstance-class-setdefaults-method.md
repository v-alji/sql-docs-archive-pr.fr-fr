---
title: Méthode SetDefaults (classe CInstance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599831"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="54105-102">Méthode SetDefaults (classe CInstance)</span><span class="sxs-lookup"><span data-stu-id="54105-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="54105-103">Définit toutes les valeurs par défaut pour l’instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client avec l’option permettant de remplacer les données existantes.</span><span class="sxs-lookup"><span data-stu-id="54105-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54105-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="54105-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="54105-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="54105-105">Parts</span></span>  
 <span data-ttu-id="54105-106">*object*</span><span class="sxs-lookup"><span data-stu-id="54105-106">*object*</span></span>  
 <span data-ttu-id="54105-107">Objet de [classe CInstance](cinstance-class.md) qui représente une instance du client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54105-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="54105-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="54105-108">Parameters</span></span>  
  
|<span data-ttu-id="54105-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="54105-109">Parameter</span></span>|<span data-ttu-id="54105-110">Description</span><span class="sxs-lookup"><span data-stu-id="54105-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54105-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="54105-111">*OverwriteAll*</span></span>|<span data-ttu-id="54105-112">Valeur booléenne qui spécifie s'il faut remplacer les valeurs existantes sur l'instance du client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : `true` pour remplacer les données existantes ou `false` si les données existantes ne doivent pas être remplacées.</span><span class="sxs-lookup"><span data-stu-id="54105-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="54105-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="54105-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="54105-114">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="54105-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54105-115">Notes</span><span class="sxs-lookup"><span data-stu-id="54105-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54105-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54105-116">See Also</span></span>  
 [<span data-ttu-id="54105-117">Configurer des protocoles clients</span><span class="sxs-lookup"><span data-stu-id="54105-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
