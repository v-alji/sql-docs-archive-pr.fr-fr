---
title: Générateur de requêtes (Assistant rapport) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600618"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="eda31-102">Générateur de requêtes (Assistant Rapport)</span><span class="sxs-lookup"><span data-stu-id="eda31-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="eda31-103">Utilisez le générateur de requêtes pour spécifier une requête qui extrait un jeu de résultats à utiliser dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="eda31-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="eda31-104">Vous pouvez choisir l'un des deux générateurs de requêtes suivants :</span><span class="sxs-lookup"><span data-stu-id="eda31-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="eda31-105">Le générateur de requêtes textuel (par défaut) fournit un espace de travail simple permettant de spécifier une requête et d'afficher les résultats.</span><span class="sxs-lookup"><span data-stu-id="eda31-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="eda31-106">Vous pouvez spécifier plusieurs instructions [!INCLUDE[tsql](../includes/tsql-md.md)] , une syntaxe de requête ou de commande pour les extensions pour le traitement des données personnalisées et des requêtes spécifiées en tant qu'expressions.</span><span class="sxs-lookup"><span data-stu-id="eda31-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="eda31-107">Comme le générateur de requêtes générique n'effectue pas de prétraitement de la requête et peut accepter toute sorte de syntaxe de requête, il représente l'outil par défaut du Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="eda31-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="eda31-108">Le générateur de requêtes graphique propose une expérience visuelle plus riche.</span><span class="sxs-lookup"><span data-stu-id="eda31-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="eda31-109">Il est utilisé dans [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] et dans d’autres parties de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eda31-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eda31-110">Vous pouvez utiliser le générateur de requêtes graphique si vous ne créez pas d'expressions ou d'instructions SQL en plusieurs parties.</span><span class="sxs-lookup"><span data-stu-id="eda31-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="eda31-111">Pour basculer vers le générateur de requêtes graphique, actionnez le bouton bascule **Modifier en tant que texte** en haut à gauche de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="eda31-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="eda31-112">Vous pouvez également importer une requête à partir d'un autre rapport.</span><span class="sxs-lookup"><span data-stu-id="eda31-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="eda31-113">Options du générateur de requêtes</span><span class="sxs-lookup"><span data-stu-id="eda31-113">Query Builder Options</span></span>  
 <span data-ttu-id="eda31-114">**Modifier en tant que texte**</span><span class="sxs-lookup"><span data-stu-id="eda31-114">**Edit As Text**</span></span>  
 <span data-ttu-id="eda31-115">Bascule entre le concepteur de requêtes textuel et le concepteur de requêtes graphique, si les deux sont utilisables pour la requête.</span><span class="sxs-lookup"><span data-stu-id="eda31-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="eda31-116">**Importer**</span><span class="sxs-lookup"><span data-stu-id="eda31-116">**Import**</span></span>  
 <span data-ttu-id="eda31-117">Ouvre la boîte de dialogue **Importer une requête** et affiche les fichiers .rdl et .sql de tous les rapports disponibles.</span><span class="sxs-lookup"><span data-stu-id="eda31-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="eda31-118">Vous pouvez utiliser la requête importée telle quelle ou vous pouvez la modifier dans le générateur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="eda31-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="eda31-119">**! (Exécuter)**</span><span class="sxs-lookup"><span data-stu-id="eda31-119">**! (Run)**</span></span>  
 <span data-ttu-id="eda31-120">Exécute la requête et retourne un jeu de résultats si la requête est valide.</span><span class="sxs-lookup"><span data-stu-id="eda31-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="eda31-121">Notez que si la requête est une expression, vous ne pouvez pas l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="eda31-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="eda31-122">Pour vérifier une requête basée sur une expression, vous devez afficher un aperçu du rapport.</span><span class="sxs-lookup"><span data-stu-id="eda31-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="eda31-123">**Type de commande**</span><span class="sxs-lookup"><span data-stu-id="eda31-123">**Command type**</span></span>  
 <span data-ttu-id="eda31-124">Spécifie le type Text, StoredProcedure ou TableDirect.</span><span class="sxs-lookup"><span data-stu-id="eda31-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="eda31-125">La disponibilité d'un type de commande dépend de l'extension pour le traitement des données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="eda31-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="eda31-126">**Volet requête**</span><span class="sxs-lookup"><span data-stu-id="eda31-126">**Query pane**</span></span>  
 <span data-ttu-id="eda31-127">Tapez la requête</span><span class="sxs-lookup"><span data-stu-id="eda31-127">Type the query.</span></span>  
  
 <span data-ttu-id="eda31-128">**Volet résultats**</span><span class="sxs-lookup"><span data-stu-id="eda31-128">**Result pane**</span></span>  
 <span data-ttu-id="eda31-129">Affiche le jeu de résultats retourné par la requête.</span><span class="sxs-lookup"><span data-stu-id="eda31-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda31-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eda31-130">See Also</span></span>  
 <span data-ttu-id="eda31-131">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="eda31-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="eda31-132">Aide de l'Assistant Rapport</span><span class="sxs-lookup"><span data-stu-id="eda31-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
