---
title: SetVirtualDirectory, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- SetVirtualDirectory method
ms.assetid: 1a25cb1d-38d5-401a-970b-87b642a780e4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7f45181f3f6a791f5cb64a7519285b6d2a87dd36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706040"
---
# <a name="setvirtualdirectory-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="fa169-102">Méthode SetVirtualDirectory (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="fa169-102">SetVirtualDirectory Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="fa169-103">Définit le nom du répertoire virtuel pour une application donnée.</span><span class="sxs-lookup"><span data-stu-id="fa169-103">Sets the name of the virtual directory for a given application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa169-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="fa169-104">Syntax</span></span>  
  
```vb  
Public Sub SetVirtualDirectory(ByVal Application As String, _  
    ByVal VirtualDirectory As String, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetVirtualDirectory(string Application, string VirtualDirectory,   
       int Lcid,out string Error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa169-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fa169-105">Parameters</span></span>  
 <span data-ttu-id="fa169-106">*Application*</span><span class="sxs-lookup"><span data-stu-id="fa169-106">*Application*</span></span>  
 <span data-ttu-id="fa169-107">Nom de l'application pour laquelle définir le répertoire virtuel.</span><span class="sxs-lookup"><span data-stu-id="fa169-107">The name of application for which to set the virtual directory.</span></span>  
  
 <span data-ttu-id="fa169-108">*VirtualDirectory*</span><span class="sxs-lookup"><span data-stu-id="fa169-108">*VirtualDirectory*</span></span>  
 <span data-ttu-id="fa169-109">Nom du répertoire virtuel.</span><span class="sxs-lookup"><span data-stu-id="fa169-109">The name of the virtual directory.</span></span>  
  
 <span data-ttu-id="fa169-110">*lcid*</span><span class="sxs-lookup"><span data-stu-id="fa169-110">*lcid*</span></span>  
 <span data-ttu-id="fa169-111">ID de paramètres régionaux du répertoire virtuel.</span><span class="sxs-lookup"><span data-stu-id="fa169-111">The locale id for the virtual directory.</span></span>  
  
 <span data-ttu-id="fa169-112">*Error*</span><span class="sxs-lookup"><span data-stu-id="fa169-112">*Error*</span></span>  
 <span data-ttu-id="fa169-113">[out] Description de l'erreur qui s'est produite.</span><span class="sxs-lookup"><span data-stu-id="fa169-113">[out] The description of the error that occurred.</span></span>  
  
 <span data-ttu-id="fa169-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="fa169-114">*HRESULT*</span></span>  
 <span data-ttu-id="fa169-115">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="fa169-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa169-116">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="fa169-116">Return Value</span></span>  
 <span data-ttu-id="fa169-117">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="fa169-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="fa169-118">La valeur 0 indique que l'appel de la méthode a abouti ; un code d'erreur indique que l'appel n'a pas abouti.</span><span class="sxs-lookup"><span data-stu-id="fa169-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa169-119">Notes</span><span class="sxs-lookup"><span data-stu-id="fa169-119">Remarks</span></span>  
 <span data-ttu-id="fa169-120">Une application ne peut avoir qu'un seul nom de répertoire virtuel pour toutes les réservations d'URL.</span><span class="sxs-lookup"><span data-stu-id="fa169-120">An application can have only one virtual directory name for all URL reservations.</span></span>  
  
 <span data-ttu-id="fa169-121">VirtualDirectory doit être conforme aux conventions d'affectation des noms pour les répertoires virtuels.</span><span class="sxs-lookup"><span data-stu-id="fa169-121">VirtualDirectory must conform to naming conventions for virtual directories.</span></span> <span data-ttu-id="fa169-122">VirtualDirectory ne doit pas être une chaîne vide ou contenant uniquement un espace.</span><span class="sxs-lookup"><span data-stu-id="fa169-122">VirtualDirectory must not be empty string or blank.</span></span>  
  
 <span data-ttu-id="fa169-123">Met à jour la valeur de l'élément \Configuration\URLReservations\Application\VirtualDirectory.</span><span class="sxs-lookup"><span data-stu-id="fa169-123">Updates the value of the \Configuration\URLReservations\Application\VirtualDirectory element.</span></span> <span data-ttu-id="fa169-124">Réussit même si aucune réservation d'URL n'a encore été créée.</span><span class="sxs-lookup"><span data-stu-id="fa169-124">Succeeds even if no URL reservations have been created yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa169-125">Spécifications</span><span class="sxs-lookup"><span data-stu-id="fa169-125">Requirements</span></span>  
 <span data-ttu-id="fa169-126">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa169-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa169-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fa169-127">See Also</span></span>  
 [<span data-ttu-id="fa169-128">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="fa169-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
