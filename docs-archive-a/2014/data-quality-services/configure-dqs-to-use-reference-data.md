---
title: Configurer DQS pour utiliser des données de référence | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.rds.f1
- sql12.dqs.administration.rdsconfiguration.f1
- sql12.dqs.administration.configuration.createDirectRDS.f1
ms.assetid: fae745e7-57a7-4cbc-8979-56ea8e392e4e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 670e984c2afabb70dece75d94701d7a3a03c95bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696092"
---
# <a name="configure-dqs-to-use-reference-data"></a><span data-ttu-id="dd413-102">Configurer DQS pour utiliser des données de référence</span><span class="sxs-lookup"><span data-stu-id="dd413-102">Configure DQS to Use Reference Data</span></span>
  <span data-ttu-id="dd413-103">Cette rubrique explique comment configurer [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) afin d'utiliser des données de référence pour le nettoyage de vos données.</span><span class="sxs-lookup"><span data-stu-id="dd413-103">This topic describes how to configure [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) to use reference data for cleansing your data.</span></span> <span data-ttu-id="dd413-104">Vous pouvez utiliser des données de référence à partir d’Azure Marketplace ou de fournisseurs de données de référence tiers en ligne directs.</span><span class="sxs-lookup"><span data-stu-id="dd413-104">You could either use reference data from Azure Marketplace or from direct online third-party reference data providers.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="dd413-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="dd413-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dd413-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dd413-106">Prerequisites</span></span>  
 <span data-ttu-id="dd413-107">Pour utiliser des données de référence de Marketplace, vous devez disposer d'une clé de compte Marketplace valide.</span><span class="sxs-lookup"><span data-stu-id="dd413-107">To use reference data from Marketplace, you must have a valid Marketplace account key.</span></span> <span data-ttu-id="dd413-108">Pour plus d’informations sur la création d’une clé de compte Marketplace, consultez [créer votre compte](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="dd413-108">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span> <span data-ttu-id="dd413-109">Vous pouvez également créer une clé de compte de la Place de marché à partir de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]. Pour ce faire, cliquez sur **Configuration** sous **Administration** dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], puis cliquez sur **Créer un ID de compte DataMarket** sous l'onglet **Données de référence**.</span><span class="sxs-lookup"><span data-stu-id="dd413-109">You can also create a Marketplace account key from within [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] by clicking **Configuration** under **Administration** in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, and then clicking **Create a DataMarket Account ID** under the **Reference Data** tab.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dd413-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="dd413-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dd413-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="dd413-111">Permissions</span></span>  
 <span data-ttu-id="dd413-112">Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour configurer les paramètres du service de données de référence dans DQS.</span><span class="sxs-lookup"><span data-stu-id="dd413-112">You must have the dqs_administrator role on the DQS_MAIN database to configure reference data service settings in DQS.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-marketplace"></a><a name="Marketplace"></a> <span data-ttu-id="dd413-113">Configurer DQS pour utiliser des données de référence de Marketplace</span><span class="sxs-lookup"><span data-stu-id="dd413-113">Configure DQS to Use Reference Data from Marketplace</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="dd413-114">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="dd413-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="dd413-115">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , sous **Administration**, cliquez sur **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="dd413-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="dd413-116">Sous l'onglet **Données de référence** , sous la zone **Paramètres réseau** , tapez les valeurs appropriées dans les zones **Serveur proxy** et **Port** si vous ou votre organisation utilisez un serveur proxy pour vous connecter à Internet.</span><span class="sxs-lookup"><span data-stu-id="dd413-116">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="dd413-117">Spécifiez la clé de compte de la Place de marché dans la zone **ID de compte DataMarket**, puis cliquez sur l'icône **Valider l'ID de compte DataMarket** pour valider la clé de compte.</span><span class="sxs-lookup"><span data-stu-id="dd413-117">Specify the Marketplace account key in the **DataMarket Account ID** box, and click the **Validate DataMarket Account ID** icon to validate the account key.</span></span> <span data-ttu-id="dd413-118">Un message indiquant si la clé de compte Marketplace spécifiée est valide s'affiche.</span><span class="sxs-lookup"><span data-stu-id="dd413-118">A message appears to display whether the specified Marketplace account key is valid.</span></span>  
  
 <span data-ttu-id="dd413-119">Vous êtes maintenant prêt à utiliser, dans DQS, les services de données de référence Marketplace faisant l'objet d'un abonnement pour la clé de compte Marketplace spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dd413-119">You are now ready to use the reference data services from Marketplace in DQS that are subscribed for the specified Marketplace account key.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-direct-online-third-party-reference-data-providers"></a><a name="ThirdParty"></a><span data-ttu-id="dd413-120">Configurer DQS pour utiliser des données de référence provenant de fournisseurs de données de référence tiers en ligne directs</span><span class="sxs-lookup"><span data-stu-id="dd413-120">Configure DQS to Use Reference Data from Direct Online Third-Party Reference Data Providers</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="dd413-121">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="dd413-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="dd413-122">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , sous **Administration**, cliquez sur **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="dd413-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="dd413-123">Sous l'onglet **Données de référence** , sous la zone **Paramètres réseau** , tapez les valeurs appropriées dans les zones **Serveur proxy** et **Port** si vous ou votre organisation utilisez un serveur proxy pour vous connecter à Internet.</span><span class="sxs-lookup"><span data-stu-id="dd413-123">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="dd413-124">Dans la zone **Paramètres du service de données de référence tiers en ligne direct** , cliquez sur l'icône **Ajouter un nouveau fournisseur de services de données de référence** .</span><span class="sxs-lookup"><span data-stu-id="dd413-124">In the **Direct Online 3rd Party Reference Data Service Settings** area, click the **Add new reference data service provider** icon.</span></span>  
  
5.  <span data-ttu-id="dd413-125">Dans la boîte de dialogue **Créer un fournisseur de services de données de référence tiers en ligne direct** , spécifiez les détails suivants :</span><span class="sxs-lookup"><span data-stu-id="dd413-125">In the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box, specify the following details:</span></span>  
  
    1.  <span data-ttu-id="dd413-126">Dans la zone **Nom** , tapez le nom du nouveau fournisseur de services de données de référence direct.</span><span class="sxs-lookup"><span data-stu-id="dd413-126">In the **Name** box, type a name of the new direct reference data service provider.</span></span>  
  
    2.  <span data-ttu-id="dd413-127">(Facultatif) Dans la zone **Description** , tapez la description du nouveau fournisseur de services de données de référence direct.</span><span class="sxs-lookup"><span data-stu-id="dd413-127">(Optional) In the **Description** box, type a description of the new direct reference data service provider.</span></span>  
  
    3.  <span data-ttu-id="dd413-128">Dans la zone **Catégorie** , tapez la catégorie des données fournies par le nouveau fournisseur de services de données de référence direct.</span><span class="sxs-lookup"><span data-stu-id="dd413-128">In the **Category** box, type the category of the data provided by the new direct reference data service provider.</span></span>  
  
    4.  <span data-ttu-id="dd413-129">Dans la zone Schéma, spécifiez le schéma qui définit la chaîne des champs (noms de colonnes) à utiliser à partir du fournisseur de services de données de référence direct.</span><span class="sxs-lookup"><span data-stu-id="dd413-129">In the Schema box, specify the schema that defines the string of fields (column names) to be used from the direct reference data service provider.</span></span> <span data-ttu-id="dd413-130">Un nom de champ ne doit pas contenir d'espace, et les champs doivent être séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="dd413-130">A field name should not contain a space, and the fields should be separated by commas.</span></span> <span data-ttu-id="dd413-131">Par exemple : `FirstName, LastName, City, State`.</span><span class="sxs-lookup"><span data-stu-id="dd413-131">For example: `FirstName, LastName, City, State`.</span></span>  
  
    5.  <span data-ttu-id="dd413-132">Dans la zone **URI** , tapez l'URI du fournisseur de services de données de référence direct.</span><span class="sxs-lookup"><span data-stu-id="dd413-132">In the **URI** box, type the URI of the direct reference data service provider.</span></span> <span data-ttu-id="dd413-133">Seuls les URI sécurisés (adresse commençant par « https:// ») sont autorisés dans DQS.</span><span class="sxs-lookup"><span data-stu-id="dd413-133">Only secure URIs (address starting with "https://") are allowed in DQS.</span></span>  
  
    6.  <span data-ttu-id="dd413-134">Dans la zone **Taille de lot maximale** , tapez le nombre maximal d'enregistrements par lot qui seront envoyés au fournisseur de services de données de référence pour être nettoyés.</span><span class="sxs-lookup"><span data-stu-id="dd413-134">In the **Max Batch Size** box, type the maximum number of records per batch that will be sent to the reference data service provider for cleansing.</span></span> <span data-ttu-id="dd413-135">Il est possible de spécifier au maximum 100 enregistrements par lot pour l'activité de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="dd413-135">A maximum of 100 records per batch can be specified for the cleansing activity.</span></span>  
  
    7.  <span data-ttu-id="dd413-136">Dans la zone **ID de compte** , tapez l'ID de compte de l'abonné avec le fournisseur de services de données de référence.</span><span class="sxs-lookup"><span data-stu-id="dd413-136">In the **Account ID** box, type the account ID of the subscriber with the reference data service provider.</span></span>  
  
6.  <span data-ttu-id="dd413-137">Cliquez sur **OK** pour enregistrer les données, puis fermez la boîte de dialogue **Créer un fournisseur de services de données de référence tiers en ligne direct** .</span><span class="sxs-lookup"><span data-stu-id="dd413-137">Click **OK** to save the data, and close the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box.</span></span> <span data-ttu-id="dd413-138">Le fournisseur de données de référence tiers en ligne direct que vous venez d'ajouter devient disponible dans la grille des **Fournisseurs de services de données de référence** dans DQS.</span><span class="sxs-lookup"><span data-stu-id="dd413-138">The newly added direct online third party reference data provider becomes available in the **Direct Reference Data Service Providers Grid** in DQS.</span></span>  
  
 <span data-ttu-id="dd413-139">Vous êtes maintenant prêt à utiliser, dans DQS, les services de données de référence à partir du fournisseur de données de référence tiers en ligne direct que vous venez de configurer.</span><span class="sxs-lookup"><span data-stu-id="dd413-139">You are now ready to use the reference data services from the newly configured direct online third-party reference data service provider in DQS.</span></span>  
  
##  <a name="follow-up-after-configuring-dqs-to-use-reference-data"></a><a name="FollowUp"></a><span data-ttu-id="dd413-140">Suivi : après avoir configuré DQS pour utiliser des données de référence</span><span class="sxs-lookup"><span data-stu-id="dd413-140">Follow Up: After Configuring DQS to use Reference Data</span></span>  
 <span data-ttu-id="dd413-141">Vous devez maintenant mapper les domaines de base de connaissances requis aux données de référence disponibles auprès des fournisseurs de données que vous venez de configurer.</span><span class="sxs-lookup"><span data-stu-id="dd413-141">You must now map the required knowledge base domains to the reference data available from the data providers you just configured.</span></span> <span data-ttu-id="dd413-142">Pour ce faire, consultez [attacher un domaine ou un domaine composite à des données de référence](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="dd413-142">To do so, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
  
