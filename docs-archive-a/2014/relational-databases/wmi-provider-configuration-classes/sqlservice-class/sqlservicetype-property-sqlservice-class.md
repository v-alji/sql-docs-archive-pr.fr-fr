---
title: Propriété SqlServiceType (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702556"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="d8dbf-102">Propriété SqlServiceType (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="d8dbf-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="d8dbf-103">Obtient le type du service managé.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dbf-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d8dbf-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="d8dbf-105">Éléments</span><span class="sxs-lookup"><span data-stu-id="d8dbf-105">Parts</span></span>  
 <span data-ttu-id="d8dbf-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-106">*object*</span></span>  
 <span data-ttu-id="d8dbf-107">Objet de [classe SqlService](sqlservice-class.md) qui représente le service.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d8dbf-108">Valeur de propriété/valeur de retour</span><span class="sxs-lookup"><span data-stu-id="d8dbf-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="d8dbf-109">Valeur uint32 qui spécifie le type du service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8dbf-110">Notes</span><span class="sxs-lookup"><span data-stu-id="d8dbf-110">Remarks</span></span>  
 <span data-ttu-id="d8dbf-111">Les valeurs retournées peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8dbf-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="d8dbf-112">Type</span><span class="sxs-lookup"><span data-stu-id="d8dbf-112">Type</span></span>|<span data-ttu-id="d8dbf-113">Définition</span><span class="sxs-lookup"><span data-stu-id="d8dbf-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="d8dbf-114">*1*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-114">*1*</span></span>|<span data-ttu-id="d8dbf-115">MSSQLSERVER est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="d8dbf-116">*2*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-116">*2*</span></span>|<span data-ttu-id="d8dbf-117">SQLSERVERAGENT est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="d8dbf-118">*3*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-118">*3*</span></span>|<span data-ttu-id="d8dbf-119">MSFTESQL est le service du moteur de recherche en texte intégral [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="d8dbf-120">*4*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-120">*4*</span></span>|<span data-ttu-id="d8dbf-121">MsDtsServer est le service [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="d8dbf-122">*5*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-122">*5*</span></span>|<span data-ttu-id="d8dbf-123">MSSQLServerOLAPService est le service [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="d8dbf-124">*6*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-124">*6*</span></span>|<span data-ttu-id="d8dbf-125">ReportServer est le service [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8dbf-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="d8dbf-126">*7*</span><span class="sxs-lookup"><span data-stu-id="d8dbf-126">*7*</span></span>|<span data-ttu-id="d8dbf-127">SQLBrowser est le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="d8dbf-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8dbf-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8dbf-128">See Also</span></span>  
 <span data-ttu-id="d8dbf-129">[Démarrage et arrêt des services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d8dbf-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
