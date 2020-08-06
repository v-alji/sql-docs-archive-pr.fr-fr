---
title: SetExtendedProtectionSettings, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d8e7232-42f4-41b6-98eb-c856f6c85d8c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ee937747b74bcf8d53012721b4be5bfca04185df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706060"
---
# <a name="setextendedprotectionsettings-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="3b182-102">Méthode SetExtendedProtectionSettings (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="3b182-102">SetExtendedProtectionSettings Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="3b182-103">La méthode SetExtendedProtectionSettings sert à définir les propriétés RSWindowsExtendedProtectionLevel et RSWindowsExtendedProtectionScenario dans le fichier de configuration [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (RSReportServer.config).</span><span class="sxs-lookup"><span data-stu-id="3b182-103">The SetExtendedProtectionSettings method is used to set the RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration file RSReportServer.config.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b182-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="3b182-104">Syntax</span></span>  
  
```vb  
Public Sub SetExtendedProtectionSettings( _  
        ByVal ExtendedProtectionLevel As String, _  
        ByVal ExtendedProtectionScenario As String, _  
        ByRef Warnings() As String, _  
        ByRef Length As Int32, _  
        ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetExtendedProtectionSettings(  
            string ExtendedProtectionLevel,  
            string ExtendedProtectionScenario,  
            out string[] Warnings,  
            out Int32 Length,  
            out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b182-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="3b182-105">Parameters</span></span>  
 <span data-ttu-id="3b182-106">*ExtendedProtectionLevel*</span><span class="sxs-lookup"><span data-stu-id="3b182-106">*ExtendedProtectionLevel*</span></span>  
 <span data-ttu-id="3b182-107">Définit RSWindowsExtendedProtectionLevel dans le fichier RSRreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="3b182-107">Sets the RSWindowsExtendedProtectionLevel in the RSRreportserver.config file.</span></span> <span data-ttu-id="3b182-108">La valeur est obligatoire et ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="3b182-108">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="3b182-109">La liste suivante affiche les valeurs valides :</span><span class="sxs-lookup"><span data-stu-id="3b182-109">The following list shows valid values:</span></span>  
  
 `"Off | Allow | Require"`  
  
 <span data-ttu-id="3b182-110">*ExtendedProtectionScenario*</span><span class="sxs-lookup"><span data-stu-id="3b182-110">*ExtendedProtectionScenario*</span></span>  
 <span data-ttu-id="3b182-111">Définit RSWindowsExtendedProtectionScenario dans le fichier RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="3b182-111">Sets the RSWindowsExtendedProtectionScenario in the RSReportserver.config file.</span></span> <span data-ttu-id="3b182-112">La valeur est obligatoire et ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="3b182-112">The required value is not case sensitive.</span></span>  
  
 <span data-ttu-id="3b182-113">La liste suivante affiche les valeurs valides :</span><span class="sxs-lookup"><span data-stu-id="3b182-113">The following list shows valid values:</span></span>  
  
 `"Any" | "Proxy" | "Direct"`  
  
## <a name="remarks"></a><span data-ttu-id="3b182-114">Notes</span><span class="sxs-lookup"><span data-stu-id="3b182-114">Remarks</span></span>  
 <span data-ttu-id="3b182-115">Les propriétés RSWindowsExtendedProtectionLevel et RSWindowsExtendedProtectionScenario s'appliquent lorsque AuthenticationTypes dans le fichier RSReportServer.config inclut RSWindowNTLM, RSWindowsNegotiate ou RSWindowsKerberos.</span><span class="sxs-lookup"><span data-stu-id="3b182-115">The RSWindowsExtendedProtectionLevel and the RSWindowsExtendedProtectionScenario properties apply when the AuthenticationTypes in the RSReportServer.config file include RSWindowNTLM, RSWindowsNegotiate, or RSWindowsKerberos.</span></span> <span data-ttu-id="3b182-116">La définition de ces propriétés change la manière dont les utilisateurs et le logiciel client sont authentifiés au niveau du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3b182-116">Setting these properties affects how users and client software authenticate with a report server.</span></span> <span data-ttu-id="3b182-117">Nosu vous conseillons de lire la documentation relative à la protection étendue avant de définir la propriété ExtendedProtectionLevel sur `Allow` ou `Require`.</span><span class="sxs-lookup"><span data-stu-id="3b182-117">It is recommended that you read the documentation for extended protection before setting ExtendedProtectionLevel to either `Allow` or `Require`.</span></span>  
  
 <span data-ttu-id="3b182-118">Pour définir la propriété ExtendedProtectionLevel, l'utilisateur doit être un membre du groupe BUILTIN\Administrators sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3b182-118">To set the ExtendedProtectionLevel, the user must be a member of the BUILTIN\Administrators group on the report server.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b182-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="3b182-119">Requirements</span></span>  
 <span data-ttu-id="3b182-120">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b182-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b182-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3b182-121">See Also</span></span>  
 <span data-ttu-id="3b182-122">[Propriété RSWindowsExtendedProtectionScenario &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="3b182-122">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="3b182-123">[Propriété RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="3b182-123">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="3b182-124">[Protection étendue de l’authentification avec Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b182-124">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="3b182-125">Fichier de configuration RSReportServer</span><span class="sxs-lookup"><span data-stu-id="3b182-125">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
