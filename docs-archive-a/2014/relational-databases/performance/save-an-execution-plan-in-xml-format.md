---
title: Enregistrer un plan d’exécution au format XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- XML query plans [SQL Server]
- opening execution plans
- XML Showplans [SQL Server]
- execution plans [SQL Server], saving
- saving execution plans
ms.assetid: c439e53b-56f3-4442-97c6-dabd48a203d8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 84ed341d186993ed77260e8361156b324c597839
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611732"
---
# <a name="save-an-execution-plan-in-xml-format"></a><span data-ttu-id="206f3-102">Enregistrer un plan d'exécution au format XML</span><span class="sxs-lookup"><span data-stu-id="206f3-102">Save an Execution Plan in XML Format</span></span>
  <span data-ttu-id="206f3-103">Utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour enregistrer un plan d'exécution en tant que fichier XML, puis pour l'ouvrir et le consulter.</span><span class="sxs-lookup"><span data-stu-id="206f3-103">Use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to save execution plans as an XML file, and to open them for viewing.</span></span>  
  
 <span data-ttu-id="206f3-104">Pour utiliser la fonctionnalité de plan d'exécution de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ou les options SET de Showplan XML, les utilisateurs doivent disposer des autorisations appropriées pour exécuter la requête [!INCLUDE[tsql](../../includes/tsql-md.md)] pour laquelle un plan d'exécution est généré et doivent obtenir l'autorisation SHOWPLAN pour toutes les bases de données référencées par la requête.</span><span class="sxs-lookup"><span data-stu-id="206f3-104">To use the execution plan feature in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or to use the XML Showplan SET options, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which an execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-save-a-query-plan-by-using-the-xml-showplan-set-options"></a><span data-ttu-id="206f3-105">Pour enregistrer un plan de requête avec les options SET de Showplan XML</span><span class="sxs-lookup"><span data-stu-id="206f3-105">To save a query plan by using the XML Showplan SET options</span></span>  
  
1.  <span data-ttu-id="206f3-106">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , ouvrez un éditeur de requête et connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="206f3-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] open a query editor and connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="206f3-107">Activez SHOWPLAN_XML avec l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="206f3-107">Turn SHOWPLAN_XML on with the following statement:</span></span>  
  
    ```  
    SET SHOWPLAN_XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="206f3-108">Pour activer STATISTICS XML, utilisez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="206f3-108">To turn STATISTICS XML on, use the following statement:</span></span>  
  
    ```  
    SET STATISTICS XML ON;  
    GO  
    ```  
  
     <span data-ttu-id="206f3-109">SHOWPLAN_XML génère des informations de plan d'exécution de requête de compilation pour une requête, mais sans exécuter cette dernière.</span><span class="sxs-lookup"><span data-stu-id="206f3-109">SHOWPLAN_XML generates compile-time query execution plan information for a query, but does not execute the query.</span></span> <span data-ttu-id="206f3-110">STATISTICS XML génère des informations de plan d'exécution de requête à l'exécution pour une requête et exécute cette dernière.</span><span class="sxs-lookup"><span data-stu-id="206f3-110">STATISTICS XML generates run-time query execution plan information for a query, and executes the query.</span></span>  
  
3.  <span data-ttu-id="206f3-111">Exécuter une requête.</span><span class="sxs-lookup"><span data-stu-id="206f3-111">Execute a query.</span></span> <span data-ttu-id="206f3-112">Exemple :</span><span class="sxs-lookup"><span data-stu-id="206f3-112">Example:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SET SHOWPLAN_XML ON;  
    GO  
    -- Execute a query.  
    SELECT BusinessEntityID   
    FROM HumanResources.Employee  
    WHERE NationalIDNumber = '509647174';  
    GO  
    SET SHOWPLAN_XML OFF;  
    ```  
  
4.  <span data-ttu-id="206f3-113">Dans le volet **Résultats** , cliquez avec le bouton droit sur le **Plan d’exécution XML Microsoft SQL Server** contenant le plan de requête, puis cliquez sur **Enregistrer les résultats sous**.</span><span class="sxs-lookup"><span data-stu-id="206f3-113">In the **Results** pane, right-click the **Microsoft SQL Server XML Showplan** that contains the query plan, and then click **Save Results As**.</span></span>  
  
5.  <span data-ttu-id="206f3-114">Dans la boîte de dialogue **Enregistrer** \<Grid or Text> **les Résultats**, dans la boîte **Enregistrer comme type**, cliquez sur **Tous les fichiers (\*.\*)** .</span><span class="sxs-lookup"><span data-stu-id="206f3-114">In the **Save** \<Grid or Text> **Results** dialog box, in the **Save as type** box, click **All files (\*.\*)**.</span></span>  
  
6.  <span data-ttu-id="206f3-115">Dans la boîte **Nom de fichier**, fournissez un nom au format \<name**>.sqlplan\*\*, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="206f3-115">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-save-an-execution-plan-by-using-sql-server-management-studio-options"></a><span data-ttu-id="206f3-116">Pour enregistrer un plan d'exécution avec les options de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="206f3-116">To save an execution plan by using SQL Server Management Studio options</span></span>  
  
1.  <span data-ttu-id="206f3-117">Générez un plan d'exécution soit estimé soit réel au moyen de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="206f3-117">Generate either an estimated execution plan or an actual execution plan by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="206f3-118">Pour plus d’informations, consultez [Affichage du plan d’exécution estimé](display-the-estimated-execution-plan.md) ou [Afficher un plan d’exécution réel](display-an-actual-execution-plan.md).</span><span class="sxs-lookup"><span data-stu-id="206f3-118">For more information, see [Display the Estimated Execution Plan](display-the-estimated-execution-plan.md) or [Display an Actual Execution Plan](display-an-actual-execution-plan.md).</span></span>  
  
2.  <span data-ttu-id="206f3-119">Sous l’onglet **Plan d’exécution** du volet de résultats, cliquez avec le bouton droit sur le plan d’exécution graphique, puis choisissez **Enregistrer le plan d’exécution en tant que**.</span><span class="sxs-lookup"><span data-stu-id="206f3-119">In the **Execution plan** tab of the results pane, right-click the graphical execution plan, and choose **Save Execution Plan As**.</span></span>  
  
     <span data-ttu-id="206f3-120">Vous pouvez aussi choisir **Enregistrer le plan d’exécution en tant que** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="206f3-120">As an alternative, you can also choose **Save Execution Plan As** on the **File** menu.</span></span>  
  
3.  <span data-ttu-id="206f3-121">Dans la boîte de dialogue **Enregistrer sous**, assurez-vous que **Type de fichier** est défini à **Fichiers de plan d’exécution (\*.sqlplan)** .</span><span class="sxs-lookup"><span data-stu-id="206f3-121">In the **Save As** dialog box, make sure that the **Save as type** is set to **Execution Plan Files (\*.sqlplan)**.</span></span>  
  
4.  <span data-ttu-id="206f3-122">Dans la boîte **Nom de fichier**, fournissez un nom au format \<name**>.sqlplan\*\*, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="206f3-122">In the **File name** box provide a name, in the format \<name**>.sqlplan\*\*, and then click **Save**.</span></span>  
  
### <a name="to-open-a-saved-xml-query-plan-in-sql-server-management-studio"></a><span data-ttu-id="206f3-123">Pour ouvrir un plan de requête XML dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="206f3-123">To open a saved XML query plan in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="206f3-124">Dans le menu [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Fichier **de** , choisissez **Ouvrir**, puis cliquez sur **Fichier**.</span><span class="sxs-lookup"><span data-stu-id="206f3-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **File** menu, choose **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="206f3-125">Dans la boîte de dialogue **Ouvrir un fichier**, définissez **Types de fichiers** à **Fichiers de plan d’exécution (\*.sqlplan)** pour produire une liste filtrée des fichiers de plan de requête XML enregistrés.</span><span class="sxs-lookup"><span data-stu-id="206f3-125">In the **Open File** dialog box, set **Files of type** to **Execution Plan Files (\*.sqlplan)** to produce a filtered list of saved XML query plan files.</span></span>  
  
3.  <span data-ttu-id="206f3-126">Sélectionnez le fichier de plan de requête XML que vous voulez consulter, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="206f3-126">Select the XML query plan file that you want to view, and click **Open**.</span></span>  
  
     <span data-ttu-id="206f3-127">En guise d’alternative, dans l’Explorateur Windows, double-cliquez sur un fichier avec l’extension **.sqlplan**.</span><span class="sxs-lookup"><span data-stu-id="206f3-127">As an alternative, in Windows Explorer, double-click a file with extension **.sqlplan**.</span></span> <span data-ttu-id="206f3-128">Le plan s'ouvre dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="206f3-128">The plan opens in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="206f3-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="206f3-129">See Also</span></span>  
 <span data-ttu-id="206f3-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="206f3-130">[SET SHOWPLAN_XML &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-showplan-xml-transact-sql) </span></span>  
 [<span data-ttu-id="206f3-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="206f3-131">SET STATISTICS XML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-statistics-xml-transact-sql)  
  
  
