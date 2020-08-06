---
title: Propriété RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 162ffe86-69c3-49d2-b9ed-49d097c05551
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02ff3bad42ae25adf6cfa563944d89bac2c600e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604343"
---
# <a name="rswindowsextendedprotectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="95572-102">Propriété RSWindowsExtendedProtectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="95572-102">RSWindowsExtendedProtectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="95572-103">Retourne une valeur de chaîne indiquant le niveau de protection configuré pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="95572-103">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="95572-104">Cette propriété est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="95572-104">This property is read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95572-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="95572-105">Syntax</span></span>  
  
```vb  
Public Dim RSWindowsExtendedProtectionLevel As String  
```  
  
```csharp  
public string RSWindowsExtendedProtectionLevel;  
```  
  
## <a name="remarks"></a><span data-ttu-id="95572-106">Notes</span><span class="sxs-lookup"><span data-stu-id="95572-106">Remarks</span></span>  
 <span data-ttu-id="95572-107">Retourne une valeur de chaîne indiquant le niveau de protection configuré pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="95572-107">Returns a string value that indicates the level of protection the report server is configured to support.</span></span> <span data-ttu-id="95572-108">Si le serveur de rapports auquel le fournisseur WMI est connecté ne prend pas en charge la protection étendue, "" (chaîne vide) est retourné.</span><span class="sxs-lookup"><span data-stu-id="95572-108">If the report server that the WMI provider is connected to does not support extended protection, "" (empty string) is returned.</span></span> <span data-ttu-id="95572-109">La liste suivante affiche les valeurs valides :</span><span class="sxs-lookup"><span data-stu-id="95572-109">The following list shows valid values:</span></span>  
  
 `"Off" | "Allow" | "Require"`  
  
## <a name="example-code"></a><span data-ttu-id="95572-110">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="95572-110">Example Code</span></span>  
 [<span data-ttu-id="95572-111">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="95572-111">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="see-also"></a><span data-ttu-id="95572-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95572-112">See Also</span></span>  
 <span data-ttu-id="95572-113">[Propriété RSWindowsExtendedProtectionScenario &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span><span class="sxs-lookup"><span data-stu-id="95572-113">[RSWindowsExtendedProtectionScenario Property &#40;WMI MSReportServer_ConfigurationSetting&#41;](rswindowsextendedprotectionscenario-property.md) </span></span>  
 <span data-ttu-id="95572-114">[Méthode SetExtendedProtectionSettings &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span><span class="sxs-lookup"><span data-stu-id="95572-114">[SetExtendedProtectionSettings Method &#40;WMI MSReportServer_ConfigurationSetting&#41;](configurationsetting-method-setextendedprotectionsettings.md) </span></span>  
 <span data-ttu-id="95572-115">[Protection étendue de l’authentification avec Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="95572-115">[Extended Protection for Authentication with Reporting Services](../security/extended-protection-for-authentication-with-reporting-services.md) </span></span>  
 [<span data-ttu-id="95572-116">Fichier de configuration RSReportServer</span><span class="sxs-lookup"><span data-stu-id="95572-116">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
  
  
