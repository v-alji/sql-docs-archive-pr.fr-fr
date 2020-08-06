---
title: 'Étape 2 : Activation et configuration des configurations de package | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 005218ab-8dd5-48e9-a185-6bc60cd43a7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a804efcd84ebe563a13f61443fe19096788ca809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602886"
---
# <a name="step-2-enabling-and-configuring-package-configurations"></a><span data-ttu-id="e6bb3-102">Étape 2 : Activation et configuration des configurations de package</span><span class="sxs-lookup"><span data-stu-id="e6bb3-102">Step 2: Enabling and Configuring Package Configurations</span></span>
  <span data-ttu-id="e6bb3-103">Au cours de cette tâche, vous allez convertir le projet en modèle de déploiement de package et activer les configurations du package à l'aide de l'Assistant Configuration de package.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-103">In this task, you will convert the project to the Package Deployment Model and enable package configurations using the Package Configuration Wizard.</span></span> <span data-ttu-id="e6bb3-104">Vous allez utiliser cet Assistant pour générer un fichier de configuration XML qui contient les paramètres de configuration de la propriété `Directory` du conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-104">You will use this wizard to generate an XML configuration file that contains configuration settings for the `Directory` property of the Foreach Loop container.</span></span> <span data-ttu-id="e6bb3-105">La valeur de la propriété Directory est fournie par la nouvelle variable de niveau package que vous pouvez mettre à jour au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-105">The value of the Directory property is supplied by a new package-level variable that you can update at run time.</span></span> <span data-ttu-id="e6bb3-106">De plus, vous allez remplir un nouveau dossier de données exemple à utiliser au cours du test.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-106">Additionally, you will populate a new sample data folder to use during testing.</span></span>  
  
### <a name="to-create-a-new-package-level-variable-mapped-to-the-directory-property"></a><span data-ttu-id="e6bb3-107">Pour créer une nouvelle variable de niveau package mappée à la propriété Directory</span><span class="sxs-lookup"><span data-stu-id="e6bb3-107">To create a new package-level variable mapped to the Directory property</span></span>  
  
1.  <span data-ttu-id="e6bb3-108">Cliquez sur l’arrière-plan de l’onglet **Flux de contrôle** dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-108">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e6bb3-109">Cette opération permet de définir l'étendue de la variable que vous allez créer pour le package.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-109">This sets the scope for the variable you will create to the package.</span></span>  
  
2.  <span data-ttu-id="e6bb3-110">Dans le menu [!INCLUDE[ssIS](../includes/ssis-md.md)] , cliquez sur **Variables**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-110">On the [!INCLUDE[ssIS](../includes/ssis-md.md)] menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="e6bb3-111">Dans la fenêtre **Variables** , cliquez sur l’icône Ajouter une variable.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-111">In the **Variables** window, click the Add Variable icon.</span></span>  
  
4.  <span data-ttu-id="e6bb3-112">Dans la zone **Nom** , tapez **varFolderName**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-112">In the **Name** box, type **varFolderName**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e6bb3-113">Les noms des variables tiennent compte de la casse.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-113">Variable names are case sensitive.</span></span>  
  
5.  <span data-ttu-id="e6bb3-114">Vérifiez que la zone **étendue** affiche le nom du package, leçon 5.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-114">Verify that the **Scope** box shows the name of the package, Lesson 5.</span></span>  
  
6.  <span data-ttu-id="e6bb3-115">Définissez la valeur de la zone **Type de données** de la variable `varFolderName` à **String**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-115">Set the value of the **Data Type** box of the `varFolderName` variable to **String**.</span></span>  
  
7.  <span data-ttu-id="e6bb3-116">Réaffichez l’onglet **Flux de contrôle** et double-cliquez sur le conteneur **Foreach File in Folder** .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-116">Return to the **Control Flow** tab and double-click the **Foreach File in Folder** container.</span></span>  
  
8.  <span data-ttu-id="e6bb3-117">Dans la page **Collection** de l’**Éditeur de boucle Foreach**, cliquez sur **Expressions**, puis sur le bouton **(...)**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-117">On the **Collection** page of the **Foreach Loop Editor**, click **Expressions**, and then click the ellipsis button **(...)**.</span></span>  
  
9. <span data-ttu-id="e6bb3-118">Dans l' **éditeur d’expressions**de la propriété, cliquez dans la liste **propriété** , puis sélectionnez `Directory` .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-118">In the **Property Expressions Editor**, click in the **Property** list, and select `Directory`.</span></span>  
  
10. <span data-ttu-id="e6bb3-119">Dans la zone **expression** , cliquez sur le bouton de sélection **(...)**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-119">In the **Expression** box, click the ellipsis button **(...)**.</span></span>  
  
11. <span data-ttu-id="e6bb3-120">Dans le **Générateur d’expressions**, développez le dossier Variables et faites glisser la variable **User::varFolderName** vers la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-120">In the **Expression Builder**, expand the Variables folder, and drag the variable **User::varFolderName** to the **Expression** box.</span></span>  
  
12. <span data-ttu-id="e6bb3-121">Cliquez sur **OK** pour quitter le **Générateur d’expressions**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-121">Click **OK** to exit the **Expression Builder**.</span></span>  
  
13. <span data-ttu-id="e6bb3-122">Cliquez sur **OK** pour quitter **l’Éditeur d’expressions de la propriété**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-122">Click **OK** to exit the **Property Expressions Editor**.</span></span>  
  
14. <span data-ttu-id="e6bb3-123">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur de boucle Foreach**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-123">Click **OK** to exit the **Foreach Loop Editor**.</span></span>  
  
### <a name="to-enable-package-configurations"></a><span data-ttu-id="e6bb3-124">Pour activer les configurations de package</span><span class="sxs-lookup"><span data-stu-id="e6bb3-124">To enable package configurations</span></span>  
  
1.  <span data-ttu-id="e6bb3-125">Dans le menu **Projet**, cliquez sur **Convertir en modèle de déploiement de package**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-125">On the **Project Menu**, click **Convert to Package Deployment Model**.</span></span>  
  
2.  <span data-ttu-id="e6bb3-126">Cliquez sur **OK** dans la boîte de dialogue d’avertissement et, une fois la conversion terminée, cliquez sur **OK** dans la boîte de dialogue **Convertir en modèle de déploiement de package** .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-126">Click **OK** on the warning prompt and, once the conversion is complete, click **OK** on the **Convert to Package Deployment Model** dialog.</span></span>  
  
3.  <span data-ttu-id="e6bb3-127">Cliquez sur l’arrière-plan de l’onglet **Flux de contrôle** dans le Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-127">Click the background of the **Control Flow** tab in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
4.  <span data-ttu-id="e6bb3-128">Dans le menu **SSIS** , cliquez sur **Configurations du package**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-128">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
5.  <span data-ttu-id="e6bb3-129">Dans la boîte de dialogue **Bibliothèque des configurations du package** , sélectionnez **Activer les configurations du package**et cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-129">In the **Package Configurations Organizer** dialog box, select **Enable Package Configurations**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="e6bb3-130">Sur la page d’accueil de l’Assistant Configuration de package, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-130">On the welcome page of the Package Configuration Wizard, click **Next**.</span></span>  
  
7.  <span data-ttu-id="e6bb3-131">Dans la page **Sélectionner le type de configuration** , vérifiez que **Type de configuration** a la valeur **Fichier de configuration XML**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-131">On the **Select Configuration Type** page, verify that the **Configuration type** is set to **XML configuration file**.</span></span>  
  
8.  <span data-ttu-id="e6bb3-132">Dans la page **Sélectionner le type de configuration** , cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-132">On the **Select Configuration Type** page, click **Browse**.</span></span>  
  
9. <span data-ttu-id="e6bb3-133">Par défaut, quand la boîte de dialogue **Sélectionner l’emplacement du fichier de configuration** s’ouvre, elle contient le dossier du projet.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-133">By default, the **Select Configuration File Location** dialog box will open to the project folder.</span></span>  
  
10. <span data-ttu-id="e6bb3-134">Dans la boîte de dialogue **Sélectionner l’emplacement du fichier de configuration** , tapez **SSISTutorial** dans la zone **Nom de fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-134">In the **Select Configuration File Location** dialog box, for **File name** type **SSISTutorial**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="e6bb3-135">Dans la page **Sélectionner le type de configuration** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-135">On the **Select Configuration Type** page, click **Next.**</span></span>  
  
12. <span data-ttu-id="e6bb3-136">Dans la **page Sélectionner les propriétés à exporter** , dans le volet **objets** , développez **variables**, **varFolderName**, **Propriétés**, puis sélectionnez **valeur**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-136">On the **Select Properties to Export** page, in the **Objects** pane, expand **Variables**, expand **varFolderName**, expand **Properties**, and then select **Value**.</span></span>  
  
13. <span data-ttu-id="e6bb3-137">Dans la page **Sélectionner les propriétés à exporter** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-137">On the **Select Properties to Export** page, click **Next**.</span></span>  
  
14. <span data-ttu-id="e6bb3-138">Dans la page **Fin de l’Assistant** , tapez un nom de configuration par exemple : **Configuration du répertoire du didacticiel SSIS**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-138">On the **Completing the Wizard** page, type a configuration name for the configuration, such as **SSIS Tutorial Directory configuration**.</span></span> <span data-ttu-id="e6bb3-139">Il s’agit du nom de configuration qui s’affiche dans la boîte de dialogue **Bibliothèque des configurations du package** .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-139">This is the configuration name that is displayed in the **Package Configuration Organizer** dialog box.</span></span>  
  
15. <span data-ttu-id="e6bb3-140">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-140">Click **Finish**.</span></span>  
  
16. <span data-ttu-id="e6bb3-141">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-141">Click **Close**.</span></span>  
  
17. <span data-ttu-id="e6bb3-142">L’Assistant crée un fichier de configuration, nommé SSISTutorial. dtsConfig, qui contient des paramètres de configuration pour le `value` de la variable qui, à son tour, définit la `Directory` propriété de l’énumérateur.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-142">The wizard creates a configuration file, named SSISTutorial.dtsConfig, that contains configuration settings for the `value` of the variable that in turn sets the `Directory` property of the enumerator.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6bb3-143">Un fichier de configuration contient généralement des informations complexes sur les propriétés de package, mais dans le cadre de ce didacticiel, la seule information qui nous concerne est :</span><span class="sxs-lookup"><span data-stu-id="e6bb3-143">A configuration file typically contains complex information about the package properties, but for this tutorial the only configuration information should be</span></span>  
    > <span data-ttu-id="e6bb3-144"><Configuration ConfiguredType="Property"</span><span class="sxs-lookup"><span data-stu-id="e6bb3-144"><Configuration ConfiguredType="Property"</span></span>  
    > <span data-ttu-id="e6bb3-145">Path = " : \package.variables [user :: varFolderName]. Propriétés [valeur] "ValueType =" chaîne "\></span><span class="sxs-lookup"><span data-stu-id="e6bb3-145">Path="\Package.Variables[User::varFolderName].Properties[Value]" ValueType="String"\></span></span>  
    >  \<ConfiguredValue>\</ConfiguredValue>  
    > <span data-ttu-id="e6bb3-146">\</Configuration>.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-146">\</Configuration>.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="e6bb3-147">Pour créer et remplir un nouveau dossier de données exemple</span><span class="sxs-lookup"><span data-stu-id="e6bb3-147">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="e6bb3-148">Dans l’Explorateur Windows, au niveau racine de votre lecteur (par exemple, C : \\ ), créez un nouveau dossier nommé `New Sample Data` .</span><span class="sxs-lookup"><span data-stu-id="e6bb3-148">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named `New Sample Data`.</span></span>  
  
2.  <span data-ttu-id="e6bb3-149">Localisez les fichiers d'exemple sur votre ordinateur et copiez trois des fichiers du dossier.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-149">Locate the sample files on your computer and copy three of the files from the folder.</span></span>  
  
3.  <span data-ttu-id="e6bb3-150">Dans le `New Sample Data` dossier, collez les fichiers copiés.</span><span class="sxs-lookup"><span data-stu-id="e6bb3-150">In the `New Sample Data` folder, paste the copied files.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e6bb3-151">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="e6bb3-151">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e6bb3-152">Étape 3 : Modification de la valeur de configuration de la propriété Directory</span><span class="sxs-lookup"><span data-stu-id="e6bb3-152">Step 3: Modifying the Directory Property Configuration Value</span></span>](lesson-5-3-modifying-the-directory-property-configuration-value.md)  
  
  
