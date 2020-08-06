---
title: Créer et mapper un environnement serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isenvprop.variables.f1
- sql12.ssis.ssms.iscreateenv.f1
- sql12.ssis.ssms.isenvprop.permissions.f1
- sql12.ssis.ssms.isenvprop.general.f1
ms.assetid: b1cbb697-713f-48e4-b234-b23724d87451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9331b5078effb562931f45c48bd8ff975c1d1998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604061"
---
# <a name="create-and-map-a-server-environment"></a><span data-ttu-id="7c3d5-102">Créer et mapper un environnement serveur</span><span class="sxs-lookup"><span data-stu-id="7c3d5-102">Create and Map a Server Environment</span></span>
  <span data-ttu-id="7c3d5-103">Vous créez un environnement serveur pour spécifier les valeurs d’exécution des packages contenus dans un projet que vous avez déployé sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c3d5-103">You create a server environment to specify runtime values for packages contained in a project you've deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="7c3d5-104">Vous pouvez ensuite mapper les variables d'environnement aux paramètres, pour un package spécifique, pour les packages de point d'entrée, ou pour tous les packages dans un projet donné.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-104">You can then map the environment variables to parameters, for a specific package, for entry-point packages, or for all the packages in a given project.</span></span> <span data-ttu-id="7c3d5-105">Un package de point d'entrée est généralement un package parent qui exécute un package enfant.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-105">An entry-point package is typically a parent package that executes a child package.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7c3d5-106">Pour une exécution données, un package peut s'exécuter uniquement avec les valeurs contenues dans un seul environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-106">For a given execution, a package can execute only with the values contained in a single server environment.</span></span>  
  
 <span data-ttu-id="7c3d5-107">Vous pouvez interroger les affichages afin d'obtenir la liste des environnements serveur, des références environnementales et des variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-107">You can query views for a list of server environments, environment references, and environment variables.</span></span> <span data-ttu-id="7c3d5-108">Vous pouvez également appeler des procédures stockées pour ajouter, supprimer et modifier des environnements, des références environnementales et des variables d'environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-108">You can also call stored to add, delete, and modify environments, environment references, and environment variables.</span></span> <span data-ttu-id="7c3d5-109">Pour plus d'informations, consultez la section **Environnements serveur, variables de serveur et références d'environnement serveur** dans [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d5-109">For more information, see the **Server Environments, Server Variables and Server Environment References** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
### <a name="to-create-and-use-a-server-environment"></a><span data-ttu-id="7c3d5-110">Pour créer et utiliser un environnement serveur</span><span class="sxs-lookup"><span data-stu-id="7c3d5-110">To create and use a server environment</span></span>  
  
1.  <span data-ttu-id="7c3d5-111">Dans [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , développez le [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nœud catalogues> **SSISDB** dans l’Explorateur d’objets, puis recherchez le dossier **environnements** du projet pour lequel vous souhaitez créer un environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-111">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], expand the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Catalogs> **SSISDB** node in Object Explorer, and locate the **Environments** folder of the project for which you want to create an environment.</span></span>  
  
2.  <span data-ttu-id="7c3d5-112">Cliquez avec le bouton droit sur le dossier **Environnements** , puis cliquez sur **Créer l’environnement**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-112">Right-click the **Environments** folder, and then click **Create Environment**.</span></span>  
  
3.  <span data-ttu-id="7c3d5-113">Tapez un nom pour l'environnement, et éventuellement une description, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-113">Type a name for the environment and optionally a description, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="7c3d5-114">Cliquez avec le bouton droit sur le nouvel environnement, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-114">Right-click the new environment and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="7c3d5-115">Dans la page **Variables** , procédez comme suit pour ajouter une variable.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-115">On the **Variables** page, do the following to add a variable.</span></span>  
  
    1.  <span data-ttu-id="7c3d5-116">Sélectionnez le **Type** de la variable.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-116">Select the **Type** for the variable.</span></span> <span data-ttu-id="7c3d5-117">Le nom de la variable ne doit **pas** nécessairement correspondre au nom du paramètre du projet que vous mappez à la variable.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-117">The name of the variable **does not** need to match the name of the project parameter that you map to the variable.</span></span>  
  
    2.  <span data-ttu-id="7c3d5-118">Entrez une **Description** facultative pour la variable.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-118">Enter an optional **Description** for the variable.</span></span>  
  
    3.  <span data-ttu-id="7c3d5-119">Entrez la **Valeur** de la variable d'environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-119">Enter the **Value** for the environment variable.</span></span>  
  
         <span data-ttu-id="7c3d5-120">Pour plus d'informations sur les règles énoncées pour les noms de variable d'environnement, consultez la section **Variable d'environnement** dans [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d5-120">For information about the rules for environment variable names, see the **Environment Variable** section in [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
    4.  <span data-ttu-id="7c3d5-121">Indiquez si la variable contient une valeur sensible, en activant ou désactivant la case à cocher **Sensible** .</span><span class="sxs-lookup"><span data-stu-id="7c3d5-121">Indicate whether the variable contains sensitive value, by selecting or clearing the **Sensitive** checkbox.</span></span>  
  
         <span data-ttu-id="7c3d5-122">Si vous sélectionnez **Sensible**, la valeur de la variable ne s'affiche pas dans le champ **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="7c3d5-122">If you select **Sensitive**, the variable value does not display in the **Value** field.</span></span>  
  
         <span data-ttu-id="7c3d5-123">Les valeurs sensibles sont chiffrées dans le catalogue SSISDB.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-123">Sensitive values are encrypted in the SSISDB catalog.</span></span> <span data-ttu-id="7c3d5-124">Pour plus d'informations sur le chiffrement, consultez [SSIS Catalog](catalog/ssis-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="7c3d5-124">For more information about the encryption, see [SSIS Catalog](catalog/ssis-catalog.md).</span></span>  
  
6.  <span data-ttu-id="7c3d5-125">Dans la page **Autorisations** , accordez ou refusez des autorisations pour les rôles et les utilisateurs sélectionnés en procédant comme suit.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-125">On the **Permissions** page, grant or deny permissions for selected users and roles by doing the following.</span></span>  
  
    1.  <span data-ttu-id="7c3d5-126">Cliquez sur **Parcourir**, puis sélectionnez un ou plusieurs utilisateurs et rôles dans la boîte de dialogue **Parcourir tous les principaux** .</span><span class="sxs-lookup"><span data-stu-id="7c3d5-126">Click **Browse**, and then select one or more users and roles in the **Browse All Principals** dialog box.</span></span>  
  
    2.  <span data-ttu-id="7c3d5-127">Dans la zone **Connexions ou rôles** , sélectionnez l'utilisateur ou le rôle auquel vous souhaitez accorder ou refuser des autorisations.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-127">In the **Logins or roles** area, select the user or role that you want to grant or deny permissions for.</span></span>  
  
    3.  <span data-ttu-id="7c3d5-128">Dans la zone **Explicite** , cliquez sur **Accorder** ou sur **Refuser** en regard de chaque autorisation.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-128">In the **Explicit** area, click **Grant** or **Deny** next to each permission.</span></span>  
  
7.  <span data-ttu-id="7c3d5-129">Pour générer un script de l'environnement, cliquez sur **Script**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-129">To script the environment, click **Script**.</span></span> <span data-ttu-id="7c3d5-130">Par défaut, le script s'affiche dans une nouvelle fenêtre de l'Éditeur de requête.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-130">By default, the script displays in a new Query Editor window.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="7c3d5-131">Vous devez cliquer sur **Script** après avoir apporté des modifications aux propriétés d’environnement, telles que l’ajout d’une variable, et avant de cliquer sur **OK** dans la boîte de dialogue **Propriétés d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-131">You need to click **Script** after you've made one or changes to the environment properties, such as adding a variable, and before you click **OK** in the **Environment Properties** dialog box.</span></span> <span data-ttu-id="7c3d5-132">Sinon, aucun script n'est généré.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-132">Otherwise, a script is not generated.</span></span>  
  
8.  <span data-ttu-id="7c3d5-133">Cliquez sur **OK** pour enregistrer les propriétés de l'environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-133">Click **OK** to save your changes to the environment properties.</span></span>  
  
9. <span data-ttu-id="7c3d5-134">Sous le nœud **SSISDB** dans l’Explorateur d’objets, développez le dossier **Projets** , cliquez avec le bouton droit sur le projet, puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-134">Under the **SSISDB** node in Object Explorer, expand the **Projects** folder, right-click the project, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="7c3d5-135">Dans la page **Références** , cliquez sur **Ajouter** pour ajouter un environnement, puis cliquez sur **OK** pour enregistrer la référence dans l'environnement.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-135">On the **References** page, click **Add** to add an environment, and then click **OK** to save the reference to the environment.</span></span>  
  
11. <span data-ttu-id="7c3d5-136">Recliquez avec le bouton droit sur le projet, puis cliquez sur **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-136">Right-click the project again, and then click **Configure**.</span></span>  
  
12. <span data-ttu-id="7c3d5-137">Mappez la variable d'environnement à un paramètre que vous avez ajouté au package au moment de la conception, ou à un paramètre généré lors de la conversion du projet de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en modèle de déploiement de projet, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-137">To map the environment variable to a parameter that you added to the package at design-time or to a parameter that was generated when you converted the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the project deployment model, do the following.,</span></span>  
  
    1.  <span data-ttu-id="7c3d5-138">Dans l'onglet **Paramètres** dans la page **Paramètres** , cliquez sur le bouton Parcourir en regard du champ **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="7c3d5-138">In the **Parameters** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="7c3d5-139">Cliquez sur **Utiliser la variable d'environnement**, puis sélectionnez la variable d'environnement que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-139">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
13. <span data-ttu-id="7c3d5-140">Pour mapper la variable d'environnement à une propriété du gestionnaire de connexions, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-140">To map the environment variable to a connection manager property, do the following.</span></span> <span data-ttu-id="7c3d5-141">Les paramètres sont automatiquement générés sur le serveur SSIS pour les propriétés du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-141">Parameters are automatically generated on the SSIS server for the connection manager properties.</span></span>  
  
    1.  <span data-ttu-id="7c3d5-142">Dans l'onglet **Gestionnaires de connexions** dans la page **Paramètres** , cliquez sur le bouton Parcourir en regard du champ **Valeur** .</span><span class="sxs-lookup"><span data-stu-id="7c3d5-142">In the **Connection Managers** tab on the **Parameters** page, click the browse button next to the **Value** field.</span></span>  
  
    2.  <span data-ttu-id="7c3d5-143">Cliquez sur **Utiliser la variable d'environnement**, puis sélectionnez la variable d'environnement que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-143">Click **Use environment variable**, and then select the environment variable you created.</span></span>  
  
14. <span data-ttu-id="7c3d5-144">Cliquez deux fois sur **OK** pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="7c3d5-144">Click **OK** twice to save your changes.</span></span>  
  
  
