---
title: Spécifier le comportement du paramétrage de requêtes grâce aux repères de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- TEMPLATE plan guide
- PARAMETERIZATION FORCED option
- PARAMETERIZATION option
- PARAMETERIZATION SIMPLE option
- parameterization [SQL Server]
- overriding parameterization behavior
- plan guides [SQL Server], parameterization
- parameterized queries [SQL Server]
ms.assetid: f0f738ff-2819-4675-a8c8-1eb6c210a7e6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f595b9f0e0a6d7bceffc5cb283c60b6f40e025b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614558"
---
# <a name="specify-query-parameterization-behavior-by-using-plan-guides"></a><span data-ttu-id="4639b-102">Spécifier le comportement du paramétrage de requêtes grâce aux repères de plan</span><span class="sxs-lookup"><span data-stu-id="4639b-102">Specify Query Parameterization Behavior by Using Plan Guides</span></span>
  <span data-ttu-id="4639b-103">Si l'option de base de données PARAMETERIZATION a la valeur SIMPLE, il se peut que l'optimiseur de requête [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] opte pour le paramétrage des requêtes.</span><span class="sxs-lookup"><span data-stu-id="4639b-103">When the PARAMETERIZATION database option is set to SIMPLE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query optimizer may choose to parameterize the queries.</span></span> <span data-ttu-id="4639b-104">En d'autres termes, toute valeur littérale contenue dans une requête est substituée par des paramètres.</span><span class="sxs-lookup"><span data-stu-id="4639b-104">This means that any literal values that are contained in a query are substituted with parameters.</span></span> <span data-ttu-id="4639b-105">Ce processus s'appelle le paramétrage simple.</span><span class="sxs-lookup"><span data-stu-id="4639b-105">This process is referred to as simple parameterization.</span></span> <span data-ttu-id="4639b-106">Lorsque le paramétrage SIMPLE s'applique, vous ne pouvez pas décider des requêtes devant être paramétrables et de celles ne devant pas l'être.</span><span class="sxs-lookup"><span data-stu-id="4639b-106">When SIMPLE parameterization is in effect, you cannot control which queries are parameterized and which queries are not.</span></span> <span data-ttu-id="4639b-107">Vous pouvez cependant indiquer que toutes les requêtes d'une base de données soient paramétrables en affectant à l'option de base de données PARAMETERIZATION la valeur FORCED.</span><span class="sxs-lookup"><span data-stu-id="4639b-107">However, you can specify that all queries in a database be parameterized by setting the PARAMETERIZATION database option to FORCED.</span></span> <span data-ttu-id="4639b-108">Ce processus s'appelle le paramétrage forcé.</span><span class="sxs-lookup"><span data-stu-id="4639b-108">This process is referred to as forced parameterization.</span></span>  
  
 <span data-ttu-id="4639b-109">Vous pouvez outrepasser ce comportement de paramétrage d'une base de données par le biais de repères de plan des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="4639b-109">You can override the parameterization behavior of a database by using plan guides in the following ways:</span></span>  
  
-   <span data-ttu-id="4639b-110">Quand l'option de base de données PARAMETERIZATION a la valeur SIMPLE, vous pouvez spécifier que le paramétrage forcé doit être tenté sur une certaine classe de requêtes.</span><span class="sxs-lookup"><span data-stu-id="4639b-110">When the PARAMETERIZATION database option is set to SIMPLE, you can specify that forced parameterization is attempted on a certain class of queries.</span></span> <span data-ttu-id="4639b-111">Pour ce faire, créez un repère de plan TEMPLATE sur la forme paramétrable de la requête et spécifiez l’indicateur de requête PARAMETERIZATION FORCED dans la procédure stockée [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4639b-111">You do this by creating a TEMPLATE plan guide on the parameterized form of the query, and specifying the PARAMETERIZATION FORCED query hint in the [sp_create_plan_guide](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql) stored procedure.</span></span> <span data-ttu-id="4639b-112">Ce type de repère de plan peut être considéré comme un moyen de forcer le paramétrage sur une classe de requêtes seulement plutôt que sur toutes les requêtes.</span><span class="sxs-lookup"><span data-stu-id="4639b-112">You can consider this kind of plan guide as a way to enable forced parameterization only on a certain class of queries, instead of all queries.</span></span>  
  
-   <span data-ttu-id="4639b-113">Quand l'option de base de données PARAMETERIZATION a la valeur FORCED, vous pouvez spécifier que, pour une certaine classe de requêtes, seul un paramétrage simple est tenté, et non pas un paramétrage forcé.</span><span class="sxs-lookup"><span data-stu-id="4639b-113">When the PARAMETERIZATION database option is set to FORCED, you can specify that for a certain class of queries, only simple parameterization is attempted, not forced parameterization.</span></span> <span data-ttu-id="4639b-114">Pour ce faire, créez un repère de plan TEMPLATE sur la forme avec paramétrage forcé de la requête et spécifiez l’indicateur de requête PARAMETERIZATION SIMPLE dans la procédure stockée **sp_create_plan_guide**.</span><span class="sxs-lookup"><span data-stu-id="4639b-114">You do this by creating a TEMPLATE plan guide on the force-parameterized form of the query, and specifying the PARAMETERIZATION SIMPLE query hint in **sp_create_plan_guide**.</span></span>  
  
 <span data-ttu-id="4639b-115">Supposons la requête suivante portant sur la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4639b-115">Consider the following query on the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database:</span></span>  
  
```  
SELECT pi.ProductID, SUM(pi.Quantity) AS Total  
FROM Production.ProductModel AS pm   
    INNER JOIN Production.ProductInventory AS pi   
        ON pm.ProductModelID = pi.ProductID   
WHERE pi.ProductID = 101   
GROUP BY pi.ProductID, pi.Quantity HAVING SUM(pi.Quantity) > 50;  
```  
  
 <span data-ttu-id="4639b-116">Vous pouvez choisir de ne pas activer le paramétrage forcé de toutes les requêtes portant sur la base de données à condition d'en être l'administrateur.</span><span class="sxs-lookup"><span data-stu-id="4639b-116">As a database administrator, you have determined that you do not want to enable forced parameterization on all queries in the database.</span></span> <span data-ttu-id="4639b-117">En revanche, vous voulez éviter les coûts de compilation sur toutes les requêtes équivalentes dans leur syntaxe à la requête précédente, mais différant sur leurs valeurs littérales constantes uniquement.</span><span class="sxs-lookup"><span data-stu-id="4639b-117">However, you do want to avoid compilation costs on all queries that are syntactically equivalent to the previous query, but differ only in their constant literal values.</span></span> <span data-ttu-id="4639b-118">En d'autres termes, il peut être préférable que la requête soit paramétrable afin qu'un plan de requête correspondant à ce type de requête soit réutilisé.</span><span class="sxs-lookup"><span data-stu-id="4639b-118">In other words, you want the query to be parameterized so that a query plan for this kind of query is reused.</span></span> <span data-ttu-id="4639b-119">Dans ce cas, suivez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4639b-119">In this case, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="4639b-120">Récupérez la forme paramétrable de la requête.</span><span class="sxs-lookup"><span data-stu-id="4639b-120">Retrieve the parameterized form of the query.</span></span> <span data-ttu-id="4639b-121">La seule méthode sûre pour obtenir cette valeur et l’utiliser dans la procédure stockée **sp_create_plan_guide** consiste à passer par la procédure stockée système [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4639b-121">The only safe way to obtain this value for use in **sp_create_plan_guide** is by using the [sp_get_query_template](/sql/relational-databases/system-stored-procedures/sp-get-query-template-transact-sql) system stored procedure.</span></span>  
  
2.  <span data-ttu-id="4639b-122">Créez le repère de plan sur la forme paramétrable de la requête en spécifiant l'indicateur de requête PARAMETERIZATION FORCED.</span><span class="sxs-lookup"><span data-stu-id="4639b-122">Create the plan guide on the parameterized form of the query, specifying the PARAMETERIZATION FORCED query hint.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="4639b-123">Dans le cadre du paramétrage d'une requête, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affecte un type de données aux paramètres remplaçant les valeurs littérales, en fonction de la valeur et de la taille du littéral.</span><span class="sxs-lookup"><span data-stu-id="4639b-123">As part of parameterizing a query, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns a data type to the parameters that replace the literal values, depending on the value and size of the literal.</span></span> <span data-ttu-id="4639b-124">Le même processus se produit à la valeur des littéraux constants passés au **@stmt** paramètre de sortie de **sp_get_query_template**.</span><span class="sxs-lookup"><span data-stu-id="4639b-124">The same process occurs to the value of the constant literals passed to the **@stmt** output parameter of **sp_get_query_template**.</span></span> <span data-ttu-id="4639b-125">Étant donné que le type de données spécifié dans l' **@params** argument de **sp_create_plan_guide** doit correspondre à celui de la requête tel qu’il est paramétré par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devrez peut-être créer plusieurs repères de plan pour couvrir la plage complète des valeurs de paramètres possibles pour la requête.</span><span class="sxs-lookup"><span data-stu-id="4639b-125">Because the data type specified in the **@params** argument of **sp_create_plan_guide** must match that of the query as it is parameterized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you may have to create more than one plan guide to cover the complete range of possible parameter values for the query.</span></span>  
  
 <span data-ttu-id="4639b-126">Le script suivant peut être utilisé aussi bien pour obtenir la requête paramétrable que pour créer plus tard un repère de plan s'y rapportant :</span><span class="sxs-lookup"><span data-stu-id="4639b-126">The following script can be used both to obtain the parameterized query and then create a plan guide on it:</span></span>  
  
```  
DECLARE @stmt nvarchar(max);  
DECLARE @params nvarchar(max);  
EXEC sp_get_query_template   
    N'SELECT pi.ProductID, SUM(pi.Quantity) AS Total   
      FROM Production.ProductModel AS pm   
      INNER JOIN Production.ProductInventory AS pi ON pm.ProductModelID = pi.ProductID   
      WHERE pi.ProductID = 101   
      GROUP BY pi.ProductID, pi.Quantity   
      HAVING sum(pi.Quantity) > 50',  
    @stmt OUTPUT,   
    @params OUTPUT;  
EXEC sp_create_plan_guide   
    N'TemplateGuide1',   
    @stmt,   
    N'TEMPLATE',   
    NULL,   
    @params,   
    N'OPTION(PARAMETERIZATION FORCED)';  
```  
  
 <span data-ttu-id="4639b-127">De même, dans une base de données où le paramétrage forcé est déjà activé, vous pouvez vous assurer que la requête donnée en exemple et celles dont la syntaxe est équivalente, sauf pour leurs valeurs littérales constantes, sont paramétrables selon les règles du paramétrage simple.</span><span class="sxs-lookup"><span data-stu-id="4639b-127">Similarly, in a database in which forced parameterization is already enabled, you can make sure that the sample query, and others that are syntactically equivalent, except for their constant literal values, are parameterized according to the rules of simple parameterization.</span></span> <span data-ttu-id="4639b-128">Pour ce faire, spécifiez PARAMETERIZATION SIMPLE plutôt que PARAMETERIZATION FORCED dans la clause OPTION.</span><span class="sxs-lookup"><span data-stu-id="4639b-128">To do this, specify PARAMETERIZATION SIMPLE instead of PARAMETERIZATION FORCED in the OPTION clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4639b-129">Les repères de plan TEMPLATE font correspondre les instructions aux requêtes envoyées par traitements qui sont composées d'une seule instruction.</span><span class="sxs-lookup"><span data-stu-id="4639b-129">TEMPLATE plan guides match statements to queries submitted in batches that consist of a single statement only.</span></span> <span data-ttu-id="4639b-130">Les instructions à l'intérieur de traitements à instructions multiples ne peuvent pas être mises en correspondance avec les repères de plan TEMPLATE.</span><span class="sxs-lookup"><span data-stu-id="4639b-130">Statements inside multistatement batches are not eligible to be matched by TEMPLATE plan guides.</span></span>  
  
  
