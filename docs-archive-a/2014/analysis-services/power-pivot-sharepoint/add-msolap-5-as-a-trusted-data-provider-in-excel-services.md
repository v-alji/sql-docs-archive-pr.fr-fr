---
title: Ajouter MSOLAP. 5 en tant que Fournisseur de données approuvé dans Excel Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1f40fa4-de6d-41ee-8124-14b4d65988f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 876ec613f18b2d91b5e06ab5fed4a7b258c30a36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613171"
---
# <a name="add-msolap5-as-a-trusted-data-provider-in-excel-services"></a><span data-ttu-id="a078d-102">Ajouter MSOLAP.5 en tant que fournisseur de données approuvé dans Excel Services</span><span class="sxs-lookup"><span data-stu-id="a078d-102">Add MSOLAP.5 as a Trusted Data Provider in Excel Services</span></span>
  <span data-ttu-id="a078d-103">MSOLAP.5 fait référence au fournisseur OLE DB Analysis Services pour SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a078d-103">MSOLAP.5 refers to the Analysis Services OLE DB provider for SQL Server 2012.</span></span> <span data-ttu-id="a078d-104">Excel Services doit approuver ce fournisseur avant d'effectuer la demande de connexion qui se traduit par la disponibilité des données PowerPivot sur un serveur.</span><span class="sxs-lookup"><span data-stu-id="a078d-104">Excel Services must trust this provider before it will make the connection request that results in the availability of PowerPivot data on a server.</span></span>  
  
 <span data-ttu-id="a078d-105">Si vous avez configuré PowerPivot pour SharePoint à l'aide de l'outil de configuration PowerPivot, MSOLAP.5 est peut-être déjà un fournisseur approuvé, car l'outil inclut une action qui répond à cette exigence.</span><span class="sxs-lookup"><span data-stu-id="a078d-105">If you configured PowerPivot for SharePoint using the PowerPivot Configuration Tool, MSOLAP.5 might already be a trusted provider because the tool includes an action that satisfies this requirement.</span></span> <span data-ttu-id="a078d-106">Toutefois, si vous utilisez PowerShell, l'administration centrale, ou si vous avez exclu l'action du fournisseur approuvé dans l'outil de configuration, le fournisseur peut être manquant, auquel cas vous devez l'ajouter maintenant, dans le cadre de la configuration de la batterie de serveurs pour l'accès aux données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="a078d-106">However, if you are using PowerShell, Central Administration, or if you excluded the trusted provider action in the configuration tool, the provider might be missing, which case you should add it now as part of configuring the farm for PowerPivot data access.</span></span>  
  
 <span data-ttu-id="a078d-107">Vous ne devez effectuer cette étape qu'une seule fois pour chaque application de service Excel Services.</span><span class="sxs-lookup"><span data-stu-id="a078d-107">You only need to perform this step once for each Excel Services service application.</span></span>  
  
 <span data-ttu-id="a078d-108">Chaque serveur physique qui traite une requête de données PowerPivot, tel que PowerPivot pour SharePoint ou un serveur Excel Services, doit avoir installé le fournisseur OLE DB sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a078d-108">Each physical server that handles a PowerPivot data request, such as a PowerPivot for SharePoint server or an Excel Services server, must have the OLE DB provider installed on the computer.</span></span> <span data-ttu-id="a078d-109">Une installation de PowerPivot pour SharePoint inclut toujours le fournisseur OLE DB, mais si Excel Services s'exécute sur un ordinateur qui ne dispose pas de PowerPivot pour SharePoint, vous devez installer le fournisseur manuellement.</span><span class="sxs-lookup"><span data-stu-id="a078d-109">A PowerPivot for SharePoint installation always includes the OLE DB provider, but if Excel Services is running on a computer that does not have PowerPivot for SharePoint, you must install the provider manually.</span></span> <span data-ttu-id="a078d-110">Pour plus d’informations, voir [Installer le fournisseur OLE DB Analysis Services sur les serveurs SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a078d-110">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="add-a-trusted-provider-to-excel-services"></a><span data-ttu-id="a078d-111">Ajouter un fournisseur approuvé à Excel Services</span><span class="sxs-lookup"><span data-stu-id="a078d-111">Add a trusted provider to Excel Services</span></span>  
  
1.  <span data-ttu-id="a078d-112">Dans l'administration centrale, cliquez sur **Gérer les applications de service**, puis cliquez sur l'application de service Excel Services.</span><span class="sxs-lookup"><span data-stu-id="a078d-112">In Central Administration, click **Manage service applications**, and then click the Excel Services service application.</span></span>  
  
2.  <span data-ttu-id="a078d-113">Cliquez sur **Fournisseurs de données approuvés**.</span><span class="sxs-lookup"><span data-stu-id="a078d-113">Click **Trusted Data Providers**.</span></span>  
  
3.  <span data-ttu-id="a078d-114">Vérifiez que MSOLAP.5 figure dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a078d-114">Verify that MSOLAP.5 appears in the list.</span></span> <span data-ttu-id="a078d-115">Selon la manière dont vous avez configuré PowerPivot pour SharePoint, MSOLAP.5 peut être déjà approuvé.</span><span class="sxs-lookup"><span data-stu-id="a078d-115">Depending on how you configured PowerPivot for SharePoint, MSOLAP.5 might already be trusted.</span></span>  
  
4.  <span data-ttu-id="a078d-116">S'il n'est pas répertorié, cliquez sur **Ajouter un fournisseur de données approuvé**.</span><span class="sxs-lookup"><span data-stu-id="a078d-116">If it is not listed, click **Add Trusted Data Provider**.</span></span>  
  
5.  <span data-ttu-id="a078d-117">Pour l’ID du fournisseur, tapez `MSOLAP.5`.</span><span class="sxs-lookup"><span data-stu-id="a078d-117">In Provider ID, type `MSOLAP.5`.</span></span>  
  
6.  <span data-ttu-id="a078d-118">Pour le type de fournisseur, vérifiez que OLE DB est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a078d-118">For Provider Type, ensure that OLE DB is selected.</span></span>  
  
7.  <span data-ttu-id="a078d-119">Dans la description du fournisseur, tapez **Fournisseur Microsoft OLE DB pour OLAP Services 11.0**.</span><span class="sxs-lookup"><span data-stu-id="a078d-119">In Provider Description, type **Microsoft OLE DB Provider for OLAP Services 11.0**.</span></span>  
  
  
