---
title: Fournir une requête source (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611879"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="7d937-102">Fournir une requête source (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7d937-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="7d937-103">Utilisez la page **fournir une requête source** pour taper l’instruction SQL qui va générer les données à copier de la source de données vers la destination.</span><span class="sxs-lookup"><span data-stu-id="7d937-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="7d937-104">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7d937-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="7d937-105">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7d937-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="7d937-106">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="7d937-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="7d937-107">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="7d937-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="7d937-108">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="7d937-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="7d937-109">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7d937-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d937-110">Options</span><span class="sxs-lookup"><span data-stu-id="7d937-110">Options</span></span>  
 <span data-ttu-id="7d937-111">**Instruction SQL**</span><span class="sxs-lookup"><span data-stu-id="7d937-111">**SQL statement**</span></span>  
 <span data-ttu-id="7d937-112">Tapez une instruction de requête pour extraire des lignes de données sélectionnées de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="7d937-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="7d937-113">Par exemple, l'instruction de requête suivante extrait les données **SalesPersonID**, **SalesQuota**et **SalesYTD** de la base de données AdventureWorks pour le personnel commercial dont le pourcentage des commissions est supérieur à 1,5 %.</span><span class="sxs-lookup"><span data-stu-id="7d937-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="7d937-114">**Analyser**.</span><span class="sxs-lookup"><span data-stu-id="7d937-114">**Parse**</span></span>  
 <span data-ttu-id="7d937-115">Vérifie la syntaxe de l’instruction SQL affichée dans la zone de texte **Instruction SQL**.</span><span class="sxs-lookup"><span data-stu-id="7d937-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d937-116">Si le temps requis pour vérifier la syntaxe de l'instruction dépasse la valeur du délai d'attente de 30 secondes, l'analyse s'arrête et génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="7d937-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="7d937-117">Vous ne serez pas en mesure de dépasser cette page de l'Assistant tant que l'analyse n'aura pas réussi.</span><span class="sxs-lookup"><span data-stu-id="7d937-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="7d937-118">Une solution consiste à créer une vue de base de données basée sur la requête, puis à interroger la vue à partir de l'Assistant, au lieu d'entrer directement le texte de requête.</span><span class="sxs-lookup"><span data-stu-id="7d937-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="7d937-119">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="7d937-119">**Browse**</span></span>  
 <span data-ttu-id="7d937-120">Sélectionnez un fichier contenant une instruction SQL à l’aide de la boîte de dialogue **ouvrir** .</span><span class="sxs-lookup"><span data-stu-id="7d937-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="7d937-121">La sélection d'un fichier copie le texte dans la zone de texte **Instruction de requête** .</span><span class="sxs-lookup"><span data-stu-id="7d937-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
