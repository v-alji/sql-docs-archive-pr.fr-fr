---
title: "Une erreur s'est produite lors de la tentative de connexion à la source de données externe. Échec de l’actualisation des connexions suivantes : données PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1b951da1-f62d-43d2-b40b-270a4a9ab92c
author: minewiskan
ms.author: owend
ms.openlocfilehash: eb4329440b69d1bdfdbb96fbcc3926fa000d8877
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700320"
---
# <a name="an-error-occurred-during-an-attempt-to-establish-a-connection-to-the-external-data-source-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="e6d5c-103">Une erreur s'est produite lors de la tentative de connexion à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-103">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="e6d5c-104">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e6d5c-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="e6d5c-105">Cette erreur se produit si vous interrogez des données PowerPivot sur un serveur sur lequel PowerPivot pour SharePoint n'est pas installé.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-105">This error occurs if you query PowerPivot data on a server that does not have PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="e6d5c-106">Se produit également si le service SQL Server Analysis Services (PowerPivot) est arrêté, ou si vous essayez d'afficher des données PowerPivot d'une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-106">It also occurs if the SQL Server Analysis Services (PowerPivot) service is stopped, or if you are attempting to view PowerPivot data from an earlier version.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e6d5c-107">Détails</span><span class="sxs-lookup"><span data-stu-id="e6d5c-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6d5c-108">S’applique à</span><span class="sxs-lookup"><span data-stu-id="e6d5c-108">Applies to</span></span>|<span data-ttu-id="e6d5c-109">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6d5c-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="e6d5c-110">Version du produit</span><span class="sxs-lookup"><span data-stu-id="e6d5c-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="e6d5c-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d5c-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="e6d5c-112">Cause</span><span class="sxs-lookup"><span data-stu-id="e6d5c-112">Cause</span></span>|<span data-ttu-id="e6d5c-113">La connexion de données a échoué.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-113">The data connection failed.</span></span>|  
|<span data-ttu-id="e6d5c-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e6d5c-114">Message Text</span></span>|<span data-ttu-id="e6d5c-115">Une erreur s'est produite lors de la tentative de connexion à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-115">An error occurred during an attempt to establish a connection to the external data source.</span></span> <span data-ttu-id="e6d5c-116">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e6d5c-116">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6d5c-117">Explication</span><span class="sxs-lookup"><span data-stu-id="e6d5c-117">Explanation</span></span>  
 <span data-ttu-id="e6d5c-118">Excel Services retourne cette erreur lorsque vous interrogez des données PowerPivot dans un classeur Excel qui est publié dans SharePoint et que l'environnement SharePoint ne dispose pas d'un serveur PowerPivot pour SharePoint, ou si le service SQL Server Analysis Services (PowerPivot) est arrêté.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-118">Excel Services returns this error when you query PowerPivot data in an Excel workbook that is published to SharePoint, and the SharePoint environment does not have a PowerPivot for SharePoint server, or the SQL Server Analysis Services (PowerPivot) service is stopped.</span></span>  
  
 <span data-ttu-id="e6d5c-119">L'erreur se produit lorsque vous découpez ou filtrez des données PowerPivot alors que le moteur d'interrogation n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-119">The error occurs when you slice or filter PowerPivot data when the query engine is not available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6d5c-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6d5c-120">User Action</span></span>  
 <span data-ttu-id="e6d5c-121">Installez PowerPivot pour SharePoint ou déplacez le classeur PowerPivot vers un environnement SharePoint dans lequel PowerPivot pour SharePoint est installé.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-121">Install PowerPivot for SharePoint or move the PowerPivot workbook to a SharePoint environment that has PowerPivot for SharePoint installed.</span></span> <span data-ttu-id="e6d5c-122">Pour plus d'informations, consultez [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span><span class="sxs-lookup"><span data-stu-id="e6d5c-122">For more information, see [PowerPivot for SharePoint 2010 Installation](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md).</span></span>  
  
 <span data-ttu-id="e6d5c-123">Si le logiciel est installé, vérifiez que l'instance SQL Server Analysis Services (PowerPivot) s'exécute.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-123">If the software is installed, verify that the SQL Server Analysis Services (PowerPivot) instance is running.</span></span> <span data-ttu-id="e6d5c-124">Sélectionnez **Gérer les services sur le serveur** dans Administration centrale.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-124">Check **Manage services on server** in Central Administration.</span></span> <span data-ttu-id="e6d5c-125">Sélectionnez également l'application de console Services dans Outils d'administration.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-125">Also check the Services console application in Administrative Tools.</span></span>  
  
 <span data-ttu-id="e6d5c-126">Pour les classeurs PowerPivot créés dans une version SQL Server 2008 R2 PowerPivot pour Excel, vous devez installer la version SQL Server 2008 R2 du fournisseur OLE DB Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-126">For PowerPivot workbooks that were created in a SQL Server 2008 R2 version of PowerPivot for Excel, you must install the SQL Server 2008 R2 version of the Analysis Services OLE DB provider.</span></span> <span data-ttu-id="e6d5c-127">Cette erreur se produira si vous avez installé le fournisseur, mais n'avez pas enregistré le fichier Microsoft.AnalysisServices.ChannelTransport.dll.</span><span class="sxs-lookup"><span data-stu-id="e6d5c-127">This error will occur if you installed the provider, but did not register the Microsoft.AnalysisServices.ChannelTransport.dll file.</span></span> <span data-ttu-id="e6d5c-128">Pour plus d’informations sur l’enregistrement du fichier, consultez [Installer le fournisseur OLE DB Analysis Services sur les serveurs SharePoint](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e6d5c-128">For more information about file registration, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d5c-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6d5c-129">See Also</span></span>  
 [<span data-ttu-id="e6d5c-130">La connexion de données utilise l’authentification Windows et les informations d’identification de l’utilisateur n’ont pas pu être déléguées. Échec de l’actualisation des connexions suivantes : données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="e6d5c-130">The data connection uses Windows Authentication and user credentials could not be delegated. The following connections failed to refresh: PowerPivot Data</span></span>](the-data-connection-user-could-not-be-delegated.md)  
  
  
