---
title: Propriété RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5ac7ab80-9adf-4f65-abfa-fedf53b082b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84e14d056cc0352b0d1d85bc12c9c873a1b89ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703747"
---
# <a name="rswindowsextendedprotectionscenario-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="86ddc-102">Propriété RSWindowsExtendedProtectionScenario (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="86ddc-102">RSWindowsExtendedProtectionScenario Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="86ddc-103">Retourne une valeur de chaîne indiquant le scénario de protection étendue que le serveur de rapports est configuré à autoriser.</span><span class="sxs-lookup"><span data-stu-id="86ddc-103">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ddc-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="86ddc-104">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionScenario As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionScenario;  
```  
  
## <a name="remarks"></a><span data-ttu-id="86ddc-105">Notes</span><span class="sxs-lookup"><span data-stu-id="86ddc-105">Remarks</span></span>  
 <span data-ttu-id="86ddc-106">Retourne une valeur de chaîne indiquant le scénario de protection étendue que le serveur de rapports est configuré à autoriser.</span><span class="sxs-lookup"><span data-stu-id="86ddc-106">Returns a string value that indicates the extended protection scenario the report server is configured to allow.</span></span> <span data-ttu-id="86ddc-107">Si le serveur de rapports auquel le fournisseur WMI est connecté ne prend pas en charge la protection étendue, "" (chaîne vide) est retourné.</span><span class="sxs-lookup"><span data-stu-id="86ddc-107">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span>  
  
 <span data-ttu-id="86ddc-108">La liste suivante affiche les valeurs valides :</span><span class="sxs-lookup"><span data-stu-id="86ddc-108">The following list shows valid values:</span></span>  
  
 `"Any | Proxy | Direct"`  
  
## <a name="example-code"></a><span data-ttu-id="86ddc-109">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="86ddc-109">Example Code</span></span>  
 [<span data-ttu-id="86ddc-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="86ddc-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="86ddc-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="86ddc-111">See Also</span></span>  
 <span data-ttu-id="86ddc-112">[Propriété RSWindowsExtendedProtectionLevel &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span><span class="sxs-lookup"><span data-stu-id="86ddc-112">[RSWindowsExtendedProtectionLevel Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionlevel-property.md) </span></span>  
 <span data-ttu-id="86ddc-113">[Méthode SetExtendedProtectionSettings &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="86ddc-113">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="86ddc-114">[Protection étendue de l’authentification avec Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="86ddc-114">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="86ddc-115">Fichier de configuration RSReportServer</span><span class="sxs-lookup"><span data-stu-id="86ddc-115">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
