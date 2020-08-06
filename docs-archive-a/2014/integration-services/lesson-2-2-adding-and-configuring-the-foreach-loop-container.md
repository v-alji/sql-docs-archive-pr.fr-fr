---
title: 'Étape 2 : Ajout et configuration du conteneur de boucles Foreach | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 88a973cc-0f23-4ecf-adb6-5b06279c2df6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de5e8875c43edda618ccef4839c88c3b84a003cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601567"
---
# <a name="step-2-adding-and-configuring-the-foreach-loop-container"></a><span data-ttu-id="11aee-102">Étape 2 : Ajout et configuration du conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="11aee-102">Step 2: Adding and Configuring the Foreach Loop Container</span></span>
  <span data-ttu-id="11aee-103">Dans cette tâche, vous allez activer la fonction qui permet d'effectuer des boucles dans un dossier de fichiers plats et d'appliquer la transformation de flux de données utilisée dans la leçon 1 à chacun de ces fichiers plats.</span><span class="sxs-lookup"><span data-stu-id="11aee-103">In this task, you will add the ability to loop through a folder of flat files and apply the same data flow transformation used in Lesson 1 to each of those flat files.</span></span> <span data-ttu-id="11aee-104">Pour activer cette fonction, vous allez ajouter et configurer un conteneur de boucles Foreach dans le flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="11aee-104">You do this by adding and configuring a Foreach Loop container to the control flow.</span></span>  
  
 <span data-ttu-id="11aee-105">Le conteneur de boucles Foreach que vous allez ajouter doit pouvoir se connecter à chaque fichier plat dans le dossier.</span><span class="sxs-lookup"><span data-stu-id="11aee-105">The Foreach Loop container that you add must be able to connect to each flat file in the folder.</span></span> <span data-ttu-id="11aee-106">Étant donné que tous les fichiers du dossier ont le même format, le conteneur de boucles Foreach peut utiliser le même Gestionnaire de connexions de fichiers plats pour se connecter à chacun de ces fichiers.</span><span class="sxs-lookup"><span data-stu-id="11aee-106">Because all the files in the folder have the same format, the Foreach Loop container can use the same Flat File connection manager to connect to each of these files.</span></span> <span data-ttu-id="11aee-107">Le Gestionnaire de connexions de fichiers plats que le conteneur va utiliser est le même que celui créé au cours de la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="11aee-107">The Flat File connection manager that the container will use is the same Flat File connection manager that you created in Lesson 1.</span></span>  
  
 <span data-ttu-id="11aee-108">Pour l'instant, le Gestionnaire de connexions de fichiers plats créé au cours de la leçon 1 se connecte uniquement à un seul fichier plat spécifique.</span><span class="sxs-lookup"><span data-stu-id="11aee-108">Currently, the Flat File connection manager from Lesson 1 connects to only one, specific flat file.</span></span> <span data-ttu-id="11aee-109">Pour que la connexion réitère et s'établisse à chaque fichier plat dans le dossier, vous devez configurer le conteneur de boucles Foreach et le Gestionnaire de connexions de fichiers plats comme suit :</span><span class="sxs-lookup"><span data-stu-id="11aee-109">To iteratively connect to each flat file in the folder, you will have to configure both the Foreach Loop container and the Flat File connection manager as follows:</span></span>  
  
-   <span data-ttu-id="11aee-110">**Conteneur de boucles Foreach :** vous allez mapper la valeur énumérée du conteneur à une variable de package définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11aee-110">**Foreach Loop container:** You will map the enumerated value of the container to a user-defined package variable.</span></span> <span data-ttu-id="11aee-111">Le conteneur va ensuite utiliser cette variable définie par l'utilisateur pour modifier dynamiquement la propriété `ConnectionString` du Gestionnaire de connexions de fichiers plats et répéter la connexion à chaque fichier plat dans le dossier.</span><span class="sxs-lookup"><span data-stu-id="11aee-111">The container will then use this user-defined variable to dynamically modify the `ConnectionString` property of the Flat File connection manager and iteratively connect to each flat file in the folder.</span></span>  
  
-   <span data-ttu-id="11aee-112">**Gestionnaire de connexions de fichiers plats :** Vous allez modifier le gestionnaire de connexions qui a été créé au cours de la leçon 1 en utilisant une variable définie par l’utilisateur pour remplir la propriété du gestionnaire de connexions `ConnectionString` .</span><span class="sxs-lookup"><span data-stu-id="11aee-112">**Flat File connection manager:** You will modify the connection manager that was created in Lesson 1 by using a user-defined variable to populate the connection manager's `ConnectionString` property.</span></span>  
  
 <span data-ttu-id="11aee-113">Les procédures de cette tâche montrent comment créer et modifier le conteneur de boucles Foreach pour utiliser une variable de package définie par l'utilisateur et comment ajouter la tâche de flux de données à la boucle.</span><span class="sxs-lookup"><span data-stu-id="11aee-113">The procedures in this task show you how to create and modify the Foreach Loop container to use a user-defined package variable and to add the data flow task to the loop.</span></span> <span data-ttu-id="11aee-114">Au cours de la tâche suivante, vous allez apprendre à modifier le Gestionnaire de connexions de fichiers plats pour qu'il utilise une variable définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="11aee-114">You will learn how to modify the Flat File connection manager to use a user-defined variable in the next task.</span></span>  
  
 <span data-ttu-id="11aee-115">Une fois ces modifications apportées au package et le package exécuté, le conteneur de boucles Foreach effectue une itération dans la collection de fichiers dans le dossier Sample Data.</span><span class="sxs-lookup"><span data-stu-id="11aee-115">After you have made these modifications to the package, when the package is run, the Foreach Loop Container will iterate through the collection of files in the Sample Data folder.</span></span> <span data-ttu-id="11aee-116">À chaque fois qu'un fichier répondant aux critères est trouvé, le conteneur de boucles Foreach renseigne la variable définie par l'utilisateur avec le nom du fichier, mappe cette variable sur la propriété `ConnectionString` du gestionnaire de connexions de fichiers plats SampleCurrencyData, puis exécute le flux de données par rapport à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="11aee-116">Each time a file is found that matches the criteria, the Foreach Loop Container will populate the user-defined variable with the file name, map the user-defined variable to the `ConnectionString` property of the Sample Currency Data Flat File connection manager, and then run the data flow against that file.</span></span> <span data-ttu-id="11aee-117">Par conséquent, à chaque itération de la boucle Foreach, la tâche de flux de données utilise un fichier plat différent.</span><span class="sxs-lookup"><span data-stu-id="11aee-117">Therefore, in each iteration of the Foreach Loop the Data Flow task will consume a different flat file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11aee-118">Étant donné que [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sépare le flux de contrôle du flux de données, les boucles que vous ajoutez au flux de contrôle ne nécessitent pas la modification du flux de données.</span><span class="sxs-lookup"><span data-stu-id="11aee-118">Because [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates control flow from data flow, any looping that you add to the control flow will not require modification to the data flow.</span></span> <span data-ttu-id="11aee-119">Par conséquent, il n'est pas nécessaire de modifier le flux de données que vous avez créé au cours de la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="11aee-119">Therefore, the data flow that you created in Lesson 1 does not have to be changed.</span></span>  
  
### <a name="to-add-a-foreach-loop-container"></a><span data-ttu-id="11aee-120">Pour ajouter un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="11aee-120">To add a Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="11aee-121">Dans **SQL Server Data Tools**, cliquez sur l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="11aee-121">In **SQL Server Data Tools**, click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="11aee-122">Dans la **Boîte à outils SSIS**, développez **Conteneurs**, puis faites glisser un **conteneur de boucles Foreach** dans l’aire de conception de l’onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="11aee-122">In the **SSIS Toolbox**, expand **Containers**, and then drag a **Foreach Loop Container** onto the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="11aee-123">Cliquez avec le bouton droit sur le **conteneur de boucles Foreach** que vous venez d’ajouter et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="11aee-123">Right-click the newly added **Foreach Loop Container** and select **Edit**.</span></span>  
  
4.  <span data-ttu-id="11aee-124">Dans la boîte de dialogue **éditeur de boucle foreach** , dans la page **général** , pour **nom**, entrez `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="11aee-124">In the **Foreach Loop Editor** dialog box, on the **General** page, for **Name**, enter `Foreach File in Folder`.</span></span> <span data-ttu-id="11aee-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="11aee-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="11aee-126">Cliquez avec le bouton droit sur le conteneur de boucles Foreach, cliquez sur **Propriétés**, et dans la fenêtre Propriétés, vérifiez que la `LocaleID` propriété est définie sur **anglais (États-Unis)**.</span><span class="sxs-lookup"><span data-stu-id="11aee-126">Right-click the Foreach Loop container, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
### <a name="to-configure-the-enumerator-for-the-foreach-loop-container"></a><span data-ttu-id="11aee-127">Pour configurer l'énumérateur pour le conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="11aee-127">To configure the enumerator for the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="11aee-128">Double-cliquez sur Foreach File in Folder pour rouvrir l’**Éditeur de boucle Foreach**.</span><span class="sxs-lookup"><span data-stu-id="11aee-128">Double-click Foreach File in Folder to reopen the **Foreach Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="11aee-129">Cliquez sur **Collection**.</span><span class="sxs-lookup"><span data-stu-id="11aee-129">Click **Collection**.</span></span>  
  
3.  <span data-ttu-id="11aee-130">Dans la page **Collection** , cliquez sur **Énumérateur Foreach File**.</span><span class="sxs-lookup"><span data-stu-id="11aee-130">On the **Collection** page, select **Foreach File Enumerator**.</span></span>  
  
4.  <span data-ttu-id="11aee-131">Dans le groupe **Configuration de l’énumérateur** , cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="11aee-131">In the **Enumerator configuration** group, click **Browse**.</span></span>  
  
5.  <span data-ttu-id="11aee-132">Dans la boîte de dialogue **Rechercher un dossier** , recherchez dans votre ordinateur le dossier qui contient les fichiers Currency_\*.txt.</span><span class="sxs-lookup"><span data-stu-id="11aee-132">In the **Browse for Folder** dialog box, locate the folder on your machine that contains the Currency_\*.txt files.</span></span>  
  
     <span data-ttu-id="11aee-133">Ces exemples de données sont inclus dans les packages de leçons [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="11aee-133">This sample data is included with the [!INCLUDE[ssIS](../includes/ssis-md.md)] lesson packages.</span></span> <span data-ttu-id="11aee-134">Pour télécharger ces exemples de données et les packages de leçons, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="11aee-134">To download the sample data and the lesson packages, do the following.</span></span>  
  
    1.  <span data-ttu-id="11aee-135">Accédez à [Exemples de produits Integration Services](https://go.microsoft.com/fwlink/?LinkId=275027)</span><span class="sxs-lookup"><span data-stu-id="11aee-135">Navigate to [Integration Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=275027)</span></span>  
  
    2.  <span data-ttu-id="11aee-136">Cliquez sur l’onglet **téléchargements** .</span><span class="sxs-lookup"><span data-stu-id="11aee-136">Click the **DOWNLOADS** tab.</span></span>  
  
    3.  <span data-ttu-id="11aee-137">Cliquez sur le lien hypertexte « https://msftisprodsamples.codeplex.com/downloads/get/578097 » SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip fichier.</span><span class="sxs-lookup"><span data-stu-id="11aee-137">Click the  HYPERLINK "https://msftisprodsamples.codeplex.com/downloads/get/578097" SQL2012.Integration_Services.Create_Simple_ETL_Tutorial.Sample.zip file.</span></span>  
  
6.  <span data-ttu-id="11aee-138">Dans la zone **Fichiers**, tapez **Currency_\*.txt**.</span><span class="sxs-lookup"><span data-stu-id="11aee-138">In the **Files** box, type **Currency_\*.txt**.</span></span>  
  
### <a name="to-map-the-enumerator-to-a-user-defined-variable"></a><span data-ttu-id="11aee-139">Pour mapper l'énumérateur à une variable définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="11aee-139">To map the enumerator to a user-defined variable</span></span>  
  
1.  <span data-ttu-id="11aee-140">Cliquez sur **Mappages de variables**.</span><span class="sxs-lookup"><span data-stu-id="11aee-140">Click **Variable Mappings**.</span></span>  
  
2.  <span data-ttu-id="11aee-141">Dans la page **mappage de variables** , dans la colonne **variable** , cliquez sur la cellule vide et sélectionnez **\<New Variable...>** .</span><span class="sxs-lookup"><span data-stu-id="11aee-141">On the **Variable Mappings** page, in the **Variable** column, click the empty cell and select **\<New Variable...>**.</span></span>  
  
3.  <span data-ttu-id="11aee-142">Dans la boîte de dialogue **Ajouter une variable** , pour **nom**, tapez `varFileName` .</span><span class="sxs-lookup"><span data-stu-id="11aee-142">In the **Add Variable** dialog box, for **Name**, type `varFileName`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="11aee-143">Les noms des variables tiennent compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="11aee-143">Variable names are case sensitive.</span></span>  
  
4.  <span data-ttu-id="11aee-144">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="11aee-144">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="11aee-145">Cliquez à nouveau sur **OK** pour quitter la boîte de dialogue **Éditeur de boucle Foreach** .</span><span class="sxs-lookup"><span data-stu-id="11aee-145">Click **OK** again to exit the **Foreach Loop Editor** dialog box.</span></span>  
  
### <a name="to-add-the-data-flow-task-to-the-loop"></a><span data-ttu-id="11aee-146">Pour ajouter la tâche de flux de données à la boucle</span><span class="sxs-lookup"><span data-stu-id="11aee-146">To add the data flow task to the loop</span></span>  
  
-   <span data-ttu-id="11aee-147">Faites glisser la tâche de workflow **extraire l’exemple de données monétaires** sur le conteneur de boucles Foreach maintenant renommé `Foreach File in Folder` .</span><span class="sxs-lookup"><span data-stu-id="11aee-147">Drag the **Extract Sample Currency Data** data flow task onto the Foreach Loop container now renamed `Foreach File in Folder`.</span></span>  
  
## <a name="next-lesson-task"></a><span data-ttu-id="11aee-148">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="11aee-148">Next Lesson Task</span></span>  
 [<span data-ttu-id="11aee-149">Étape 3 : Modification du Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="11aee-149">Step 3: Modifying the Flat File Connection Manager</span></span>](lesson-2-3-modifying-the-flat-file-connection-manager.md)  
  
## <a name="see-also"></a><span data-ttu-id="11aee-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11aee-150">See Also</span></span>  
 <span data-ttu-id="11aee-151">[Configurer un conteneur de boucles Foreach](control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="11aee-151">[Configure a Foreach Loop Container](control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="11aee-152">Utiliser des variables dans des packages</span><span class="sxs-lookup"><span data-stu-id="11aee-152">Use Variables in Packages</span></span>](use-variables-in-packages.md)  
  
