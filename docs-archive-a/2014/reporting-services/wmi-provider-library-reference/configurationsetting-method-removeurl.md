---
title: RemoveURL, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RemoveURL method
ms.assetid: 3d98bd97-e152-48ce-ab1c-bd2c4f8b7fe9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3a32989e8ce8986b785e829d8cc7fcf58fbbf240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610964"
---
# <a name="removeurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b1341-102">Méthode RemoveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b1341-102">RemoveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b1341-103">Supprime une URL réservée pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b1341-103">Removes a URL reserved for the report server.</span></span> <span data-ttu-id="b1341-104">Si plusieurs URL doivent être supprimées, elles doivent l'être l'une après l'autre en appelant cette API.</span><span class="sxs-lookup"><span data-stu-id="b1341-104">If there are multiple URLs that need to be removed, this must be done one by one calling this API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1341-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b1341-105">Syntax</span></span>  
  
```vb  
Public Sub RemoveURL(ByVal Application As String, _  
    ByVal UrlString As String, ByVal Lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void RemoveURL(string Application, string UrlString, int Lcid,   
    out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1341-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b1341-106">Parameters</span></span>  
 <span data-ttu-id="b1341-107">*Application*</span><span class="sxs-lookup"><span data-stu-id="b1341-107">*Application*</span></span>  
 <span data-ttu-id="b1341-108">Nom de l'application pour laquelle supprimer la réservation.</span><span class="sxs-lookup"><span data-stu-id="b1341-108">The name of application for which to remove the reservation.</span></span>  
  
 <span data-ttu-id="b1341-109">*URLString*</span><span class="sxs-lookup"><span data-stu-id="b1341-109">*URLString*</span></span>  
 <span data-ttu-id="b1341-110">URL pour la réservation.</span><span class="sxs-lookup"><span data-stu-id="b1341-110">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="b1341-111">*lcid*</span><span class="sxs-lookup"><span data-stu-id="b1341-111">*lcid*</span></span>  
 <span data-ttu-id="b1341-112">Paramètres régionaux à utiliser pour les messages d'erreur retournés.</span><span class="sxs-lookup"><span data-stu-id="b1341-112">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="b1341-113">*Error*</span><span class="sxs-lookup"><span data-stu-id="b1341-113">*Error*</span></span>  
 <span data-ttu-id="b1341-114">[out] Description de l'erreur qui s'est produite.</span><span class="sxs-lookup"><span data-stu-id="b1341-114">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="b1341-115">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b1341-115">*HRESULT*</span></span>  
 <span data-ttu-id="b1341-116">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="b1341-116">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1341-117">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b1341-117">Return Value</span></span>  
 <span data-ttu-id="b1341-118">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="b1341-118">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="b1341-119">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="b1341-119">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1341-120">Notes</span><span class="sxs-lookup"><span data-stu-id="b1341-120">Remarks</span></span>  
 <span data-ttu-id="b1341-121">*UrlString* n’inclut pas le nom du répertoire virtuel. La [méthode SetVirtualDirectory &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) est fournie à cet effet.</span><span class="sxs-lookup"><span data-stu-id="b1341-121">*UrlString* does not include the Virtual Directory name - the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="b1341-122">Avant d’appeler la méthode [ReserveURL](configurationsetting-method-reserveurl.md) , vous devez fournir une valeur pour la propriété de configuration VirtualDirectory du paramètre *Application* .</span><span class="sxs-lookup"><span data-stu-id="b1341-122">Before calling the [ReserveURL](configurationsetting-method-reserveurl.md) method, you must supply a value for the VirtualDirectory configuration property for the *Application* parameter.</span></span> <span data-ttu-id="b1341-123">Utilisez la [méthode SetVirtualDirectory &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) pour définir la propriété VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="b1341-123">Use the [SetVirtualDirectory Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setvirtualdirectory.md) method to set the VirtualDirectory property.</span></span>  
  
 <span data-ttu-id="b1341-124">Si un certificat SSL a été fourni par [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et qu'aucune autre URL n'en a besoin, il est supprimé.</span><span class="sxs-lookup"><span data-stu-id="b1341-124">If an SSL Certificate was provisioned by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and no other URLs need it, it is removed.</span></span>  
  
 <span data-ttu-id="b1341-125">Cette méthode entraîne un recyclage et un arrêt forcés de tous les domaines d'application autres que de configuration au cours de cette opération ; les domaines d'application sont redémarrés une fois cette opération terminée.</span><span class="sxs-lookup"><span data-stu-id="b1341-125">This method causes all non-configuration app domains to hard recycle and stop during this operation; app domains are restarted after this operation complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1341-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b1341-126">Requirements</span></span>  
 <span data-ttu-id="b1341-127">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1341-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1341-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1341-128">See Also</span></span>  
 [<span data-ttu-id="b1341-129">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b1341-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
