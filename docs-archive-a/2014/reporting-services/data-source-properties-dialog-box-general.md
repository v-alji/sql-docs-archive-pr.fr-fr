---
title: Boîte de dialogue Propriétés de la source de données, général | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c79ad70cdd4dcb10e1abce1102fa39eef4c67461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600651"
---
# <a name="data-source-properties-dialog-box-general"></a><span data-ttu-id="7f645-102">Boîte de dialogue Propriétés de la source de données, Général</span><span class="sxs-lookup"><span data-stu-id="7f645-102">Data Source Properties Dialog Box, General</span></span>
  <span data-ttu-id="7f645-103">Sélectionnez **Général** dans la boîte de dialogue **Propriétés de la source de données** pour afficher et modifier les informations de connexion d'une source de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="7f645-103">Select **General** on the **Data Source Properties** dialog box to display and modify connection information for a data source in the report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f645-104">Options</span><span class="sxs-lookup"><span data-stu-id="7f645-104">Options</span></span>  
 <span data-ttu-id="7f645-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="7f645-105">**Name**</span></span>  
 <span data-ttu-id="7f645-106">Tapez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="7f645-106">Type the name of the data source.</span></span> <span data-ttu-id="7f645-107">Ce nom de source de données doit être unique dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="7f645-107">The data source name must be unique within the report.</span></span> <span data-ttu-id="7f645-108">Par défaut, un nom général, tel que DataSource1 ou DataSource2, est assigné à la source de données.</span><span class="sxs-lookup"><span data-stu-id="7f645-108">By default, a general name, such as DataSource1 or DataSource2, is assigned to the data source.</span></span>  
  
 <span data-ttu-id="7f645-109">**Connexion incorporée**</span><span class="sxs-lookup"><span data-stu-id="7f645-109">**Embedded connection**</span></span>  
 <span data-ttu-id="7f645-110">Sélectionnez cette option lorsque vous ne souhaitez pas utiliser une source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="7f645-110">Select this option when you do not want to use a shared data source.</span></span>  
  
 <span data-ttu-id="7f645-111">**Type**</span><span class="sxs-lookup"><span data-stu-id="7f645-111">**Type**</span></span>  
 <span data-ttu-id="7f645-112">Sélectionnez une extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="7f645-112">Select a data processing extension.</span></span> <span data-ttu-id="7f645-113">La liste affiche toutes les extensions inscrites.</span><span class="sxs-lookup"><span data-stu-id="7f645-113">The list displays all registered extensions.</span></span>  
  
 <span data-ttu-id="7f645-114">**Chaîne de connexion**</span><span class="sxs-lookup"><span data-stu-id="7f645-114">**Connection string**</span></span>  
 <span data-ttu-id="7f645-115">Entrez une chaîne de connexion pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="7f645-115">Enter a connection string for the data source.</span></span> <span data-ttu-id="7f645-116">Cliquez sur **Modifier** pour créer la chaîne de connexion à l'aide de la boîte de dialogue **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="7f645-116">Click **Edit** to build the connection string using the **Connection Properties** dialog box.</span></span> <span data-ttu-id="7f645-117">Cliquez sur le bouton **Expressions** (*fx*) pour modifier l’expression.</span><span class="sxs-lookup"><span data-stu-id="7f645-117">Click the **Expressions** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="7f645-118">**Utiliser une référence de source de données partagée**</span><span class="sxs-lookup"><span data-stu-id="7f645-118">**Use shared data source reference**</span></span>  
 <span data-ttu-id="7f645-119">Sélectionnez cette option pour créer un lien vers une source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="7f645-119">Select this option to link to a shared data source.</span></span> <span data-ttu-id="7f645-120">Sélectionnez une source de données partagée dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7f645-120">Select a shared data source from the drop-down list.</span></span> <span data-ttu-id="7f645-121">Pour modifier la source de données sélectionnée, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="7f645-121">To edit the selected data source, click **Edit**.</span></span> <span data-ttu-id="7f645-122">Si l'option **Utiliser une référence de source de données partagée** est sélectionnée, les options **Type** et **Chaîne de connexion** sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="7f645-122">If **Use shared data source reference** is selected, **Type** and **Connection string** are disabled.</span></span>  
  
 <span data-ttu-id="7f645-123">**Utiliser une transaction unique lors du traitement des requêtes**</span><span class="sxs-lookup"><span data-stu-id="7f645-123">**Use a single transaction when processing the queries**</span></span>  
 <span data-ttu-id="7f645-124">Sélectionnez cette option pour indiquer que les datasets qui utilisent cette source de données sont exécutés dans une transaction unique sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="7f645-124">Select this option to indicate that datasets that use this data source are run in a single transaction against the database.</span></span> <span data-ttu-id="7f645-125">Pour inclure des transactions pour les sous-rapports qui utilisent la même source de données, définissez **MergeTransactions** à **True** dans la section **Autre** du volet **Propriétés** du sous-rapport.</span><span class="sxs-lookup"><span data-stu-id="7f645-125">To include transactions for subreports that use the same data source, set **MergeTransactions** to **True** in the subreport's **Other** properties section of the **Properties** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f645-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f645-126">See Also</span></span>  
 <span data-ttu-id="7f645-127">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f645-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="7f645-128">[Créer une source de données incorporée ou partagée &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f645-128">[Create an Embedded or Shared Data Source &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="7f645-129">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7f645-129">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="7f645-130">Boîte de dialogue Propriétés de la source de données, Informations d'identification</span><span class="sxs-lookup"><span data-stu-id="7f645-130">Data Source Properties Dialog Box, Credentials</span></span>](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  
