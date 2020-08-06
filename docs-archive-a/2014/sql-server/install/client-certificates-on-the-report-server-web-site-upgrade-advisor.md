---
title: Certificats clients sur le site Web du serveur de rapports (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604957"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="a1db5-102">Certificats clients sur le site Web du serveur de rapports (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="a1db5-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="a1db5-103">Le Conseiller de mise à niveau a détecté un ou plusieurs certificats clients sur le site Web IIS qui héberge les répertoires virtuels du serveur de rapports ou du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="a1db5-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="a1db5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode natif.</span><span class="sxs-lookup"><span data-stu-id="a1db5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="a1db5-105">Composant</span><span class="sxs-lookup"><span data-stu-id="a1db5-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a1db5-106">Description</span><span class="sxs-lookup"><span data-stu-id="a1db5-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="a1db5-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]ne prend pas en charge l’utilisation de certificats clients pour authentifier les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a1db5-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="a1db5-108">La mise à niveau peut se poursuivre, mais les certificats clients ne seront pas utilisés par le serveur de rapports mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="a1db5-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a1db5-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a1db5-109">Corrective Action</span></span>  
 <span data-ttu-id="a1db5-110">Vous devrez recourir à une solution distincte, par exemple ISA Server, pour garantir que toutes les exigences d'authentification des certificats clients seront satisfaites.</span><span class="sxs-lookup"><span data-stu-id="a1db5-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1db5-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a1db5-111">See Also</span></span>  
 [<span data-ttu-id="a1db5-112">Problèmes de mise à niveau de Reporting Services &#40;conseiller de mise à niveau&#41;</span><span class="sxs-lookup"><span data-stu-id="a1db5-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
