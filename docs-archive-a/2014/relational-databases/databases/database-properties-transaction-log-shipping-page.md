---
title: Propriétés de la base de données (page Envoi des journaux de transactions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.f1
ms.assetid: 72c4e539-fe11-4d57-b977-65b418d5916f
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd36b3bc56bcd48c53871c9bc1e334d72c80ac78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709587"
---
# <a name="database-properties-transaction-log-shipping-page"></a><span data-ttu-id="c0083-102">Propriétés de la base de données (page Envoi des journaux de transactions)</span><span class="sxs-lookup"><span data-stu-id="c0083-102">Database Properties (Transaction Log Shipping Page)</span></span>
  <span data-ttu-id="c0083-103">Cette page vous permet de configurer et de modifier les propriétés de copie des journaux de transactions d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="c0083-103">Use this page to configure and modify the properties of log shipping for a database.</span></span>  
  
 <span data-ttu-id="c0083-104">Pour obtenir des explications sur les concepts de copie des journaux de transaction, consultez [À propos de la copie des journaux de transaction &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c0083-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c0083-105">Options</span><span class="sxs-lookup"><span data-stu-id="c0083-105">Options</span></span>  
 <span data-ttu-id="c0083-106">**Activer en tant que base de données primaire dans une configuration de la copie des journaux de transactions**</span><span class="sxs-lookup"><span data-stu-id="c0083-106">**Enable this as a primary database in a log shipping configuration**</span></span>  
 <span data-ttu-id="c0083-107">Active la base de données comme base de données primaire de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="c0083-107">Enables this database as a log shipping primary database.</span></span> <span data-ttu-id="c0083-108">Activez cette option, puis configurez les options restantes dans cette page.</span><span class="sxs-lookup"><span data-stu-id="c0083-108">Select it and then configure the remaining options on this page.</span></span> <span data-ttu-id="c0083-109">Si vous désactivez cette case à cocher, la configuration de copie des journaux de transactions est supprimée pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="c0083-109">If you clear this check box, the log shipping configuration will be dropped for this database.</span></span>  
  
 <span data-ttu-id="c0083-110">**Paramètres de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="c0083-110">**Backup Settings**</span></span>  
 <span data-ttu-id="c0083-111">Cliquez sur **Paramètres de sauvegarde** pour configurer la planification, l’emplacement, l’alerte et les paramètres d’archivage de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c0083-111">Click **Backup Settings** to configure backup schedule, location, alert, and archiving parameters.</span></span>  
  
 <span data-ttu-id="c0083-112">**Planification de la sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="c0083-112">**Backup schedule**</span></span>  
 <span data-ttu-id="c0083-113">Indique la planification de sauvegarde actuellement sélectionnée pour la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="c0083-113">Shows the currently selected backup schedule for the primary database.</span></span> <span data-ttu-id="c0083-114">Cliquez sur **Paramètres de sauvegarde** pour modifier ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="c0083-114">Click **Backup Settings** to modify these settings.</span></span>  
  
 <span data-ttu-id="c0083-115">**Date de la dernière sauvegarde créée**</span><span class="sxs-lookup"><span data-stu-id="c0083-115">**Last backup created**</span></span>  
 <span data-ttu-id="c0083-116">Indique la date et l'heure de la dernière sauvegarde des journaux de transactions de la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="c0083-116">Indicates the time and date of the last transaction log backup of the primary database.</span></span>  
  
 <span data-ttu-id="c0083-117">**Instances de serveurs et bases de données secondaires**</span><span class="sxs-lookup"><span data-stu-id="c0083-117">**Secondary server instances and databases**</span></span>  
 <span data-ttu-id="c0083-118">Répertorie les serveurs et les bases de données secondaires actuellement configurés pour la base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="c0083-118">Lists the currently configured secondary servers and databases for this primary database.</span></span> <span data-ttu-id="c0083-119">Mettez en surbrillance une base de données, puis cliquez sur **...** pour modifier les paramètres associés à cette base de données secondaire.</span><span class="sxs-lookup"><span data-stu-id="c0083-119">Highlight a database, and then click **...** to modify the parameters associated with that secondary database.</span></span>  
  
 <span data-ttu-id="c0083-120">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="c0083-120">**Add**</span></span>  
 <span data-ttu-id="c0083-121">Cliquez sur **Ajouter** pour ajouter une base de données secondaire à la configuration de copie des journaux de transactions pour cette base de données primaire.</span><span class="sxs-lookup"><span data-stu-id="c0083-121">Click **Add** to add a secondary database to the log shipping configuration for this primary database.</span></span>  
  
 <span data-ttu-id="c0083-122">**Remove**</span><span class="sxs-lookup"><span data-stu-id="c0083-122">**Remove**</span></span>  
 <span data-ttu-id="c0083-123">Supprime une base de données sélectionnée de cette configuration de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="c0083-123">Removes a selected database from this log shipping configuration.</span></span> <span data-ttu-id="c0083-124">Sélectionnez la base de données, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="c0083-124">Select the database first and then click **Remove**.</span></span>  
  
 <span data-ttu-id="c0083-125">**Utiliser une instance du serveur moniteur**</span><span class="sxs-lookup"><span data-stu-id="c0083-125">**Use a monitor server instance**</span></span>  
 <span data-ttu-id="c0083-126">Permet de définir une instance de serveur moniteur pour cette configuration de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="c0083-126">Sets up a monitor server instance for this log shipping configuration.</span></span> <span data-ttu-id="c0083-127">Activez la case à cocher **Utiliser une instance du serveur moniteur** , puis cliquez sur **Paramètres** pour spécifier l'instance de serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="c0083-127">Select the **Use a monitor server instance** check box and then click **Settings** to specify the monitor server instance.</span></span>  
  
 <span data-ttu-id="c0083-128">**Instance du serveur moniteur**</span><span class="sxs-lookup"><span data-stu-id="c0083-128">**Monitor server instance**</span></span>  
 <span data-ttu-id="c0083-129">Spécifie l'instance de serveur moniteur actuellement configurée pour cette configuration de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="c0083-129">Indicates the currently configured monitor server instance for this log shipping configuration.</span></span>  
  
 <span data-ttu-id="c0083-130">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="c0083-130">**Settings**</span></span>  
 <span data-ttu-id="c0083-131">Permet de configurer l'instance de serveur moniteur pour une configuration de copie des journaux de transactions.</span><span class="sxs-lookup"><span data-stu-id="c0083-131">Configures the monitor server instance for a log shipping configuration.</span></span> <span data-ttu-id="c0083-132">Cliquez sur **Paramètres** pour configurer cette instance de serveur moniteur.</span><span class="sxs-lookup"><span data-stu-id="c0083-132">Click **Settings** to configure this monitor server instance.</span></span>  
  
 <span data-ttu-id="c0083-133">**Créer un script de configuration**</span><span class="sxs-lookup"><span data-stu-id="c0083-133">**Script Configuration**</span></span>  
 <span data-ttu-id="c0083-134">Génère un script pour la configuration de la copie des journaux de transactions avec les paramètres que vous avez sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c0083-134">Generates a script for configuring log shipping with the parameters you have selected.</span></span> <span data-ttu-id="c0083-135">Cliquez sur **Créer un script de configuration**, puis sélectionnez une destination de sortie pour le script.</span><span class="sxs-lookup"><span data-stu-id="c0083-135">Click **Script Configuration**, and then choose an output destination for the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c0083-136">Avant de créer un script des paramètres pour une base de données secondaire, vous devez appeler la boîte de dialogue **Paramètres de base de données secondaire** .</span><span class="sxs-lookup"><span data-stu-id="c0083-136">Before scripting settings for a secondary database, you must invoke the **Secondary Database Settings** dialog box.</span></span> <span data-ttu-id="c0083-137">L'appel de cette boîte de dialogue vous connecte au serveur secondaire et récupère les paramètres actuels de la base de données secondaire, nécessaires pour générer le script.</span><span class="sxs-lookup"><span data-stu-id="c0083-137">Invoking this dialog box connects you to the secondary server and retrieves the current settings of the secondary database that are needed to generate the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0083-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c0083-138">See Also</span></span>  
 <span data-ttu-id="c0083-139">[Procédures stockées de copie des journaux de transaction &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c0083-139">[Log Shipping Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/log-shipping-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="c0083-140">Tables de copie des journaux de transaction &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c0083-140">Log Shipping Tables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/log-shipping-tables-transact-sql)  
  
  
