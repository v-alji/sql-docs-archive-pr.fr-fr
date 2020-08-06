---
title: Ajouter et vérifier une connexion de données ou une source de données (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1d3b2573-e29d-480d-9dde-d26379c86618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d86b3e6598c12545f0e24ef1d162eeb1131bd15d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600595"
---
# <a name="add-and-verify-a-data-connection-or-data-source-report-builder-and-ssrs"></a><span data-ttu-id="440b7-102">Ajouter et vérifier une connexion de données ou une source de données (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="440b7-102">Add and Verify a Data Connection or Data Source (Report Builder and SSRS)</span></span>
  <span data-ttu-id="440b7-103">Dans le Générateur de rapports, vous pouvez ajouter une source de données partagée depuis le serveur de rapports ou créer une source de données incorporée pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="440b7-103">In Report Builder, you can add a shared data source from the report server or create an embedded data source for your report.</span></span> <span data-ttu-id="440b7-104">Dans le Concepteur de rapports, vous pouvez créer une source de données partagée ou une source de données incorporée et la déployer sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="440b7-104">In Report Designer, you can create a shared data source or an embedded data source and deploy it to a report server.</span></span>  
  
 <span data-ttu-id="440b7-105">Pour ajouter une source de données partagée à votre rapport, accédez à un serveur de rapports et sélectionnez une source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="440b7-105">To add a shared data source to your report, browse to a report server and select a shared data source.</span></span> <span data-ttu-id="440b7-106">La source de données partagée de votre rapport pointe vers la définition de la source de données partagée sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="440b7-106">The shared data source in your report points to the shared data source definition on the report server.</span></span>  
  
 <span data-ttu-id="440b7-107">Pour créer une source de données incorporée, vous devez disposer des informations de connexion à la source de données externe et connaître les autorisations dont vous avez besoin pour accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="440b7-107">To create an embedded data source, you must have connection information to the external source of data and you must know which permissions you need to access the data.</span></span> <span data-ttu-id="440b7-108">Ces informations proviennent généralement du propriétaire de la source de données.</span><span class="sxs-lookup"><span data-stu-id="440b7-108">This information usually comes from the owner of the data source.</span></span> <span data-ttu-id="440b7-109">Vous pouvez tester la connexion pour vérifier que les informations d'identification spécifiées sont suffisantes.</span><span class="sxs-lookup"><span data-stu-id="440b7-109">You can test the connection to verify that the credentials that are specified are sufficient.</span></span>  
  
 <span data-ttu-id="440b7-110">Pour plus d’informations, consultez [Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports](../data-connections-data-sources-and-connection-strings-in-report-builder.md) ou [Spécifier des informations d’identification dans le Générateur de rapports](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="440b7-110">For more information, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md) and [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-create-a-reference-to-a-shared-data-source"></a><span data-ttu-id="440b7-111">Pour créer une référence à une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="440b7-111">To create a reference to a shared data source</span></span>  
  
1.  <span data-ttu-id="440b7-112">Dans la barre d’outils du volet des données de rapport, cliquez sur **Nouveau** , puis sur **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="440b7-112">On the toolbar in the Report Data pane, click **New,** and then click **Data Source**.</span></span> <span data-ttu-id="440b7-113">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="440b7-113">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="440b7-114">Dans la zone de texte **Nom** , tapez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="440b7-114">In the **Name** text box, type a name for the data source.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="440b7-115">Ce nom est enregistré dans la définition de rapport locale.</span><span class="sxs-lookup"><span data-stu-id="440b7-115">This name is saved in the local report definition.</span></span> <span data-ttu-id="440b7-116">Ce nom ne correspond pas au nom de la source de données partagée sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="440b7-116">This name is not the name of the shared data source on the report server.</span></span>  
  
3.  <span data-ttu-id="440b7-117">Sélectionnez **Utiliser une connexion partagée ou un modèle de rapport**.</span><span class="sxs-lookup"><span data-stu-id="440b7-117">Select **Use a shared connection or report model**.</span></span> <span data-ttu-id="440b7-118">Vous obtenez la liste des sources de données partagées et des modèles de rapport utilisés récemment.</span><span class="sxs-lookup"><span data-stu-id="440b7-118">The list of recently used shared data sources and report models appears.</span></span> <span data-ttu-id="440b7-119">Pour en sélectionner un à partir d’un serveur de rapports, cliquez sur **Parcourir** et accédez au dossier où sont stockées les sources de données partagées disponibles sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="440b7-119">To select one from a report server, click **Browse** and browse to the folder on the report server where shared data sources are available.</span></span>  
  
4.  <span data-ttu-id="440b7-120">Sélectionnez la source de données partagée, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="440b7-120">Select the shared data source and then click **Open**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="440b7-121">La source de données apparaît dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="440b7-121">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="440b7-122">Pour créer une source de données incorporée</span><span class="sxs-lookup"><span data-stu-id="440b7-122">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="440b7-123">Dans la barre d'outils du volet Données du rapport, cliquez sur **Nouveau**, puis sur **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="440b7-123">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span> <span data-ttu-id="440b7-124">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="440b7-124">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="440b7-125">Dans la zone de texte **Nom** , tapez un nom pour la source de données ou acceptez la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="440b7-125">In the **Name** text box, type a name for the data source or accept the default.</span></span>  
  
3.  <span data-ttu-id="440b7-126">Vérifiez que l'option **Utiliser une connexion incorporée dans mon rapport** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="440b7-126">Verify that **Use a connection embedded in my report** is selected.</span></span>  
  
    1.  <span data-ttu-id="440b7-127">Dans la liste déroulante **Sélectionner un type de connexion** , sélectionnez un type de source de données ; par exemple, **Microsoft SQL Server** ou **OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="440b7-127">From the **Select connection type** drop-down list, select a data source type; for example, **Microsoft SQL Server** or **OLE DB**.</span></span>  
  
    2.  <span data-ttu-id="440b7-128">Spécifiez une chaîne de connexion en utilisant l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="440b7-128">Specify a connection string by using one of the following alternatives:</span></span>  
  
    -   <span data-ttu-id="440b7-129">Tapez directement la chaîne de connexion dans la zone de texte **Chaîne de connexion** .</span><span class="sxs-lookup"><span data-stu-id="440b7-129">Type the connection string directly in the **Connection string** text box.</span></span> <span data-ttu-id="440b7-130">Pour obtenir une liste d’exemples de chaînes de connexion, consultez [Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="440b7-130">For a list of example connection strings, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
    -   <span data-ttu-id="440b7-131">Cliquez sur le bouton d’expression (**fx)** pour créer une expression qui prend la valeur d’une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="440b7-131">Click the expression (**fx)** button to create an expression that evaluates to a connection string.</span></span> <span data-ttu-id="440b7-132">Dans la boîte de dialogue **Expression** , tapez l'expression dans le volet Expression.</span><span class="sxs-lookup"><span data-stu-id="440b7-132">In the **Expression** dialog box, type the expression in the Expression pane.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    -   <span data-ttu-id="440b7-133">Cliquez sur **Générer** pour ouvrir la boîte de dialogue **Propriétés de connexion** correspondant au type de source de données choisi à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="440b7-133">Click **Build** to open the **Connection Properties** dialog box for the data source type that you chose in step 2.</span></span>  
  
         <span data-ttu-id="440b7-134">Renseignez les champs de la boîte de dialogue **Propriétés de connexion** comme il convient pour le type de source de données.</span><span class="sxs-lookup"><span data-stu-id="440b7-134">Fill in the fields in the **Connection Properties** dialog box as appropriate for the data source type.</span></span> <span data-ttu-id="440b7-135">Les propriétés de connexion incluent le type de la source de données, son nom, ainsi que les informations d'identification à utiliser.</span><span class="sxs-lookup"><span data-stu-id="440b7-135">Connection properties include the type of data source, the name of the data source, and the credentials to use.</span></span> <span data-ttu-id="440b7-136">Une fois que vous avez spécifié les valeurs dans cette boîte de dialogue, cliquez sur **Tester la connexion** pour vérifier que la source de données est disponible et que les informations d'identification indiquées sont correctes.</span><span class="sxs-lookup"><span data-stu-id="440b7-136">After you specify values in this dialog box, click **Test Connection** to verify that the data source is available and that the credentials you specified are correct.</span></span>  
  
4.  <span data-ttu-id="440b7-137">Cliquez sur **Informations d'identification**.</span><span class="sxs-lookup"><span data-stu-id="440b7-137">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="440b7-138">Spécifiez les informations d'identification à utiliser pour cette source de données.</span><span class="sxs-lookup"><span data-stu-id="440b7-138">Specify the credentials to use for this data source.</span></span> <span data-ttu-id="440b7-139">Le propriétaire de la source de données choisit le type d'informations d'identification pris en charge.</span><span class="sxs-lookup"><span data-stu-id="440b7-139">The owner of the data source chooses the type of credentials that are supported.</span></span> <span data-ttu-id="440b7-140">Dans certains cas, le propriétaire de la source de données conserve une source de données partagée sur un serveur de rapports et la configure avec des informations d'identification que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="440b7-140">In some cases, the owner of the data source maintains a shared data source on a report server and configures the data source with credentials that you can use.</span></span> <span data-ttu-id="440b7-141">Contactez le propriétaire de la source de données pour vous procurer ces informations.</span><span class="sxs-lookup"><span data-stu-id="440b7-141">Contact the data source owner for this information.</span></span> <span data-ttu-id="440b7-142">Pour plus d’informations, consultez [Spécifier des informations d’identification dans le Générateur de rapports](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="440b7-142">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
 <span data-ttu-id="440b7-143">La source de données apparaît dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="440b7-143">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-verify-a-data-connection"></a><span data-ttu-id="440b7-144">Pour vérifier une connexion de données</span><span class="sxs-lookup"><span data-stu-id="440b7-144">To verify a data connection</span></span>  
  
1.  <span data-ttu-id="440b7-145">Dans la barre d'outils du volet des données de rapport, double-cliquez sur la source de données.</span><span class="sxs-lookup"><span data-stu-id="440b7-145">On the toolbar in the Report Data pane, double-click the data source.</span></span> <span data-ttu-id="440b7-146">La boîte de dialogue **Propriétés de la source de données** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="440b7-146">The **Data Source Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="440b7-147">Cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="440b7-147">Click **Test Connection**.</span></span>  
  
3.  <span data-ttu-id="440b7-148">Si la connexion a abouti, le message suivant apparaît : « La connexion a été correctement créée ».</span><span class="sxs-lookup"><span data-stu-id="440b7-148">If the connection is successful, the following message appears: "Connection created successfully".</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="440b7-149">Si la connexion n'a pas abouti, le message suivant s'affiche : « Impossible de se connecter à la source de données ».</span><span class="sxs-lookup"><span data-stu-id="440b7-149">If the connection is not successful, the following message appears: "Unable to connect to the data source."</span></span>  
  
5.  <span data-ttu-id="440b7-150">Cliquez sur **Détails**et utilisez les informations pour corriger le problème.</span><span class="sxs-lookup"><span data-stu-id="440b7-150">Click **Details**, and use the information to correct the issue.</span></span>  
  
     <span data-ttu-id="440b7-151">Pour plus d’informations, consultez [Spécifier des informations d’identification dans le Générateur de rapports](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="440b7-151">For more information, see [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="440b7-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="440b7-152">See Also</span></span>  
 <span data-ttu-id="440b7-153">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="440b7-153">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="440b7-154">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="440b7-154">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="440b7-155">[Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="440b7-155">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="440b7-156">Connexions de données, sources de données et chaînes de connexion dans le Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="440b7-156">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
  
  
