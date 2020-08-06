---
title: RemoveSSLCertificateBindings, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveSSLCertificateBindings method
ms.assetid: b8b484c9-04c4-4ae9-980e-67bbe5aa8481
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d42d17d9c92f2e100a7800e607536ff6c7eab891
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704767"
---
# <a name="removesslcertificatebindings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="479ed-102">Méthode RemoveSSLCertificateBindings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="479ed-102">RemoveSSLCertificateBindings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="479ed-103">Supprime une liaison de certificat SSL.</span><span class="sxs-lookup"><span data-stu-id="479ed-103">Removes an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479ed-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="479ed-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveSSLCertificateBindings(string Application,  
    string CertificateHash, string IPAddress, Int32 Port, Int32 Lcid,  
    out string Error, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="479ed-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="479ed-105">Parameters</span></span>  
 <span data-ttu-id="479ed-106">*Application*</span><span class="sxs-lookup"><span data-stu-id="479ed-106">*Application*</span></span>  
 <span data-ttu-id="479ed-107">Nom de l'application pour laquelle la liaison de certificat doit être supprimée.</span><span class="sxs-lookup"><span data-stu-id="479ed-107">The name of application for which the certificate binding should be removed.</span></span>  
  
 <span data-ttu-id="479ed-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="479ed-108">*CertificateHash*</span></span>  
 <span data-ttu-id="479ed-109">Hachage du certificat.</span><span class="sxs-lookup"><span data-stu-id="479ed-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="479ed-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="479ed-110">*IPAddress*</span></span>  
 <span data-ttu-id="479ed-111">Adresse IP de l'application.</span><span class="sxs-lookup"><span data-stu-id="479ed-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="479ed-112">*Port*</span><span class="sxs-lookup"><span data-stu-id="479ed-112">*Port*</span></span>  
 <span data-ttu-id="479ed-113">Port SSL associé à la liaison.</span><span class="sxs-lookup"><span data-stu-id="479ed-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="479ed-114">*lcid*</span><span class="sxs-lookup"><span data-stu-id="479ed-114">*lcid*</span></span>  
 <span data-ttu-id="479ed-115">Paramètres régionaux à utiliser pour les messages d’erreur renvoyés.</span><span class="sxs-lookup"><span data-stu-id="479ed-115">The locale to use for the error messages that are returned.</span></span>  
  
 <span data-ttu-id="479ed-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="479ed-116">*Error*</span></span>  
 <span data-ttu-id="479ed-117">[out] Description de l'erreur qui s'est produite.</span><span class="sxs-lookup"><span data-stu-id="479ed-117">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="479ed-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="479ed-118">*HRESULT*</span></span>  
 <span data-ttu-id="479ed-119">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="479ed-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="479ed-120">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="479ed-120">Return Value</span></span>  
 <span data-ttu-id="479ed-121">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="479ed-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="479ed-122">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="479ed-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="479ed-123">Notes</span><span class="sxs-lookup"><span data-stu-id="479ed-123">Remarks</span></span>  
 <span data-ttu-id="479ed-124">Cette méthode supprime la liaison spécifique du fichier rsreportserver.config et éventuellement HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="479ed-124">This method removes the specific binding from the rsreportserver.config file and optionally HTTP.SYS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479ed-125">Spécifications</span><span class="sxs-lookup"><span data-stu-id="479ed-125">Requirements</span></span>  
 <span data-ttu-id="479ed-126">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479ed-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479ed-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="479ed-127">See Also</span></span>  
 [<span data-ttu-id="479ed-128">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="479ed-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
