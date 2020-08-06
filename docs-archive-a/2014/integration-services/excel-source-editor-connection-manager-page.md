---
title: Éditeur de source Excel (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610750"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="036df-102">Éditeur de source Excel (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="036df-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="036df-103">Le nœud **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source Excel** vous permet de sélectionner le classeur [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] de la source à utiliser.</span><span class="sxs-lookup"><span data-stu-id="036df-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="036df-104">La source Excel lit les données à partir d'une feuille de calcul ou d'une plage nommée dans un classeur existant.</span><span class="sxs-lookup"><span data-stu-id="036df-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="036df-105">La `CommandTimeout` propriété de la source Excel n’est pas disponible dans l **'éditeur de source Excel**, mais elle peut être définie à l’aide de l' **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="036df-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="036df-106">Pour plus d’informations sur cette propriété, consultez la section sur la source Excel dans [Propriétés personnalisées d’Excel](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="036df-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="036df-107">Pour en savoir plus sur la source Excel, consultez [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="036df-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="036df-108">Options statiques</span><span class="sxs-lookup"><span data-stu-id="036df-108">Static Options</span></span>  
 <span data-ttu-id="036df-109">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="036df-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="036df-110">Sélectionnez un gestionnaire de connexions Excel existant dans la liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="036df-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="036df-111">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="036df-111">**New**</span></span>  
 <span data-ttu-id="036df-112">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Gestionnaire de connexions Excel** .</span><span class="sxs-lookup"><span data-stu-id="036df-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="036df-113">**Mode d'accès aux données**</span><span class="sxs-lookup"><span data-stu-id="036df-113">**Data access mode**</span></span>  
 <span data-ttu-id="036df-114">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="036df-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="036df-115">Valeur</span><span class="sxs-lookup"><span data-stu-id="036df-115">Value</span></span>|<span data-ttu-id="036df-116">Description</span><span class="sxs-lookup"><span data-stu-id="036df-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="036df-117">Table ou vue</span><span class="sxs-lookup"><span data-stu-id="036df-117">Table or view</span></span>|<span data-ttu-id="036df-118">Récupérez des données à partir d'une feuille de calcul ou d'une plage nommée dans le fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="036df-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="036df-119">Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="036df-119">Table name or view name variable</span></span>|<span data-ttu-id="036df-120">Spécifiez le nom de la feuille de calcul ou de la plage dans une variable.</span><span class="sxs-lookup"><span data-stu-id="036df-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="036df-121">**Informations connexes :** [Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="036df-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="036df-122">Commande SQL</span><span class="sxs-lookup"><span data-stu-id="036df-122">SQL command</span></span>|<span data-ttu-id="036df-123">Récupérez des données à partir du fichier Excel à l'aide d'une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="036df-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="036df-124">Pour plus d’informations sur la syntaxe de la requête, consultez [Source Excel](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="036df-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="036df-125">Commande SQL à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="036df-125">SQL command from variable</span></span>|<span data-ttu-id="036df-126">Spécifiez le texte de la requête SQL dans une variable.</span><span class="sxs-lookup"><span data-stu-id="036df-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="036df-127">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="036df-127">**Preview**</span></span>  
 <span data-ttu-id="036df-128">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Vue de données** .</span><span class="sxs-lookup"><span data-stu-id="036df-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="036df-129">L'aperçu peut afficher jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="036df-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="036df-130">Options dynamiques du mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="036df-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="036df-131">Mode d'accès aux données = Table ou vue</span><span class="sxs-lookup"><span data-stu-id="036df-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="036df-132">**Nom de la feuille Excel**</span><span class="sxs-lookup"><span data-stu-id="036df-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="036df-133">Sélectionnez le nom de la feuille de calcul ou de la plage nommée dans la liste des éléments disponibles dans le classeur Excel.</span><span class="sxs-lookup"><span data-stu-id="036df-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="036df-134">Mode d'accès aux données = Variable de nom de table ou de vue</span><span class="sxs-lookup"><span data-stu-id="036df-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="036df-135">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="036df-135">**Variable name**</span></span>  
 <span data-ttu-id="036df-136">Sélectionnez la variable contenant le nom de la feuille de calcul ou de la plage nommée.</span><span class="sxs-lookup"><span data-stu-id="036df-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="036df-137">Mode d'accès aux données = Commande SQL</span><span class="sxs-lookup"><span data-stu-id="036df-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="036df-138">**Texte de la commande SQL**</span><span class="sxs-lookup"><span data-stu-id="036df-138">**SQL command text**</span></span>  
 <span data-ttu-id="036df-139">Entrez le texte d’une requête SQL, créez la requête en cliquant sur **Générer une requête**ou parcourez l’arborescence jusqu’au fichier qui contient le texte de la requête en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="036df-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="036df-140">**Paramètres**</span><span class="sxs-lookup"><span data-stu-id="036df-140">**Parameters**</span></span>  
 <span data-ttu-id="036df-141">Si vous avez entré une requête paramétrable en spécifiant ?</span><span class="sxs-lookup"><span data-stu-id="036df-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="036df-142">comme espace réservé de paramètre dans le texte de la requête, utilisez la boîte de dialogue **Définition des paramètres de la requête** pour mapper des paramètres d’entrée de la requête à des variables du package.</span><span class="sxs-lookup"><span data-stu-id="036df-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="036df-143">**Construire une requête**</span><span class="sxs-lookup"><span data-stu-id="036df-143">**Build query**</span></span>  
 <span data-ttu-id="036df-144">Utilisez la boîte de dialogue **Générateur de requêtes** pour construire la requête SQL visuellement.</span><span class="sxs-lookup"><span data-stu-id="036df-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="036df-145">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="036df-145">**Browse**</span></span>  
 <span data-ttu-id="036df-146">Dans la boîte de dialogue **Ouvrir** , localisez le fichier qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="036df-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="036df-147">**Analyser la requête**</span><span class="sxs-lookup"><span data-stu-id="036df-147">**Parse query**</span></span>  
 <span data-ttu-id="036df-148">Vérifiez la syntaxe du texte de la requête.</span><span class="sxs-lookup"><span data-stu-id="036df-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="036df-149">Mode d'accès aux données = Commande SQL à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="036df-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="036df-150">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="036df-150">**Variable name**</span></span>  
 <span data-ttu-id="036df-151">Sélectionnez la variable qui contient le texte de la requête SQL.</span><span class="sxs-lookup"><span data-stu-id="036df-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036df-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="036df-152">See Also</span></span>  
 <span data-ttu-id="036df-153">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="036df-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="036df-154">[Éditeur de source Excel &#40;page colonnes&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="036df-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="036df-155">[Éditeur de source Excel &#40;page sortie d’erreur&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="036df-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="036df-156">[Gestionnaire de connexions Excel](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="036df-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="036df-157">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="036df-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
