---
title: Octroi d’autorisations de base de données de processus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 69ba952e-09ae-49a9-9297-00e32e8e89a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6ada30e3fb509bd1ffd210485ce0e34b7bf86fb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600292"
---
# <a name="granting-process-database-permissions"></a><span data-ttu-id="3742b-102">Attribution de l'autorisation de traiter la base de données</span><span class="sxs-lookup"><span data-stu-id="3742b-102">Granting Process Database Permissions</span></span>
  <span data-ttu-id="3742b-103">Après avoir installé une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tous les membres du rôle d'administrateur de serveur [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans cette instance disposent d'autorisations sur le serveur pour exécuter n'importe quelle tâche dans l'instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3742b-103">After you install an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], all members of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server administrator role in that instance have server-wide permissions to perform any task within the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="3742b-104">Par défaut, aucun autre utilisateur n'est autorisé à administrer ou afficher des objets dans l'instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3742b-104">By default, no other users have any permission to administer or view any objects in the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

 <span data-ttu-id="3742b-105">Un membre du rôle d'administrateur de serveur peut octroyer aux utilisateurs l'accès administratif sur le serveur en les faisant membres du rôle.</span><span class="sxs-lookup"><span data-stu-id="3742b-105">A member of the server administrator role can grant users administrative access on a server-wide basis by making them members of the role.</span></span> <span data-ttu-id="3742b-106">Un membre du rôle d'administrateur de serveur peut également accorder à des utilisateurs un accès plus limité en leur octroyant des autorisations d'administration ou d'accès limitées ou complètes au niveau de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3742b-106">A member of the server administrator role can also grant users access on a more limited basis by granting them limited or complete administrative or access permissions at the database level.</span></span> <span data-ttu-id="3742b-107">Les autorisations administratives limitées incluent les autorisations de traiter ou de lire la définition au niveau de la base de données, du cube ou de la dimension.</span><span class="sxs-lookup"><span data-stu-id="3742b-107">Limited administrative permissions include process or read definition permissions at the database, cube, or dimension level.</span></span>

 <span data-ttu-id="3742b-108">Dans les tâches de cette rubrique, vous allez définir le rôle de sécurité Process Database Objects, qui confère à ses membres l'autorisation de traiter tous les objets de base de données, mais ne les autorise pas à afficher des données dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3742b-108">In the tasks in this topic, you will define a Process Database Objects security role that grants members of the role permission to process all database objects, but no permission to view data within the database.</span></span>

## <a name="defining-a-process-database-objects-security-role"></a><span data-ttu-id="3742b-109">Définition du rôle de sécurité Process Database Objects</span><span class="sxs-lookup"><span data-stu-id="3742b-109">Defining a Process Database Objects Security Role</span></span>

1.  <span data-ttu-id="3742b-110">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur **Rôles** , puis cliquez sur **Nouveau rôle** pour ouvrir le Concepteur de rôle.</span><span class="sxs-lookup"><span data-stu-id="3742b-110">In Solution Explorer, right-click **Roles** and then click **New Role** to open the Role Designer.</span></span>

2.  <span data-ttu-id="3742b-111">Activez la case à cocher **Traiter la base de données** .</span><span class="sxs-lookup"><span data-stu-id="3742b-111">Click the **Process database** check box.</span></span>

3.  <span data-ttu-id="3742b-112">Dans la Fenêtre Propriétés, remplacez la propriété **nom** de ce nouveau rôle par `Process Database Objects Role` .</span><span class="sxs-lookup"><span data-stu-id="3742b-112">In the Properties window, change the **Name** property for this new role to `Process Database Objects Role`.</span></span>

     <span data-ttu-id="3742b-113">![Concepteur de rôle](../../2014/tutorials/media/l10-security-1.png "Concepteur de rôle")</span><span class="sxs-lookup"><span data-stu-id="3742b-113">![Role Designer](../../2014/tutorials/media/l10-security-1.png "Role Designer")</span></span>

4.  <span data-ttu-id="3742b-114">Cliquez sur l'onglet **Adhésion** du Concepteur de rôles et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3742b-114">Switch to the **Membership** tab of Role Designer and click **Add**.</span></span>

5.  <span data-ttu-id="3742b-115">Entrez les comptes d'utilisateur de domaine ou de groupe Windows qui seront membres de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="3742b-115">Enter the accounts of the Windows domain users or groups who will be members of this role.</span></span> <span data-ttu-id="3742b-116">Cliquez sur **Vérifier les noms** pour vérifier les informations de compte, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3742b-116">Click **Check Names** to verify the account information, and then click **OK**.</span></span>

6.  <span data-ttu-id="3742b-117">Cliquez sur l'onglet **Cubes** du Concepteur de rôles.</span><span class="sxs-lookup"><span data-stu-id="3742b-117">Switch to the **Cubes** tab of Role Designer.</span></span>

     <span data-ttu-id="3742b-118">Notez que les membres de ce rôle sont autorisés à traiter cette base de données, mais n'ont pas l'autorisation d'accéder aux données du cube du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , ni d'accès Cube/Extraction local, comme le montre l'image suivante.</span><span class="sxs-lookup"><span data-stu-id="3742b-118">Notice that members of this role have permissions to process this database, but have no permission to access the data in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube and have no local cube/drillthrough access, as shown in the following image.</span></span>

     <span data-ttu-id="3742b-119">![Onglet Cubes du Concepteur de rôle](../../2014/tutorials/media/l10-security-2.png "Onglet Cubes du Concepteur de rôle")</span><span class="sxs-lookup"><span data-stu-id="3742b-119">![Cubes tab of Role Designer](../../2014/tutorials/media/l10-security-2.png "Cubes tab of Role Designer")</span></span>

7.  <span data-ttu-id="3742b-120">Cliquez sur l'onglet **Dimensions** du Concepteur de rôles.</span><span class="sxs-lookup"><span data-stu-id="3742b-120">Switch to the **Dimensions** tab of Role Designer.</span></span>

     <span data-ttu-id="3742b-121">Notez que les membres de ce rôle ont les autorisations nécessaires pour traiter tous les objets de dimension de cette base de données et, par défaut, ont les autorisations de lecture pour accéder à chaque objet de dimension dans la base de données du didacticiel de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3742b-121">Notice that members of this role have permissions to process all dimension objects in this database, and, by default, have read permissions to access each dimension object in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial database.</span></span>

8.  <span data-ttu-id="3742b-122">Dans le menu **Générer** , cliquez sur **Déployer Analysis Services Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="3742b-122">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>

     <span data-ttu-id="3742b-123">Au terme de cette procédure, vous avez défini et déployé le rôle de sécurité Process Database Objects.</span><span class="sxs-lookup"><span data-stu-id="3742b-123">You have now successfully defined and deployed the Process Database Objects security role.</span></span> <span data-ttu-id="3742b-124">Après le déploiement d'un cube vers l'environnement de production, les administrateurs du cube déployé peuvent ajouter des utilisateurs à ce rôle, ce qui leur permet de déléguer des responsabilités de traitement à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3742b-124">After a cube is deployed to the production environment, the administrators of the deployed cube can add users to this role as required to delegate processing responsibilities to specific users.</span></span>

> [!NOTE]
>  <span data-ttu-id="3742b-125">Un projet complet pour la leçon 10 est disponible en téléchargeant et en installant les exemples mis à jour.</span><span class="sxs-lookup"><span data-stu-id="3742b-125">A completed project for Lesson 10 is available by downloading and installing the samples.</span></span> <span data-ttu-id="3742b-126">Pour plus d’informations, consultez [installer des exemples de données et de projets pour le Analysis Services didacticiel sur la modélisation multidimensionnelle](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="3742b-126">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3742b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3742b-127">See Also</span></span>
 [<span data-ttu-id="3742b-128">Rôles et autorisations &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3742b-128">Roles and Permissions &#40;Analysis Services&#41;</span></span>](multidimensional-models/roles-and-permissions-analysis-services.md)


