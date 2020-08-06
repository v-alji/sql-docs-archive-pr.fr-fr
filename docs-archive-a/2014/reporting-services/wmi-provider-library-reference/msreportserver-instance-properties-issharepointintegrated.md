---
title: IsSharePointIntegrated, propriété (WMI MSReportServer_Instance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: e21d00ad-5d9a-4290-8d74-7eeeda39e1ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0c92ebe586d37053b47f90ca98c31b3068a7b91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604344"
---
# <a name="issharepointintegrated-property-wmi-msreportserver_instance"></a><span data-ttu-id="958c1-102">Propriété IsSharePointIntegrated (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="958c1-102">IsSharePointIntegrated Property (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="958c1-103">Spécifie si le serveur de rapports s'exécute en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="958c1-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="958c1-104">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], cette propriété retourne toujours `False`, car en mode SharePoint, les instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sont des services partagés SharePoint et ne sont pas contrôlées par les fournisseurs WMI.</span><span class="sxs-lookup"><span data-stu-id="958c1-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958c1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="958c1-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="958c1-106">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="958c1-106">Property Values</span></span>  
 <span data-ttu-id="958c1-107">Valeur `Boolean` qui indique si le serveur de rapports fonctionne en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="958c1-107">A `Boolean` value that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="958c1-108">Spécifications</span><span class="sxs-lookup"><span data-stu-id="958c1-108">Requirements</span></span>  
 <span data-ttu-id="958c1-109">**Espace de noms :** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="958c1-109">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958c1-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="958c1-110">See Also</span></span>  
 <span data-ttu-id="958c1-111">[Membres MSReportServer_Instance](msreportserver-instance-members.md) </span><span class="sxs-lookup"><span data-stu-id="958c1-111">[MSReportServer_Instance Members](msreportserver-instance-members.md) </span></span>  
 [<span data-ttu-id="958c1-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="958c1-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
  
