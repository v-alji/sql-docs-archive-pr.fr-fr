---
title: Utiliser une destination de recordset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613029"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="33bfd-102">Utiliser une destination de jeu d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="33bfd-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="33bfd-103">La destination d'ensemble d'enregistrements n'enregistre pas les données sur une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="33bfd-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="33bfd-104">Elle enregistre les données en mémoire dans un ensemble d'enregistrements stocké dans une variable de package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de type `Object`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="33bfd-105">Une fois que la destination d'ensemble d'enregistrements a sauvegardé les données, vous devez en général utiliser un conteneur de boucles Foreach avec l'énumérateur ADO Foreach pour traiter une par une les lignes de l'ensemble d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="33bfd-106">L'énumérateur ADO Foreach enregistre la valeur de chaque colonne de la ligne actuelle dans une variable de package distincte.</span><span class="sxs-lookup"><span data-stu-id="33bfd-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="33bfd-107">Ensuite, les tâches que vous configurez à l'intérieur du conteneur de boucles Foreach lisent les valeurs contenues dans ces variables et effectuent certaines actions sur ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="33bfd-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="33bfd-108">Vous pouvez utiliser la destination d'ensemble d'enregistrements dans de nombreux scénarios différents.</span><span class="sxs-lookup"><span data-stu-id="33bfd-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="33bfd-109">Voici quelques exemples :</span><span class="sxs-lookup"><span data-stu-id="33bfd-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="33bfd-110">Vous pouvez utiliser une tâche Envoyer un message et le langage d’expression [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour envoyer un message électronique personnalisé pour chaque ligne de l’ensemble d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="33bfd-111">Vous pouvez utiliser un composant Script configuré en tant que source à l'intérieur d'une tâche de flux de données pour lire les valeurs de colonne dans les colonnes du flux de données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="33bfd-112">Vous pouvez ensuite utiliser des transformations et des destinations pour transformer et enregistrer la ligne.</span><span class="sxs-lookup"><span data-stu-id="33bfd-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="33bfd-113">Dans cet exemple, la tâche de flux de données s'exécute une fois pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="33bfd-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="33bfd-114">Les sections suivantes décrivent tout d'abord le processus général d'utilisation de la destination d'ensemble d'enregistrements et présentent ensuite un exemple spécifique d'utilisation de la destination.</span><span class="sxs-lookup"><span data-stu-id="33bfd-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="33bfd-115">Étapes générales d'utilisation d'une destination d'ensemble d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="33bfd-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="33bfd-116">La procédure suivante résume les étapes requises pour enregistrer des données dans une destination d'ensemble d'enregistrements, puis l'utilisation du conteneur de boucles Foreach pour traiter chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="33bfd-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="33bfd-117">Pour enregistrer des données dans une destination d'ensemble d'enregistrements et traiter chaque ligne à l'aide du conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="33bfd-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="33bfd-118">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], créez ou ouvrez un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33bfd-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="33bfd-119">Créez une variable qui contiendra l'ensemble d'enregistrements enregistré en mémoire par la destination d'ensemble d'enregistrements et définissez le type de la variable sur `Object`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="33bfd-120">Créez des variables supplémentaires avec les types appropriés pour contenir les valeurs de chaque colonne de l'ensemble d'enregistrements que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="33bfd-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="33bfd-121">Ajoutez et configurez le gestionnaire de connexions requis par la source de données que vous envisagez d'utiliser dans votre flux de données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="33bfd-122">Ajoutez une tâche de flux de données au package et, sous l'onglet Flux de données du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , configurez des sources et des transformations pour le chargement et la transformation des données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="33bfd-123">Ajoutez une destination d'ensemble d'enregistrements au flux de données et connectez-la aux transformations.</span><span class="sxs-lookup"><span data-stu-id="33bfd-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="33bfd-124">Pour la propriété `VariableName` de la destination d'ensemble d'enregistrements, entrez le nom de la variable que vous avez créée pour contenir l'ensemble d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="33bfd-125">Sous l'onglet Flux de contrôle du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez un conteneur de boucles Foreach et connectez ce conteneur à la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="33bfd-126">Ouvrez ensuite l' **Éditeur de boucle Foreach** pour configurer le conteneur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33bfd-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="33bfd-127">Dans la page **Collection** , sélectionnez l'énumérateur ADO Foreach.</span><span class="sxs-lookup"><span data-stu-id="33bfd-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="33bfd-128">Puis, pour **Variable source de l'objet ADO**, sélectionnez la variable qui contient l'ensemble d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="33bfd-129">Dans la page **Mappage de variables** , mappez l’index de base zéro de chaque colonne que vous souhaitez utiliser à la variable appropriée.</span><span class="sxs-lookup"><span data-stu-id="33bfd-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="33bfd-130">Sur chaque itération de la boucle, l'énumérateur remplit les variables avec les valeurs de colonne de la ligne actuelle.</span><span class="sxs-lookup"><span data-stu-id="33bfd-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="33bfd-131">À l'intérieur du conteneur de boucles Foreach, ajoutez et configurez des tâches destinées à traiter une par une les lignes de l'ensemble d'enregistrements en lisant les valeurs des variables.</span><span class="sxs-lookup"><span data-stu-id="33bfd-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="33bfd-132">Exemple d'utilisation de la destination d'ensemble d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="33bfd-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="33bfd-133">Dans l'exemple suivant, la tâche de flux de données charge des informations relatives aux employés [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] de la table Sales.SalesPerson dans une destination d'ensemble d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="33bfd-134">Un conteneur de boucles Foreach lit ensuite les lignes de données une par une et appelle une tâche Envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="33bfd-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="33bfd-135">Cette tâche utilise des expressions pour envoyer un message électronique personnalisé à chaque vendeur au sujet du montant de sa prime.</span><span class="sxs-lookup"><span data-stu-id="33bfd-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="33bfd-136">Pour créer le projet et configurer les variables</span><span class="sxs-lookup"><span data-stu-id="33bfd-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="33bfd-137">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], créez un projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33bfd-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="33bfd-138">Dans le menu **SSIS** , sélectionnez **Variables**.</span><span class="sxs-lookup"><span data-stu-id="33bfd-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="33bfd-139">Dans la fenêtre **Variables** , créez les variables qui contiendront l'ensemble d'enregistrements et les valeurs de colonne de la ligne actuelle :</span><span class="sxs-lookup"><span data-stu-id="33bfd-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="33bfd-140">Créez une variable nommée `BonusRecordset` et définissez son type sur `Object`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="33bfd-141">La variable `BonusRecordset` contient le jeu d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="33bfd-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="33bfd-142">Créez une variable nommée `EmailAddress` et définissez son type sur `String`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="33bfd-143">La variable `EmailAddress` contient l’adresse de messagerie du vendeur.</span><span class="sxs-lookup"><span data-stu-id="33bfd-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="33bfd-144">Créez une variable nommée `FirstName` et définissez son type sur `String`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="33bfd-145">La variable `FirstName` contient le prénom du vendeur.</span><span class="sxs-lookup"><span data-stu-id="33bfd-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="33bfd-146">Créez une variable nommée `Bonus` et définissez son type sur `Double`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="33bfd-147">La variable `Bonus` contient le montant de la prime du vendeur.</span><span class="sxs-lookup"><span data-stu-id="33bfd-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="33bfd-148">Pour configurer les gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="33bfd-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="33bfd-149">Dans la zone Gestionnaires de connexions du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez et configurez un nouveau gestionnaire de connexions OLE DB qui se connecte à l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33bfd-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="33bfd-150">La source OLE DB dans la tâche de flux de données utilisera ce gestionnaire de connexions pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="33bfd-151">Dans la zone Gestionnaires de connexions, ajoutez et configurez un nouveau gestionnaire de connexions SMTP qui se connecte à un serveur SMTP disponible.</span><span class="sxs-lookup"><span data-stu-id="33bfd-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="33bfd-152">La tâche Envoyer un message à l'intérieur du conteneur de boucles Foreach utilisera ce gestionnaire de connexions pour envoyer des courriers électroniques.</span><span class="sxs-lookup"><span data-stu-id="33bfd-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="33bfd-153">Pour configurer le flux de données et la destination d'ensemble d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="33bfd-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="33bfd-154">Sous l'onglet **Flux de contrôle** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez une tâche de flux de données à l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="33bfd-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="33bfd-155">Sous l'onglet **Flux de données** tab, add an OLE DB source to the Flux de données task, and then open the **Éditeur de source OLE DB.**</span><span class="sxs-lookup"><span data-stu-id="33bfd-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="33bfd-156">Dans la page **Gestionnaire de connexions** de l'éditeur, configurez la source avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33bfd-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="33bfd-157">Pour **Gestionnaire de connexions OLE DB**, sélectionnez le gestionnaire de connexions OLE DB que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="33bfd-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="33bfd-158">Pour **Mode d'accès aux données**, sélectionnez **Commande SQL**.</span><span class="sxs-lookup"><span data-stu-id="33bfd-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="33bfd-159">Pour **Texte de la commande SQL**, entrez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="33bfd-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="33bfd-160">Vous devez remplacer la valeur `currency` de la colonne Bonus par `float` pour pouvoir charger cette valeur dans une variable de package de type `Double`.</span><span class="sxs-lookup"><span data-stu-id="33bfd-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="33bfd-161">Sous l'onglet **Flux de données** , ajoutez une destination d'ensemble d'enregistrements et connectez-la à la source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="33bfd-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="33bfd-162">Ouvrez l' **Éditeur de destination d'ensemble d'enregistrements**et configurez la destination avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33bfd-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="33bfd-163">Sous l’onglet **Propriétés du composant** , pour `VariableName` propriété, `User::BonusRecordset` sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="33bfd-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="33bfd-164">Sous l'onglet **Colonnes d'entrée** , sélectionnez les trois colonnes disponibles.</span><span class="sxs-lookup"><span data-stu-id="33bfd-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="33bfd-165">Pour configurer le conteneur de boucles Foreach et exécuter le package</span><span class="sxs-lookup"><span data-stu-id="33bfd-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="33bfd-166">Sous l'onglet **Flux de contrôle** du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , ajoutez un conteneur de boucles Foreach et connectez-le à la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="33bfd-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="33bfd-167">Ouvrez l' **Éditeur de boucle Foreach**et configurez le conteneur avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33bfd-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="33bfd-168">Dans la page **collection** , pour **énumérateur**, sélectionnez **énumérateur ADO Foreach**, et pour **variable source de l’objet ADO**, sélectionnez `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="33bfd-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="33bfd-169">Dans la page **mappage de variables** , mappez à l' `User::EmailAddress` index 0, à l’index `User::FirstName` 1 et `User::Bonus` à l’index 2.</span><span class="sxs-lookup"><span data-stu-id="33bfd-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="33bfd-170">Sous l'onglet **Flux de contrôle** , à l'intérieur du conteneur de boucles Foreach, ajoutez une tâche Envoyer un message.</span><span class="sxs-lookup"><span data-stu-id="33bfd-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="33bfd-171">Ouvrez l' **Éditeur de tâche Envoyer un message**, puis dans la page **Courrier** , configurez la tâche avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="33bfd-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="33bfd-172">Pour **SmtpConnection**, sélectionnez le gestionnaire de connexions SMTP qui a été préalablement configuré.</span><span class="sxs-lookup"><span data-stu-id="33bfd-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="33bfd-173">Pour **De**, entrez une adresse e-mail appropriée.</span><span class="sxs-lookup"><span data-stu-id="33bfd-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="33bfd-174">Si vous utilisez votre propre adresse de messagerie, vous pourrez vérifier que le package s'est exécuté avec succès.</span><span class="sxs-lookup"><span data-stu-id="33bfd-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="33bfd-175">Vous recevrez des accusés de non remise pour les messages envoyés par la tâche Envoyer un message aux vendeurs fictifs de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33bfd-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="33bfd-176">Pour **À**, entrez une adresse e-mail par défaut.</span><span class="sxs-lookup"><span data-stu-id="33bfd-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="33bfd-177">Cette valeur ne sera pas utilisée, mais sera remplacée au moment de l'exécution par l'adresse de messagerie de chaque vendeur.</span><span class="sxs-lookup"><span data-stu-id="33bfd-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="33bfd-178">Pour **Objet**, entrez « Votre prime annuelle ».</span><span class="sxs-lookup"><span data-stu-id="33bfd-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="33bfd-179">Pour **MessageSourceType**, sélectionnez **Entrée directe**.</span><span class="sxs-lookup"><span data-stu-id="33bfd-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="33bfd-180">Dans la page **Expressions** de **l’Éditeur de tâche Envoyer un message**, cliquez sur le bouton de sélection ( **...** ) pour ouvrir **l’Éditeur d’expressions de la propriété**.</span><span class="sxs-lookup"><span data-stu-id="33bfd-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="33bfd-181">Dans l' **Éditeur d'expressions de la propriété**, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="33bfd-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="33bfd-182">Pour **ToLine**, ajoutez l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="33bfd-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="33bfd-183">Pour la propriété **MessageSource** , ajoutez l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="33bfd-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="33bfd-184">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="33bfd-184">Run the package.</span></span>  
  
     <span data-ttu-id="33bfd-185">Si vous avez spécifié un serveur SMTP valide et avez fourni votre propre adresse de messagerie, vous recevrez des accusés de non remise pour les messages envoyés par la tâche Envoyer un message aux vendeurs fictifs de [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33bfd-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
