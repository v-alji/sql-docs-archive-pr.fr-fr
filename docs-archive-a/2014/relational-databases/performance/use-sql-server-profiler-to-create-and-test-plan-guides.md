---
title: Utiliser le Générateur de profils SQL Server pour créer et tester des repères de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- checking plan guides
- plan guides [SQL Server], testing
- plan guides [SQL Server], SQL Server Profiler
- matching queries to plan guides [SQL Server]
- testing plan guides
- SQL Server Profiler, plan guides
- plan guides [SQL Server], creating
- capturing query text [SQL Server]
- verifying plan guides
- Profiler [SQL Server Profiler], plan guides
- query-to-plan guide matching [SQL Server]
ms.assetid: 7018dbf0-1a1a-411a-88af-327bedf9cfbd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 543905343d74c9fbabe5f671d9021657ea5f76b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701076"
---
# <a name="use-sql-server-profiler-to-create-and-test-plan-guides"></a><span data-ttu-id="47b39-102">Utiliser le Générateur de profils SQL Server pour créer et tester des repères de plan</span><span class="sxs-lookup"><span data-stu-id="47b39-102">Use SQL Server Profiler to Create and Test Plan Guides</span></span>
  <span data-ttu-id="47b39-103">Lorsque vous créez un repère de plan, vous pouvez recourir à [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour capturer le texte de requête exact à utiliser dans l’argument *statement_text* de la procédure stockée **sp_create_plan_guide** .</span><span class="sxs-lookup"><span data-stu-id="47b39-103">When you are creating a plan guide, you can use [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to capture the exact query text for use in the *statement_text* argument of the **sp_create_plan_guide** stored procedure.</span></span> <span data-ttu-id="47b39-104">Ainsi, au moment de la compilation, le repère de plan correspondra à la requête.</span><span class="sxs-lookup"><span data-stu-id="47b39-104">This helps make sure that the plan guide will be matched to the query at compile time.</span></span> <span data-ttu-id="47b39-105">Une fois le repère de plan créé, vous pouvez également utiliser [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour tester la correspondance effective du repère de plan à la requête.</span><span class="sxs-lookup"><span data-stu-id="47b39-105">After the plan guide is created, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can also be used to test that the plan guide is, in fact, being matched to the query.</span></span> <span data-ttu-id="47b39-106">En règle générale, vous devez tester les repères de plan à l'aide de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] pour vérifier que la requête correspond au repère de plan.</span><span class="sxs-lookup"><span data-stu-id="47b39-106">Generally, you should test plan guides by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] to verify that your query is being matched to your plan guide.</span></span>  
  
## <a name="capturing-query-text-by-using-sql-server-profiler"></a><span data-ttu-id="47b39-107">Capture du texte de requête à l'aide du Générateur de profils SQL Server</span><span class="sxs-lookup"><span data-stu-id="47b39-107">Capturing Query Text by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="47b39-108">Si vous exécutez une requête et capturez le texte tel qu'il a été soumis à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'aide du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], vous pouvez créer un repère de plan de type SQL ou TEMPLATE qui corresponde exactement à ce texte.</span><span class="sxs-lookup"><span data-stu-id="47b39-108">If you run a query and capture the text exactly as it was submitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can create a plan guide of type SQL or TEMPLATE that will match the query text exactly.</span></span> <span data-ttu-id="47b39-109">Cela permet de faire en sorte que le repère de plan soit utilisé par l'optimiseur de requête.</span><span class="sxs-lookup"><span data-stu-id="47b39-109">This makes sure that the plan guide is used by the query optimizer.</span></span>  
  
 <span data-ttu-id="47b39-110">Imaginons la requête suivante soumise par une application en tant que traitement autonome :</span><span class="sxs-lookup"><span data-stu-id="47b39-110">Consider the following query that is submitted by an application as a stand-alone batch:</span></span>  
  
```  
SELECT COUNT(*) AS c  
FROM Sales.SalesOrderHeader AS h  
INNER JOIN Sales.SalesOrderDetail AS d  
  ON h.SalesOrderID = d.SalesOrderID  
WHERE h.OrderDate BETWEEN '20000101' and '20050101';  
```  
  
 <span data-ttu-id="47b39-111">Supposons que vous souhaitiez exécuter cette requête à l'aide d'une opération de jointure de fusion, mais que SHOWPLAN indique qu'elle n'est pas en train d'utiliser une jointure de fusion.</span><span class="sxs-lookup"><span data-stu-id="47b39-111">Suppose you want this query to execute using a merge join operation, but SHOWPLAN indicates that the query is not using a merge join.</span></span> <span data-ttu-id="47b39-112">Étant donné que vous ne pouvez pas modifier la requête directement dans l'application, vous créez un repère de plan pour spécifier que l'indicateur de requête MERGE JOIN soit ajouté à la requête au moment de la compilation.</span><span class="sxs-lookup"><span data-stu-id="47b39-112">You cannot change the query directly in the application, so instead you create a plan guide to specify that the MERGE JOIN query hint be appended to the query at compile time.</span></span>  
  
 <span data-ttu-id="47b39-113">Pour capturer le texte de la requête tel que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le reçoit, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="47b39-113">To capture the text of the query exactly as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] receives it, follow these steps:</span></span>  
  
1.  <span data-ttu-id="47b39-114">Démarrez une trace du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , en veillant à ce que le type d'événement **SQL:BatchStarting** soit sélectionné.</span><span class="sxs-lookup"><span data-stu-id="47b39-114">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making sure that the **SQL:BatchStarting** event type is selected.</span></span>  
  
2.  <span data-ttu-id="47b39-115">Faites exécuter la requête par l'application.</span><span class="sxs-lookup"><span data-stu-id="47b39-115">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="47b39-116">Suspendez la trace du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47b39-116">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="47b39-117">Cliquez sur l'événement **SQL:BatchStarting** qui correspond à la requête.</span><span class="sxs-lookup"><span data-stu-id="47b39-117">Click the **SQL:BatchStarting** event that corresponds to the query.</span></span>  
  
5.  <span data-ttu-id="47b39-118">Cliquez avec le bouton droit et sélectionnez **Extraire les données d’événement**.</span><span class="sxs-lookup"><span data-stu-id="47b39-118">Right-click and select **Extract Event Data**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="47b39-119">N'essayez pas de copier le texte du traitement en le sélectionnant dans le volet inférieur de la fenêtre de trace du Générateur de profils.</span><span class="sxs-lookup"><span data-stu-id="47b39-119">Do not try to copy the batch text by selecting it from the lower pane of the Profiler trace window.</span></span> <span data-ttu-id="47b39-120">Le repère de plan que vous créez risque alors de ne pas correspondre au traitement d'origine.</span><span class="sxs-lookup"><span data-stu-id="47b39-120">This might cause the plan guide that you create to not match the original batch.</span></span>  
  
6.  <span data-ttu-id="47b39-121">Enregistrez les données d'événement dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="47b39-121">Save the event data to a file.</span></span> <span data-ttu-id="47b39-122">Il s'agit du texte de traitement.</span><span class="sxs-lookup"><span data-stu-id="47b39-122">This is the batch text.</span></span>  
  
7.  <span data-ttu-id="47b39-123">Ouvrez le fichier du texte de traitement dans l'application Bloc-notes puis copiez le texte dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="47b39-123">Open the batch text file in Notepad and copy the text to the copy and paste buffer.</span></span>  
  
8.  <span data-ttu-id="47b39-124">Créez le repère de plan, puis collez le texte copié entre les guillemets (**''**) de l’argument **@stmt** .</span><span class="sxs-lookup"><span data-stu-id="47b39-124">Create the plan guide and paste the copied text inside the quotation marks (**''**) specified for the **@stmt** argument.</span></span> <span data-ttu-id="47b39-125">Vous devez placer les guillemets simples dans l’argument dans une séquence d’échappement **@stmt** en les faisant précéder d’un autre guillemet simple.</span><span class="sxs-lookup"><span data-stu-id="47b39-125">You must escape any single quotation marks in the **@stmt** argument by preceding them with another single quotation mark.</span></span> <span data-ttu-id="47b39-126">Faites attention de ne pas ajouter ou supprimer d'autres caractères lorsque vous insérez ces guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="47b39-126">Be careful not to add or remove any other characters when you insert these single quotation marks.</span></span> <span data-ttu-id="47b39-127">Par exemple, le littéral de date **'** 20000101 **'** doit être délimité de la façon suivante : **''** 20000101 **''** .</span><span class="sxs-lookup"><span data-stu-id="47b39-127">For example, the date literal **'** 20000101 **'** must be delimited as **''** 20000101 **''**.</span></span>  
  
 <span data-ttu-id="47b39-128">Voici le repère de plan :</span><span class="sxs-lookup"><span data-stu-id="47b39-128">Here is the plan guide:</span></span>  
  
```  
EXEC sp_create_plan_guide   
    @name = N'MyGuide1',  
    @stmt = N'<paste the text copied from the batch text file here>',  
    @type = N'SQL',  
    @module_or_batch = NULL,  
    @params = NULL,  
    @hints = N'OPTION (MERGE JOIN)';  
```  
  
## <a name="testing-plan-guides-by-using-sql-server-profiler"></a><span data-ttu-id="47b39-129">Test des repères de plan à l'aide du Générateur de profils SQL Server</span><span class="sxs-lookup"><span data-stu-id="47b39-129">Testing Plan Guides by Using SQL Server Profiler</span></span>  
 <span data-ttu-id="47b39-130">Pour vérifier qu'un repère de plan correspond à une requête, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="47b39-130">To verify that a plan guide is being matched to a query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="47b39-131">Démarrez une trace du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , en veillant à ce que le type d’événement **Showplan XML** , situé sous le nœud **Performances** , soit sélectionné.</span><span class="sxs-lookup"><span data-stu-id="47b39-131">Start a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] trace, making certain that the **Showplan XML** event type is selected (located under the **Performance** node).</span></span>  
  
2.  <span data-ttu-id="47b39-132">Faites exécuter la requête par l'application.</span><span class="sxs-lookup"><span data-stu-id="47b39-132">Have the application run the query.</span></span>  
  
3.  <span data-ttu-id="47b39-133">Suspendez la trace du [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47b39-133">Pause the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Trace.</span></span>  
  
4.  <span data-ttu-id="47b39-134">Recherchez l'événement **Showplan XML** de la requête affectée.</span><span class="sxs-lookup"><span data-stu-id="47b39-134">Find the **Showplan XML** event for the affected query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="47b39-135">L'événement **Showplan XML For Query Compile** ne peut pas être utilisé.</span><span class="sxs-lookup"><span data-stu-id="47b39-135">The **Showplan XML for Query Compile** event cannot be used.</span></span> <span data-ttu-id="47b39-136">**PlanGuideDB** n'existe pas dans cet événement.</span><span class="sxs-lookup"><span data-stu-id="47b39-136">**PlanGuideDB** does not exist in that event.</span></span>  
  
5.  <span data-ttu-id="47b39-137">Si le repère de plan est de type OBJECT ou SQL, vérifiez que l'événement **Showplan XML** contient les attributs **PlanGuideDB** et **PlanGuideName** du repère de plan qui doit correspondre à la requête.</span><span class="sxs-lookup"><span data-stu-id="47b39-137">If the plan guide is of type OBJECT or SQL, verify that the **Showplan XML** event contains the **PlanGuideDB** and **PlanGuideName** attributes for the plan guide that you expected to match the query.</span></span> <span data-ttu-id="47b39-138">Ou, dans le cas d'un repère de plan TEMPLATE, vérifiez que l'événement **Showplan XML** contient les attributs **TemplatePlanGuideDB** et **TemplatePlanGuideName** du repère de plan prévu.</span><span class="sxs-lookup"><span data-stu-id="47b39-138">Or, in the case of a TEMPLATE plan guide, verify that the **Showplan XML** event contains the **TemplatePlanGuideDB** and **TemplatePlanGuideName** attributes for the expected plan guide.</span></span> <span data-ttu-id="47b39-139">Cette opération vérifie que le repère de plan fonctionne.</span><span class="sxs-lookup"><span data-stu-id="47b39-139">This verifies that the plan guide is working.</span></span> <span data-ttu-id="47b39-140">Ces attributs sont contenus sous l'élément du plan **\<StmtSimple>** .</span><span class="sxs-lookup"><span data-stu-id="47b39-140">These attributes are contained under the **\<StmtSimple>** element of the plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b39-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47b39-141">See Also</span></span>  
 [<span data-ttu-id="47b39-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47b39-142">sp_create_plan_guide &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)  
  
  
