---
title: Modèles DMX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a577e52-821d-4bd3-ba35-075a6be285c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79c8615933baf4fa3d80974daae91b4d1c7fa101
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613207"
---
# <a name="dmx-templates"></a><span data-ttu-id="f1626-102">Modèles DMX</span><span class="sxs-lookup"><span data-stu-id="f1626-102">DMX Templates</span></span>
  <span data-ttu-id="f1626-103">Les modèles d'exploration de données vous aident à créer rapidement des requêtes sophistiquées.</span><span class="sxs-lookup"><span data-stu-id="f1626-103">The data mining templates help you quickly build sophisticated queries.</span></span> <span data-ttu-id="f1626-104">Bien que la syntaxe générale des requêtes DMX soit bien documentée, l'utilisation de modèles facilite leur création car il suffit de cliquer et pointer sur les arguments et les sources de données.</span><span class="sxs-lookup"><span data-stu-id="f1626-104">Although the general syntax for DMX queries is well documented, using the templates makes it easier to build queries by clicking and pointing to arguments and data sources.</span></span>  
  
## <a name="using-the-templates"></a><span data-ttu-id="f1626-105">Utilisation des modèles</span><span class="sxs-lookup"><span data-stu-id="f1626-105">Using the Templates</span></span>  
  
1.  <span data-ttu-id="f1626-106">Dans le client d’exploration de données pour Excel, cliquez sur **requête**.</span><span class="sxs-lookup"><span data-stu-id="f1626-106">In the Data Mining Client for Excel, click **Query**.</span></span>  
  
2.  <span data-ttu-id="f1626-107">Dans la page de **démarrage** de l’Assistant, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="f1626-107">On the wizard **Start** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="f1626-108">Sur la page, **Sélectionnez modèle**, puis cliquez sur **avancé**.</span><span class="sxs-lookup"><span data-stu-id="f1626-108">On the page, **Select Model**, click **Advanced**.</span></span>  
  
     <span data-ttu-id="f1626-109">**Conseil :** Si vous envisagez de créer une requête de prédiction sur un modèle, vous pouvez d’abord sélectionner le modèle, puis cliquer sur **avancé**pour préremplir le modèle avec le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="f1626-109">**Tip:** If you are going to create a prediction query on a model, you can select the model first, and then click **Advanced**, to prepopulate the template with the model name.</span></span>  
  
4.  <span data-ttu-id="f1626-110">Dans l' **éditeur de requêtes avancé d’exploration de données**, cliquez sur **modèles DMX**, puis sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="f1626-110">In the **Data Mining Advanced Query Editor**, click **DMX Templates**, and select a template.</span></span>  
  
5.  <span data-ttu-id="f1626-111">Appuyez sur ENTRÉE pour charger le modèle dans le volet de Requête DMX.</span><span class="sxs-lookup"><span data-stu-id="f1626-111">Press ENTER to load the template into the DMX Query pane.</span></span>  
  
6.  <span data-ttu-id="f1626-112">Cliquez ensuite sur les liens dans le modèle, et quand la boîte de dialogue apparaît, sélectionnez un résultat, un modèle, ou un paramètre approprié.</span><span class="sxs-lookup"><span data-stu-id="f1626-112">Continue clicking the links in the template, and as the dialog box appears, select an appropriate output, model, or parameter.</span></span>  
  
     <span data-ttu-id="f1626-113">Pour les requêtes de prédiction, choisissez le dataset d'entrée en premier, puis mappez les colonnes.</span><span class="sxs-lookup"><span data-stu-id="f1626-113">For prediction queries, choose the input dataset first, and then map the columns.</span></span>  
  
7.  <span data-ttu-id="f1626-114">Cliquez sur **modifier la requête** pour basculer vers l’affichage de l’éditeur de texte et modifier manuellement la requête.</span><span class="sxs-lookup"><span data-stu-id="f1626-114">Click **Edit Query** to switch to text editor view and manually change the query.</span></span>  
  
     <span data-ttu-id="f1626-115">Sachez cependant que si vous passez d'un affichage à l'autre lorsque vous utilisez l'éditeur de requêtes, toutes les informations figurant dans l'affichage précédent seront effacées.</span><span class="sxs-lookup"><span data-stu-id="f1626-115">Be aware, however, that if you switch views when working in the query editor, any information that you had in the previous view will be cleared.</span></span> <span data-ttu-id="f1626-116">Avant de changer d'affichage, enregistrez votre travail en copiant les instructions DMX et en les collant dans un autre fichier.</span><span class="sxs-lookup"><span data-stu-id="f1626-116">Before changing views, save your work by copying and pasting the DMX statements to a separate file.</span></span>  
  
8.  <span data-ttu-id="f1626-117">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f1626-117">Click **Finish**.</span></span> <span data-ttu-id="f1626-118">Dans la boîte de dialogue **choisir la destination** , spécifiez l’emplacement où vous souhaitez enregistrer le résultat.</span><span class="sxs-lookup"><span data-stu-id="f1626-118">In the **Choose Destination** dialog  box, specify where you want the result saved.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="f1626-119">Si vous avez exécuté une instruction avec succès, l’instruction DMX que vous avez envoyée au serveur est également enregistrée dans la fenêtre de **trace** .</span><span class="sxs-lookup"><span data-stu-id="f1626-119">If you executed a statement successfully, the DMX statement that you sent to the server is also recorded in the **Trace** window.</span></span> <span data-ttu-id="f1626-120">Pour plus d’informations sur l’utilisation de la fonctionnalité de suivi, consultez [trace &#40;client d’exploration de données pour Excel&#41;](trace-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="f1626-120">For more information about how to use the Trace feature, see [Trace &#40;Data Mining Client for Excel&#41;](trace-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="f1626-121">Pour plus d’informations sur l’utilisation de l’éditeur de requêtes avancé d’exploration de données, consultez [&#40;des compléments d’exploration de données SQL Server&#41;](query-sql-server-data-mining-add-ins.md) et éditeur de requêtes d’exploration de [données avancé](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f1626-121">For more information about how to use the Data Mining Advanced Query Editor, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md) and [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="list-of-dmx-templates"></a><span data-ttu-id="f1626-122">Liste des modèles DMX</span><span class="sxs-lookup"><span data-stu-id="f1626-122">List of DMX Templates</span></span>  
 <span data-ttu-id="f1626-123">Les modèles DMX suivants sont inclus dans le Client d'exploration de données pour Excel.</span><span class="sxs-lookup"><span data-stu-id="f1626-123">The following DMX templates are included in the Data Mining Client for Excel.</span></span>  
  
 <span data-ttu-id="f1626-124">**Prédiction**</span><span class="sxs-lookup"><span data-stu-id="f1626-124">**Prediction**</span></span>  
  
 <span data-ttu-id="f1626-125">Utilisez ces modèles pour créer des requêtes de prédiction avancées, notamment des requêtes non prises en charge par les Assistants des compléments, par exemple les requêtes qui utilisent des tables imbriquées ou des sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="f1626-125">Use these templates to create advanced prediction queries, including queries not supported by the wizards in the add-ins, such as queries that use nested tables or external data sources.</span></span>  
  
-   <span data-ttu-id="f1626-126">Prédictions filtrées</span><span class="sxs-lookup"><span data-stu-id="f1626-126">Filtered predictions</span></span>  
  
-   <span data-ttu-id="f1626-127">Prédictions imbriquées filtrées</span><span class="sxs-lookup"><span data-stu-id="f1626-127">Filtered nested predictions</span></span>  
  
-   <span data-ttu-id="f1626-128">Prédictions imbriquées</span><span class="sxs-lookup"><span data-stu-id="f1626-128">Nested predictions</span></span>  
  
-   <span data-ttu-id="f1626-129">Prédictions singleton</span><span class="sxs-lookup"><span data-stu-id="f1626-129">Singleton predictions</span></span>  
  
-   <span data-ttu-id="f1626-130">Prédictions standard</span><span class="sxs-lookup"><span data-stu-id="f1626-130">Standard predictions</span></span>  
  
-   <span data-ttu-id="f1626-131">Prédictions de série chronologique</span><span class="sxs-lookup"><span data-stu-id="f1626-131">Time series predictions</span></span>  
  
-   <span data-ttu-id="f1626-132">Requête de prédiction TOP</span><span class="sxs-lookup"><span data-stu-id="f1626-132">TOP prediction query</span></span>  
  
-   <span data-ttu-id="f1626-133">Requête de prédiction TOP sur la table imbriquée</span><span class="sxs-lookup"><span data-stu-id="f1626-133">TOP prediction query on nested table</span></span>  
  
 <span data-ttu-id="f1626-134">**Créer**</span><span class="sxs-lookup"><span data-stu-id="f1626-134">**Create**</span></span>  
  
 <span data-ttu-id="f1626-135">Utilisez ces modèles pour créer des modèles ou des structures de données personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f1626-135">Use these templates to build custom models or data structures.</span></span> <span data-ttu-id="f1626-136">Vous n’êtes pas limité aux modèles pris en charge par les assistants : vous pouvez utiliser n’importe quel algorithme d’exploration de données pris en charge par l’instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] à laquelle vous êtes connecté, y compris les algorithmes de plug-in.</span><span class="sxs-lookup"><span data-stu-id="f1626-136">You are not limited to the models supported by the wizards - you can use any data mining algorithm supported by the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you are connected to, including plug-in algorithms.</span></span>  
  
-   <span data-ttu-id="f1626-137">Modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-137">Mining model</span></span>  
  
-   <span data-ttu-id="f1626-138">Structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-138">Mining structure</span></span>  
  
-   <span data-ttu-id="f1626-139">Structure d'exploration de données avec données d'exclusion</span><span class="sxs-lookup"><span data-stu-id="f1626-139">Mining structure with holdout</span></span>  
  
-   <span data-ttu-id="f1626-140">Modèle temporaire</span><span class="sxs-lookup"><span data-stu-id="f1626-140">Temporary model</span></span>  
  
-   <span data-ttu-id="f1626-141">Structure temporaire</span><span class="sxs-lookup"><span data-stu-id="f1626-141">Temporary structure</span></span>  
  
 <span data-ttu-id="f1626-142">**Propriétés de modèle**</span><span class="sxs-lookup"><span data-stu-id="f1626-142">**Model Properties**</span></span>  
  
 <span data-ttu-id="f1626-143">Utilisez ces modèles pour créer des requêtes qui obtiennent des métadonnées sur le modèle et le jeu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="f1626-143">Use these templates to create queries that get metadata about the model and the training set.</span></span> <span data-ttu-id="f1626-144">Récupérez également les détails du contenu du modèle, ou obtenez un profil statistique des données d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="f1626-144">You can also retrieve details from the model content, or get a statistical profile of the training data.</span></span>  
  
-   <span data-ttu-id="f1626-145">Contenu du modèle d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-145">Mining model content</span></span>  
  
-   <span data-ttu-id="f1626-146">Valeurs de colonne minimale et maximale</span><span class="sxs-lookup"><span data-stu-id="f1626-146">Minimum and maximum column values</span></span>  
  
-   <span data-ttu-id="f1626-147">Cas d'apprentissage/scénarios de test de la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-147">Mining structure test/training cases</span></span>  
  
-   <span data-ttu-id="f1626-148">Valeurs de colonnes discrètes</span><span class="sxs-lookup"><span data-stu-id="f1626-148">Discrete column values</span></span>  
  
 <span data-ttu-id="f1626-149">**Gestion**</span><span class="sxs-lookup"><span data-stu-id="f1626-149">**Management**</span></span>  
  
 <span data-ttu-id="f1626-150">Utilisez ces modèles pour effectuer toutes les tâches de gestion prises en charge par DMX, notamment pour importer et exporter des modèles, ou pour supprimer et nettoyer des modèles ou des structures de données.</span><span class="sxs-lookup"><span data-stu-id="f1626-150">Use these templates to perform any management task supported by DMX, which includes importing and exporting models, deleting models, and clearing models or data structures.</span></span>  
  
-   <span data-ttu-id="f1626-151">Effacer le modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-151">Clear mining model</span></span>  
  
-   <span data-ttu-id="f1626-152">Effacer la structure et les modèles</span><span class="sxs-lookup"><span data-stu-id="f1626-152">Clear structure and models</span></span>  
  
-   <span data-ttu-id="f1626-153">Effacer la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-153">Clear mining structure</span></span>  
  
-   <span data-ttu-id="f1626-154">Supprimer le modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-154">Delete mining model</span></span>  
  
-   <span data-ttu-id="f1626-155">Supprimer la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-155">Delete mining structure</span></span>  
  
-   <span data-ttu-id="f1626-156">Renommer le modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-156">Rename mining model</span></span>  
  
-   <span data-ttu-id="f1626-157">Renommer la structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-157">Rename mining structure</span></span>  
  
-   <span data-ttu-id="f1626-158">Effectuer l'apprentissage du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-158">Train mining model</span></span>  
  
-   <span data-ttu-id="f1626-159">Effectuer l'apprentissage d'une structure d'exploration de données imbriquée</span><span class="sxs-lookup"><span data-stu-id="f1626-159">Train nested mining structure</span></span>  
  
-   <span data-ttu-id="f1626-160">Effectuer l'apprentissage d'une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-160">Train mining structure</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="f1626-161">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f1626-161">Requirements</span></span>  
 <span data-ttu-id="f1626-162">En fonction du modèle vous utilisez, vous pouvez avoir besoin d'autorisations administratives pour accéder au serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="f1626-162">Depending on which template you are using, you might need administrative permissions to access the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server and execute the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1626-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1626-163">See Also</span></span>  
 [<span data-ttu-id="f1626-164">Création d'un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="f1626-164">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
