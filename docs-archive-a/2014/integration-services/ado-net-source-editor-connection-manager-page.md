---
title: Éditeur de source ADO NET (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705364"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="a8113-102">Éditeur de source ADO NET (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="a8113-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="a8113-103">La page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source ADO NET** permet de sélectionner le gestionnaire de connexions [!INCLUDE[vstecado](../includes/vstecado-md.md)] pour la source.</span><span class="sxs-lookup"><span data-stu-id="a8113-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="a8113-104">Cette page vous permet également de sélectionner une table ou une vue à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a8113-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="a8113-105">Pour en savoir plus sur la source ADO NET, consultez [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="a8113-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="a8113-106">**Pour ouvrir la page Gestionnaire de connexions**</span><span class="sxs-lookup"><span data-stu-id="a8113-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="a8113-107">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui possède la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="a8113-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="a8113-108">Sous l’onglet **Flux de données** , double-cliquez sur la source ADO NET.</span><span class="sxs-lookup"><span data-stu-id="a8113-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="a8113-109">Dans **l’Éditeur de source ADO NET**, cliquez sur **Gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="a8113-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="a8113-110">Options statiques</span><span class="sxs-lookup"><span data-stu-id="a8113-110">Static Options</span></span>  
 <span data-ttu-id="a8113-111">**Gestionnaire de connexions ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="a8113-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="a8113-112">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a8113-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="a8113-113">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="a8113-113">**New**</span></span>  
 <span data-ttu-id="a8113-114">Créez un gestionnaire de connexions à partir de la boîte de dialogue **Configurer le gestionnaire de connexions ADO.NET** .</span><span class="sxs-lookup"><span data-stu-id="a8113-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="a8113-115">**Mode d'accès aux données**</span><span class="sxs-lookup"><span data-stu-id="a8113-115">**Data access mode**</span></span>  
 <span data-ttu-id="a8113-116">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="a8113-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="a8113-117">Option</span><span class="sxs-lookup"><span data-stu-id="a8113-117">Option</span></span>|<span data-ttu-id="a8113-118">Description</span><span class="sxs-lookup"><span data-stu-id="a8113-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a8113-119">Table ou vue</span><span class="sxs-lookup"><span data-stu-id="a8113-119">Table or view</span></span>|<span data-ttu-id="a8113-120">Permet de récupérer les données d’une table ou d’une vue dans la source de données [!INCLUDE[vstecado](../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8113-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="a8113-121">Commande SQL</span><span class="sxs-lookup"><span data-stu-id="a8113-121">SQL command</span></span>|<span data-ttu-id="a8113-122">Permet de récupérer les données auprès de la source de données [!INCLUDE[vstecado](../includes/vstecado-md.md)] à l’aide d’une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="a8113-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="a8113-123">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="a8113-123">**Preview**</span></span>  
 <span data-ttu-id="a8113-124">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Vue de données** .</span><span class="sxs-lookup"><span data-stu-id="a8113-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="a8113-125">Le mode**Aperçu** peut afficher jusqu’à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="a8113-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a8113-126">Lorsque vous affichez l'aperçu des données, les colonnes ayant un type CLR défini par l'utilisateur ne contiennent pas de données.</span><span class="sxs-lookup"><span data-stu-id="a8113-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="a8113-127">À la place, les valeurs \<value too big to display> ou System.Byte[] sont affichées.</span><span class="sxs-lookup"><span data-stu-id="a8113-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="a8113-128">La première s'affiche lorsque le fournisseur [!INCLUDE[vstecado](../includes/vstecado-md.md)] accède à la source de données ; la seconde lorsque vous utilisez le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8113-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="a8113-129">Options dynamiques du mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="a8113-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="a8113-130">Mode d'accès aux données = Table ou vue</span><span class="sxs-lookup"><span data-stu-id="a8113-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="a8113-131">**Nom de la table ou de la vue**</span><span class="sxs-lookup"><span data-stu-id="a8113-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="a8113-132">Sélectionnez le nom de la table ou de la vue dans la liste de celles qui sont disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="a8113-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="a8113-133">Mode d'accès aux données = Commande SQL</span><span class="sxs-lookup"><span data-stu-id="a8113-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="a8113-134">**Texte de la commande SQL**</span><span class="sxs-lookup"><span data-stu-id="a8113-134">**SQL command text**</span></span>  
 <span data-ttu-id="a8113-135">Entrez le texte d’une requête SQL, générez la requête en cliquant sur **Générer une requête**ou recherchez le fichier qui contient le texte de la requête en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="a8113-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="a8113-136">**Construire une requête**</span><span class="sxs-lookup"><span data-stu-id="a8113-136">**Build query**</span></span>  
 <span data-ttu-id="a8113-137">Utilisez la boîte de dialogue **Générateur de requêtes** pour construire la requête SQL visuellement.</span><span class="sxs-lookup"><span data-stu-id="a8113-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="a8113-138">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="a8113-138">**Browse**</span></span>  
 <span data-ttu-id="a8113-139">Dans la boîte de dialogue **Ouvrir** , localisez le fichier qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="a8113-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8113-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a8113-140">See Also</span></span>  
 <span data-ttu-id="a8113-141">[Éditeur de source ADO NET &#40;page colonnes&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="a8113-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="a8113-142">[Éditeur de source ADO NET &#40;page sortie d’erreur&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a8113-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="a8113-143">Gestionnaire de connexions ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8113-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
