---
title: Créer un dataset partagé ou incorporé (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d1d7bc71-f0e9-4ce5-b3ad-6fee54388a31
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fca74e1ba7965eeef6ce562e79e378af5bb9e145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696472"
---
# <a name="create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs"></a><span data-ttu-id="cbede-102">Créer un dataset partagé ou incorporé (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="cbede-102">Create a Shared Dataset or Embedded Dataset (Report Builder and SSRS)</span></span>
  <span data-ttu-id="cbede-103">Vous pouvez créer un dataset incorporé pour une utilisation dans un rapport unique ou un dataset partagé à enregistrer sur un serveur de rapports, en vue d'une utilisation par plusieurs rapports.</span><span class="sxs-lookup"><span data-stu-id="cbede-103">You can create an embedded dataset for use in a single report or a shared dataset to save to a report server, for use by multiple reports.</span></span> <span data-ttu-id="cbede-104">Pour créer un dataset, vous devez disposer d'une source de données incorporée ou partagée.</span><span class="sxs-lookup"><span data-stu-id="cbede-104">To create a dataset, you must have an embedded or shared data source.</span></span>

 <span data-ttu-id="cbede-105">Utilisez le Générateur de rapports pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbede-105">Use Report Builder to do the following tasks:</span></span>

-   <span data-ttu-id="cbede-106">Créez un dataset partagé en mode création de dataset.</span><span class="sxs-lookup"><span data-stu-id="cbede-106">Create a shared dataset in Dataset Design View.</span></span> <span data-ttu-id="cbede-107">Les datasets partagés doivent utiliser des sources de données partagées publiées.</span><span class="sxs-lookup"><span data-stu-id="cbede-107">Shared datasets must use published shared data sources.</span></span>

-   <span data-ttu-id="cbede-108">Créez un dataset incorporé en mode création de rapport.</span><span class="sxs-lookup"><span data-stu-id="cbede-108">Create an embedded dataset in Report Design View.</span></span>

-   <span data-ttu-id="cbede-109">Enregistrez le dataset directement sur le serveur de rapports ou le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cbede-109">Save the dataset directly to the report server or SharePoint site.</span></span>

 <span data-ttu-id="cbede-110">Utilisez le Concepteur de rapports dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="cbede-110">Use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to do the following tasks:</span></span>

1.  <span data-ttu-id="cbede-111">Créez un dataset partagé dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="cbede-111">Create a shared dataset in Solution Explorer.</span></span> <span data-ttu-id="cbede-112">Les datasets partagés doivent utiliser les sources de données du dossier Sources de données partagées dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="cbede-112">Shared datasets must use data sources from the Shared Data Sources folder in Solution Explorer.</span></span>

2.  <span data-ttu-id="cbede-113">Créez un dataset incorporé dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="cbede-113">Create an embedded dataset in the Report Data pane.</span></span>

3.  <span data-ttu-id="cbede-114">Éventuellement déployez des datasets partagés et la source de données partagées avec le rapport.</span><span class="sxs-lookup"><span data-stu-id="cbede-114">Optionally deploy the shared datasets and shared data source with the report.</span></span> <span data-ttu-id="cbede-115">Pour chaque type d'élément, utilisez les propriétés du projet pour spécifier les chemins d'accès aux dossiers sur le serveur de rapports ou le site SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cbede-115">For each type of item, use Project Properties to specify paths to folders on the report server or SharePoint site.</span></span>

 <span data-ttu-id="cbede-116">Pour plus d’informations, consultez [Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="cbede-116">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-open-report-builder-and-create-a-shared-dataset"></a><span data-ttu-id="cbede-117">Pour ouvrir le Générateur de rapports et créer un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="cbede-117">To open Report Builder and create a shared dataset</span></span>

1.  <span data-ttu-id="cbede-118">Ouvrez le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbede-118">Open Report Builder.</span></span> <span data-ttu-id="cbede-119">Le volet **Nouveau rapport ou dataset** s'ouvre, comme indiqué dans l'illustration suivante :</span><span class="sxs-lookup"><span data-stu-id="cbede-119">The **New report or dataset pane** opens, as shown in the following figure:</span></span>

     <span data-ttu-id="cbede-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span><span class="sxs-lookup"><span data-stu-id="cbede-120">![rs_NewSharedDataset](../media/rs-newshareddataset.gif "rs_NewSharedDataset")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="cbede-121"> Si le volet **Nouveau rapport ou dataset** ne s'affiche pas, à partir du bouton Générateur de rapports, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="cbede-121">If the **New report or dataset pane** does not appear, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="cbede-122">Dans le volet gauche, sous **Créer un dataset**, cliquez sur **Dataset partagé**.</span><span class="sxs-lookup"><span data-stu-id="cbede-122">In the left pane, under **Create a dataset**, click **Shared Dataset**.</span></span>

3.  <span data-ttu-id="cbede-123">Dans le volet droit, cliquez sur **Parcourir** pour sélectionner une source de données partagée sur le serveur de rapports, puis cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="cbede-123">In the right pane, click **Browse** to select a shared data source from the report server, and then click **Create**.</span></span> <span data-ttu-id="cbede-124">Le concepteur de requêtes associé à la source de données partagée s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="cbede-124">The query designer associated with the shared data source opens.</span></span>

4.  <span data-ttu-id="cbede-125">Dans le Concepteur de requêtes, spécifiez les champs à inclure au dataset.</span><span class="sxs-lookup"><span data-stu-id="cbede-125">In the query designer, specify the fields to include in the dataset.</span></span>

5.  <span data-ttu-id="cbede-126">Cliquez sur **exécuter** (**!**) pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="cbede-126">Click **Run** (**!**) to run the query.</span></span>

6.  <span data-ttu-id="cbede-127">Sur le bouton **Générateur de rapports** , cliquez sur **Enregistrer** ou **Enregistrer sous** pour enregistrer le dataset partagé sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbede-127">On the **Report Builder** button, click **Save** or **Save As** to save the shared dataset to the report server.</span></span>

7.  <span data-ttu-id="cbede-128">Pour quitter le Générateur de rapports, cliquez sur **Générateur de rapports**, puis sur **Quitter le Générateur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="cbede-128">To exit Report Builder, click **Report Builder**, and then click **Exit Report Builder**.</span></span> <span data-ttu-id="cbede-129">Pour utiliser des rapports, cliquez sur **Générateur de rapports**, puis sur **Nouveau** ou **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="cbede-129">To work with reports, click **Report Builder**, and then click **New** or **Open**.</span></span>

### <a name="to-set-query-parameter-options"></a><span data-ttu-id="cbede-130">Pour définir des options de paramètre de requête</span><span class="sxs-lookup"><span data-stu-id="cbede-130">To set query parameter options</span></span>

1.  <span data-ttu-id="cbede-131">Ouvrez le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="cbede-131">Open Report Builder.</span></span>

2.  <span data-ttu-id="cbede-132">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="cbede-132">Click **Open**.</span></span>

3.  <span data-ttu-id="cbede-133">Accédez au serveur de rapports et sélectionnez le dossier pour la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="cbede-133">Browse to the report server, and select the folder for the shared data source.</span></span>

4.  <span data-ttu-id="cbede-134">Dans **Éléments de type**, cliquez sur Datasets (\*.rsd) dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cbede-134">In **Items of type**, click Datasets (\*.rsd) in the drop-down list.</span></span>

5.  <span data-ttu-id="cbede-135">Sélectionnez le dataset partagé, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="cbede-135">Select the shared dataset, and then click **Open**.</span></span> <span data-ttu-id="cbede-136">Le concepteur de requêtes associé s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="cbede-136">The associated query designer opens.</span></span>

6.  <span data-ttu-id="cbede-137">Sur le ruban, cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="cbede-137">On the Ribbon, click **Dataset Properties**.</span></span>

7.  <span data-ttu-id="cbede-138">Cliquez sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="cbede-138">Click **Parameters**.</span></span> <span data-ttu-id="cbede-139">Dans cette page, définissez une valeur par défaut sur une constante ou une expression, marquez le paramètre en lecture seule, nullable ou **Omettre de la requête**.</span><span class="sxs-lookup"><span data-stu-id="cbede-139">On this page, set a default value to a constant or an expression, mark the parameter as read-only, nullable, or **Omit From Query**.</span></span> <span data-ttu-id="cbede-140">Pour plus d’informations, consultez [Boîte de dialogue Propriétés du dataset, Paramètres &#40;Générateur de rapports&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="cbede-140">For more information, see [Dataset Properties Dialog Box, Parameters &#40;Report Builder&#41;](../dataset-properties-dialog-box-parameters-report-builder.md).</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]


### <a name="to-create-a-dataset-from-a-sql-server-relational-database"></a><span data-ttu-id="cbede-141">Pour créer un dataset à partir d'une base de données relationnelle SQL Server</span><span class="sxs-lookup"><span data-stu-id="cbede-141">To create a dataset from a SQL Server relational database</span></span>

1.  <span data-ttu-id="cbede-142">Dans le volet Données du rapport, cliquez avec le bouton droit sur le nom de la source de données, puis cliquez sur **Ajouter un dataset**.</span><span class="sxs-lookup"><span data-stu-id="cbede-142">In the Report Data pane, right-click the name of the data source, and then click **Add Dataset**.</span></span> <span data-ttu-id="cbede-143">La page **Requête** de la boîte de dialogue **Propriétés du dataset** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="cbede-143">The **Query** page of the **Dataset Properties** dialog box opens.</span></span>

2.  <span data-ttu-id="cbede-144">Dans **Nom**, tapez un nom pour le dataset ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbede-144">In **Name**, type a name for the dataset or accept the default name.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="cbede-145">Le nom du dataset est utilisé en interne dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="cbede-145">The dataset name is used internally within the report.</span></span> <span data-ttu-id="cbede-146">Par souci de clarté, il est recommandé d'utiliser un nom de dataset qui décrit les données retournées par la requête.</span><span class="sxs-lookup"><span data-stu-id="cbede-146">For clarity, we recommend that the name of the dataset describe the data that the query returns.</span></span>

3.  <span data-ttu-id="cbede-147">Dans **Source de données**, recherchez et sélectionnez le nom d'une source de données partagée existante ou cliquez sur **Nouveau** pour créer une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="cbede-147">In **Data source**, browse to and select the name of an existing shared data source, or click **New** to create a new embedded data source.</span></span>

4.  <span data-ttu-id="cbede-148">Sélectionnez une option pour le **Type de requête** .</span><span class="sxs-lookup"><span data-stu-id="cbede-148">Select a **Query type** option.</span></span> <span data-ttu-id="cbede-149">Les options disponibles dépendent du type de source de données.</span><span class="sxs-lookup"><span data-stu-id="cbede-149">Options depend on the data source type.</span></span>

    -   <span data-ttu-id="cbede-150">Sélectionnez **Texte** pour rédiger une requête adoptant le langage de requête de la source de données.</span><span class="sxs-lookup"><span data-stu-id="cbede-150">Select **Text** to write a query using the query language of the data source.</span></span>

    -   <span data-ttu-id="cbede-151">Sélectionnez **Table** pour retourner tous les champs dans une table de base de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="cbede-151">Select **Table** to return all the fields in a relational database table.</span></span>

    -   <span data-ttu-id="cbede-152">Sélectionnez **StoredProcedure** pour exécuter une procédure stockée par nom.</span><span class="sxs-lookup"><span data-stu-id="cbede-152">Select **StoredProcedure** to run a stored procedure by name.</span></span>

5.  <span data-ttu-id="cbede-153">Dans la zone **Requête**, tapez le nom de la requête, de la procédure stockée ou de la table.</span><span class="sxs-lookup"><span data-stu-id="cbede-153">In **Query**, type the query, stored procedure, or table name.</span></span> <span data-ttu-id="cbede-154">Vous pouvez aussi cliquer sur **Concepteur de requêtes** pour ouvrir le concepteur de requêtes graphique ou textuel, ou sur **Importer** pour importer la requête depuis un rapport existant.</span><span class="sxs-lookup"><span data-stu-id="cbede-154">Alternatively, click **Query Designer** to open the graphical or text-based query designer tool, or **Import** to import the query from an existing report.</span></span>

     <span data-ttu-id="cbede-155">Dans certains cas, la collection de champs spécifiée par la requête ne peut être déterminée qu'en exécutant la requête sur la source de données.</span><span class="sxs-lookup"><span data-stu-id="cbede-155">In a few cases, the field collection specified by the query can only be determined by running the query on the data source.</span></span> <span data-ttu-id="cbede-156">Par exemple, une procédure stockée peut retourner un jeu variable de champs dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="cbede-156">For example, a stored procedure may return a variable set of fields in the result set.</span></span> <span data-ttu-id="cbede-157">Cliquez sur **Actualiser les champs** pour exécuter la requête sur la source de données et récupérer les noms de champs qui sont requis pour remplir la collection de champs de dataset dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="cbede-157">Click **Refresh Fields** to run the query on the data source and retrieve the field names that are needed to populate the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="cbede-158">La collection de champs s'affiche sous le nœud de dataset une fois que vous avez fermé la boîte de dialogue **Propriétés du dataset** .</span><span class="sxs-lookup"><span data-stu-id="cbede-158">The field collection appears under the dataset node after you close the **Dataset Properties** dialog box.</span></span>

6.  <span data-ttu-id="cbede-159">Dans la zone **Délai d'expiration**, tapez le nombre de secondes pendant lequel le serveur de rapports attend une réponse de la base de données.</span><span class="sxs-lookup"><span data-stu-id="cbede-159">In **Timeout**, type the number of seconds that the report server waits for a response from the database.</span></span> <span data-ttu-id="cbede-160">La valeur par défaut est 0 seconde.</span><span class="sxs-lookup"><span data-stu-id="cbede-160">The default value is 0 seconds.</span></span> <span data-ttu-id="cbede-161">Lorsque la valeur du délai d'expiration est de 0 secondes, la requête n'expire pas.</span><span class="sxs-lookup"><span data-stu-id="cbede-161">When the time out value is 0 seconds, the query does not time out.</span></span>

7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="cbede-162">Le dataset et sa collection de champs s'affichent dans le volet des données de rapport sous le nœud de source de données.</span><span class="sxs-lookup"><span data-stu-id="cbede-162">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbede-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbede-163">See Also</span></span>
 <span data-ttu-id="cbede-164">[Datasets incorporés dans les rapports et datasets partagés &#40;collection de champs de dataset générateur de rapports et ssrs&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [&#40;Générateur de rapports et SSRS&#41;les](dataset-fields-collection-report-builder-and-ssrs.md) [concepteurs de requêtes](../query-designers-report-builder.md) &#40;générateur de rapports&#41;générateur de rapports [aide pour les boîtes de dialogue, les volets et les assistants](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Ajouter des données à un rapport &#40;](report-datasets-ssrs.md) générateur de rapports et [SSRS](embedded-and-shared-datasets-report-builder-and-ssrs.md)&#41;des [connexions de données, des sources de données et des chaînes de connexion dans générateur de rapports](../data-connections-data-sources-and-connection-strings-in-report-builder.md)</span><span class="sxs-lookup"><span data-stu-id="cbede-164">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) [Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) [Query Designers &#40;Report Builder&#41;](../query-designers-report-builder.md) [Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) [Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) [Embedded and Shared Datasets &#40;Report Builder and SSRS&#41;](embedded-and-shared-datasets-report-builder-and-ssrs.md)</span></span>


