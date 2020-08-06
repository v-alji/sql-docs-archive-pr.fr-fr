---
title: Ce classeur contient une ou plusieurs requêtes qui actualisent les données externes. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604760"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="96e4a-103">Ce classeur contient une ou plusieurs requêtes qui actualisent les données externes.</span><span class="sxs-lookup"><span data-stu-id="96e4a-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="96e4a-104">Pour les classeurs Excel qui contiennent des données PowerPivot, Excel Services affiche cet avertissement lorsqu'il détecte des informations de connexion et vous demande d'activer ou de désactiver des requêtes pour ce classeur.</span><span class="sxs-lookup"><span data-stu-id="96e4a-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96e4a-105">Détails</span><span class="sxs-lookup"><span data-stu-id="96e4a-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96e4a-106">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="96e4a-106">Product Name</span></span>|<span data-ttu-id="96e4a-107">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="96e4a-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="96e4a-108">Version du produit</span><span class="sxs-lookup"><span data-stu-id="96e4a-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="96e4a-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96e4a-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="96e4a-110">Cause</span><span class="sxs-lookup"><span data-stu-id="96e4a-110">Cause</span></span>|<span data-ttu-id="96e4a-111">Excel Services est configuré pour avertir lors de l'actualisation des données.</span><span class="sxs-lookup"><span data-stu-id="96e4a-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="96e4a-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="96e4a-112">Message Text</span></span>|<span data-ttu-id="96e4a-113">Ce classeur contient une ou plusieurs requêtes qui actualisent les données externes.</span><span class="sxs-lookup"><span data-stu-id="96e4a-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="96e4a-114">Un utilisateur malveillant peut concevoir une requête pour accéder aux informations confidentielles et les distribuer à d'autres utilisateurs ou effectuer d'autres actions malfaisantes.</span><span class="sxs-lookup"><span data-stu-id="96e4a-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="96e4a-115">Si vous approuvez la source de ce classeur, cliquez sur Oui pour activer les requêtes à des données externes dans ce classeur.</span><span class="sxs-lookup"><span data-stu-id="96e4a-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="96e4a-116">Si vous avez des doutes, cliquez sur Non afin que les modifications ne soient pas appliquées à votre classeur.</span><span class="sxs-lookup"><span data-stu-id="96e4a-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="96e4a-117">Souhaitez-vous activer des requêtes à des données externes dans ce classeur ?</span><span class="sxs-lookup"><span data-stu-id="96e4a-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="96e4a-118">Explication</span><span class="sxs-lookup"><span data-stu-id="96e4a-118">Explanation</span></span>  
 <span data-ttu-id="96e4a-119">Les classeurs PowerPivot contiennent des chaînes de connexion de données incorporées, utilisées par Excel pour communiquer avec un serveur PowerPivot externe qui charge et calcule les données.</span><span class="sxs-lookup"><span data-stu-id="96e4a-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="96e4a-120">Lorsque l'option Avertir lors de l'actualisation des données est activée, Excel Services détecte cette chaîne de connexion et avertit l'utilisateur en conséquence.</span><span class="sxs-lookup"><span data-stu-id="96e4a-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="96e4a-121">Pour filtrer et découper les données PowerPivot dans le classeur, les requêtes doivent être activées.</span><span class="sxs-lookup"><span data-stu-id="96e4a-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="96e4a-122">Assurez-vous que vous activez des requêtes uniquement pour les classeurs PowerPivot que vous approuvez.</span><span class="sxs-lookup"><span data-stu-id="96e4a-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="96e4a-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="96e4a-123">User Action</span></span>  
 <span data-ttu-id="96e4a-124">Cliquez sur **Oui** pour activer les requêtes.</span><span class="sxs-lookup"><span data-stu-id="96e4a-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="96e4a-125">Vous pouvez également modifier les paramètres de configuration de façon à ne plus avertir lors de l'actualisation des données :</span><span class="sxs-lookup"><span data-stu-id="96e4a-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="96e4a-126">Dans l'Administration centrale, sous Gestion des applications, cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="96e4a-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="96e4a-127">Cliquez sur **Application Excel Services**.</span><span class="sxs-lookup"><span data-stu-id="96e4a-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="96e4a-128">Cliquez sur **Emplacement de fichier approuvé**.</span><span class="sxs-lookup"><span data-stu-id="96e4a-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="96e4a-129">Cliquez sur **http://** ou sur l’emplacement à configurer.</span><span class="sxs-lookup"><span data-stu-id="96e4a-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="96e4a-130">Dans Données externes, désactivez la case à cocher **Avertir lors de l'actualisation**.</span><span class="sxs-lookup"><span data-stu-id="96e4a-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="96e4a-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="96e4a-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="96e4a-132">Vous pouvez également créer un emplacement approuvé pour les sites qui contiennent des classeurs PowerPivot, puis modifier les paramètres de configuration uniquement pour ce site.</span><span class="sxs-lookup"><span data-stu-id="96e4a-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="96e4a-133">Pour plus d'informations, consultez [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="96e4a-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
