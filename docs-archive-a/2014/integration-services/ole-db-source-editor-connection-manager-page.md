---
title: Éditeur de source de OLE DB (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613547"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="2f40a-102">Éditeur de source OLE DB (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="2f40a-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="2f40a-103">La page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source OLE DB** vous permet de sélectionner le gestionnaire de connexions OLE DB pour la source.</span><span class="sxs-lookup"><span data-stu-id="2f40a-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="2f40a-104">Cette page vous permet également de sélectionner une table ou une vue à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="2f40a-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f40a-105">Pour charger des données à partir d’une source de données qui utilise [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, utilisez une source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2f40a-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="2f40a-106">Vous ne pouvez pas utiliser une source Excel pour charger des données à partir d'une source de données Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="2f40a-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="2f40a-107">Pour plus d’informations, consultez [Configurer le gestionnaire de connexions OLE DB](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2f40a-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="2f40a-108">Pour charger des données à partir d'une source de données qui utilise [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 ou une version antérieure, utilisez une source Excel.</span><span class="sxs-lookup"><span data-stu-id="2f40a-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="2f40a-109">Pour plus d’informations, consultez [Éditeur de source Excel &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="2f40a-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f40a-110">La `CommandTimeout` propriété de la source de OLE DB n’est pas disponible dans l' **éditeur de source OLE DB**, mais elle peut être définie à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="2f40a-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="2f40a-111">Pour plus d’informations sur cette propriété, consultez la section sur la source Excel dans [Propriétés personnalisées OLE DB](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2f40a-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="2f40a-112">Pour en savoir plus sur la source OLE DB, consultez [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="2f40a-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="2f40a-113">Ouvrir l'Éditeur de source OLE (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="2f40a-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="2f40a-114">Ajoutez la source OLE DB au package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f40a-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2f40a-115">Cliquez avec le bouton droit sur le composant de la source, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="2f40a-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="2f40a-116">Cliquez sur **Gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="2f40a-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2f40a-117">Options statiques</span><span class="sxs-lookup"><span data-stu-id="2f40a-117">Static Options</span></span>  
 <span data-ttu-id="2f40a-118">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="2f40a-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="2f40a-119">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="2f40a-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="2f40a-120">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="2f40a-120">**New**</span></span>  
 <span data-ttu-id="2f40a-121">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="2f40a-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="2f40a-122">**Mode d'accès aux données**</span><span class="sxs-lookup"><span data-stu-id="2f40a-122">**Data access mode**</span></span>  
 <span data-ttu-id="2f40a-123">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="2f40a-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="2f40a-124">Option</span><span class="sxs-lookup"><span data-stu-id="2f40a-124">Option</span></span>|<span data-ttu-id="2f40a-125">Description</span><span class="sxs-lookup"><span data-stu-id="2f40a-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2f40a-126">Table ou vue</span><span class="sxs-lookup"><span data-stu-id="2f40a-126">Table or view</span></span>|<span data-ttu-id="2f40a-127">Permet de récupérer les données d'une table ou d'une vue dans la source de données OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2f40a-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="2f40a-128">Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="2f40a-128">Table name or view name variable</span></span>|<span data-ttu-id="2f40a-129">Spécifiez le nom de la table ou de la vue dans une variable.</span><span class="sxs-lookup"><span data-stu-id="2f40a-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="2f40a-130">**Informations connexes :** [Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="2f40a-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="2f40a-131">Commande SQL</span><span class="sxs-lookup"><span data-stu-id="2f40a-131">SQL command</span></span>|<span data-ttu-id="2f40a-132">Récupérez les données de la source de données OLE DB à l'aide d'une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="2f40a-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="2f40a-133">Commande SQL à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="2f40a-133">SQL command from variable</span></span>|<span data-ttu-id="2f40a-134">Spécifiez le texte de la requête SQL dans une variable.</span><span class="sxs-lookup"><span data-stu-id="2f40a-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="2f40a-135">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="2f40a-135">**Preview**</span></span>  
 <span data-ttu-id="2f40a-136">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Vue de données** .</span><span class="sxs-lookup"><span data-stu-id="2f40a-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="2f40a-137">Le mode**Aperçu** peut afficher jusqu’à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="2f40a-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f40a-138">Lorsque vous affichez l'aperçu des données, les colonnes ayant un type CLR défini par l'utilisateur ne contiennent pas de données.</span><span class="sxs-lookup"><span data-stu-id="2f40a-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="2f40a-139">À la place, les valeurs \<value too big to display> ou System.Byte[] sont affichées.</span><span class="sxs-lookup"><span data-stu-id="2f40a-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="2f40a-140">La première s’affiche lorsque le fournisseur SQL OLE DB accède à la source de données, la seconde lorsque vous utilisez le fournisseur [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2f40a-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="2f40a-141">Options dynamiques du mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="2f40a-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="2f40a-142">Mode d'accès aux données = Table ou vue</span><span class="sxs-lookup"><span data-stu-id="2f40a-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="2f40a-143">**Nom de la table ou de la vue**</span><span class="sxs-lookup"><span data-stu-id="2f40a-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="2f40a-144">Sélectionnez le nom de la table ou de la vue dans la liste de celles qui sont disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="2f40a-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="2f40a-145">Mode d'accès aux données = Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="2f40a-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="2f40a-146">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="2f40a-146">**Variable name**</span></span>  
 <span data-ttu-id="2f40a-147">Sélectionnez la variable qui contient le nom de la table ou de la vue.</span><span class="sxs-lookup"><span data-stu-id="2f40a-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="2f40a-148">Mode d'accès aux données = Commande SQL</span><span class="sxs-lookup"><span data-stu-id="2f40a-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="2f40a-149">**Texte de la commande SQL**</span><span class="sxs-lookup"><span data-stu-id="2f40a-149">**SQL command text**</span></span>  
 <span data-ttu-id="2f40a-150">Entrez le texte d’une requête SQL, générez la requête en cliquant sur **Générer une requête**ou recherchez le fichier qui contient le texte de la requête en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="2f40a-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="2f40a-151">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="2f40a-151">**Parameters**</span></span>  
 <span data-ttu-id="2f40a-152">Si vous avez entré une requête paramétrable en spécifiant ?</span><span class="sxs-lookup"><span data-stu-id="2f40a-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="2f40a-153">comme espace réservé de paramètre dans le texte de la requête, utilisez la boîte de dialogue **Définition des paramètres de la requête** pour mapper des paramètres d’entrée de la requête à des variables du package.</span><span class="sxs-lookup"><span data-stu-id="2f40a-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="2f40a-154">**Construire une requête**</span><span class="sxs-lookup"><span data-stu-id="2f40a-154">**Build query**</span></span>  
 <span data-ttu-id="2f40a-155">Utilisez la boîte de dialogue **Générateur de requêtes** pour construire la requête SQL visuellement.</span><span class="sxs-lookup"><span data-stu-id="2f40a-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="2f40a-156">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="2f40a-156">**Browse**</span></span>  
 <span data-ttu-id="2f40a-157">Dans la boîte de dialogue **Ouvrir** , localisez le fichier qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="2f40a-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="2f40a-158">**Analyser la requête**</span><span class="sxs-lookup"><span data-stu-id="2f40a-158">**Parse query**</span></span>  
 <span data-ttu-id="2f40a-159">Vérifiez la syntaxe du texte de la requête.</span><span class="sxs-lookup"><span data-stu-id="2f40a-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="2f40a-160">Mode d'accès aux données = Commande SQL à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="2f40a-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="2f40a-161">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="2f40a-161">**Variable name**</span></span>  
 <span data-ttu-id="2f40a-162">Sélectionnez la variable qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="2f40a-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f40a-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f40a-163">See Also</span></span>  
 <span data-ttu-id="2f40a-164">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2f40a-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2f40a-165">[Éditeur de source de OLE DB &#40;page colonnes&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2f40a-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="2f40a-166">[Éditeur de source de OLE DB &#40;page sortie d’erreur&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="2f40a-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="2f40a-167">[Extraire des données à l’aide de la source de OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="2f40a-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="2f40a-168">Gestionnaire de connexions OLE DB</span><span class="sxs-lookup"><span data-stu-id="2f40a-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
