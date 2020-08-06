---
title: ListSSLCertificates, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificates method
ms.assetid: 88cd0936-b202-4ab8-90f2-d9c3f66d37f4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a5ced8371817adc44bbbc89400dc83e0dfccef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604348"
---
# <a name="listsslcertificates-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e5313-102">Méthode ListSSLCertificates (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e5313-102">ListSSLCertificates Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e5313-103">Retourne la liste des certificats installés sur l'ordinateur serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e5313-103">Returns a list of certificates on the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5313-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e5313-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding (ByRef CertificateHash() as String, _  
    ByRef CertName() as String, ByRef HostName() as String, ByRef Length as Int32, _   
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListSSLCertificates(out string[] CertificateHash,   
    out string[] CertName, out string[] Hostname, out Int32 length,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5313-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e5313-105">Parameters</span></span>  
 <span data-ttu-id="e5313-106">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="e5313-106">*CertificateHash[]*</span></span>  
 <span data-ttu-id="e5313-107">[out] Hachages des certificats.</span><span class="sxs-lookup"><span data-stu-id="e5313-107">[out] The certificate hashes.</span></span>  
  
 <span data-ttu-id="e5313-108">*CertName[]*</span><span class="sxs-lookup"><span data-stu-id="e5313-108">*CertName[]*</span></span>  
 <span data-ttu-id="e5313-109">[out] Noms des certificats.</span><span class="sxs-lookup"><span data-stu-id="e5313-109">[out] Names of the certificate.</span></span>  
  
 <span data-ttu-id="e5313-110">*HostName[]*</span><span class="sxs-lookup"><span data-stu-id="e5313-110">*HostName[]*</span></span>  
 <span data-ttu-id="e5313-111">[out] Noms d'hôtes des certificats.</span><span class="sxs-lookup"><span data-stu-id="e5313-111">[out] The host names for the certificates.</span></span>  
  
 <span data-ttu-id="e5313-112">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="e5313-112">*Length*</span></span>  
 <span data-ttu-id="e5313-113">[out] Représente la longueur des tableaux *CertificateHash*, *CertName* et *HostName* .</span><span class="sxs-lookup"><span data-stu-id="e5313-113">[out] Represents the length of the *CertificateHash*, *CertName* and *HostName* arrays.</span></span>  
  
 <span data-ttu-id="e5313-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e5313-114">*HRESULT*</span></span>  
 <span data-ttu-id="e5313-115">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="e5313-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5313-116">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="e5313-116">Return Value</span></span>  
 <span data-ttu-id="e5313-117">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="e5313-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e5313-118">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="e5313-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5313-119">Notes</span><span class="sxs-lookup"><span data-stu-id="e5313-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5313-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e5313-120">Requirements</span></span>  
 <span data-ttu-id="e5313-121">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5313-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5313-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5313-122">See Also</span></span>  
 [<span data-ttu-id="e5313-123">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e5313-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
