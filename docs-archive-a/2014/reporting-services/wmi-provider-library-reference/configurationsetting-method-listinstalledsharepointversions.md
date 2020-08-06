---
title: ListInstalledSharePointVersions, méthode (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListInstalledSharePointVersions method
ms.assetid: 8f0a5e9f-23f1-41e5-9a90-dfec19ef1df7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ceee23876461cf31cbd265ea39ae015ddcbc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604362"
---
# <a name="listinstalledsharepointversions-method-wmi"></a><span data-ttu-id="997b2-102">Méthode ListInstalledSharePointVersions (WMI)</span><span class="sxs-lookup"><span data-stu-id="997b2-102">ListInstalledSharePointVersions Method (WMI)</span></span>
  <span data-ttu-id="997b2-103">Retourne un ensemble de jetons qui représentent les versions de Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installées sur le même ordinateur que le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="997b2-103">Returns a set of tokens that represent the versions of Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] that are installed on the same computer as the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997b2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="997b2-104">Syntax</span></span>  
  
```vb  
Public Sub ListInstalledSharePointVersions(ByRef VersionTokens() _  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] VersionTokens,   
    out Int32 Length, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="997b2-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="997b2-105">Parameters</span></span>  
 <span data-ttu-id="997b2-106">*VersionTokens[]*</span><span class="sxs-lookup"><span data-stu-id="997b2-106">*VersionTokens[]*</span></span>  
 <span data-ttu-id="997b2-107">[out] Tableau qui contient les jetons qui représentent la version d'un produit ou d'une technologie SharePoint compatible avec le serveur de rapports installé.</span><span class="sxs-lookup"><span data-stu-id="997b2-107">[out] An array that contains the tokens that represent the version of a SharePoint product or technology that is compatible with the installed report server.</span></span>  
  
 <span data-ttu-id="997b2-108">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="997b2-108">*Length*</span></span>  
 <span data-ttu-id="997b2-109">[out] Longueur du tableau de jetons de la version.</span><span class="sxs-lookup"><span data-stu-id="997b2-109">[out] The length of the version tokens array.</span></span>  
  
 <span data-ttu-id="997b2-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="997b2-110">*HRESULT*</span></span>  
 <span data-ttu-id="997b2-111">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="997b2-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="997b2-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="997b2-112">Return Value</span></span>  
 <span data-ttu-id="997b2-113">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="997b2-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="997b2-114">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="997b2-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="997b2-115">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="997b2-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="997b2-116">Notes</span><span class="sxs-lookup"><span data-stu-id="997b2-116">Remarks</span></span>  
 <span data-ttu-id="997b2-117">Chaque jeton retourné représente une version de [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] ou [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] compatible avec le serveur de rapports actuellement installé.</span><span class="sxs-lookup"><span data-stu-id="997b2-117">Each token that is returned represents a version of [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] or [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] that is compatible with the currently installed report server.</span></span> <span data-ttu-id="997b2-118">Si une version particulière de SharePoint est compatible avec les versions SharePoint précédentes, les jetons pour chaque version SharePoint compatible sont retournés.</span><span class="sxs-lookup"><span data-stu-id="997b2-118">If a particular version of SharePoint is compatible with previous SharePoint versions, tokens for each compatible SharePoint version are returned.</span></span>  
  
 <span data-ttu-id="997b2-119">Voici un tableau des jetons SharePoint retournés.</span><span class="sxs-lookup"><span data-stu-id="997b2-119">The following is a table of the SharePoint tokens that are returned.</span></span>  
  
|<span data-ttu-id="997b2-120">**Jetons de version**</span><span class="sxs-lookup"><span data-stu-id="997b2-120">**Version Tokens**</span></span>|<span data-ttu-id="997b2-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="997b2-121">**Description**</span></span>|  
|------------------------|---------------------|  
|<span data-ttu-id="997b2-122">WSS_V2_Compatible</span><span class="sxs-lookup"><span data-stu-id="997b2-122">WSS_V2_Compatible</span></span>|<span data-ttu-id="997b2-123">Une installation de [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatible avec [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0 est installée.</span><span class="sxs-lookup"><span data-stu-id="997b2-123">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 2.0.</span></span>|  
|<span data-ttu-id="997b2-124">WSS_V3_Compatible</span><span class="sxs-lookup"><span data-stu-id="997b2-124">WSS_V3_Compatible</span></span>|<span data-ttu-id="997b2-125">Une installation [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatible avec [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0 est installée.</span><span class="sxs-lookup"><span data-stu-id="997b2-125">A [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with [!INCLUDE[winSPServ](../../includes/winspserv-md.md)] 3.0.</span></span>|  
|<span data-ttu-id="997b2-126">WSS_V4_Compatible</span><span class="sxs-lookup"><span data-stu-id="997b2-126">WSS_V4_Compatible</span></span>|<span data-ttu-id="997b2-127">Une installation [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] compatible avec Office 14 est installée.</span><span class="sxs-lookup"><span data-stu-id="997b2-127">A [!INCLUDE[SPF2010](../../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] installation is installed that is compatible with Office 14.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="997b2-128">Spécifications</span><span class="sxs-lookup"><span data-stu-id="997b2-128">Requirements</span></span>  
 <span data-ttu-id="997b2-129">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="997b2-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997b2-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="997b2-130">See Also</span></span>  
 [<span data-ttu-id="997b2-131">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="997b2-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
