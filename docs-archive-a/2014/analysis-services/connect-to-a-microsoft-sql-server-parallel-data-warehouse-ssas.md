---
title: Se connecter à un Microsoft SQL Server Parallel Data Warehouse (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlparadatawh.f1
ms.assetid: 98c879ee-7257-40c9-bc85-6766bd3b4885
author: minewiskan
ms.author: owend
ms.openlocfilehash: 082d6b34077d1bde11b527d3bfff907073eed16e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602464"
---
# <a name="connect-to-a-microsoft-sql-server-parallel-data-warehouse-ssas"></a><span data-ttu-id="9f690-102">Connexion à un entrepôt de données Microsoft SQL Server Parallel Data Warehouse (SSAS)</span><span class="sxs-lookup"><span data-stu-id="9f690-102">Connect to a Microsoft SQL Server Parallel Data Warehouse (SSAS)</span></span>
  <span data-ttu-id="9f690-103">Cette page de **l’Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à un entrepôt de données Microsoft SQL Server Parallel Data Warehouse (PDW).</span><span class="sxs-lookup"><span data-stu-id="9f690-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a Microsoft SQL Server Parallel Data Warehouse (PDW).</span></span> <span data-ttu-id="9f690-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="9f690-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="9f690-105">SQL Server PDW est un appareil très évolutif qui offre des performances à faible coût via le traitement parallèle massif.</span><span class="sxs-lookup"><span data-stu-id="9f690-105">SQL Server PDW is a highly scalable appliance that delivers performance at low cost through massively parallel processing.</span></span> <span data-ttu-id="9f690-106">Pour plus d’informations sur SQL Server PDW, consultez le site web [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span><span class="sxs-lookup"><span data-stu-id="9f690-106">For more information about SQL Server PDW, see the web site [SQL Server 2008 R2 Parallel Data Warehouse](https://go.microsoft.com/fwlink/?LinkId=150895).</span></span> <span data-ttu-id="9f690-107">Vous pouvez vous connecter à l'entrepôt de données à l'aide de l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9f690-107">You connect to the data warehouse by using SQL Server Authentication.</span></span> <span data-ttu-id="9f690-108">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9f690-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f690-109">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="9f690-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="9f690-110">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="9f690-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="9f690-111">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="9f690-111">UI element list</span></span>  
 <span data-ttu-id="9f690-112">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="9f690-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="9f690-113">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="9f690-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="9f690-114">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9f690-114">This is a required field.</span></span>  
  
 <span data-ttu-id="9f690-115">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="9f690-115">**Server name**</span></span>  
 <span data-ttu-id="9f690-116">Tapez le nom ou l'adresse IP du serveur auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="9f690-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="9f690-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="9f690-117">**User name**</span></span>  
 <span data-ttu-id="9f690-118">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="9f690-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="9f690-119">Ce nom d'utilisateur est utilisé lors de la construction de la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="9f690-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="9f690-120">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="9f690-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="9f690-121">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="9f690-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="9f690-122">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="9f690-122">**Password**</span></span>  
 <span data-ttu-id="9f690-123">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="9f690-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="9f690-124">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="9f690-124">**Save my password**</span></span>  
 <span data-ttu-id="9f690-125">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="9f690-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="9f690-126">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="9f690-126">**Database name**</span></span>  
 <span data-ttu-id="9f690-127">Sélectionnez une base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="9f690-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="9f690-128">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="9f690-128">**Advanced**</span></span>  
 <span data-ttu-id="9f690-129">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="9f690-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="9f690-130">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="9f690-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="9f690-131">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="9f690-131">**Test Connection**</span></span>  
 <span data-ttu-id="9f690-132">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="9f690-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="9f690-133">Un message s'affiche et indique si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="9f690-133">A message displays and indicates whether the connection is successful.</span></span>  
  
  
