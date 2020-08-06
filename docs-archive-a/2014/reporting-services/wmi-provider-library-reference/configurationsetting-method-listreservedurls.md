---
title: ListReservedURLs, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604357"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="057e3-102">Méthode ListReservedURLs (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="057e3-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="057e3-103">Répertorie les URL réservées pour toutes les applications sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="057e3-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="057e3-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="057e3-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="057e3-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="057e3-105">Parameters</span></span>  
 <span data-ttu-id="057e3-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="057e3-106">*Application[]*</span></span>  
 <span data-ttu-id="057e3-107">[out] Applications qui ont des réservations d'URL.</span><span class="sxs-lookup"><span data-stu-id="057e3-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="057e3-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="057e3-108">*UrlString[]*</span></span>  
 <span data-ttu-id="057e3-109">[out] URL réservées.</span><span class="sxs-lookup"><span data-stu-id="057e3-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="057e3-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="057e3-110">*Account[]*</span></span>  
 <span data-ttu-id="057e3-111">[out] Noms de comptes associés au compte pour les réservations d'URL.</span><span class="sxs-lookup"><span data-stu-id="057e3-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="057e3-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="057e3-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="057e3-113">[out] SID de comptes associés au compte pour les réservations d'URL.</span><span class="sxs-lookup"><span data-stu-id="057e3-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="057e3-114">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="057e3-114">*Length*</span></span>  
 <span data-ttu-id="057e3-115">[out] Longueur des tableaux retournés par la méthode.</span><span class="sxs-lookup"><span data-stu-id="057e3-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="057e3-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="057e3-116">*HRESULT*</span></span>  
 <span data-ttu-id="057e3-117">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="057e3-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="057e3-118">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="057e3-118">Return Value</span></span>  
 <span data-ttu-id="057e3-119">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="057e3-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="057e3-120">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="057e3-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="057e3-121">Notes</span><span class="sxs-lookup"><span data-stu-id="057e3-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="057e3-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="057e3-122">Requirements</span></span>  
 <span data-ttu-id="057e3-123">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="057e3-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="057e3-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="057e3-124">See Also</span></span>  
 [<span data-ttu-id="057e3-125">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="057e3-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
