---
title: Créer une connexion de modèle sémantique BI à un classeur PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612533"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="348c2-102">Créer une connexion de modèle sémantique BI à un classeur PowerPivot</span><span class="sxs-lookup"><span data-stu-id="348c2-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="348c2-103">Utilisez les informations de cette rubrique pour configurer une connexion de modèle sémantique BI qui redirige vers un classeur PowerPivot dans la même batterie.</span><span class="sxs-lookup"><span data-stu-id="348c2-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="348c2-104">Après avoir créé une connexion de modèle sémantique BI et configuré les autorisations SharePoint, vous pouvez l'utiliser comme source de données pour les rapports Excel ou [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="348c2-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="348c2-105">Cette rubrique comprend les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="348c2-105">This topic includes the following sections.</span></span> <span data-ttu-id="348c2-106">Effectuez chaque tâche dans l'ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="348c2-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="348c2-107">Examiner la configuration requise</span><span class="sxs-lookup"><span data-stu-id="348c2-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="348c2-108">Créer une connexion</span><span class="sxs-lookup"><span data-stu-id="348c2-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="348c2-109">Configurer des autorisations SharePoint sur la connexion de modèle sémantique BI</span><span class="sxs-lookup"><span data-stu-id="348c2-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="348c2-110">Configurer les autorisations SharePoint sur le classeur</span><span class="sxs-lookup"><span data-stu-id="348c2-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="348c2-111">Next Steps</span><span class="sxs-lookup"><span data-stu-id="348c2-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="348c2-112">Vérifier les conditions préalables</span><span class="sxs-lookup"><span data-stu-id="348c2-112">Review Prerequisites</span></span>  
 <span data-ttu-id="348c2-113">Vous devez disposer d'autorisations Collaboration ou supérieures pour créer un fichier de connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="348c2-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="348c2-114">Vous devez disposer d'une bibliothèque qui prend en charge le type de contenu Connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="348c2-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="348c2-115">Pour plus d’informations, consultez [Ajouter un type de contenu de connexion de modèle sémantique bi à une bibliothèque &#40;PowerPivot pour SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="348c2-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="348c2-116">Vous devez connaître l’URL du classeur PowerPivot pour lequel vous configurez une connexion de modèle sémantique BI (par exemple, http://adventure-works/shared documents/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="348c2-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="348c2-117">Le classeur doit figurer dans la même batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="348c2-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="348c2-118">Tous les ordinateurs et utilisateurs qui participent à la séquence de connexion doivent être dans le même domaine ou dans un domaine approuvé (approbation bidirectionnelle).</span><span class="sxs-lookup"><span data-stu-id="348c2-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="348c2-119">Créer une connexion</span><span class="sxs-lookup"><span data-stu-id="348c2-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="348c2-120">Dans la bibliothèque qui contiendra la connexion de modèle sémantique BI, cliquez sur **Documents** sur le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="348c2-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="348c2-121">Cliquez sur la flèche de déroulement de Nouveau document, puis sélectionnez **Fichier de connexion BISM** pour ouvrir la page Nouvelle connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="348c2-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="348c2-122">![Sous-menu Nouveau document dans une bibliothèque SharePoint](../media/ssas-bismconnection-new.gif "Sous-menu Nouveau document dans une bibliothèque SharePoint")</span><span class="sxs-lookup"><span data-stu-id="348c2-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="348c2-123">Définissez la propriété de **serveur** sur l’URL SharePoint du classeur PowerPivot (par exemple, \*\* http://mysharepoint/shared documents/myWorkbook.xlsx\*\*.</span><span class="sxs-lookup"><span data-stu-id="348c2-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="348c2-124">Dans un déploiement PowerPivot pour SharePoint, les données peuvent être chargées sur tout serveur de la batterie.</span><span class="sxs-lookup"><span data-stu-id="348c2-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="348c2-125">Pour cette raison, les connexions de la source de données aux données PowerPivot spécifient juste le chemin d'accès au classeur.</span><span class="sxs-lookup"><span data-stu-id="348c2-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="348c2-126">Le service système PowerPivot détermine quel serveur charge les données.</span><span class="sxs-lookup"><span data-stu-id="348c2-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="348c2-127">N’utilisez pas la propriété **de base de données** ; elle n’est pas utilisée lors de la spécification de l’emplacement d’un classeur PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="348c2-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="348c2-128">Votre page doit ressembler à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="348c2-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="348c2-129">![Page de connexion BISM affichant l'URL du classeur](../media/ssas-bismconnection-ppvtds.gif "Page de connexion BISM affichant l'URL du classeur")</span><span class="sxs-lookup"><span data-stu-id="348c2-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="348c2-130">Éventuellement, si vous disposez d'autorisations SharePoint sur le classeur, une étape supplémentaire de validation est effectuée pour s'assurer que l'emplacement est valide.</span><span class="sxs-lookup"><span data-stu-id="348c2-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="348c2-131">Si vous n'êtes pas autorisé à accéder aux données, vous avez la possibilité d'enregistrer la connexion de modèle sémantique BI sans la réponse de validation.</span><span class="sxs-lookup"><span data-stu-id="348c2-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="348c2-132">Configurer des autorisations SharePoint sur la connexion de modèle sémantique BI</span><span class="sxs-lookup"><span data-stu-id="348c2-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="348c2-133">La possibilité d'utiliser une connexion de modèle sémantique BI comme source de données pour un classeur Excel ou un rapport Reporting Services requiert des autorisations de **Lecture** sur l'élément de connexion de modèle sémantique BI dans une bibliothèque SharePoint.</span><span class="sxs-lookup"><span data-stu-id="348c2-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="348c2-134">Le niveau d'autorisation Lecture inclut l'autorisation **Ouvrir les éléments** qui permet le téléchargement des informations de connexion de modèle sémantique BI vers une application bureautique Excel.</span><span class="sxs-lookup"><span data-stu-id="348c2-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="348c2-135">Il existe plusieurs manières d'accorder des autorisations dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="348c2-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="348c2-136">L’instruction suivante explique comment créer un groupe appelé **Utilisateurs BISM** qui dispose du niveau d’autorisation **Read** .</span><span class="sxs-lookup"><span data-stu-id="348c2-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="348c2-137">Vous devez être le propriétaire du site pour modifier des autorisations.</span><span class="sxs-lookup"><span data-stu-id="348c2-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="348c2-138">Dans Actions du site, cliquez sur **Autorisations de site**.</span><span class="sxs-lookup"><span data-stu-id="348c2-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="348c2-139">Cliquez sur **Créer un groupe** et nommez le nouveau groupe **Utilisateurs BISM**.</span><span class="sxs-lookup"><span data-stu-id="348c2-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="348c2-140">Choisissez le niveau d'autorisation **Lecture** et cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="348c2-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="348c2-141">Sélectionnez **Utilisateurs BISM** dans Personnes et groupes.</span><span class="sxs-lookup"><span data-stu-id="348c2-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="348c2-142">Pointez sur Nouveau, cliquez sur **Ajouter des utilisateurs**, puis ajoutez des comptes d'utilisateur ou de groupe.</span><span class="sxs-lookup"><span data-stu-id="348c2-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="348c2-143">Ces utilisateurs et groupes bénéficient maintenant d'autorisations de lecture sur l'ensemble du site, notamment les bibliothèques et listes qui héritent des autorisations au niveau du site.</span><span class="sxs-lookup"><span data-stu-id="348c2-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="348c2-144">Si ces autorisations sont trop élevées, vous pouvez sélectivement supprimer ce groupe de bibliothèques, de listes ou d'éléments spécifiques.</span><span class="sxs-lookup"><span data-stu-id="348c2-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="348c2-145">Pour supprimer sélectivement des autorisations au niveau de l'élément, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="348c2-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="348c2-146">Dans une bibliothèque, sélectionnez un document.</span><span class="sxs-lookup"><span data-stu-id="348c2-146">In a library, select a document.</span></span> <span data-ttu-id="348c2-147">Cliquez sur la flèche vers le bas, puis sur **Gérer les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="348c2-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="348c2-148">Par défaut, un élément hérite des autorisations.</span><span class="sxs-lookup"><span data-stu-id="348c2-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="348c2-149">Pour modifier les autorisations de documents individuels dans cette bibliothèque, cliquez sur **Arrêter l’héritage des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="348c2-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="348c2-150">Cochez la case en regard d’ **Utilisateurs BISM**.</span><span class="sxs-lookup"><span data-stu-id="348c2-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="348c2-151">Cliquez sur **Supprimer les autorisations des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="348c2-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a><span data-ttu-id="348c2-152">Configurer des autorisations SharePoint sur le classeur</span><span class="sxs-lookup"><span data-stu-id="348c2-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="348c2-153">Si vous utilisez une base de données PowerPivot dans un classeur Excel, les autorisations SharePoint sur le classeur Excel déterminent l'accès aux données par l'intermédiaire de la connexion de modèle sémantique BI.</span><span class="sxs-lookup"><span data-stu-id="348c2-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="348c2-154">Tous les utilisateurs qui accèdent au classeur doivent disposer d'autorisations de lecture sur le classeur pour pouvoir l'utiliser comme source de données externe.</span><span class="sxs-lookup"><span data-stu-id="348c2-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="348c2-155">Si vous avez créé un groupe **Utilisateurs BISM** à l’aide des instructions de la section précédente, les comptes d’utilisateur et de groupe qui sont membres d’ **Utilisateurs BISM** disposent des autorisations requises sur le classeur ainsi que sur le fichier de connexion du modèle sémantique BI, en supposant que le classeur utilise des autorisations héritées.</span><span class="sxs-lookup"><span data-stu-id="348c2-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="348c2-156">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="348c2-156">Next Steps</span></span>  
 <span data-ttu-id="348c2-157">Après avoir créé et sécurisé une connexion de modèle sémantique BI, vous pouvez la spécifier en tant que source de données.</span><span class="sxs-lookup"><span data-stu-id="348c2-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="348c2-158">Pour plus d’informations, consultez [Utiliser une connexion de modèle sémantique BI dans Excel ou Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="348c2-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="348c2-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="348c2-159">See Also</span></span>  
 <span data-ttu-id="348c2-160">[Connexion de modèle sémantique BI PowerPivot &#40;. BISM&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="348c2-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="348c2-161">[Utiliser une connexion de modèle sémantique BI dans Excel ou Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="348c2-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="348c2-162">Créer une connexion de modèle sémantique BI à une base de données model tabulaire</span><span class="sxs-lookup"><span data-stu-id="348c2-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  
