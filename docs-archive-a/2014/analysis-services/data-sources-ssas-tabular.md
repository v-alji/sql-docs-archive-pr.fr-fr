---
title: Sources de données (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702108"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="c9278-102">Sources de données (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="c9278-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="c9278-103">Les sources de données fournissent les données à inclure dans une solution de modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="c9278-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="c9278-104">Vous pouvez importer des données dans votre modèle à partir d'une grande variété de sources telles que des bases de données relationnelles, des flux de données, des sources de données multidimensionnelles, telles qu'un cube Analysis Services, et de fichiers texte comme un classeur Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c9278-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="c9278-105">Les rubriques de cette section fournissent des informations sur les types de sources de données à partir desquelles vous pouvez effectuer une importation, les différents types de données que vous pouvez importer et les tâches décrivant l'importation des données de ces sources.</span><span class="sxs-lookup"><span data-stu-id="c9278-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="c9278-106">Tâches et rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="c9278-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="c9278-107">Rubrique</span><span class="sxs-lookup"><span data-stu-id="c9278-107">Topic</span></span>|<span data-ttu-id="c9278-108">Description</span><span class="sxs-lookup"><span data-stu-id="c9278-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c9278-109">Sources de données prises en charge &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="c9278-110">Cette rubrique fournit des informations sur les différentes sources de données à partir desquelles vous pouvez importer des données.</span><span class="sxs-lookup"><span data-stu-id="c9278-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="c9278-111">Types de données pris en charge &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="c9278-112">Cette rubrique fournit des informations sur les différents types de données pris en charge dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="c9278-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="c9278-113">Emprunt d’identité &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="c9278-114">Cette rubrique contient des informations sur l'emprunt d'identité, qui fournissent des informations d'identification d'ouverture de session qui sont utilisées par Analysis Services lors de la connexion à une source de données pour importer et actualiser des données.</span><span class="sxs-lookup"><span data-stu-id="c9278-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="c9278-115">Importer des données &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="c9278-116">Les tâches de cette section décrivent comment importer des données de différentes sources de données.</span><span class="sxs-lookup"><span data-stu-id="c9278-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="c9278-117">Traiter les données &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="c9278-118">Les tâches de cette section expliquent comment traiter (actualiser) ou modifier des données qui ont déjà été importées dans un modèle.</span><span class="sxs-lookup"><span data-stu-id="c9278-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="c9278-119">Modifier une connexion à une source de données existante &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c9278-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="c9278-120">Explique comment modifier une connexion de source de données qui a déjà été créée et utilisée pour importer des données depuis une source.</span><span class="sxs-lookup"><span data-stu-id="c9278-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  
