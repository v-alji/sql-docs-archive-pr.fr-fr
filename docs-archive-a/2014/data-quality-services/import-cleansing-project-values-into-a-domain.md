---
title: Importer des valeurs de projet de nettoyage dans un domaine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700253"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="d0751-102">Importer des valeurs de projet de nettoyage dans un domaine</span><span class="sxs-lookup"><span data-stu-id="d0751-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="d0751-103">Dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), vous pouvez importer les connaissances de qualité des données collectées pendant le processus de nettoyage dans un projet de nettoyage de qualité des données ou un package Integration Services qui contient le composant de nettoyage DQS dans un domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="d0751-104">Cela garantit que des connaissances approuvées ne sont pas perdues, et que la base de connaissances est améliorée en permanence.</span><span class="sxs-lookup"><span data-stu-id="d0751-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d0751-105">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d0751-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d0751-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d0751-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="d0751-107">Pour importer les valeurs d'un projet de nettoyage dans un domaine, le domaine doit avoir été utilisé dans le projet de nettoyage dans le client de qualité des données ou dans le package Integration Services qui contient un composant de nettoyage DQS.</span><span class="sxs-lookup"><span data-stu-id="d0751-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="d0751-108">Le projet de nettoyage dans le client de qualité des données ou le package Integration Services qui contient le composant de nettoyage DQS doit s'être correctement terminé.</span><span class="sxs-lookup"><span data-stu-id="d0751-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d0751-109">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d0751-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d0751-110">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d0751-110">Permissions</span></span>  
 <span data-ttu-id="d0751-111">Vous devez disposer du rôle dqs_kb_editor ou dqs_administrator sur la base de données DQS_MAIN pour importer les connaissances de qualité des données collectées pendant le processus de nettoyage vers un domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a> <span data-ttu-id="d0751-112">Importer des valeurs de projet de nettoyage</span><span class="sxs-lookup"><span data-stu-id="d0751-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="d0751-113">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="d0751-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="d0751-114">Sur l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , ouvrez une base de connaissances dans l'activité Gestion de l'arborescence du domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="d0751-115">Si vous ajoutez des valeurs à un domaine existant, sélectionnez le domaine dans la liste des domaines.</span><span class="sxs-lookup"><span data-stu-id="d0751-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="d0751-116">Cliquez sur l'onglet **Valeurs du domaine** , cliquez sur l'icône **Importer des valeurs** dans la barre d'icônes, puis cliquez sur **Importer des valeurs de projet**.</span><span class="sxs-lookup"><span data-stu-id="d0751-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="d0751-117">La boîte de dialogue **Importer des valeurs de projet** apparaît avec la liste des projets de qualité des données et des packages Integration Services qui ont été nettoyés à l'aide du domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0751-118"> Si aucun projet utilisant le domaine ou l'un de ses domaines liés n'a été créé, ou si le projet n'est pas terminé, l'option **Importer des valeurs de projet** n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="d0751-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="d0751-119">Dans la boîte de dialogue **Importer des valeurs de projet** :</span><span class="sxs-lookup"><span data-stu-id="d0751-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="d0751-120">Sélectionnez **Tout** dans la liste déroulante **Importés** pour afficher tous les projets, ou sur **Non** pour afficher uniquement les projets dont les valeurs n'ont pas encore été importées.</span><span class="sxs-lookup"><span data-stu-id="d0751-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="d0751-121">Sélectionnez le projet à partir duquel vous voulez importer des valeurs.</span><span class="sxs-lookup"><span data-stu-id="d0751-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="d0751-122">Sélectionnez **Ajouter des valeurs à partir de l'onglet Nouveau** pour importer des valeurs du nouvel onglet, en plus des valeurs des onglets **Correct** et **Corrigés** .</span><span class="sxs-lookup"><span data-stu-id="d0751-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="d0751-123">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0751-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d0751-124">Vous revenez à l'onglet **Valeurs du domaine** et un message s'affiche indiquant l'importation réussie des valeurs.</span><span class="sxs-lookup"><span data-stu-id="d0751-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="d0751-125">Les valeurs qui ont été importées, et qui sont donc nouvelles dans le domaine, s'affichent dans la table **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="d0751-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="d0751-126">Désélectionnez **Afficher seulement les nouvelles valeurs** pour afficher toutes les valeurs qui sont dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="d0751-127">Sélectionnez **Correct**, **Erreur**ou **Non valides** pour afficher uniquement les valeurs du type sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d0751-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="d0751-128">Pour rechercher une chaîne spécifique, entrez la chaîne dans la zone de texte **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="d0751-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="d0751-129">Cliquez sur la flèche haut ou bas pour parcourir les valeurs qui répondent aux critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="d0751-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="d0751-130">Elles sont mises en surbrillance en jaune.</span><span class="sxs-lookup"><span data-stu-id="d0751-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="d0751-131">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d0751-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0751-132"> Pour plus d'informations sur l'utilisation des valeurs dans l'onglet **Valeurs du domaine** , consultez [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="d0751-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a><span data-ttu-id="d0751-133">Suivi : après l’importation de valeurs de projet dans un domaine</span><span class="sxs-lookup"><span data-stu-id="d0751-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="d0751-134">Après avoir importé les connaissances de qualité des données collectées pendant le processus de nettoyage dans un domaine, vous pouvez effectuer d'autres tâches de gestion de domaine sur le domaine et les valeurs.</span><span class="sxs-lookup"><span data-stu-id="d0751-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="d0751-135">Pour plus d’informations, consultez [Gestion d’un domaine](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="d0751-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a><span data-ttu-id="d0751-136">Valeurs qui seront importées</span><span class="sxs-lookup"><span data-stu-id="d0751-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="d0751-137">Les valeurs suivantes seront importées à partir d'un projet vers un domaine :</span><span class="sxs-lookup"><span data-stu-id="d0751-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="d0751-138">Seules les valeurs de chaîne sont importées vers le domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="d0751-139">Seules les valeurs des onglets **Correct**, **Corrigés**, et **Nouveau** disponibles dans la page **Gérer et afficher les résultats** de l'activité **Nettoyage** seront importées.</span><span class="sxs-lookup"><span data-stu-id="d0751-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="d0751-140">Les valeurs de l'onglet **Nouveau** seront importées uniquement si la case à cocher **Ajouter des valeurs à partir de l'onglet Nouveau** de la boîte de dialogue **Importer des valeurs de projet** a été activée.</span><span class="sxs-lookup"><span data-stu-id="d0751-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="d0751-141">Les valeurs seront importées comme correctes ou en tant qu'erreur avec sa correction.</span><span class="sxs-lookup"><span data-stu-id="d0751-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="d0751-142">Seule une valeur d'erreur avec une valeur de correction sera importée.</span><span class="sxs-lookup"><span data-stu-id="d0751-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="d0751-143">La valeur de correction sera soit une nouvelle valeur qui n'existe pas dans la base de connaissances, soit une valeur correcte existante.</span><span class="sxs-lookup"><span data-stu-id="d0751-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="d0751-144">Seules les corrections effectuées au niveau des valeurs, et non pas au niveau des enregistrements, seront importées dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="d0751-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="d0751-145">Les valeurs non valides seront créées si la valeur importées contredit une règle de domaine.</span><span class="sxs-lookup"><span data-stu-id="d0751-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="d0751-146">Si vous importez des valeurs à partir de plusieurs projets à la fois, les valeurs sont importées en ordre séquentiel.</span><span class="sxs-lookup"><span data-stu-id="d0751-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="d0751-147">Une correction effectuée suite à une relation à base de termes dans un domaine est importée en tant que valeur correcte (et non en tant qu'erreur).</span><span class="sxs-lookup"><span data-stu-id="d0751-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a><span data-ttu-id="d0751-148">Valeurs qui ne seront pas importées</span><span class="sxs-lookup"><span data-stu-id="d0751-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="d0751-149">Les valeurs suivantes ne seront pas importées à partir d'un projet vers un domaine :</span><span class="sxs-lookup"><span data-stu-id="d0751-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="d0751-150">Les valeurs des onglets **Suggérés** et **Non valides** disponibles dans la page **Gérer et afficher les résultats** de l'activité **Nettoyage** ne seront pas importées.</span><span class="sxs-lookup"><span data-stu-id="d0751-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="d0751-151">Si une valeur trouvée dans le projet de nettoyage contredit une valeur existante dans le domaine, la valeur trouvée dans le projet est ignorée.</span><span class="sxs-lookup"><span data-stu-id="d0751-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="d0751-152">Cela inclut les conflits entre les valeurs de nettoyage et celles de la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="d0751-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="d0751-153">Les corrections effectuées au niveau des enregistrements ne seront pas importées dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="d0751-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="d0751-154">Aucune valeur ne sera importée vers un domaine si la valeur qu'elle remplacerait a été corrigée ou approuvée comme correcte par un service de données de référence.</span><span class="sxs-lookup"><span data-stu-id="d0751-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="d0751-155">Si une valeur de correction apparaît dans la base de connaissances comme valeur non valide ou comme valeur d'erreur, ni l'erreur ni la valeur de correction ne seront importées.</span><span class="sxs-lookup"><span data-stu-id="d0751-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="d0751-156">Si le domaine fait partie d'un domaine composite, et que le nettoyage a été effectué sur le domaine composite, aucune valeur ne sera importée.</span><span class="sxs-lookup"><span data-stu-id="d0751-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="d0751-157">Vous pouvez importer des valeurs d'un projet uniquement lorsque la base de connaissances a l'état En cours et que la base de connaissances est verrouillée par l'utilisateur qui effectue l'importation.</span><span class="sxs-lookup"><span data-stu-id="d0751-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0751-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0751-158">See Also</span></span>  
 <span data-ttu-id="d0751-159">[Nettoyage des données](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="d0751-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="d0751-160">Transformation de nettoyage DQS</span><span class="sxs-lookup"><span data-stu-id="d0751-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
