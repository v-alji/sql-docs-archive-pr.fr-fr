---
title: "Le chemin d'accès à la connexion de données dans le classeur pointe vers un fichier sur le lecteur local, ou est un URI non valide. Échec de l’actualisation des connexions suivantes : données PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bd22e41a-0931-4d32-888a-633a3046fc5e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3349af08290e2ff659db1441d849b2afef51e95b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604759"
---
# <a name="the-data-connection-path-in-the-workbook-points-to-a-file-on-the-local-drive-or-is-an-invalid-uri-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="348ec-103">Le chemin d'accès à la connexion de données dans le classeur pointe vers un fichier sur le lecteur local, ou est un URI non valide.</span><span class="sxs-lookup"><span data-stu-id="348ec-103">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="348ec-104">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="348ec-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="348ec-105">Pour les classeurs Excel contenant les données PowerPivot, Excel Services retourne cette erreur s'il ne peut pas se connecter aux sources de données incorporées.</span><span class="sxs-lookup"><span data-stu-id="348ec-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="348ec-106">Détails</span><span class="sxs-lookup"><span data-stu-id="348ec-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="348ec-107">S’applique à</span><span class="sxs-lookup"><span data-stu-id="348ec-107">Applies to</span></span>|<span data-ttu-id="348ec-108">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="348ec-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="348ec-109">Version du produit</span><span class="sxs-lookup"><span data-stu-id="348ec-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="348ec-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="348ec-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="348ec-111">Cause</span><span class="sxs-lookup"><span data-stu-id="348ec-111">Cause</span></span>|<span data-ttu-id="348ec-112">Excel Services est configuré pour autoriser uniquement les connexions de données à partir de fichiers .odc se trouvant dans une bibliothèque de connexions de données approuvées.</span><span class="sxs-lookup"><span data-stu-id="348ec-112">Excel Services is configured to only allow data connections from .odc files that are in a trusted data connection library.</span></span>|  
|<span data-ttu-id="348ec-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="348ec-113">Message Text</span></span>|<span data-ttu-id="348ec-114">Le chemin d'accès à la connexion de données dans le classeur pointe vers un fichier sur le lecteur local, ou est un URI non valide.</span><span class="sxs-lookup"><span data-stu-id="348ec-114">The data connection path in the workbook points to a file on the local drive or is an invalid URI.</span></span> <span data-ttu-id="348ec-115">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="348ec-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="348ec-116">Explication</span><span class="sxs-lookup"><span data-stu-id="348ec-116">Explanation</span></span>  
 <span data-ttu-id="348ec-117">Les classeurs PowerPivot contiennent des connexions de données incorporées.</span><span class="sxs-lookup"><span data-stu-id="348ec-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="348ec-118">Pour prendre en charge l'interaction de classeurs via des segments et des filtres, Excel Services doit être configuré pour autoriser l'accès aux données externes via des informations de connexion incorporées.</span><span class="sxs-lookup"><span data-stu-id="348ec-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="348ec-119">L'accès aux données externes est requis pour la récupération de données PowerPivot chargées sur des serveurs PowerPivot de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="348ec-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="348ec-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="348ec-120">User Action</span></span>  
 <span data-ttu-id="348ec-121">Modifiez les paramètres de configuration pour autoriser les connections à une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="348ec-121">Change the configuration settings to allow embedded data source connections.</span></span>  
  
1.  <span data-ttu-id="348ec-122">Dans l'Administration centrale, sous Gestion des applications, cliquez sur **Gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="348ec-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="348ec-123">Cliquez sur **Application Excel Services**.</span><span class="sxs-lookup"><span data-stu-id="348ec-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="348ec-124">Cliquez sur **Emplacement de fichier approuvé**.</span><span class="sxs-lookup"><span data-stu-id="348ec-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="348ec-125">Cliquez sur **http://** ou sur l’emplacement à configurer.</span><span class="sxs-lookup"><span data-stu-id="348ec-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="348ec-126">Dans Données externes, dans Autoriser les données externes, cliquez sur **Bibliothèques de connexions de données approuvées et incorporées**.</span><span class="sxs-lookup"><span data-stu-id="348ec-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="348ec-127">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="348ec-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="348ec-128">Vous pouvez également créer un emplacement approuvé pour les sites qui contiennent des classeurs PowerPivot, puis modifier les paramètres de configuration uniquement pour ce site.</span><span class="sxs-lookup"><span data-stu-id="348ec-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="348ec-129">Pour plus d'informations, consultez [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="348ec-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
