---
title: ListIPAddresses, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604360"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7b8a6-102">Méthode ListIPAddresses (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="7b8a6-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7b8a6-103">Répertorie les adresses IP de l'ordinateur serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8a6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="7b8a6-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b8a6-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="7b8a6-105">Parameters</span></span>  
 <span data-ttu-id="7b8a6-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="7b8a6-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="7b8a6-107">[out] La liste d'adresses IP de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="7b8a6-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="7b8a6-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="7b8a6-109">[out] La version des adresses IP.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="7b8a6-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="7b8a6-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="7b8a6-111">[out] Indique si les adresses IP sont compatibles DHCP.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="7b8a6-112">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="7b8a6-112">*Length*</span></span>  
 <span data-ttu-id="7b8a6-113">[out] Longueur du tableau retourné par la méthode.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="7b8a6-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="7b8a6-114">*HRESULT*</span></span>  
 <span data-ttu-id="7b8a6-115">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b8a6-116">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="7b8a6-116">Return Value</span></span>  
 <span data-ttu-id="7b8a6-117">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="7b8a6-118">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b8a6-119">Notes</span><span class="sxs-lookup"><span data-stu-id="7b8a6-119">Remarks</span></span>  
 <span data-ttu-id="7b8a6-120">Les chaînes*IPVersion* sont V4, V6.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="7b8a6-121">Si *IsDhcpEnabled* a `True` la la, l' *adresse IP* est dynamique.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="7b8a6-122">Elle ne doit pas être utilisée pour les liaisons SSL.</span><span class="sxs-lookup"><span data-stu-id="7b8a6-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b8a6-123">Spécifications</span><span class="sxs-lookup"><span data-stu-id="7b8a6-123">Requirements</span></span>  
 <span data-ttu-id="7b8a6-124">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b8a6-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8a6-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b8a6-125">See Also</span></span>  
 [<span data-ttu-id="7b8a6-126">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7b8a6-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
