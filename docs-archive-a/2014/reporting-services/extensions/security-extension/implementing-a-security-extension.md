---
title: Implémentation d’une extension de sécurité | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- forms-based authentication [Reporting Services]
- custom authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: d2327e7c-0d48-49e3-bcd9-3bba4e67a68b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e5cf1fa6ce0e0a02a52e6a27f693c152d1f97152
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610466"
---
# <a name="implementing-a-security-extension"></a><span data-ttu-id="05091-102">Implémentation d'une extension de sécurité</span><span class="sxs-lookup"><span data-stu-id="05091-102">Implementing a Security Extension</span></span>
  <span data-ttu-id="05091-103">L’authentification Windows de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] constitue le principal système permettant de sécuriser des rapports dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05091-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows Authentication is the primary system for securing reports in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="05091-104">Dans certains cas, en revanche, vous pouvez avoir besoin d'étendre le système de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pour personnaliser la sécurité dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="05091-104">In certain cases, however, you may need to extend the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security system to accommodate custom security in your enterprise.</span></span> <span data-ttu-id="05091-105">Pour cela, vous pouvez utiliser la plate-forme de développement fournie par l'API [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05091-105">You can do this using the development platform provided by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] API.</span></span> <span data-ttu-id="05091-106">Cette section présente une vue d'ensemble des extensions de sécurité dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05091-106">This section will present an overview of security extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="05091-107">Pour plus d’informations sur l’implémentation, le déploiement et la suppression d’une extension de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], consultez [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Exemples Reporting Services pour le produit SQL Server).</span><span class="sxs-lookup"><span data-stu-id="05091-107">For complete details about implementing, deploying, and removing a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension, please see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05091-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="05091-108">In This Section</span></span>  
 [<span data-ttu-id="05091-109">Présentation des extensions de sécurité</span><span class="sxs-lookup"><span data-stu-id="05091-109">Security Extensions Overview</span></span>](security-extensions-overview.md)  
 <span data-ttu-id="05091-110">Fournit une vue d'ensemble des extensions de sécurité de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="05091-110">Provides an overview of Reporting Services Security Extensions.</span></span>  
  
 [<span data-ttu-id="05091-111">Authentification dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="05091-111">Authentication in Reporting Services</span></span>](authentication-in-reporting-services.md)  
 <span data-ttu-id="05091-112">Examine l'authentification dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05091-112">Discusses authentication in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="05091-113">Autorisation dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="05091-113">Authorization in Reporting Services</span></span>](authorization-in-reporting-services.md)  
 <span data-ttu-id="05091-114">Traite de l'autorisation dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05091-114">Covers authorization in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05091-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05091-115">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="05091-116">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="05091-116">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="05091-117">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="05091-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
