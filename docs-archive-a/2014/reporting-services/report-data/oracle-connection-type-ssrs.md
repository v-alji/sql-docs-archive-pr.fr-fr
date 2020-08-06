---
title: Type de connexion Oracle (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9db86dd2-beda-42d8-8af7-2629d58a8e3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bf19953c5d2dc2f818eddcacf445e641972d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605223"
---
# <a name="oracle-connection-type-ssrs"></a><span data-ttu-id="64868-102">Type de connexion Oracle (SSRS)</span><span class="sxs-lookup"><span data-stu-id="64868-102">Oracle Connection Type (SSRS)</span></span>
  <span data-ttu-id="64868-103">Pour utiliser des données d'une base de données Oracle dans votre rapport, vous devez avoir un dataset basé sur une source de données de rapport de type Oracle.</span><span class="sxs-lookup"><span data-stu-id="64868-103">To use data from an Oracle database in your report, you must you must have a dataset that is based on a report data source of type Oracle.</span></span> <span data-ttu-id="64868-104">Ce type de source de données intégré est basé sur le fournisseur managé .NET Framework pour Oracle et requiert un composant logiciel client Oracle.</span><span class="sxs-lookup"><span data-stu-id="64868-104">This built-in data source type is based on the .NET Framework Managed Provider for Oracle and requires an Oracle client software component.</span></span>  
  
 <span data-ttu-id="64868-105">Utilisez les informations de cette rubrique pour générer une source de données.</span><span class="sxs-lookup"><span data-stu-id="64868-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="64868-106">Pour obtenir des instructions pas à pas, consultez [Ajouter et vérifier une connexion de données ou une source de données &#40;générateur de rapports et des&#41;SSRS ](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="64868-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="64868-107">Chaîne de connexion</span><span class="sxs-lookup"><span data-stu-id="64868-107">Connection String</span></span>  
 <span data-ttu-id="64868-108">Contactez l'administrateur de votre base de données pour connaître les informations de connexion et d'identification à utiliser pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="64868-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="64868-109">L'exemple de chaîne de connexion suivant spécifie une base de données Oracle sur le serveur nommé Oracle9 utilisant Unicode.</span><span class="sxs-lookup"><span data-stu-id="64868-109">The following connection string example specifies an Oracle database on the server named "Oracle9" using Unicode.</span></span> <span data-ttu-id="64868-110">Le nom du serveur doit correspondre à ce qui est défini dans le fichier de configuration Tnsnames.ora comme nom d'instance de serveur Oracle.</span><span class="sxs-lookup"><span data-stu-id="64868-110">The server name must match what is defined in the Tnsnames.ora configuration file as the Oracle server instance name.</span></span>  
  
```  
Data Source="Oracle9"; Unicode="True"  
```  
  
 <span data-ttu-id="64868-111">Pour plus d’informations sur les exemples de chaînes de connexion, consultez [Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="64868-111">For more information about connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="64868-112">Informations d’identification</span><span class="sxs-lookup"><span data-stu-id="64868-112">Credentials</span></span>  
 <span data-ttu-id="64868-113">Les informations d'identification sont obligatoires pour exécuter des requêtes, afficher l'aperçu du rapport localement et afficher l'aperçu du rapport à partir du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="64868-113">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="64868-114">Après avoir publié votre rapport, vous pouvez devoir modifier les informations d'identification pour la source de données afin que les autorisations soient valides pour récupérer les données lorsque le rapport s'exécute sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="64868-114">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="64868-115">Pour plus d’informations, consultez [connexions de données, sources de données et chaînes de connexion dans Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) ou [spécifier des informations d’identification dans générateur de rapports](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="64868-115">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  

  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="64868-116">Adressée</span><span class="sxs-lookup"><span data-stu-id="64868-116">Queries</span></span>  
 <span data-ttu-id="64868-117">Pour créer un dataset, vous pouvez soit sélectionner une procédure stockée dans une liste déroulante, soit créer une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="64868-117">To create a dataset, you can either select a stored procedure from a drop-down list or create an SQL query.</span></span> <span data-ttu-id="64868-118">Pour générer une requête, vous devez utiliser le concepteur de requêtes textuel.</span><span class="sxs-lookup"><span data-stu-id="64868-118">To build a query, you must use the text-based query designer.</span></span> <span data-ttu-id="64868-119">Pour plus d’informations, consultez [Interface utilisateur du Concepteur de requêtes textuel &#40;Générateur de rapports&#41;](text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="64868-119">For more information, see [Text-based Query Designer User Interface &#40;Report Builder&#41;](text-based-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="64868-120">Vous pouvez spécifier des procédures stockées qui ne retournent qu'un seul jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="64868-120">You can specify stored procedures that return only one result set.</span></span> <span data-ttu-id="64868-121">L'utilisation des requêtes basées sur curseur n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="64868-121">Using cursor-based queries are not supported.</span></span>  
  
##  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="64868-122">Paramètres</span><span class="sxs-lookup"><span data-stu-id="64868-122">Parameters</span></span>  
 <span data-ttu-id="64868-123">Si la requête inclut des variables de requête, les paramètres de rapport sont générés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="64868-123">If the query includes query variables, corresponding report parameters are automatically generated.</span></span> <span data-ttu-id="64868-124">Les paramètres nommés sont pris en charge par cette extension.</span><span class="sxs-lookup"><span data-stu-id="64868-124">Named parameters are supported by this extension.</span></span> <span data-ttu-id="64868-125">Pour Oracle version 9 ou une version ultérieure, les paramètres à valeurs multiples sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="64868-125">For Oracle version 9 or later, multivalue parameters are supported.</span></span>  
  
 <span data-ttu-id="64868-126">Les paramètres de rapport sont créés avec des valeurs de propriétés par défaut que vous devrez peut-être modifier.</span><span class="sxs-lookup"><span data-stu-id="64868-126">Report parameters are created with default property values that you might need to modify.</span></span> <span data-ttu-id="64868-127">Par exemple, chaque paramètre de rapport a le type de données **Texte**.</span><span class="sxs-lookup"><span data-stu-id="64868-127">For example, each report parameter is data type **Text**.</span></span> <span data-ttu-id="64868-128">Après avoir créé les paramètres de rapport, vous devrez peut-être modifier les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="64868-128">After the report parameters are created, you might have to change default values.</span></span> <span data-ttu-id="64868-129">Pour plus d'informations, consultez [Paramètres de rapport &#40;Générateur de rapports et Concepteur de rapports&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="64868-129">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  

  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="64868-130">Notes</span><span class="sxs-lookup"><span data-stu-id="64868-130">Remarks</span></span>  
 <span data-ttu-id="64868-131">Avant de pouvoir connecter une source de données Oracle, l'administrateur système doit installer au préalable la version du fournisseur de données .NET pour Oracle qui prend en charge la récupération des données à partir de la base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="64868-131">Before you can connect an Oracle data source, the system administrator must have installed the version of the .NET Data Provider for Oracle that supports retrieving data from the Oracle database.</span></span> <span data-ttu-id="64868-132">Ce fournisseur de données doit être installé sur le même ordinateur que le Générateur de rapports, ainsi que sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="64868-132">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="64868-133">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="64868-133">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="64868-134">[Utilisation du fournisseur de données .NET Framework pour Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) sur msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="64868-134">[Using the .NET Framework Data Provider for Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) on msdn.microsoft.com</span></span>  
  
-   [<span data-ttu-id="64868-135">How to use Reporting Services to configure and to access an Oracle data source (en anglais)</span><span class="sxs-lookup"><span data-stu-id="64868-135">How to use Reporting Services to configure and to access an Oracle data source</span></span>](https://support.microsoft.com/kb/834305)  
  
-   [<span data-ttu-id="64868-136">Comment ajouter des autorisations pour le principal de sécurité SERVICE RÉSEAU</span><span class="sxs-lookup"><span data-stu-id="64868-136">How to add permissions for the NETWORK SERVICE security principal</span></span>](https://support.microsoft.com/kb/870668)  
  
###### <a name="alternate-data-extensions"></a><span data-ttu-id="64868-137">Autres extensions de données</span><span class="sxs-lookup"><span data-stu-id="64868-137">Alternate Data Extensions</span></span>  
 <span data-ttu-id="64868-138">Vous pouvez également récupérer des données à partir d'une base de données Oracle à l'aide d'un type de source de données OLE DB.</span><span class="sxs-lookup"><span data-stu-id="64868-138">You can also retrieve data from an Oracle database by using an OLE DB data source type.</span></span> <span data-ttu-id="64868-139">Pour plus d’informations, consultez [Type de connexion OLE DB &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="64868-139">For more information, see [OLE DB Connection Type &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span></span>  
  
###### <a name="report-models"></a><span data-ttu-id="64868-140">Modèles de rapport</span><span class="sxs-lookup"><span data-stu-id="64868-140">Report Models</span></span>  
 <span data-ttu-id="64868-141">Vous pouvez également créer des modèles basés sur une base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="64868-141">You can also create models based on an Oracle database.</span></span>  
  
###### <a name="platform-and-version-information"></a><span data-ttu-id="64868-142">Informations sur les plateformes et les versions</span><span class="sxs-lookup"><span data-stu-id="64868-142">Platform and Version Information</span></span>  
 <span data-ttu-id="64868-143">Pour plus d’informations sur la prise en charge des plateformes et des versions, consultez [Sources de données prises en charge par Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) dans la section [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] de la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [documentation en ligne](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="64868-143">For more information about platform and version support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="64868-144">Rubriques de procédures</span><span class="sxs-lookup"><span data-stu-id="64868-144">How-To Topics</span></span>  
 <span data-ttu-id="64868-145">Cette section contient des instructions pas à pas sur l'utilisation des connexions de données, des sources de données et des datasets.</span><span class="sxs-lookup"><span data-stu-id="64868-145">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="64868-146">Ajouter et vérifier une connexion de données ou une source de données &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-146">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="64868-147">Créer un dataset partagé ou incorporé &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-147">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="64868-148">Ajouter un filtre à un dataset &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-148">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 
  
##  <a name="related-sections"></a><a name="Related"></a><span data-ttu-id="64868-149">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="64868-149">Related Sections</span></span>  
 <span data-ttu-id="64868-150">Ces sections de la documentation fournissent des informations de fond d'ordre conceptuel sur les données de rapport, ainsi que des informations sur les procédures de définition, de personnalisation et d'utilisation des parties d'un rapport qui sont liées aux données.</span><span class="sxs-lookup"><span data-stu-id="64868-150">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="64868-151">Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-151">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="64868-152">Fournit une vue d'ensemble de l'accès aux données pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="64868-152">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="64868-153">Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="64868-153">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="64868-154">Fournit des informations sur les connexions de données et les sources de données.</span><span class="sxs-lookup"><span data-stu-id="64868-154">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="64868-155">Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-155">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="64868-156">Fournit des informations sur les datasets incorporés et partagés.</span><span class="sxs-lookup"><span data-stu-id="64868-156">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="64868-157">Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-157">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="64868-158">Fournit des informations sur la collection de champs de dataset générée par la requête.</span><span class="sxs-lookup"><span data-stu-id="64868-158">Provides information about the dataset field collection generated by the query.</span></span>  
  
 <span data-ttu-id="64868-159">[Sources de données prises en charge par Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) dans la section [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] de la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [documentation en ligne](https://go.microsoft.com/fwlink/?linkid=121312) de .</span><span class="sxs-lookup"><span data-stu-id="64868-159">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="64868-160">Fournit des informations détaillées sur la prise en charge des plateformes et des versions pour chaque extension de données.</span><span class="sxs-lookup"><span data-stu-id="64868-160">Provides in-depth information about platform and version support for each data extension.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="64868-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64868-161">See Also</span></span>  
 <span data-ttu-id="64868-162">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="64868-162">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="64868-163">[Filtrer, regrouper et trier les données &#40;Générateur de rapports et SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64868-163">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="64868-164">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64868-164">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
