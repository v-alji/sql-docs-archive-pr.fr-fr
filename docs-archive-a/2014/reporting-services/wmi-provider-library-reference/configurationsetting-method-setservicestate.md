---
title: SetServiceState, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetServiceState (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceState method
ms.assetid: 9e1ee42d-b388-4929-89c7-8741b956c3be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b4a29b3379fc1d312af42a1f5b1296ee35dcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706044"
---
# <a name="setservicestate-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b112d-102">Méthode SetServiceState (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b112d-102">SetServiceState Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b112d-103">Active ou désactive les services Web et Windows Report Server.</span><span class="sxs-lookup"><span data-stu-id="b112d-103">Turns the Report Server Windows and Web services on and off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b112d-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b112d-104">Syntax</span></span>  
  
```vb  
Public Sub SetServiceState(ByVal EnableWindowsService As Boolean, _  
    ByVal EnableWebService As Boolean, ByVal EnableReportManager As Boolean, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Boolean EnableWindowsService,  
    Boolean EnableWebService, Boolean EnableReportManager, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b112d-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b112d-105">Parameters</span></span>  
 <span data-ttu-id="b112d-106">*EnableWindowsService*</span><span class="sxs-lookup"><span data-stu-id="b112d-106">*EnableWindowsService*</span></span>  
 <span data-ttu-id="b112d-107">Valeur `Boolean` indiquant l'état du service Windows.</span><span class="sxs-lookup"><span data-stu-id="b112d-107">A `Boolean` value indicating the state of the Windows service.</span></span> <span data-ttu-id="b112d-108">La valeur `true` démarre le service Windows Report Server ; la valeur `false` arrête le service Windows.</span><span class="sxs-lookup"><span data-stu-id="b112d-108">A value of `true` starts the Report Server Windows service; a value of `false` stops the Windows service.</span></span>  
  
 <span data-ttu-id="b112d-109">*EnableWebService*</span><span class="sxs-lookup"><span data-stu-id="b112d-109">*EnableWebService*</span></span>  
 <span data-ttu-id="b112d-110">`Boolean`Valeur indiquant l’état du [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service Web.</span><span class="sxs-lookup"><span data-stu-id="b112d-110">A `Boolean` value indicating the state of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Web service.</span></span> <span data-ttu-id="b112d-111">La valeur `true` démarre le service Web Report Server ; la valeur `false` arrête le service Web.</span><span class="sxs-lookup"><span data-stu-id="b112d-111">A value of `true` starts the Report Server Web service; a value of `false` stops the Web service</span></span>  
  
 <span data-ttu-id="b112d-112">*EnableReportManager*</span><span class="sxs-lookup"><span data-stu-id="b112d-112">*EnableReportManager*</span></span>  
 <span data-ttu-id="b112d-113">Valeur `Boolean` indiquant l'état souhaité du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="b112d-113">A `Boolean` value indicating the desired state of the Report manager.</span></span>  
  
 <span data-ttu-id="b112d-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b112d-114">*HRESULT*</span></span>  
 <span data-ttu-id="b112d-115">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="b112d-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b112d-116">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b112d-116">Return Value</span></span>  
 <span data-ttu-id="b112d-117">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="b112d-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="b112d-118">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="b112d-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="b112d-119">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="b112d-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b112d-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b112d-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b112d-121">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b112d-121">Requirements</span></span>  
 <span data-ttu-id="b112d-122">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b112d-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b112d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b112d-123">See Also</span></span>  
 [<span data-ttu-id="b112d-124">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b112d-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
