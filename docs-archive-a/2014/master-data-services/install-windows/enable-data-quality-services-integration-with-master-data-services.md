---
title: Activer l’intégration de Data Quality Services à Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603567"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="17805-102">Activer l'intégration de Data Quality Services avec Master Data Services</span><span class="sxs-lookup"><span data-stu-id="17805-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="17805-103">Dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], la fonctionnalité de mise en correspondance est assurée par Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="17805-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="17805-104">Cette fonctionnalité doit être activée pour pouvoir être utilisée.</span><span class="sxs-lookup"><span data-stu-id="17805-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17805-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="17805-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="17805-106">Une application Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] et une base de données doivent exister.</span><span class="sxs-lookup"><span data-stu-id="17805-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="17805-107">La fonctionnalité Data Quality Services et le Data Quality Client doivent être installés sur la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge la base de données MDS.</span><span class="sxs-lookup"><span data-stu-id="17805-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="17805-108">Pour plus d’informations, consultez [Installer Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="17805-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="17805-109">Pour activer l'intégration de Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="17805-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="17805-110">Ouvrez [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17805-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="17805-111">Dans le volet gauche, cliquez sur **Configuration Web**.</span><span class="sxs-lookup"><span data-stu-id="17805-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="17805-112">Dans la page **Configuration web** , sélectionnez le site web et l’application web.</span><span class="sxs-lookup"><span data-stu-id="17805-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="17805-113">Dans la section **Activer l’intégration DQS** , cliquez sur **Activer l’intégration avec Data Quality Services**.</span><span class="sxs-lookup"><span data-stu-id="17805-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="17805-114">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="17805-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17805-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="17805-115">See Also</span></span>  
 <span data-ttu-id="17805-116">[Correspondance de la qualité des données dans le Complément MDS pour Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="17805-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="17805-117">[Complément Master Data Services pour Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="17805-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="17805-118">Installer Master Data Services</span><span class="sxs-lookup"><span data-stu-id="17805-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
