---
title: Créer, supprimer ou modifier une source de données partagée (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610506"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="da0b5-102">Créer, supprimer ou modifier une source de données partagée (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="da0b5-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="da0b5-103">Une source de données partagée spécifie les propriétés de connexion d'une source de données.</span><span class="sxs-lookup"><span data-stu-id="da0b5-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="da0b5-104">Si une source de données est utilisée par un grand nombre de rapports, de modèles ou d'abonnements pilotés par les données, songez à créer une source de données partagée pour éliminer le temps de traitement nécessaire à la gestion des mêmes informations de connexion à plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="da0b5-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="da0b5-105">L'icône suivante indique une source de données partagée dans l'arborescence des dossiers du Gestionnaire de rapports :</span><span class="sxs-lookup"><span data-stu-id="da0b5-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="da0b5-106">![Icône de source de données partagée](media/hlp-16datasource.png "Icône de source de données partagée")</span><span class="sxs-lookup"><span data-stu-id="da0b5-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="da0b5-107">icône de source de données partagée</span><span class="sxs-lookup"><span data-stu-id="da0b5-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="da0b5-108">Pour créer une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="da0b5-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="da0b5-109">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="da0b5-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="da0b5-110">Dans Gestionnaire de rapports, accédez à la page **contenu** .</span><span class="sxs-lookup"><span data-stu-id="da0b5-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="da0b5-111">Cliquez sur **Nouvelle source de données**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-111">Click **New Data Source**.</span></span> <span data-ttu-id="da0b5-112">La page **Nouvelle source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="da0b5-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="da0b5-113">Tapez le nom de l'élément.</span><span class="sxs-lookup"><span data-stu-id="da0b5-113">Type a name for the item.</span></span> <span data-ttu-id="da0b5-114">Le nom doit contenir au moins un caractère et il doit commencer par une lettre.</span><span class="sxs-lookup"><span data-stu-id="da0b5-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="da0b5-115">Il peut également comprendre des symboles, à l'exception des espaces ou des caractères ; ?</span><span class="sxs-lookup"><span data-stu-id="da0b5-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="da0b5-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="da0b5-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="da0b5-117">Si vous le souhaitez, entrez une description renseignant les utilisateurs sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="da0b5-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="da0b5-118">Ce descriptif s'affiche dans la page **Contenu** du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="da0b5-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="da0b5-119">Dans la liste **Type de source de données** , spécifiez l'extension pour le traitement des données qui est utilisée en vue d'exploiter les informations à partir de la source de données.</span><span class="sxs-lookup"><span data-stu-id="da0b5-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="da0b5-120">Dans la zone **Chaîne de connexion**, spécifiez la chaîne de connexion utilisée par le serveur de rapports pour se connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="da0b5-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="da0b5-121">Il est recommandé de n'indiquer aucune information d'identification ici.</span><span class="sxs-lookup"><span data-stu-id="da0b5-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="da0b5-122">L’exemple suivant illustre une chaîne de connexion pour la connexion à la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] base de données locale :</span><span class="sxs-lookup"><span data-stu-id="da0b5-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="da0b5-123">Pour **Se connecter en utilisant**, précisez comment les informations d'identification sont obtenues lorsque le rapport s'exécute :</span><span class="sxs-lookup"><span data-stu-id="da0b5-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="da0b5-124">Si vous voulez demander à l'utilisateur un nom de connexion et un mot de passe, cliquez sur **Informations d'identification fournies par l'utilisateur qui exécute le rapport**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="da0b5-125">Pour utiliser les informations d'identification fournies par l'utilisateur en tant qu'informations d'identification Windows, activez la case à cocher **Utiliser comme informations d'identification Windows lors de la connexion à la source de données**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="da0b5-126">Si le nom d'utilisateur et le mot de passe sont des informations d'identification de base de données, ne sélectionnez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="da0b5-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="da0b5-127">Si vous avez l’intention d’utiliser la source de données comme source de données partagée avec des informations d’identification enregistrées gérées par le propriétaire de la source de données ou pour des rapports prenant en charge les abonnements ou d’autres opérations planifiées (par exemple, la création automatique d’un historique de rapport), cliquez sur **Informations d’identification stockées de manière sécurisée sur le serveur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="da0b5-128">Si le serveur de base de données prend en charge l'emprunt d'identité ou la délégation, sélectionnez **Emprunter l'identité de l'utilisateur authentifié une fois la connexion établie à la source de données**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="da0b5-129">Si vous souhaitez que le serveur de rapports transmette les informations d'identification de l'utilisateur du rapport au serveur qui héberge la source de données externe, cliquez sur **Sécurité intégrée de Windows**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="da0b5-130">Dans ce cas, l'utilisateur n'est pas invité à taper son nom d'utilisateur ou son mot de passe.</span><span class="sxs-lookup"><span data-stu-id="da0b5-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="da0b5-131">Si la source de données n’utilise pas d’informations d’identification (par exemple, si la source de données est un fichier XML accessible à partir du le système de fichiers), cliquez sur **Informations d’identification non requises**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="da0b5-132">Spécifiez uniquement ce type d'informations d'identification s'il est valide pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="da0b5-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="da0b5-133">Si vous sélectionnez cette option pour une source de données qui requiert l'authentification, la connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="da0b5-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="da0b5-134">Si vous sélectionnez cette option, veillez à configurer le compte d'exécution sans assistance, qui permet au serveur de rapports de se connecter à d'autres ordinateurs pour récupérer des données ou des fichiers lorsque les informations d'identification de l'utilisateur ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="da0b5-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="da0b5-135">Pour plus d’informations sur la configuration des informations d’identification, consultez [Spécifier des informations d’identification et de connexion pour les sources de données de rapport](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="da0b5-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="da0b5-136">Pour plus d’informations sur le compte d’exécution sans assistance, consultez [Configurer le compte d’exécution sans assistance &#40;Gestionnaire de configuration de SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="da0b5-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="da0b5-137">Cliquez sur le bouton **Tester la connexion** pour valider la configuration de la source de données.</span><span class="sxs-lookup"><span data-stu-id="da0b5-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da0b5-138">Le bouton Tester la connexion n'est pas pris en charge pour le type de source de données XML.</span><span class="sxs-lookup"><span data-stu-id="da0b5-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="da0b5-139">Cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="da0b5-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="da0b5-140">Pour modifier une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="da0b5-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="da0b5-141">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'à la page Contenu.</span><span class="sxs-lookup"><span data-stu-id="da0b5-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="da0b5-142">Accédez à l’élément de source de données partagée, pointez sur l’élément, cliquez sur la liste déroulante, puis dans le menu contextuel, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="da0b5-143">La page de **propriétés** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="da0b5-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="da0b5-144">Modifiez la source de données, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="da0b5-145">Pour supprimer une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="da0b5-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="da0b5-146">Dans le Gestionnaire de rapports, parcourez l'arborescence jusqu'à la page **Contenu** et effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="da0b5-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="da0b5-147">Naviguez jusqu'à l'élément de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="da0b5-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="da0b5-148">Cliquez sur l'élément pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="da0b5-148">Click the item to open it.</span></span> <span data-ttu-id="da0b5-149">La page des propriétés générales s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="da0b5-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="da0b5-150">Cliquez sur **Supprimer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="da0b5-151">Dans la page **Contenu** , parcourez l'arborescence jusqu'au dossier contenant la source de données à supprimer.</span><span class="sxs-lookup"><span data-stu-id="da0b5-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="da0b5-152">Pointez sur l’élément, cliquez sur la liste déroulante, puis dans le menu contextuel, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="da0b5-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da0b5-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da0b5-153">See Also</span></span>  
 <span data-ttu-id="da0b5-154">[Connexions de données, sources de données et chaînes de connexion dans Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="da0b5-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="da0b5-155">[Page contenu &#40;Gestionnaire de rapports&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="da0b5-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="da0b5-156">[Créer, modifier et supprimer des sources de données partagées &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="da0b5-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="da0b5-157">[Gérer les sources de données de rapport](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="da0b5-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="da0b5-158">Configurer les propriétés de la source de données d’un rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="da0b5-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  
