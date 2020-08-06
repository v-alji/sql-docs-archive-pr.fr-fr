---
title: Connexion à un rapport ou à un flux de données (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602462"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="7c2a1-102">Connexion à un flux de rapport ou de données (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7c2a1-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="7c2a1-103">Cette page de l' **Assistant Importation de table** vous permet de vous connecter à un flux de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="7c2a1-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="7c2a1-105">À partir d'un rapport</span><span class="sxs-lookup"><span data-stu-id="7c2a1-105">From a Report</span></span>  
 <span data-ttu-id="7c2a1-106">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="7c2a1-107">Tapez un nom convivial pour la connexion au flux de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="7c2a1-108">**Chemin d'accès au rapport**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-108">**Report Path**</span></span>  
 <span data-ttu-id="7c2a1-109">Indique l'URL d'un rapport SQL Server Reporting Services qui génère des sources de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="7c2a1-110">Cliquez sur **Parcourir** pour spécifier l'URL du rapport.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="7c2a1-111">Cliquez sur **Afficher le rapport** pour afficher le rapport.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="7c2a1-112">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-112">**Browse**</span></span>  
 <span data-ttu-id="7c2a1-113">Naviguez jusqu'à un emplacement où un rapport est disponible.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="7c2a1-114">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-114">**Advanced**</span></span>  
 <span data-ttu-id="7c2a1-115">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="7c2a1-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="7c2a1-116">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-116">**Test Connection**</span></span>  
 <span data-ttu-id="7c2a1-117">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7c2a1-118">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="7c2a1-119">À partir d'un dataset Azure DataMarket</span><span class="sxs-lookup"><span data-stu-id="7c2a1-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="7c2a1-120">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="7c2a1-121">Tapez un nom convivial pour la connexion au flux de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="7c2a1-122">**URL du flux de données**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="7c2a1-123">Tapez le chemin d’accès complet à un document de service Atom (.atomsvc, .atom) ou l’URL d’un flux de données unique, ou cliquez sur **Parcourir** pour sélectionner un document de service Atom.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="7c2a1-124">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-124">**Browse**</span></span>  
 <span data-ttu-id="7c2a1-125">Naviguez jusqu'à un emplacement où un rapport est disponible.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="7c2a1-126">Cliquez sur **Afficher les datasets Azure DataMarket disponibles** pour afficher les datasets disponibles.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="7c2a1-127">**Clé de compte**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-127">**Account key**</span></span>  
 <span data-ttu-id="7c2a1-128">Spécifiez la clé de compte utilisée pour accéder à vos abonnements au jeu de données de la place de marché Azure.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="7c2a1-129">**Trouver**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-129">**Find**</span></span>  
 <span data-ttu-id="7c2a1-130">Recherchez une clé de compte associée à un compte Windows Live.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="7c2a1-131">**Enregistrer ma clé de compte**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-131">**Save my account key**</span></span>  
 <span data-ttu-id="7c2a1-132">Enregistre la clé de compte (chiffrée) avec la connexion de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="7c2a1-133">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-133">**Advanced**</span></span>  
 <span data-ttu-id="7c2a1-134">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="7c2a1-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="7c2a1-135">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-135">**Test Connection**</span></span>  
 <span data-ttu-id="7c2a1-136">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7c2a1-137">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="7c2a1-138">À partir d'autres flux</span><span class="sxs-lookup"><span data-stu-id="7c2a1-138">From Other Feeds</span></span>  
 <span data-ttu-id="7c2a1-139">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="7c2a1-140">Tapez un nom convivial pour la connexion au flux de données.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="7c2a1-141">**URL du flux de données**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="7c2a1-142">Tapez le chemin d’accès complet à un document de service Atom (.atomsvc, .atom) ou l’URL d’un flux de données unique, ou cliquez sur **Parcourir** pour sélectionner un document de service Atom.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="7c2a1-143">Cliquez sur **Inclure toutes les colonnes du flux** pour spécifier si toutes les colonnes du flux de données sont importées.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="7c2a1-144">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-144">**Browse**</span></span>  
 <span data-ttu-id="7c2a1-145">Naviguez jusqu'à un emplacement où un flux de données est disponible.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="7c2a1-146">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-146">**Advanced**</span></span>  
 <span data-ttu-id="7c2a1-147">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="7c2a1-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="7c2a1-148">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="7c2a1-148">**Test Connection**</span></span>  
 <span data-ttu-id="7c2a1-149">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="7c2a1-150">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="7c2a1-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
