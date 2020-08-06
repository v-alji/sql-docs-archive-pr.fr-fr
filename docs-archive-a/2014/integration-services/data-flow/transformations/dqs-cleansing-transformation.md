---
title: Nettoyage DQS, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601015"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="c6cca-102">Transformation de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="c6cca-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="c6cca-103">La transformation de nettoyage DQS utilise les services Data Quality Services (DQS) pour corriger des données provenant d'une source de données connectée en appliquant des règles approuvées créées pour la source de données connectée ou une source de données similaire.</span><span class="sxs-lookup"><span data-stu-id="c6cca-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="c6cca-104">Pour plus d'informations sur les règles de correction des données, consultez [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c6cca-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="c6cca-105">Pour plus d'informations sur DQS, consultez [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="c6cca-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="c6cca-106">Pour déterminer si les données doivent être corrigée, la transformation de nettoyage DQS traite les données d'une colonne d'entrée lorsque les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="c6cca-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="c6cca-107">La colonne est sélectionnée pour la correction des données.</span><span class="sxs-lookup"><span data-stu-id="c6cca-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="c6cca-108">Le type de données de la colonne est pris en charge pour la correction des données.</span><span class="sxs-lookup"><span data-stu-id="c6cca-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="c6cca-109">La colonne est mappée à un domaine dont le type de données est compatible.</span><span class="sxs-lookup"><span data-stu-id="c6cca-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="c6cca-110">La transformation inclut également une sortie d'erreur que vous configurez pour gérer les erreurs au niveau des lignes.</span><span class="sxs-lookup"><span data-stu-id="c6cca-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="c6cca-111">Pour configurer la sortie d'erreur, utilisez l' **Éditeur de transformation de nettoyage DQS**.</span><span class="sxs-lookup"><span data-stu-id="c6cca-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="c6cca-112">Vous pouvez inclure la [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) dans le flux de données pour identifier les lignes de données susceptibles d'être en double.</span><span class="sxs-lookup"><span data-stu-id="c6cca-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="c6cca-113">Projets de qualité des données et valeurs</span><span class="sxs-lookup"><span data-stu-id="c6cca-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="c6cca-114">Lorsque vous traitez des données avec la transformation de nettoyage DQS, un projet de nettoyage est créé sur le serveur de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="c6cca-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="c6cca-115">Vous utilisez le client de qualité des données pour gérer le projet.</span><span class="sxs-lookup"><span data-stu-id="c6cca-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="c6cca-116">En outre, vous pouvez utiliser le client de qualité des données pour importer les valeurs du projet dans un domaine de base de connaissances DQS.</span><span class="sxs-lookup"><span data-stu-id="c6cca-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="c6cca-117">Vous pouvez importer les valeurs uniquement vers un domaine (ou un domaine lié) configuré pour être utilisé par la transformation de nettoyage DQS.</span><span class="sxs-lookup"><span data-stu-id="c6cca-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c6cca-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c6cca-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c6cca-119">Ouvrir des projets Integration Services dans Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="c6cca-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="c6cca-120">Importer des valeurs de projet de nettoyage dans un domaine</span><span class="sxs-lookup"><span data-stu-id="c6cca-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="c6cca-121">Appliquer des règles de qualité des données à la source de données</span><span class="sxs-lookup"><span data-stu-id="c6cca-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="c6cca-122">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="c6cca-122">Related Content</span></span>  
  
-   [<span data-ttu-id="c6cca-123">Gérer &#40;ouvrir, déverrouiller, renommer et supprimer des&#41; un projet de qualité des données</span><span class="sxs-lookup"><span data-stu-id="c6cca-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="c6cca-124">Article [Nettoyage de données complexes à l'aide des domaines composites](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), sur social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c6cca-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
