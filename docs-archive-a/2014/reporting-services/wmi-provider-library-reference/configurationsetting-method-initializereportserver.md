---
title: InitializeReportServer, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- InitializeReportServer (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- InitializeReportServer method
ms.assetid: 0304acc2-1fd7-437b-94d9-1c1073dd3ca4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6a8e44a98320ca2c9add6a1b6eef9362eef7731
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604366"
---
# <a name="initializereportserver-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="44c54-102">Méthode InitializeReportServer (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="44c54-102">InitializeReportServer Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="44c54-103">Initialise l'instance du service de rapports spécifiée.</span><span class="sxs-lookup"><span data-stu-id="44c54-103">Initializes the specified report service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c54-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="44c54-104">Syntax</span></span>  
  
```vb  
Public Sub InitializeReportServer(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void InitializeReportServer(string InstallationID,   
    out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c54-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="44c54-105">Parameters</span></span>  
 <span data-ttu-id="44c54-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="44c54-106">*InstallationID*</span></span>  
 <span data-ttu-id="44c54-107">Chaîne utilisée pour chiffrer la clé de chiffrement avant qu'elle soit retournée.</span><span class="sxs-lookup"><span data-stu-id="44c54-107">A string used to encrypt the encryption key before it is returned.</span></span>  
  
 <span data-ttu-id="44c54-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="44c54-108">*HRESULT*</span></span>  
 <span data-ttu-id="44c54-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="44c54-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="44c54-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="44c54-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="44c54-111">[out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.</span><span class="sxs-lookup"><span data-stu-id="44c54-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44c54-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="44c54-112">Return Value</span></span>  
 <span data-ttu-id="44c54-113">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="44c54-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="44c54-114">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="44c54-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="44c54-115">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="44c54-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44c54-116">Notes</span><span class="sxs-lookup"><span data-stu-id="44c54-116">Remarks</span></span>  
 <span data-ttu-id="44c54-117">Lorsque cette méthode est appelée, la clé de chiffrement qui accède aux informations sécurisées de la base de données du serveur de rapports est chiffrée à l'aide de la clé publique du serveur de rapports identifiée par *InstallationID*.</span><span class="sxs-lookup"><span data-stu-id="44c54-117">When this method is called, the encryption key that accesses the report server database secure information is encrypted using the public key of the report server identified by *InstallationID*.</span></span>  
  
 <span data-ttu-id="44c54-118">La clé publique du serveur de rapports spécifiée doit au préalable avoir été écrite dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="44c54-118">The specified report server's public key must have previously been written into the report server database.</span></span>  
  
 <span data-ttu-id="44c54-119">La méthode *InitializeReportServer* doit être appelée contre un serveur de rapports qui a déjà accès aux informations sécurisées, afin qu'il puisse déchiffrer la clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="44c54-119">The *InitializeReportServer* method must be called against a report server that already has access to the secure information so that it can decrypt the encryption key.</span></span> <span data-ttu-id="44c54-120">La clé de chiffrement chiffrée résultante est ensuite stockée dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="44c54-120">The resulting encrypted encryption key is then stored in the report server database.</span></span>  
  
 <span data-ttu-id="44c54-121">Si la propriété [IsInitialized](configurationsetting-property-isinitialized.md) du serveur de rapports a la valeur `true` lorsque la méthode InitializeReportServer est appelée, la méthode retourne la valeur Success sans essayer de chiffrer la clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="44c54-121">If the report server's [IsInitialized](configurationsetting-property-isinitialized.md) property is set to `true` when the InitializeReportServer method is called, the method returns success without trying to encrypt the encryption key.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c54-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="44c54-122">Requirements</span></span>  
 <span data-ttu-id="44c54-123">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c54-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c54-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44c54-124">See Also</span></span>  
 [<span data-ttu-id="44c54-125">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="44c54-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
