---
title: GetDatabaseVersionDisplayName, méthode (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetDatabaseVersionDisplayName method
ms.assetid: e1286424-7043-4f12-a7ad-1cf69e81baa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b39ce39a4f26964c148631c903869b0234e2b9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604363"
---
# <a name="getdatabaseversiondisplayname-method-wmi"></a><span data-ttu-id="d1aa3-102">Méthode GetDatabaseVersionDisplayName (WMI)</span><span class="sxs-lookup"><span data-stu-id="d1aa3-102">GetDatabaseVersionDisplayName Method (WMI)</span></span>
  <span data-ttu-id="d1aa3-103">Obtient le nom complet de la chaîne de version d'une base de données de serveur de rapports spécifique.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-103">Gets the display name for a given report server database version string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1aa3-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d1aa3-104">Syntax</span></span>  
  
```vb  
Public Sub GetDatabaseVersionDisplayName(Version As String, DisplayName As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetDatabaseVersionDisplayName(string Version, string DisplayName, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1aa3-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d1aa3-105">Parameters</span></span>  
 <span data-ttu-id="d1aa3-106">*Version*</span><span class="sxs-lookup"><span data-stu-id="d1aa3-106">*Version*</span></span>  
 <span data-ttu-id="d1aa3-107">Chaîne qui contient la chaîne de version d'une base de données de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-107">A string that contains the version string for a report server database.</span></span>  
  
 <span data-ttu-id="d1aa3-108">*DisplayName*</span><span class="sxs-lookup"><span data-stu-id="d1aa3-108">*DisplayName*</span></span>  
 <span data-ttu-id="d1aa3-109">[out] Chaîne qui contient le nom complet correspondant à la version fournie.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-109">[out] A string that contains the display name that corresponds to the version supplied.</span></span>  
  
 <span data-ttu-id="d1aa3-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d1aa3-110">*HRESULT*</span></span>  
 <span data-ttu-id="d1aa3-111">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1aa3-112">Notes</span><span class="sxs-lookup"><span data-stu-id="d1aa3-112">Remarks</span></span>  
 <span data-ttu-id="d1aa3-113">Le tableau suivant indique la correspondance entre la version de la base de données et la chaîne d'affichage.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-113">The following table shows the mapping from database version to display string.</span></span>  
  
|<span data-ttu-id="d1aa3-114">**Version release**</span><span class="sxs-lookup"><span data-stu-id="d1aa3-114">**Release**</span></span>|`Version`|<span data-ttu-id="d1aa3-115">**Nom complet**</span><span class="sxs-lookup"><span data-stu-id="d1aa3-115">**Display Name**</span></span>|  
|-----------------|-----------------|----------------------|  
|<span data-ttu-id="d1aa3-116">RS 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="d1aa3-116">RS 2005 SP2</span></span>|<span data-ttu-id="d1aa3-117">@DBVersion = 'C.0.8.54'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-117">@DBVersion = 'C.0.8.54'</span></span>|<span data-ttu-id="d1aa3-118">SQL Server 2005 SP2</span><span class="sxs-lookup"><span data-stu-id="d1aa3-118">SQL Server 2005 SP2</span></span>|  
|<span data-ttu-id="d1aa3-119">RS 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="d1aa3-119">RS 2005 SP1</span></span>|<span data-ttu-id="d1aa3-120">@DBVersion = 'C.0.8.43'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-120">@DBVersion = 'C.0.8.43'</span></span>|<span data-ttu-id="d1aa3-121">SQL Server 2005 SP1</span><span class="sxs-lookup"><span data-stu-id="d1aa3-121">SQL Server 2005 SP1</span></span>|  
|<span data-ttu-id="d1aa3-122">RS 2005 RTM</span><span class="sxs-lookup"><span data-stu-id="d1aa3-122">RS 2005 RTM</span></span>|<span data-ttu-id="d1aa3-123">@DBVersion = 'C.0.8.40'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-123">@DBVersion = 'C.0.8.40'</span></span>|<span data-ttu-id="d1aa3-124">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="d1aa3-124">SQL Server 2005</span></span>|  
|<span data-ttu-id="d1aa3-125">RS 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="d1aa3-125">RS 2000 SP2</span></span>|<span data-ttu-id="d1aa3-126">@DBVersion = 'C.0.6.54'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-126">@DBVersion = 'C.0.6.54'</span></span>|<span data-ttu-id="d1aa3-127">SQL Server 2000 SP2</span><span class="sxs-lookup"><span data-stu-id="d1aa3-127">SQL Server 2000 SP2</span></span>|  
|<span data-ttu-id="d1aa3-128">RS 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="d1aa3-128">RS 2000 SP1</span></span>|<span data-ttu-id="d1aa3-129">@DBVersion = 'C.0.6.51'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-129">@DBVersion = 'C.0.6.51'</span></span>|<span data-ttu-id="d1aa3-130">SQL Server 2000 SP1</span><span class="sxs-lookup"><span data-stu-id="d1aa3-130">SQL Server 2000 SP1</span></span>|  
|<span data-ttu-id="d1aa3-131">RS 2000 RTM</span><span class="sxs-lookup"><span data-stu-id="d1aa3-131">RS 2000 RTM</span></span>|<span data-ttu-id="d1aa3-132">@DBVersion = 'C.0.6.43'</span><span class="sxs-lookup"><span data-stu-id="d1aa3-132">@DBVersion = 'C.0.6.43'</span></span>|<span data-ttu-id="d1aa3-133">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="d1aa3-133">SQL Server 2000</span></span>|  
|<span data-ttu-id="d1aa3-134">Correctif logiciel</span><span class="sxs-lookup"><span data-stu-id="d1aa3-134">Hotfix</span></span>||<span data-ttu-id="d1aa3-135">Version applicable la plus proche</span><span class="sxs-lookup"><span data-stu-id="d1aa3-135">Closest applicable version</span></span>|  
  
 <span data-ttu-id="d1aa3-136">Pour une *Version* antérieure à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000, le paramètre HRESULT ACT_E_BAD_VERSION est retourné.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-136">For a *Version* prior to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 an HRESULT of ACT_E_BAD_VERSION is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1aa3-137">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="d1aa3-137">Return Value</span></span>  
 <span data-ttu-id="d1aa3-138">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-138">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="d1aa3-139">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-139">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="d1aa3-140">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="d1aa3-140">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1aa3-141">Spécifications</span><span class="sxs-lookup"><span data-stu-id="d1aa3-141">Requirements</span></span>  
 <span data-ttu-id="d1aa3-142">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1aa3-142">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1aa3-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d1aa3-143">See Also</span></span>  
 [<span data-ttu-id="d1aa3-144">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d1aa3-144">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
