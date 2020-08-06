---
title: Éditeur de destination SQL (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604044"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="52202-102">Éditeur de destination SQL (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="52202-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="52202-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination SQL** pour spécifier des informations sur la source de données et afficher un aperçu des résultats.</span><span class="sxs-lookup"><span data-stu-id="52202-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="52202-104">La [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination charge les données dans des tables ou des vues d’une [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="52202-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="52202-105">Pour en savoir plus sur la destination pour SQL Server, consultez [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="52202-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="52202-106">Options</span><span class="sxs-lookup"><span data-stu-id="52202-106">Options</span></span>  
 <span data-ttu-id="52202-107">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="52202-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="52202-108">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une connexion en cliquant sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="52202-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="52202-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="52202-109">**New**</span></span>  
 <span data-ttu-id="52202-110">Crée une connexion en utilisant la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="52202-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="52202-111">**Utiliser une table ou une vue**</span><span class="sxs-lookup"><span data-stu-id="52202-111">**Use a table or view**</span></span>  
 <span data-ttu-id="52202-112">Sélectionnez une table ou une vue existante dans la liste, ou créez une connexion en cliquant sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="52202-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="52202-113">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="52202-113">**New**</span></span>  
 <span data-ttu-id="52202-114">Utilisez la boîte de dialogue **Créer une table** pour créer une table.</span><span class="sxs-lookup"><span data-stu-id="52202-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52202-115">Quand vous cliquez sur **Nouvelle**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] génère une instruction CREATE TABLE par défaut, basée sur la source de données connectée.</span><span class="sxs-lookup"><span data-stu-id="52202-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="52202-116">Cette instruction CREATE TABLE par défaut n'inclut pas l'attribut FILESTREAM, même si la table source inclut une colonne dans laquelle l'attribut FILESTREAM est déclaré.</span><span class="sxs-lookup"><span data-stu-id="52202-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="52202-117">Pour exécuter un composant [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] avec l'attribut FILESTREAM, implémentez d'abord le stockage FILESTREAM sur la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="52202-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="52202-118">Ajoutez ensuite l’attribut FILESTREAM à l’instruction CREATE TABLE dans la boîte de dialogue **Créer une table** .</span><span class="sxs-lookup"><span data-stu-id="52202-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="52202-119">Pour plus d’informations, consultez [Données blob &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52202-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="52202-120">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="52202-120">**Preview**</span></span>  
 <span data-ttu-id="52202-121">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Visualiser les résultats de la requête** .</span><span class="sxs-lookup"><span data-stu-id="52202-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="52202-122">L'aperçu peut afficher jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="52202-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52202-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="52202-123">See Also</span></span>  
 <span data-ttu-id="52202-124">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="52202-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="52202-125">[Éditeur de destination SQL &#40;page Mappages&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="52202-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="52202-126">[Éditeur de destination SQL &#40;page avancé&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="52202-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="52202-127">Charger des données en masse à l'aide de la destination SQL Server</span><span class="sxs-lookup"><span data-stu-id="52202-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
