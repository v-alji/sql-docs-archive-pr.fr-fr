---
title: CreateSSLCertificateBinding, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604379"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c1096-102">Méthode CreateSSLCertificateBinding (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c1096-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c1096-103">Crée une liaison de certificat SSL.</span><span class="sxs-lookup"><span data-stu-id="c1096-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1096-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c1096-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1096-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c1096-105">Parameters</span></span>  
 <span data-ttu-id="c1096-106">*Application*</span><span class="sxs-lookup"><span data-stu-id="c1096-106">*Application*</span></span>  
 <span data-ttu-id="c1096-107">Nom de l'application pour laquelle la liaison de certificat doit être créée.</span><span class="sxs-lookup"><span data-stu-id="c1096-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="c1096-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="c1096-108">*CertificateHash*</span></span>  
 <span data-ttu-id="c1096-109">Hachage du certificat.</span><span class="sxs-lookup"><span data-stu-id="c1096-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="c1096-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="c1096-110">*IPAddress*</span></span>  
 <span data-ttu-id="c1096-111">Adresse IP de l'application.</span><span class="sxs-lookup"><span data-stu-id="c1096-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="c1096-112">*Port*</span><span class="sxs-lookup"><span data-stu-id="c1096-112">*Port*</span></span>  
 <span data-ttu-id="c1096-113">Port SSL associé à la liaison.</span><span class="sxs-lookup"><span data-stu-id="c1096-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="c1096-114">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="c1096-114">*Lcid*</span></span>  
 <span data-ttu-id="c1096-115">Paramètres régionaux à utiliser pour les messages d'erreur retournés.</span><span class="sxs-lookup"><span data-stu-id="c1096-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="c1096-116">*Error*</span><span class="sxs-lookup"><span data-stu-id="c1096-116">*Error*</span></span>  
 <span data-ttu-id="c1096-117">[out] Description des erreurs qui se sont produites.</span><span class="sxs-lookup"><span data-stu-id="c1096-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="c1096-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c1096-118">*HRESULT*</span></span>  
 <span data-ttu-id="c1096-119">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="c1096-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1096-120">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c1096-120">Return Value</span></span>  
 <span data-ttu-id="c1096-121">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="c1096-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c1096-122">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="c1096-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1096-123">Notes</span><span class="sxs-lookup"><span data-stu-id="c1096-123">Remarks</span></span>  
 <span data-ttu-id="c1096-124">Cette méthode ajoute une liaison à rsreportserver.config pour l'application.</span><span class="sxs-lookup"><span data-stu-id="c1096-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="c1096-125">Si aucune liaison n'existe déjà dans HTTP.SYS, elle est créée ici.</span><span class="sxs-lookup"><span data-stu-id="c1096-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="c1096-126">Avant de créer la liaison, l'appel de méthode examine les réservations d'URL pour l'application spécifiée afin de déterminer si la liaison de certificat SSL est valide.</span><span class="sxs-lookup"><span data-stu-id="c1096-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="c1096-127">Les conditions suivantes sont validées et peuvent provoquer des erreurs :</span><span class="sxs-lookup"><span data-stu-id="c1096-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="c1096-128">Le certificat n'existe pas.</span><span class="sxs-lookup"><span data-stu-id="c1096-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="c1096-129">L'adresse IP spécifiée ne correspond à aucune adresse IP de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c1096-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="c1096-130">L’adresse IP spécifiée est une adresse IP DHCP (modifications régulières) ; utilisez plutôt l’adresse IP générique (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="c1096-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="c1096-131">L'adresse IP spécifiée ne correspond pas à l'adresse IP des réservations d'URL ET il n'existe pas de réservation d'URL générique ni de nom d'hôte.</span><span class="sxs-lookup"><span data-stu-id="c1096-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="c1096-132">Une réservation d'URL qui spécifie un nom d'hôte existe, mais le nom d'hôte ne correspond pas au nom d'hôte de certificat.</span><span class="sxs-lookup"><span data-stu-id="c1096-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1096-133">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c1096-133">Requirements</span></span>  
 <span data-ttu-id="c1096-134">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1096-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1096-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1096-135">See Also</span></span>  
 [<span data-ttu-id="c1096-136">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c1096-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
