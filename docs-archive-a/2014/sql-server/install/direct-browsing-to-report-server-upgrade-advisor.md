---
title: Navigation directe vers le serveur de rapports (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d2814a4-318a-45ed-b093-1e852fab561f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ab4d146bba4bd87de56b30ad100b57f79eb68de3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614361"
---
# <a name="direct-browsing-to-report-server-upgrade-advisor"></a><span data-ttu-id="b3c91-102">Accès direct au serveur de rapports (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="b3c91-102">Direct Browsing to Report Server (Upgrade Advisor)</span></span>
  <span data-ttu-id="b3c91-103">Le conseiller de mise à niveau a détecté que votre installation actuelle de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] accède directement au répertoire virtuel du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b3c91-103">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory.</span></span>  
  
||  
|-|  
|<span data-ttu-id="b3c91-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b3c91-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="b3c91-105">Composant</span><span class="sxs-lookup"><span data-stu-id="b3c91-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b3c91-106">Description</span><span class="sxs-lookup"><span data-stu-id="b3c91-106">Description</span></span>  
 <span data-ttu-id="b3c91-107">Le conseiller de mise à niveau a détecté que votre installation actuelle de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] accède directement au répertoire virtuel du serveur de rapports, par exemple **http:// \<server name> /reportserver**.</span><span class="sxs-lookup"><span data-stu-id="b3c91-107">Upgrade Advisor detected your current installation of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is browsing directly to the report server virtual directory, for example **http://\<server name>/ReportServer**.</span></span> <span data-ttu-id="b3c91-108">Non pris en charge dans les versions actuelles de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3c91-108">This is not supported in current versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3c91-109">Cette règle est un avertissement et la mise à jour n'est pas bloquée.</span><span class="sxs-lookup"><span data-stu-id="b3c91-109">This rule is a warning and upgrade is not blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b3c91-110">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b3c91-110">Corrective Action</span></span>  
 <span data-ttu-id="b3c91-111">Parcourez l’interface utilisateur SharePoint pour les bibliothèques de documents ou utilisez **http:// \<server name> /sharepoint site>/_vti_bin/ReportServer**.</span><span class="sxs-lookup"><span data-stu-id="b3c91-111">Browse using the SharePoint user interface for document libraries or use **http://\<server name>/sharepoint site>/_vti_bin/reportserver**.</span></span>  
  
  
