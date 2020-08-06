---
title: Méthode SetDefaults (classe ClientSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613850"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="10132-102">Méthode SetDefaults (classe ClientSettings)</span><span class="sxs-lookup"><span data-stu-id="10132-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="10132-103">Définit toutes les valeurs par défaut pour l’instance du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client avec l’option permettant de remplacer les données existantes.</span><span class="sxs-lookup"><span data-stu-id="10132-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10132-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="10132-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="10132-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="10132-105">Parts</span></span>  
 <span data-ttu-id="10132-106">*object*</span><span class="sxs-lookup"><span data-stu-id="10132-106">*object*</span></span>  
 <span data-ttu-id="10132-107">Objet `ClientSettings` qui représente une instance du client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10132-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="10132-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="10132-108">Parameters</span></span>  
  
|<span data-ttu-id="10132-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="10132-109">Parameter</span></span>|<span data-ttu-id="10132-110">Description</span><span class="sxs-lookup"><span data-stu-id="10132-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10132-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="10132-111">*OverwriteAll*</span></span>|<span data-ttu-id="10132-112">Valeur booléenne qui spécifie s'il faut remplacer les valeurs existantes sur l'instance du client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10132-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="10132-113">`true` pour remplacer les données existantes ou `false` si les données existantes ne doivent pas être remplacées.</span><span class="sxs-lookup"><span data-stu-id="10132-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="10132-114">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="10132-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="10132-115">Valeur `uint32`, égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="10132-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10132-116">Notes</span><span class="sxs-lookup"><span data-stu-id="10132-116">Remarks</span></span>  
  
