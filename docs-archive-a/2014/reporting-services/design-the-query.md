---
title: Concevoir la requête | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703927"
---
# <a name="design-the-query"></a><span data-ttu-id="41c5e-102">Concevoir la requête</span><span class="sxs-lookup"><span data-stu-id="41c5e-102">Design the Query</span></span>
  <span data-ttu-id="41c5e-103">Utilisez cette page de l'Assistant Rapport pour créer une requête en la tapant manuellement, en utilisant le Générateur de requêtes pour créer une requête de manière interactive ou en important une requête à partir d'un autre rapport.</span><span class="sxs-lookup"><span data-stu-id="41c5e-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="41c5e-104">Le type de source de données sélectionné dans la page Sélectionner la source de données, à la page précédente de l'Assistant Rapport, détermine la requête que vous pouvez spécifier dans cette page.</span><span class="sxs-lookup"><span data-stu-id="41c5e-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="41c5e-105">Par exemple, si le type de source de données est [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous pouvez entrer des [!INCLUDE[tsql](../includes/tsql-md.md)] instructions ou des noms de procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="41c5e-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="41c5e-106">Si le type de source de données est [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , le volet requête est désactivé et vous ne pouvez pas entrer de requête directement.</span><span class="sxs-lookup"><span data-stu-id="41c5e-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="41c5e-107">Vous pouvez spécifier la requête en utilisant le Générateur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="41c5e-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41c5e-108">Options</span><span class="sxs-lookup"><span data-stu-id="41c5e-108">Options</span></span>  
 <span data-ttu-id="41c5e-109">**Chaîne de requête**</span><span class="sxs-lookup"><span data-stu-id="41c5e-109">**Query string**</span></span>  
 <span data-ttu-id="41c5e-110">Tapez une requête qui extrait les données que vous voulez utiliser dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="41c5e-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="41c5e-111">**Générateur de requêtes**</span><span class="sxs-lookup"><span data-stu-id="41c5e-111">**Query Builder**</span></span>  
 <span data-ttu-id="41c5e-112">Cliquez sur **Générateur de requêtes** pour ouvrir un concepteur de requêtes pour la source de données ou pour importer une requête à partir d’un autre rapport.</span><span class="sxs-lookup"><span data-stu-id="41c5e-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="41c5e-113">Pour plus d'informations sur les concepteurs de requêtes, consultez [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="41c5e-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41c5e-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="41c5e-114">Example</span></span>  
 <span data-ttu-id="41c5e-115">Pour le type de source de données **Microsoft SQL Server**, la requête suivante extrait une liste des noms de la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] table de base de données `Person` .</span><span class="sxs-lookup"><span data-stu-id="41c5e-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="41c5e-116">Pour le type de source de données **Microsoft SQL Server**, la requête suivante exécute la [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procédure stockée `uspGetEmployeeManagers` pour l’employé dont le numéro d’identification est 1 :</span><span class="sxs-lookup"><span data-stu-id="41c5e-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="41c5e-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41c5e-117">See Also</span></span>  
 <span data-ttu-id="41c5e-118">[Aide de l’Assistant Rapport](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="41c5e-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="41c5e-119">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="41c5e-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="41c5e-120">Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="41c5e-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
