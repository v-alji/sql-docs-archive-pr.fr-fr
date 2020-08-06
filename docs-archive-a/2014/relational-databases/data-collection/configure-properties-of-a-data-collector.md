---
title: Configurer les propriétés d’un collecteur de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702975"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="c43ba-102">Configurer les propriétés d'un collecteur de données</span><span class="sxs-lookup"><span data-stu-id="c43ba-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="c43ba-103">Cette rubrique explique comment configurer les propriétés d'un collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="c43ba-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="c43ba-104">Propriétés de la collecte de données (onglet Général)</span><span class="sxs-lookup"><span data-stu-id="c43ba-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="c43ba-105">Utilisez cette page pour configurer les paramètres relatifs à l'entrepôt de données de gestion et spécifier l'emplacement où les données collectées doivent être stockées avant d'être téléchargées dans l'entrepôt de données.</span><span class="sxs-lookup"><span data-stu-id="c43ba-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="c43ba-106">**Activer la collecte de données**</span><span class="sxs-lookup"><span data-stu-id="c43ba-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="c43ba-107">Sélectionnez cette option pour activer la collecte de données.</span><span class="sxs-lookup"><span data-stu-id="c43ba-107">Select to enable data collection.</span></span> <span data-ttu-id="c43ba-108">Cela équivaut à exécuter la procédure stockée sp_syscollector_enable_collector.</span><span class="sxs-lookup"><span data-stu-id="c43ba-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="c43ba-109">La désactivation de cette case à cocher désactive la collecte de données et équivaut à exécuter la procédure stockée p_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="c43ba-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="c43ba-110">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="c43ba-110">**Server**</span></span>  
 <span data-ttu-id="c43ba-111">Affiche le nom du serveur qui hébergera l'entrepôt de données de gestion</span><span class="sxs-lookup"><span data-stu-id="c43ba-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="c43ba-112">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="c43ba-112">**Database name**</span></span>  
 <span data-ttu-id="c43ba-113">Affiche le nom de la base de données relationnelle utilisée pour l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="c43ba-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="c43ba-114">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="c43ba-114">**Test Connection**</span></span>  
 <span data-ttu-id="c43ba-115">Testez la connexion au **Serveur** spécifié à l’aide des informations fournies quand la collecte de données est configurée.</span><span class="sxs-lookup"><span data-stu-id="c43ba-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="c43ba-116">**Répertoire du cache**</span><span class="sxs-lookup"><span data-stu-id="c43ba-116">**Cache directory**</span></span>  
 <span data-ttu-id="c43ba-117">Spécifie le répertoire où les données collectées sont stockées sur le système collectant les données avant d'être téléchargées dans l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="c43ba-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="c43ba-118">Si le **Répertoire du cache** n'est pas spécifié, le collecteur de données tente de localiser les variables d'environnement %TEMP% et %TMP% et utilise l'un de ces emplacements comme emplacement par défaut pour le stockage temporaire.</span><span class="sxs-lookup"><span data-stu-id="c43ba-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="c43ba-119">Si ces variables d'environnement ne sont pas configurées, une erreur se produit et vous êtes invité à créer un répertoire de cache.</span><span class="sxs-lookup"><span data-stu-id="c43ba-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="c43ba-120">Propriétés de la collecte de données (onglet Avancé)</span><span class="sxs-lookup"><span data-stu-id="c43ba-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="c43ba-121">Utilisez cette page pour configurer les paramètres du délai entre reprises pour la connexion à l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="c43ba-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="c43ba-122">**Nombre de tentatives en cas d'échec du téléchargement**</span><span class="sxs-lookup"><span data-stu-id="c43ba-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="c43ba-123">Spécifie le nombre de tentatives de téléchargement dans l'entrepôt de données de gestion en cas d'échec du téléchargement.</span><span class="sxs-lookup"><span data-stu-id="c43ba-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="c43ba-124">La valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="c43ba-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43ba-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c43ba-125">See Also</span></span>  
 <span data-ttu-id="c43ba-126">[Gérer la collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="c43ba-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="c43ba-127">Configurer l’entrepôt de données de gestion &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="c43ba-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
