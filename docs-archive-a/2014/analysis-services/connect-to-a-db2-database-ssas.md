---
title: Se connecter à une base de données DB2 (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndb2db.f1
ms.assetid: eeef3697-a4fd-4263-ba7e-f86afa1f46cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: f36a583956c1fe75bb0a6acd827d083a6c7562f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602477"
---
# <a name="connect-to-a-db2-database-ssas"></a><span data-ttu-id="91a14-102">Connexion à une base de données DB2 (SSAS)</span><span class="sxs-lookup"><span data-stu-id="91a14-102">Connect to a DB2 Database (SSAS)</span></span>
  <span data-ttu-id="91a14-103">Cette page de l' **Assistant Importation de table** vous permet de spécifier des paramètres pour vous connecter à une base de données DB2.</span><span class="sxs-lookup"><span data-stu-id="91a14-103">This page of the **Table Import Wizard** enables you to specify settings to connect to a DB2 database.</span></span> <span data-ttu-id="91a14-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="91a14-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="91a14-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="91a14-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91a14-106">Lors de la sélection d'une base de données dans cette page, les informations d'identification de l'utilisateur spécifiées sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="91a14-106">When selecting a database in this page, the credentials of the user specified are used.</span></span> <span data-ttu-id="91a14-107">Toutefois, l'importation ne réussira pas si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="91a14-107">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="91a14-108">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="91a14-108">UI element list</span></span>  
 <span data-ttu-id="91a14-109">**Nom convivial de la connexion**</span><span class="sxs-lookup"><span data-stu-id="91a14-109">**Friendly connection name**</span></span>  
 <span data-ttu-id="91a14-110">Tapez un nom unique pour cette connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="91a14-110">Type a unique name for this data source connection.</span></span> <span data-ttu-id="91a14-111">Ce champ est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="91a14-111">This is a required field.</span></span>  
  
 <span data-ttu-id="91a14-112">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="91a14-112">**Server name**</span></span>  
 <span data-ttu-id="91a14-113">Tapez ou sélectionnez l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="91a14-113">Type or select the server instance to connect to.</span></span>  
  
 <span data-ttu-id="91a14-114">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="91a14-114">**User name**</span></span>  
 <span data-ttu-id="91a14-115">Spécifiez un nom d'utilisateur pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="91a14-115">Specify a user name for the database connection.</span></span>  
  
 <span data-ttu-id="91a14-116">Ce nom d'utilisateur est utilisé lors de la construction de la chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="91a14-116">This user name is used when constructing the connection string for the data source.</span></span> <span data-ttu-id="91a14-117">Ces informations d'identification sont également utilisées lors de l'affichage un aperçu et du filtrage des données dans la fenêtre Propriétés de la table et dans l'Assistant Importation.</span><span class="sxs-lookup"><span data-stu-id="91a14-117">These credentials are also used when previewing and filtering data in the Table Properties window and in the Import Wizard.</span></span> <span data-ttu-id="91a14-118">Ces informations d'identification ne sont pas utilisées pour importer ou actualiser des données ; les informations d'identification Windows spécifiées dans la page Informations d'emprunt d'identité sont utilisées à la place.</span><span class="sxs-lookup"><span data-stu-id="91a14-118">These credentials are not used to import or refresh data; the Windows credentials specified on the Impersonation Information page are used instead.</span></span>  
  
 <span data-ttu-id="91a14-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="91a14-119">**Password**</span></span>  
 <span data-ttu-id="91a14-120">Spécifiez un mot de passe pour la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="91a14-120">Specify a password for the database connection.</span></span>  
  
 <span data-ttu-id="91a14-121">**Enregistrer mon mot de passe**</span><span class="sxs-lookup"><span data-stu-id="91a14-121">**Save my password**</span></span>  
 <span data-ttu-id="91a14-122">Précisez si le mot de passe que vous avez entré dans la zone **Mot de passe** est mémorisé.</span><span class="sxs-lookup"><span data-stu-id="91a14-122">Specify whether the password you have entered in the **Password** box is stored.</span></span>  
  
 <span data-ttu-id="91a14-123">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="91a14-123">**Database name**</span></span>  
 <span data-ttu-id="91a14-124">Sélectionnez une base de données dans la liste.</span><span class="sxs-lookup"><span data-stu-id="91a14-124">Select a database from the list of databases.</span></span>  
  
 <span data-ttu-id="91a14-125">**Collection de packages**</span><span class="sxs-lookup"><span data-stu-id="91a14-125">**Package Collection**</span></span>  
 <span data-ttu-id="91a14-126">Spécifiez le nom de la collection pour les packages DB2.</span><span class="sxs-lookup"><span data-stu-id="91a14-126">Specify the name of the collection for the DB2 packages.</span></span> <span data-ttu-id="91a14-127">Un fournisseur utilise des packages pour émettre des instructions SQL et appeler des procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="91a14-127">A provider uses packages to issue SQL statements and call stored procedures.</span></span>  
  
 <span data-ttu-id="91a14-128">**Schéma par défaut**</span><span class="sxs-lookup"><span data-stu-id="91a14-128">**Default Schema**</span></span>  
 <span data-ttu-id="91a14-129">Spécifiez le nom du schéma par défaut de la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="91a14-129">Specify the name of the default schema for the selected database.</span></span>  
  
 <span data-ttu-id="91a14-130">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="91a14-130">**Advanced**</span></span>  
 <span data-ttu-id="91a14-131">Définissez des propriétés de connexion supplémentaires à l’aide de la boîte de dialogue **définir les propriétés avancées** .</span><span class="sxs-lookup"><span data-stu-id="91a14-131">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="91a14-132">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="91a14-132">**Test Connection**</span></span>  
 <span data-ttu-id="91a14-133">Essayez d'établir une connexion à la source de données à l'aide des paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="91a14-133">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="91a14-134">Un message est affiché pour indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="91a14-134">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
