---
title: Propriété DisplayName (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706316"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="0be38-102">Propriété DisplayName (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="0be38-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="0be38-103">Obtient le nom complet du service.</span><span class="sxs-lookup"><span data-stu-id="0be38-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be38-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0be38-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="0be38-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="0be38-105">Parts</span></span>  
 <span data-ttu-id="0be38-106">*object*</span><span class="sxs-lookup"><span data-stu-id="0be38-106">*object*</span></span>  
 <span data-ttu-id="0be38-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="0be38-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0be38-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="0be38-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="0be38-109">Valeur de chaîne qui spécifie le nom complet du service.</span><span class="sxs-lookup"><span data-stu-id="0be38-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be38-110">Notes</span><span class="sxs-lookup"><span data-stu-id="0be38-110">Remarks</span></span>  
 <span data-ttu-id="0be38-111">Cette chaîne a une longueur maximale de 256 caractères.</span><span class="sxs-lookup"><span data-stu-id="0be38-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="0be38-112">La casse est préservée dans le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0be38-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="0be38-113">Toutefois, les comparaisons de noms complets ne respectent jamais pas la casse.</span><span class="sxs-lookup"><span data-stu-id="0be38-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0be38-114"> Exemple</span><span class="sxs-lookup"><span data-stu-id="0be38-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="0be38-115"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0be38-115">See Also</span></span>  
 <span data-ttu-id="0be38-116">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0be38-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
