---
title: Propriété SqlServiceType (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614416"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="e5d6c-102">Propriété SqlServiceType (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="e5d6c-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="e5d6c-103">Obtient le type du service managé associé à la propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="e5d6c-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d6c-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e5d6c-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e5d6c-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="e5d6c-105">Parts</span></span>  
 <span data-ttu-id="e5d6c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-106">*object*</span></span>  
 <span data-ttu-id="e5d6c-107">Objet de [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) qui représente une propriété avancée.</span><span class="sxs-lookup"><span data-stu-id="e5d6c-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e5d6c-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="e5d6c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="e5d6c-109">Valeur uint32 qui spécifie le type du service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d6c-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5d6c-110">Notes</span><span class="sxs-lookup"><span data-stu-id="e5d6c-110">Remarks</span></span>  
 <span data-ttu-id="e5d6c-111">Les valeurs retournées peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="e5d6c-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="e5d6c-112">Type</span><span class="sxs-lookup"><span data-stu-id="e5d6c-112">Type</span></span>|<span data-ttu-id="e5d6c-113">Définition</span><span class="sxs-lookup"><span data-stu-id="e5d6c-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e5d6c-114">*1*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-114">*1*</span></span>|<span data-ttu-id="e5d6c-115">MSSQLSERVER est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d6c-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="e5d6c-116">*2*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-116">*2*</span></span>|<span data-ttu-id="e5d6c-117">SQLSERVERAGENT est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="e5d6c-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="e5d6c-118">*3*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-118">*3*</span></span>|<span data-ttu-id="e5d6c-119">MSFTESQL est le service du moteur de recherche en texte intégral [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d6c-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="e5d6c-120">*4*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-120">*4*</span></span>|<span data-ttu-id="e5d6c-121">MsDtsServer est le service [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d6c-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="e5d6c-122">*5*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-122">*5*</span></span>|<span data-ttu-id="e5d6c-123">MSSQLServerOLAPService est le service [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d6c-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="e5d6c-124">*6*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-124">*6*</span></span>|<span data-ttu-id="e5d6c-125">ReportServer est le service [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d6c-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="e5d6c-126">*7*</span><span class="sxs-lookup"><span data-stu-id="e5d6c-126">*7*</span></span>|<span data-ttu-id="e5d6c-127">SQLBrowser est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="e5d6c-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5d6c-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5d6c-128">See Also</span></span>  
 <span data-ttu-id="e5d6c-129">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e5d6c-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
