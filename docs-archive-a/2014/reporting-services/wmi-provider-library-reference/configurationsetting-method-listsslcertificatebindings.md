---
title: ListSSLCertificateBindings, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListSSLCertificateBindings method
ms.assetid: d12d280c-9b6f-47a8-bcd9-34cde31c8886
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56b19a138dc95b94a20183909dd444c90b158b26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604351"
---
# <a name="listsslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a6fd7-102">Méthode ListSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a6fd7-102">ListSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a6fd7-103">Retourne la liste des certificats SSL installés sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-103">Returns a list of installed SSL certificates on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fd7-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a6fd7-104">Syntax</span></span>  
  
```vb  
Public Sub ListSSLCertificateBindings(ByVal LCID As Int32, ByRef Application() As String, _  
    ByRef CertificateHash() As String, ByRef IPAddresses() As String, ByRef Port() As Int32, _  
    ByRef Errors() As String, ByRef Length As Int32, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListSSLCertificateBindings(Int32 Lcid, out string[] Application,   
    out string[] CertificateHash,out string[] IPAddress,   
    out Int32[] Port, out string Errors,   
    out Int32 length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6fd7-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a6fd7-105">Parameters</span></span>  
 <span data-ttu-id="a6fd7-106">*LCID*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-106">*LCID*</span></span>  
 <span data-ttu-id="a6fd7-107">Paramètres régionaux à utiliser pour les messages d’erreur renvoyés.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-107">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="a6fd7-108">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-108">*Application[]*</span></span>  
 <span data-ttu-id="a6fd7-109">[out] Applications comportant des liaisons de certificat.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-109">[out] The applications that have certificate bindings.</span></span>  
  
 <span data-ttu-id="a6fd7-110">*CertificateHash[]*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-110">*CertificateHash[]*</span></span>  
 <span data-ttu-id="a6fd7-111">[out] Hachages pour les certificats.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-111">[out] The hashes for the certificates.</span></span>  
  
 <span data-ttu-id="a6fd7-112">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-112">*IPAddress[]*</span></span>  
 <span data-ttu-id="a6fd7-113">[out] Adresses IP des applications.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-113">[out] The IP address for the applications.</span></span>  
  
 <span data-ttu-id="a6fd7-114">*Port[]*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-114">*Port[]*</span></span>  
 <span data-ttu-id="a6fd7-115">[out] Numéro de port stocké dans la liaison dans rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-115">[out] The port number stored in the binding in rsreportserver.config.</span></span>  
  
 <span data-ttu-id="a6fd7-116">*Errors[]*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-116">*Errors[]*</span></span>  
 <span data-ttu-id="a6fd7-117">[out] Descriptions des erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-117">[out] The descriptions for errors that occurred.</span></span>  
  
 <span data-ttu-id="a6fd7-118">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-118">*Length*</span></span>  
 <span data-ttu-id="a6fd7-119">[out] Longueur du tableau retourné par la méthode.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-119">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="a6fd7-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a6fd7-120">*HRESULT*</span></span>  
 <span data-ttu-id="a6fd7-121">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6fd7-122">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="a6fd7-122">Return Value</span></span>  
 <span data-ttu-id="a6fd7-123">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a6fd7-124">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="a6fd7-125">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="a6fd7-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6fd7-126">Notes</span><span class="sxs-lookup"><span data-stu-id="a6fd7-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6fd7-127">Spécifications</span><span class="sxs-lookup"><span data-stu-id="a6fd7-127">Requirements</span></span>  
 <span data-ttu-id="a6fd7-128">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6fd7-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fd7-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6fd7-129">See Also</span></span>  
 [<span data-ttu-id="a6fd7-130">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="a6fd7-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
