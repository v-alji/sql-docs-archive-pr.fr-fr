---
title: Se connecter à un Azure SQL Database (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlazure.f1
ms.assetid: 4e0344e9-1822-4698-ad22-05f1f341ced7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91ae6f0f5ab95d3013b6348bd43ddb746fff1c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602461"
---
# <a name="connect-to-an-azure-sql-database-ssas"></a><span data-ttu-id="97c5e-102">Connexion à une base de données Azure SQL Database (SSAS)</span><span class="sxs-lookup"><span data-stu-id="97c5e-102">Connect to an Azure SQL Database (SSAS)</span></span>
  <span data-ttu-id="97c5e-103">Cette page de l' **Assistant Importation de table** vous permet de vous connecter à un [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97c5e-103">This page of the **Table Import Wizard** enables you to connect to a [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="97c5e-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="97c5e-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97c5e-105">Si vous vous connectez à un dataset Azure DataMarket, consultez [Connexion à un flux de rapport ou de données &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="97c5e-105">If you are connecting to an Azure DataMarket dataset, see [Connect to a Report or Data Feed &#40;SSAS&#41;](connect-to-a-report-or-data-feed-ssas.md).</span></span>  
  
 <span data-ttu-id="97c5e-106">La [!INCLUDE[ssSDS](../includes/sssds-md.md)] est une base de données relationnelle hébergée à laquelle vous vous connectez à l'aide de l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97c5e-106">The [!INCLUDE[ssSDS](../includes/sssds-md.md)] is a hosted, relational database that you connect to by using SQL Server Authentication.</span></span> <span data-ttu-id="97c5e-107">Pour plus d'informations sur [!INCLUDE[ssSDS](../includes/sssds-md.md)], consultez le site Web [Base de données SQL](https://go.microsoft.com/fwlink/?LinkID=157856).</span><span class="sxs-lookup"><span data-stu-id="97c5e-107">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)], see the web site [SQL Database](https://go.microsoft.com/fwlink/?LinkID=157856).</span></span> <span data-ttu-id="97c5e-108">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="97c5e-108">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97c5e-109">Les informations d'identification de l'utilisateur actuel sont utilisées lors de la sélection d'une base de données sur cette page.</span><span class="sxs-lookup"><span data-stu-id="97c5e-109">The credentials of the current user are used when selecting a database in this page.</span></span> <span data-ttu-id="97c5e-110">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="97c5e-110">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="97c5e-111">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="97c5e-111">UI element list</span></span>  
 <span data-ttu-id="97c5e-112">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="97c5e-112">**Friendly connection name**</span></span>  
 <span data-ttu-id="97c5e-113">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="97c5e-113">Type a unique name for this data source connection.</span></span> <span data-ttu-id="97c5e-114">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="97c5e-114">This is a required field.</span></span>  
  
 <span data-ttu-id="97c5e-115">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="97c5e-115">**Server name**</span></span>  
 <span data-ttu-id="97c5e-116">Tapez le nom ou l'adresse IP du serveur auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="97c5e-116">Type the name, or IP address, of the server to connect to.</span></span>  
  
 <span data-ttu-id="97c5e-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="97c5e-117">**User name**</span></span>  
 <span data-ttu-id="97c5e-118">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="97c5e-118">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="97c5e-119">Ce nom d'utilisateur est utilisé lors de la construction de la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="97c5e-119">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="97c5e-120">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="97c5e-120">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="97c5e-121">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="97c5e-121">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="97c5e-122">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="97c5e-122">**Password**</span></span>  
 <span data-ttu-id="97c5e-123">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="97c5e-123">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="97c5e-124">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="97c5e-124">**Save my password**</span></span>  
 <span data-ttu-id="97c5e-125">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="97c5e-125">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="97c5e-126">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="97c5e-126">**Database name**</span></span>  
 <span data-ttu-id="97c5e-127">Sélectionnez une base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="97c5e-127">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="97c5e-128">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="97c5e-128">**Advanced**</span></span>  
 <span data-ttu-id="97c5e-129">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **Définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="97c5e-129">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span> <span data-ttu-id="97c5e-130">Pour plus d’informations, consultez [Définir les propriétés avancées &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="97c5e-130">For more information, see [Set Advanced Properties &#40;SSAS&#41;](set-advanced-properties-ssas.md).</span></span>  
  
 <span data-ttu-id="97c5e-131">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="97c5e-131">**Test Connection**</span></span>  
 <span data-ttu-id="97c5e-132">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="97c5e-132">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="97c5e-133">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="97c5e-133">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
