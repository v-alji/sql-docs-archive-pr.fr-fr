---
title: Connexions (Complément MDS pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600124"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="5c791-102">Connexions (Complément MDS pour Excel)</span><span class="sxs-lookup"><span data-stu-id="5c791-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5c791-103">Pour télécharger des données dans le [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], vous devez d’abord créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="5c791-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="5c791-104">Une connexion permet au service web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] de savoir à quelle base de données MDS se connecter.</span><span class="sxs-lookup"><span data-stu-id="5c791-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="5c791-105">La chaîne de connexion est généralement l’URL de l’application web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], par exemple http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="5c791-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="5c791-106">Chaque fois que vous démarrez Excel, vous devez vous connecter à un référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="5c791-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="5c791-107">La seule exception est lorsque la feuille de calcul active contient déjà des données managées MDS.</span><span class="sxs-lookup"><span data-stu-id="5c791-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="5c791-108">Dans ce cas, un rapport est automatiquement créé chaque fois que vous actualisez ou publiez des données dans la feuille.</span><span class="sxs-lookup"><span data-stu-id="5c791-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="5c791-109">Vous pouvez créer plusieurs connexions.</span><span class="sxs-lookup"><span data-stu-id="5c791-109">You can create multiple connections.</span></span> <span data-ttu-id="5c791-110">La connexion récemment accédée est utilisée par défaut.</span><span class="sxs-lookup"><span data-stu-id="5c791-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="5c791-111">Plusieurs utilisateurs peuvent se connecter simultanément.</span><span class="sxs-lookup"><span data-stu-id="5c791-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="5c791-112">Toutefois, des conflits peuvent se produire lorsque plusieurs utilisateurs tentent de publier les mêmes données.</span><span class="sxs-lookup"><span data-stu-id="5c791-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="5c791-113">Pour plus d’informations, consultez [publication de données &#40;Complément MDS pour Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5c791-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="5c791-114">Connexion automatique et chargement de données fréquemment utilisées</span><span class="sxs-lookup"><span data-stu-id="5c791-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="5c791-115">Si vous souhaitez vous connecter toujours au même serveur et charger le même jeu de données, vous pouvez créer des fichiers de requête de raccourci contenant les informations de connexion et de filtre.</span><span class="sxs-lookup"><span data-stu-id="5c791-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="5c791-116">Pour plus d’informations sur les fichiers de requête, consultez [Fichiers de requête de raccourci &#40;Complément MDS pour Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5c791-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="5c791-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="5c791-117">Data Quality Services</span></span>  
 <span data-ttu-id="5c791-118">Le [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] inclut la fonctionnalité Data Quality Services qui vous aide à mettre en correspondance les données avant de les publier sur le référentiel MDS.</span><span class="sxs-lookup"><span data-stu-id="5c791-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="5c791-119">Lorsque vous vous connectez, si une base de données DQS est installée sur la même instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que la base de données MDS, vous pouvez voir les boutons DQS sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="5c791-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="5c791-120">Si la base de données DQS_Main n'existe pas sur l'instance, ces boutons ne sont pas affichés et les fonctionnalités de qualité des données ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="5c791-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="5c791-121">Dépannage des connexions</span><span class="sxs-lookup"><span data-stu-id="5c791-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="5c791-122">Lorsque vous vous connectez à MDS, si vous rencontrez des problèmes, consultez [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) pour obtenir des conseils de dépannage.</span><span class="sxs-lookup"><span data-stu-id="5c791-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5c791-123">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5c791-123">Related Tasks</span></span>  
  
|<span data-ttu-id="5c791-124">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="5c791-124">Task Description</span></span>|<span data-ttu-id="5c791-125">Rubrique</span><span class="sxs-lookup"><span data-stu-id="5c791-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="5c791-126">Créez une connexion à une base de données [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c791-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="5c791-127">Se connecter à un référentiel MDS &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c791-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="5c791-128">Chargez des données MDS dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5c791-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="5c791-129">Charger des données MDS dans Excel</span><span class="sxs-lookup"><span data-stu-id="5c791-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="5c791-130">Filtrez les données MDS avant de les charger dans Excel.</span><span class="sxs-lookup"><span data-stu-id="5c791-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="5c791-131">Filtrer les données avant de charger &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c791-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="5c791-132">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5c791-132">Related Content</span></span>  
  
-   [<span data-ttu-id="5c791-133">Chargement de données &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c791-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="5c791-134">Fichiers de requête de raccourci &#40;Complément MDS pour Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c791-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="5c791-135">Complément Master Data Services pour Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5c791-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
