---
title: Importer à partir d’une source de données relationnelle (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613677"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="3efc4-102">Importer à partir d'une source de données relationnelles (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="3efc4-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="3efc4-103">Vous pouvez importer des données provenant de diverses bases de données relationnelles à l’aide de l’Assistant Importation de table.</span><span class="sxs-lookup"><span data-stu-id="3efc4-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="3efc4-104">L’assistant est disponible dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dans le menu **Modèle** .</span><span class="sxs-lookup"><span data-stu-id="3efc4-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="3efc4-105">Pour vous connecter à une source de données, vous devez disposer du fournisseur approprié, installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3efc4-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="3efc4-106">Pour plus d’informations sur les fournisseurs et les sources de données pris en charge, consultez [Sources de données prises en charge &#40;SSAS Tabulaire&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3efc4-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="3efc4-107">L'Assistant Importation de table prend en charge l'importation des données à partir des sources de données suivantes :</span><span class="sxs-lookup"><span data-stu-id="3efc4-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="3efc4-108">**Bases de données relationnelles**</span><span class="sxs-lookup"><span data-stu-id="3efc4-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="3efc4-109">Base de données Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3efc4-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="3efc4-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="3efc4-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="3efc4-111">Base de données Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="3efc4-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="3efc4-112">Microsoft SQL Server Parallel Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="3efc4-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="3efc4-113">Oracle</span><span class="sxs-lookup"><span data-stu-id="3efc4-113">Oracle</span></span>  
  
-   <span data-ttu-id="3efc4-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="3efc4-114">Teradata</span></span>  
  
-   <span data-ttu-id="3efc4-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="3efc4-115">Sybase</span></span>  
  
-   <span data-ttu-id="3efc4-116">Informix</span><span class="sxs-lookup"><span data-stu-id="3efc4-116">Informix</span></span>  
  
-   <span data-ttu-id="3efc4-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="3efc4-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="3efc4-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="3efc4-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="3efc4-119">**Sources multidimensionnelles**</span><span class="sxs-lookup"><span data-stu-id="3efc4-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="3efc4-120">Cube Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3efc4-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="3efc4-121">L’Assistant Importation de table ne prend pas en charge l’importation des données d’un classeur [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] comme source de données.</span><span class="sxs-lookup"><span data-stu-id="3efc4-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="3efc4-122">Pour importer des données à partir d'une base de données</span><span class="sxs-lookup"><span data-stu-id="3efc4-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="3efc4-123">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="3efc4-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="3efc4-124">Dans la page **Connexion à une source de données** , sélectionnez le type de base de données à laquelle établir une connexion, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3efc4-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="3efc4-125">Suivez les étapes de l'Assistant Importation de table.</span><span class="sxs-lookup"><span data-stu-id="3efc4-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="3efc4-126">Dans les pages suivantes, vous pouvez sélectionner des vues et des tables spécifiques ou appliquer des filtres à l’aide de la page **Sélectionner des tables et des vues** ou en créant une requête SQL dans la page **Spécifier une requête SQL** .</span><span class="sxs-lookup"><span data-stu-id="3efc4-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efc4-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3efc4-127">See Also</span></span>  
 <span data-ttu-id="3efc4-128">[Importer des données &#40;&#41;tabulaire SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="3efc4-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="3efc4-129">Sources de données prises en charge &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="3efc4-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
