---
title: IsSharePointIntegrated, propriété (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- IsSharePointIntegrated property
ms.assetid: c548fed8-5e04-4faf-8b10-b37c86178056
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a1f3f38c23546ddf4dfb52c2a3af7c122af10cbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612154"
---
# <a name="issharepointintegrated-property-wmi"></a><span data-ttu-id="5ea0f-102">Propriété IsSharePointIntegrated (WMI)</span><span class="sxs-lookup"><span data-stu-id="5ea0f-102">IsSharePointIntegrated Property (WMI)</span></span>
  <span data-ttu-id="5ea0f-103">Spécifie si le serveur de rapports s'exécute en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-103">Specifies whether the report server is in SharePoint integrated mode.</span></span> <span data-ttu-id="5ea0f-104">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], cette propriété retourne toujours `False`, car en mode SharePoint, les instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sont des services partagés SharePoint et ne sont pas contrôlées par les fournisseurs WMI.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-104">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this property always returns `False` because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instances are SharePoint shared services and are not controlled by WMI providers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ea0f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5ea0f-105">Syntax</span></span>  
  
```vb  
Public Dim IsSharePointIntegrated As Boolean  
```  
  
```csharp  
public Boolean IsSharePointIntegrated;  
```  
  
## <a name="property-values"></a><span data-ttu-id="5ea0f-106">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="5ea0f-106">Property Values</span></span>  
 <span data-ttu-id="5ea0f-107">Objet `Boolean` qui indique si le serveur de rapports fonctionne en mode intégré SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ea0f-107">A `Boolean` object that indicates whether the report server is in SharePoint integrated mode.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="5ea0f-108">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="5ea0f-108">Example Code</span></span>  
 [<span data-ttu-id="5ea0f-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="5ea0f-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="5ea0f-110">Spécifications</span><span class="sxs-lookup"><span data-stu-id="5ea0f-110">Requirements</span></span>  
 <span data-ttu-id="5ea0f-111">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ea0f-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea0f-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ea0f-112">See Also</span></span>  
 [<span data-ttu-id="5ea0f-113">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="5ea0f-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
