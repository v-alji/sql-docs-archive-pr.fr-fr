---
title: Méthode SetDefaults (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699336"
---
# <a name="setdefaults-method-serversettings-class"></a><span data-ttu-id="8d3de-102">Méthode SetDefaults (classe ServerSettings)</span><span class="sxs-lookup"><span data-stu-id="8d3de-102">SetDefaults Method (ServerSettings Class)</span></span>
  <span data-ttu-id="8d3de-103">Définit toutes les valeurs par défaut de l’instance de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avec l’option permettant de remplacer les données existantes.</span><span class="sxs-lookup"><span data-stu-id="8d3de-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3de-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="8d3de-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="8d3de-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="8d3de-105">Parts</span></span>  
 <span data-ttu-id="8d3de-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8d3de-106">*object*</span></span>  
 <span data-ttu-id="8d3de-107">Objet de [classe ServerSettings](serversettings-class.md) qui représente une [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance de client.</span><span class="sxs-lookup"><span data-stu-id="8d3de-107">A [ServerSettings Class](serversettings-class.md) object that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="8d3de-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="8d3de-108">Parameters</span></span>  
  
|<span data-ttu-id="8d3de-109">Paramètre</span><span class="sxs-lookup"><span data-stu-id="8d3de-109">Parameter</span></span>|<span data-ttu-id="8d3de-110">Description</span><span class="sxs-lookup"><span data-stu-id="8d3de-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d3de-111">*OverwriteAll*</span><span class="sxs-lookup"><span data-stu-id="8d3de-111">*OverwriteAll*</span></span>|<span data-ttu-id="8d3de-112">Valeur booléenne qui spécifie s'il faut remplacer les valeurs existantes sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : `true` pour remplacer les données existantes ou `false` si les données existantes ne doivent pas être remplacées.</span><span class="sxs-lookup"><span data-stu-id="8d3de-112">A Boolean value that specifies whether to overwrite existing values on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8d3de-113">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="8d3de-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="8d3de-114">Valeur u`int32` égale à 0 si le service a été correctement modifié, égale à 1 si la demande n'est pas prise en charge ou égale à tout autre nombre pour indiquer une erreur.</span><span class="sxs-lookup"><span data-stu-id="8d3de-114">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d3de-115">Notes</span><span class="sxs-lookup"><span data-stu-id="8d3de-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3de-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d3de-116">See Also</span></span>  
 <span data-ttu-id="8d3de-117">[Configuration des bibliothèques réseau et des protocoles réseau du serveur](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8d3de-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
