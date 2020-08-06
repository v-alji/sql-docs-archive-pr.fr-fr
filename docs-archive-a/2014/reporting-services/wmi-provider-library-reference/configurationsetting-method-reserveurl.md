---
title: ReserveURL, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706075"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c8c92-102">Méthode ReserveURL (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c8c92-102">ReserveURL Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c8c92-103">Ajoute une réservation d'URL pour une application donnée.</span><span class="sxs-lookup"><span data-stu-id="c8c92-103">Adds a URL reservation for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c92-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c8c92-104">Syntax</span></span>  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8c92-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c8c92-105">Parameters</span></span>  
 <span data-ttu-id="c8c92-106">*Application*</span><span class="sxs-lookup"><span data-stu-id="c8c92-106">*Application*</span></span>  
 <span data-ttu-id="c8c92-107">Nom de l'application pour laquelle l'URL doit être réservée.</span><span class="sxs-lookup"><span data-stu-id="c8c92-107">The name of application to reserve the URL for.</span></span>  
  
 <span data-ttu-id="c8c92-108">*URLString*</span><span class="sxs-lookup"><span data-stu-id="c8c92-108">*URLString*</span></span>  
 <span data-ttu-id="c8c92-109">URL pour la réservation.</span><span class="sxs-lookup"><span data-stu-id="c8c92-109">The URL for the reservation.</span></span>  
  
 <span data-ttu-id="c8c92-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="c8c92-110">*lcid*</span></span>  
 <span data-ttu-id="c8c92-111">Paramètres régionaux à utiliser pour les messages d'erreur retournés.</span><span class="sxs-lookup"><span data-stu-id="c8c92-111">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="c8c92-112">*Error*</span><span class="sxs-lookup"><span data-stu-id="c8c92-112">*Error*</span></span>  
 <span data-ttu-id="c8c92-113">[out] Description de l'erreur qui s'est produite.</span><span class="sxs-lookup"><span data-stu-id="c8c92-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="c8c92-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="c8c92-114">*HRESULT*</span></span>  
 <span data-ttu-id="c8c92-115">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="c8c92-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8c92-116">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="c8c92-116">Return Value</span></span>  
 <span data-ttu-id="c8c92-117">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="c8c92-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="c8c92-118">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="c8c92-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8c92-119">Notes</span><span class="sxs-lookup"><span data-stu-id="c8c92-119">Remarks</span></span>  
 <span data-ttu-id="c8c92-120">La propriété*UrlString* n'inclut pas le nom de répertoire virtuel.</span><span class="sxs-lookup"><span data-stu-id="c8c92-120">*UrlString* does not include the virtual directory name.</span></span> <span data-ttu-id="c8c92-121">La méthode [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) est fournie à cette fin.</span><span class="sxs-lookup"><span data-stu-id="c8c92-121">The [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) method is provided for that purpose.</span></span>  
  
 <span data-ttu-id="c8c92-122">Des réservations d'URL sont créées pour le compte de service Windows actuel.</span><span class="sxs-lookup"><span data-stu-id="c8c92-122">URL reservations are created for the current windows service account.</span></span> <span data-ttu-id="c8c92-123">La modification du compte de service Windows nécessite la mise à jour manuelle de toutes les réservations d'URL.</span><span class="sxs-lookup"><span data-stu-id="c8c92-123">Changing the windows service account requires updating all the URL reservations manually.</span></span>  
  
 <span data-ttu-id="c8c92-124">Cette méthode entraîne un recyclage forcé de tous les domaines d'application.</span><span class="sxs-lookup"><span data-stu-id="c8c92-124">This method causes all application domains to hard recycle.</span></span> <span data-ttu-id="c8c92-125">Les domaines d'application sont redémarrés une fois cette opération terminée.</span><span class="sxs-lookup"><span data-stu-id="c8c92-125">Application domains are restarted after this operation is complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c92-126">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c8c92-126">Requirements</span></span>  
 <span data-ttu-id="c8c92-127">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c92-127">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c92-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c8c92-128">See Also</span></span>  
 [<span data-ttu-id="c8c92-129">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c8c92-129">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
