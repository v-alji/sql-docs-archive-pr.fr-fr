---
title: GetAdminSiteUrl, méthode (WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetAdminSiteUrl method
ms.assetid: fbc5bf3c-120c-4aec-a4f2-f5391bd415f6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cae1a6f7e363ddce8c47c00eb5ef25fc832e59c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604364"
---
# <a name="getadminsiteurl-method-wmi"></a><span data-ttu-id="6f450-102">Méthode GetAdminSiteUrl (WMI)</span><span class="sxs-lookup"><span data-stu-id="6f450-102">GetAdminSiteUrl Method (WMI)</span></span>
  <span data-ttu-id="6f450-103">Obtient l'URL absolue du site Web Administration centrale pour la batterie de serveurs Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)]ou [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] à laquelle le serveur de rapports est intégré.</span><span class="sxs-lookup"><span data-stu-id="6f450-103">Gets the absolute URL for the Central Administration Web site for the Microsoft [!INCLUDE[winSPServ](../../includes/winspserv-md.md)], [!INCLUDE[offSPServ](../../includes/offspserv-md.md)], [!INCLUDE[SPF2010](../../includes/spf2010-md.md)], or [!INCLUDE[SPS2010](../../includes/sps2010-md.md)] farm that the report server is integrated with.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f450-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6f450-104">Syntax</span></span>  
  
```vb  
Public Sub GetAdminSiteUrl(ByRef AdminSiteUrl as String, _  
ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GetAdminSiteUrl(out string AdminSiteUrl, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f450-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6f450-105">Parameters</span></span>  
 <span data-ttu-id="6f450-106">*AdminSiteUrl*</span><span class="sxs-lookup"><span data-stu-id="6f450-106">*AdminSiteUrl*</span></span>  
 <span data-ttu-id="6f450-107">[out] Chaîne qui contient l'URL absolue du site Web Administration centrale pour la batterie de serveurs SharePoint à laquelle le serveur de rapports est intégré.</span><span class="sxs-lookup"><span data-stu-id="6f450-107">[out] A string that contains the absolute URL for the Central Administration Web site for the SharePoint farm that the report server is integrated with.</span></span>  
  
 <span data-ttu-id="6f450-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6f450-108">*HRESULT*</span></span>  
 <span data-ttu-id="6f450-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="6f450-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f450-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="6f450-110">Return Value</span></span>  
 <span data-ttu-id="6f450-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="6f450-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6f450-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="6f450-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6f450-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="6f450-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f450-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="6f450-114">Requirements</span></span>  
 <span data-ttu-id="6f450-115">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f450-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f450-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6f450-116">See Also</span></span>  
 [<span data-ttu-id="6f450-117">Méthodes MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="6f450-117">MSReportServer_ConfigurationSetting Methods</span></span>](msreportserver-configurationsetting-methods.md)  
  
  
