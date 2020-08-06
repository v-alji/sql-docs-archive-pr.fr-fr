---
title: Éditeur de destination Excel (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610766"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="96b93-102">Éditeur de destination Excel (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="96b93-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="96b93-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination Excel** pour spécifier des informations sur la source de données et afficher un aperçu des résultats.</span><span class="sxs-lookup"><span data-stu-id="96b93-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="96b93-104">La destination Excel charge les données dans une feuille de calcul ou dans une plage (de cellules) nommée d'un classeur [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96b93-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96b93-105">La `CommandTimeout` propriété de la destination Excel n’est pas disponible dans l' **éditeur de destination Excel**, mais peut être définie à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="96b93-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="96b93-106">De plus, certaines options de chargement rapide sont uniquement disponibles dans la **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="96b93-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="96b93-107">Pour plus d'informations sur ces propriétés, consultez la section sur la destination Excel dans [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="96b93-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="96b93-108">Pour en savoir plus sur la destination Excel, consultez [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="96b93-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="96b93-109">Options statiques</span><span class="sxs-lookup"><span data-stu-id="96b93-109">Static Options</span></span>  
 <span data-ttu-id="96b93-110">**Gestionnaire de connexions Excel**</span><span class="sxs-lookup"><span data-stu-id="96b93-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="96b93-111">Sélectionnez un gestionnaire de connexions Excel existant dans la liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="96b93-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="96b93-112">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="96b93-112">**New**</span></span>  
 <span data-ttu-id="96b93-113">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Gestionnaire de connexions Excel** .</span><span class="sxs-lookup"><span data-stu-id="96b93-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="96b93-114">**Mode d'accès aux données**</span><span class="sxs-lookup"><span data-stu-id="96b93-114">**Data access mode**</span></span>  
 <span data-ttu-id="96b93-115">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="96b93-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="96b93-116">Option</span><span class="sxs-lookup"><span data-stu-id="96b93-116">Option</span></span>|<span data-ttu-id="96b93-117">Description</span><span class="sxs-lookup"><span data-stu-id="96b93-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="96b93-118">Table ou vue</span><span class="sxs-lookup"><span data-stu-id="96b93-118">Table or view</span></span>|<span data-ttu-id="96b93-119">Charge les données dans une feuille de calcul ou dans une plage nommée de la source de données Excel.</span><span class="sxs-lookup"><span data-stu-id="96b93-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="96b93-120">Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="96b93-120">Table name or view name variable</span></span>|<span data-ttu-id="96b93-121">Spécifiez le nom de la feuille de calcul ou de la plage dans une variable.</span><span class="sxs-lookup"><span data-stu-id="96b93-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="96b93-122">**Informations connexes** : [Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="96b93-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="96b93-123">Commande SQL</span><span class="sxs-lookup"><span data-stu-id="96b93-123">SQL command</span></span>|<span data-ttu-id="96b93-124">Charge les données dans la destination Excel à l'aide d'une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="96b93-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="96b93-125">**Nom de la feuille Excel**</span><span class="sxs-lookup"><span data-stu-id="96b93-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="96b93-126">Sélectionnez la destination Excel dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="96b93-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="96b93-127">Si la liste est vide, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="96b93-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="96b93-128">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="96b93-128">**New**</span></span>  
 <span data-ttu-id="96b93-129">Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue **Créer une table** .</span><span class="sxs-lookup"><span data-stu-id="96b93-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="96b93-130">Lorsque vous cliquez sur **OK**, la boîte de dialogue crée le fichier Excel vers lequel le **Gestionnaire de connexions Excel** pointe.</span><span class="sxs-lookup"><span data-stu-id="96b93-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="96b93-131">**Afficher les données existantes**</span><span class="sxs-lookup"><span data-stu-id="96b93-131">**View Existing Data**</span></span>  
 <span data-ttu-id="96b93-132">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Visualiser les résultats de la requête** .</span><span class="sxs-lookup"><span data-stu-id="96b93-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="96b93-133">L'aperçu peut afficher jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="96b93-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="96b93-134"> Si le **Gestionnaire de connexions Excel** que vous avez sélectionné pointe vers un fichier Excel qui n'existe pas, vous verrez un message d'erreur lorsque vous cliquez sur ce bouton.</span><span class="sxs-lookup"><span data-stu-id="96b93-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="96b93-135">Options dynamiques du mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="96b93-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="96b93-136">Mode d'accès aux données = Table ou vue</span><span class="sxs-lookup"><span data-stu-id="96b93-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="96b93-137">**Nom de la feuille Excel**</span><span class="sxs-lookup"><span data-stu-id="96b93-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="96b93-138">Sélectionnez le nom de la feuille de calcul ou de la plage nommée dans une liste des feuilles ou plages disponibles dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="96b93-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="96b93-139">Mode d'accès aux données = Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="96b93-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="96b93-140">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="96b93-140">**Variable name**</span></span>  
 <span data-ttu-id="96b93-141">Sélectionnez la variable contenant le nom de la feuille de calcul ou de la plage nommée.</span><span class="sxs-lookup"><span data-stu-id="96b93-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="96b93-142">Mode d'accès aux données = Commande SQL</span><span class="sxs-lookup"><span data-stu-id="96b93-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="96b93-143">**Texte de la commande SQL**</span><span class="sxs-lookup"><span data-stu-id="96b93-143">**SQL command text**</span></span>  
 <span data-ttu-id="96b93-144">Entrez le texte de la requête SQL, générez la requête en cliquant sur **Générer la requête**ou cliquez sur **Parcourir**pour accéder au fichier contenant le texte de la requête.</span><span class="sxs-lookup"><span data-stu-id="96b93-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="96b93-145">**Générer la requête**</span><span class="sxs-lookup"><span data-stu-id="96b93-145">**Build Query**</span></span>  
 <span data-ttu-id="96b93-146">Utilisez la boîte de dialogue **Générateur de requêtes** pour construire la requête SQL visuellement.</span><span class="sxs-lookup"><span data-stu-id="96b93-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="96b93-147">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="96b93-147">**Browse**</span></span>  
 <span data-ttu-id="96b93-148">Dans la boîte de dialogue **Ouvrir** , localisez le fichier qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="96b93-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="96b93-149">**Analyser la requête**</span><span class="sxs-lookup"><span data-stu-id="96b93-149">**Parse Query**</span></span>  
 <span data-ttu-id="96b93-150">Vérifiez la syntaxe du texte de la requête.</span><span class="sxs-lookup"><span data-stu-id="96b93-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b93-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96b93-151">See Also</span></span>  
 <span data-ttu-id="96b93-152">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="96b93-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="96b93-153">[Éditeur de destination Excel &#40;page Mappages&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="96b93-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="96b93-154">[Éditeur de destination Excel &#40;page sortie d’erreur&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="96b93-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="96b93-155">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="96b93-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
