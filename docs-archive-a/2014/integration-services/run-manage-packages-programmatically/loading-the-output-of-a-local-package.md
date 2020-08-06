---
title: Chargement de la sortie d’un package local | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data flow [Integration Services], loading results
- loading data flow results
ms.assetid: aba8ecb7-0dcf-40d0-a2a8-64da0da94b93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6799e593ab9d5ae1a9358bf54f4927838991ebd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707671"
---
# <a name="loading-the-output-of-a-local-package"></a><span data-ttu-id="a5f2a-102">Chargement de la sortie d'un package local</span><span class="sxs-lookup"><span data-stu-id="a5f2a-102">Loading the Output of a Local Package</span></span>
  <span data-ttu-id="a5f2a-103">Les applications clientes peuvent lire la sortie des packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] quand la sortie est enregistrée dans les destinations [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] via [!INCLUDE[vstecado](../../includes/vstecado-md.md)], ou quand la sortie est enregistrée dans une destination de fichier plat à l’aide des classes présentes dans l’espace de noms **System.IO**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-103">Client applications can read the output of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages when the output is saved to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destinations by using [!INCLUDE[vstecado](../../includes/vstecado-md.md)], or when the output is saved to a flat file destination by using the classes in the **System.IO** namespace.</span></span> <span data-ttu-id="a5f2a-104">Toutefois, une application cliente peut également lire directement la sortie d'un package dans la mémoire, sans avoir besoin d'étape intermédiaire pour rendre les données persistantes.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-104">However, a client application can also read the output of a package directly from memory, without the need for an intermediate step to persist the data.</span></span> <span data-ttu-id="a5f2a-105">La clé de cette solution est l' `Microsoft.SqlServer.Dts.DtsClient` espace de noms, qui contient des implémentations spécialisées des `IDbConnection` `IDbCommand` interfaces, et **IDbDataParameter** de l’espace de noms **System. Data** .</span><span class="sxs-lookup"><span data-stu-id="a5f2a-105">The key to this solution is the `Microsoft.SqlServer.Dts.DtsClient` namespace, which contains specialized implementations of the `IDbConnection`, `IDbCommand`, and **IDbDataParameter** interfaces from the **System.Data** namespace.</span></span> <span data-ttu-id="a5f2a-106">L’assembly Microsoft.SqlServer.Dts.DtsClient.dll est installé par défaut dans **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-106">The assembly Microsoft.SqlServer.Dts.DtsClient.dll is installed by default in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

> [!NOTE]
>  <span data-ttu-id="a5f2a-107">Conformément à la procédure décrite dans cette rubrique, la propriété DelayValidation de la tâche de flux de données et de tous les objets parents doit avoir la valeur par défaut **False**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-107">The procedure described in this topic requires that the DelayValidation property of the Data Flow task and of any parent objects be set to its default value of **False**.</span></span>

## <a name="description"></a><span data-ttu-id="a5f2a-108">Description</span><span class="sxs-lookup"><span data-stu-id="a5f2a-108">Description</span></span>
 <span data-ttu-id="a5f2a-109">Cette procédure montre comment développer une application cliente en code managé qui charge directement la sortie d'un package avec une destination DataReader à partir de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-109">This procedure demonstrates how to develop a client application in managed code that loads the output of a package with a DataReader destination directly from memory.</span></span> <span data-ttu-id="a5f2a-110">Les étapes résumées ici sont illustrées dans l'exemple de code qui suit.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-110">The steps summarized here are demonstrated in the code sample that follows.</span></span>

#### <a name="to-load-data-package-output-into-a-client-application"></a><span data-ttu-id="a5f2a-111">Pour charger la sortie d'un package de données dans une application cliente</span><span class="sxs-lookup"><span data-stu-id="a5f2a-111">To load data package output into a client application</span></span>

1.  <span data-ttu-id="a5f2a-112">Dans le package, configurez une destination DataReader afin de recevoir la sortie que vous souhaitez lire dans l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-112">In the package, configure a DataReader destination to receive the output that you want to read into the client application.</span></span> <span data-ttu-id="a5f2a-113">Donnez un nom descriptif à la destination DataReader, puisque vous l'utiliserez ultérieurement dans votre application cliente.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-113">Give the DataReader destination a descriptive name, since you will use this name later in your client application.</span></span> <span data-ttu-id="a5f2a-114">Prenez note du nom de la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-114">Make a note of the name of the DataReader destination.</span></span>

2.  <span data-ttu-id="a5f2a-115">Dans le projet de développement, définissez une référence à l' `Microsoft.SqlServer.Dts.DtsClient` espace de noms en localisant l’assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-115">In the development project, set a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by locating the assembly **Microsoft.SqlServer.Dts.DtsClient.dll**.</span></span> <span data-ttu-id="a5f2a-116">Par défaut, cet assembly est installé dans **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-116">By default, this assembly is installed in **C:\Program Files\Microsoft SQL Server\100\DTS\Binn**.</span></span> <span data-ttu-id="a5f2a-117">Importez l’espace de noms dans votre code à l’aide de l' `Using` instruction C# ou [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` .</span><span class="sxs-lookup"><span data-stu-id="a5f2a-117">Import the namespace into your code by using the C# `Using` or the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] `Imports` statement.</span></span>

3.  <span data-ttu-id="a5f2a-118">Dans votre code, créez un objet de type `DtsClient.DtsConnection` avec une chaîne de connexion qui contient les paramètres de ligne de commande requis par **dtexec.exe** pour exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-118">In your code, create an object of type `DtsClient.DtsConnection` with a connection string that contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="a5f2a-119">Pour plus d'informations, consultez [Utilitaire dtexec](../packages/dtexec-utility.md).</span><span class="sxs-lookup"><span data-stu-id="a5f2a-119">For more information, see [dtexec Utility](../packages/dtexec-utility.md).</span></span> <span data-ttu-id="a5f2a-120">Ouvrez ensuite la connexion à l'aide de cette chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-120">Then open the connection with this connection string.</span></span> <span data-ttu-id="a5f2a-121">Vous pouvez également vous servir de l’utilitaire **dtexecui** pour créer visuellement la chaîne de connexion nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-121">You can also use the **dtexecui** utility to create the required connection string visually.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a5f2a-122">L'exemple de code montre le chargement du package à partir du système de fichiers en utilisant la syntaxe `/FILE <path and filename>`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-122">The sample code demonstrates loading the package from the file system by using the `/FILE <path and filename>` syntax.</span></span> <span data-ttu-id="a5f2a-123">Toutefois, vous pouvez également charger le package à partir de la base de données MSDB en utilisant la syntaxe `/SQL <package name>` ou à partir du magasin de packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en utilisant la syntaxe `/DTS \<folder name>\<package name>`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-123">However you can also load the package from the MSDB database by using the `/SQL <package name>` syntax, or from the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package store by using the `/DTS \<folder name>\<package name>` syntax.</span></span>

4.  <span data-ttu-id="a5f2a-124">Créez un objet de type `DtsClient.DtsCommand` qui utilise le `DtsConnection` créé précédemment et qui définit sa propriété `CommandText` sur le nom de la destination DataReader dans le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-124">Create an object of type `DtsClient.DtsCommand` that uses the previously created `DtsConnection` and set its `CommandText` property to the name of the DataReader destination in the package.</span></span> <span data-ttu-id="a5f2a-125">Appelez ensuite la méthode `ExecuteReader` de l'objet de commande pour charger les résultats de package dans un nouveau DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-125">Then call the `ExecuteReader` method of the command object to load the package results into a new DataReader.</span></span>

5.  <span data-ttu-id="a5f2a-126">Vous pouvez éventuellement paramétrer indirectement la sortie du package en utilisant la collection d'objets `DtsDataParameter` sur l'objet `DtsCommand` pour passer des valeurs aux variables définies dans le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-126">Optionally, you can indirectly parameterize the output of the package by using the collection of `DtsDataParameter` objects on the `DtsCommand` object to pass values to variables defined in the package.</span></span> <span data-ttu-id="a5f2a-127">Dans le package, vous pouvez utiliser ces variables comme paramètres de requête ou dans des expressions pour affecter les résultats retournés à la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-127">Within the package, you can use these variables as query parameters or in expressions to affect the results returned to the DataReader destination.</span></span> <span data-ttu-id="a5f2a-128">Vous devez définir ces variables dans le package dans l’espace de noms **DtsClient** avant de pouvoir les utiliser avec l' `DtsDataParameter` objet à partir d’une application cliente.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-128">You must define these variables in the package in the **DtsClient** namespace before you can use them with the `DtsDataParameter` object from a client application.</span></span> <span data-ttu-id="a5f2a-129">(Vous devrez peut-être cliquer sur le bouton de barre d’outils **choisir les colonnes de variables** dans la fenêtre **variables** pour afficher la colonne **espace de noms** .) Dans votre code client, lorsque vous ajoutez un `DtsDataParameter` à la `Parameters` collection de `DtsCommand` , omettez la référence d’espace de noms DtsClient à partir du nom de la variable.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-129">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.) In your client code, when you add a `DtsDataParameter` to the `Parameters` collection of the `DtsCommand`, omit the DtsClient namespace reference from the variable name.</span></span> <span data-ttu-id="a5f2a-130">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a5f2a-130">For example:</span></span>

    ```
    command.Parameters.Add(new DtsDataParameter("MyVariable", 1));
    ```

6.  <span data-ttu-id="a5f2a-131">Appelez la méthode `Read` du DataReader autant de fois que nécessaire pour faire une boucle dans les lignes de données de sortie.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-131">Call the `Read` method of the DataReader repeatedly as needed to loop through the rows of output data.</span></span> <span data-ttu-id="a5f2a-132">Utilisez les données, ou enregistrez-les à des fins d'utilisation ultérieure, dans l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-132">Use the data, or save the data for later use, in the client application.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="a5f2a-133">La méthode `Read` de cette implémentation du DataReader retourne `true` une dernière fois une fois que la dernière ligne de données a été lue.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-133">The `Read` method of this implementation of the DataReader returns `true` one more time after the last row of data has been read.</span></span> <span data-ttu-id="a5f2a-134">Cela rend difficile l'utilisation du code habituel qui effectue une boucle dans le DataReader alors que `Read` retourne `true`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-134">This makes it difficult to use the usual code that loops through the DataReader while `Read` returns `true`.</span></span> <span data-ttu-id="a5f2a-135">Si votre code essaie de fermer le DataReader ou la connexion après avoir lu le nombre attendu de lignes, sans un dernier appel supplémentaire de la méthode `Read`, le code déclenchera une exception non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-135">If your code attempts to close the DataReader or the connection after reading the expected number of rows, without an additional, final call to the `Read` method, the code will raise an unhandled exception.</span></span> <span data-ttu-id="a5f2a-136">Toutefois, si votre code essaie de lire des données sur cette dernière itération via une boucle, lorsque `Read` retourne encore `true` mais que la dernière ligne est passée, le code déclenchera un `ApplicationException` non pris en charge avec le message : « SSIS IDataReader se trouve au-delà de la fin du jeu de résultats ».</span><span class="sxs-lookup"><span data-stu-id="a5f2a-136">However, if your code attempts to read data on this final iteration through a loop, when `Read` still returns `true` but the last row has been passed, the code will raise an unhandled `ApplicationException` with the message, "The SSIS IDataReader is past the end of the resultset."</span></span> <span data-ttu-id="a5f2a-137">Ce comportement est différent de celui des autres implémentations DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-137">This behavior is different from that of other DataReader implementations.</span></span> <span data-ttu-id="a5f2a-138">Par conséquent, lors de l'utilisation d'une boucle pour lire les lignes du DataReader pendant que `Read` retourne `true`, vous devez écrire le code de sorte à détecter, tester et ignorer ce `ApplicationException` anticipé sur le dernier appel réussi de la méthode `Read`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-138">Therefore, when using a loop to read through the rows in the DataReader while `Read` returns `true`, you need to write code to catch, test, and discard this anticipated `ApplicationException` on the last successful call to the `Read` method.</span></span> <span data-ttu-id="a5f2a-139">Ou, si vous connaissez à l'avance le nombre de lignes attendu, vous pouvez traiter les lignes, puis appeler la méthode `Read` une fois de plus avant de fermer le DataReader et la connexion.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-139">Or, if you know in advance the number of rows expected, you can process the rows, and then call the `Read` method one more time before closing the DataReader and the connection.</span></span>

7.  <span data-ttu-id="a5f2a-140">Appelez la méthode `Dispose` de l'objet `DtsCommand`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-140">Call the `Dispose` method of the `DtsCommand` object.</span></span> <span data-ttu-id="a5f2a-141">Cet appel s'avère particulièrement important si vous avez utilisé des objets `DtsDataParameter`.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-141">This is particularly important if you have used any `DtsDataParameter` objects.</span></span>

8.  <span data-ttu-id="a5f2a-142">Fermez le DataReader et les objets de connexion.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-142">Close the DataReader and the connection objects.</span></span>

## <a name="example"></a><span data-ttu-id="a5f2a-143">Exemple</span><span class="sxs-lookup"><span data-stu-id="a5f2a-143">Example</span></span>
 <span data-ttu-id="a5f2a-144">L'exemple suivant exécute un package qui calcule une valeur d'agrégation unique et qui enregistre cette valeur dans une destination DataReader, puis qui lit cette valeur depuis le DataReader et qui l'affiche dans une zone de texte sur un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-144">The following example runs a package that calculates a single aggregate value and saves the value to a DataReader destination, and then reads this value from the DataReader and displays the value in a text box on a Windows Form.</span></span>

 <span data-ttu-id="a5f2a-145">L'utilisation de paramètres n'est pas requise lors du chargement de la sortie d'un package dans une application cliente.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-145">The use of parameters is not required when loading the output of a package into a client application.</span></span> <span data-ttu-id="a5f2a-146">Si vous ne souhaitez pas utiliser un paramètre, vous pouvez omettre l’utilisation de la variable dans l’espace de noms **DtsClient** et omettre le code qui utilise l' `DtsDataParameter` objet.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-146">If you do not want to use a parameter, you can omit the use of the variable in the **DtsClient** namespace, and omit the code that uses the `DtsDataParameter` object.</span></span>

#### <a name="to-create-the-test-package"></a><span data-ttu-id="a5f2a-147">Pour créer le package de test</span><span class="sxs-lookup"><span data-stu-id="a5f2a-147">To create the test package</span></span>

1.  <span data-ttu-id="a5f2a-148">Créez un nouveau package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f2a-148">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="a5f2a-149">L'exemple de code utilise « DtsClientWParamPkg.dtsx » comme nom de package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-149">The sample code uses "DtsClientWParamPkg.dtsx" as the name of the package.</span></span>

2.  <span data-ttu-id="a5f2a-150">Ajoutez une variable de type Chaîne à l'espace de noms DtsClient.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-150">Add a variable of type String in the DtsClient namespace.</span></span> <span data-ttu-id="a5f2a-151">L'exemple de code utilise le pays comme nom de la variable.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-151">The sample code use Country as the name of the variable.</span></span> <span data-ttu-id="a5f2a-152">(Vous pouvez être amené à cliquer sur le bouton de barre d’outils **Choisir les colonnes variables** dans la fenêtre **Variables** pour afficher la colonne **Espace de noms**.)</span><span class="sxs-lookup"><span data-stu-id="a5f2a-152">(You may need to click the **Choose Variable Columns** toolbar button in the **Variables** window to display the **Namespace** column.)</span></span>

3.  <span data-ttu-id="a5f2a-153">Ajoutez un gestionnaire de connexions OLE DB qui se connecte à l'exemple de base de données [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5f2a-153">Add an OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>

4.  <span data-ttu-id="a5f2a-154">Ajoutez une tâche de flux de données au package et basculez vers l'aire de conception du flux de données.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-154">Add a data flow task to the package and switch to the Data Flow design surface.</span></span>

5.  <span data-ttu-id="a5f2a-155">Ajoutez une source OLE DB au flux de données et configurez-la afin d'utiliser le gestionnaire de connexions OLE DB créé précédemment, ainsi que la commande SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="a5f2a-155">Add an OLE DB source to the data flow and configure it to use the OLE DB connection manager created previously, and the following SQL command:</span></span>

    ```
    SELECT * FROM Sales.vIndividualCustomer WHERE CountryRegionName = ?
    ```

6.  <span data-ttu-id="a5f2a-156">Cliquez sur `Parameters` et, dans la boîte de dialogue **définir les paramètres** de la requête, mappez le paramètre d’entrée unique dans la requête, Parameter0, à la variable DtsClient :: Country.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-156">Click `Parameters` and, in the **Set Query Parameters** dialog box, map the single input parameter in the query, Parameter0, to the DtsClient::Country variable.</span></span>

7.  <span data-ttu-id="a5f2a-157">Ajoutez une transformation d'agrégation au flux de données et connectez la sortie de la source OLE DB à la transformation.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-157">Add an Aggregate transformation to the data flow, and connect the output of the OLE DB source to the transformation.</span></span> <span data-ttu-id="a5f2a-158">Ouvrez l’éditeur de transformation d’agrégation et configurez-le pour effectuer une opération « Count All » sur toutes les colonnes d’entrée (\*) et pour générer la sortie de la valeur agrégée avec l’alias CustomerCount.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-158">Open the Aggregate Transformation Editor and configure it to perform a "Count all" operation on all input columns (\*) and to output the aggregated value with the alias CustomerCount.</span></span>

8.  <span data-ttu-id="a5f2a-159">Ajoutez une destination DataReader au flux de données et connectez la sortie de la transformation d'agrégation à la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-159">Add a DataReader destination to the data flow and connect the output of the Aggregate transformation to the DataReader destination.</span></span> <span data-ttu-id="a5f2a-160">L'exemple de code utilise « DataReaderDest » comme nom du DataReader.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-160">The sample code uses "DataReaderDest" as the name of the DataReader.</span></span> <span data-ttu-id="a5f2a-161">Sélectionnez l'unique colonne d'entrée disponible, CustomerCount, pour la destination.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-161">Select the single available input column, CustomerCount, for the destination.</span></span>

9. <span data-ttu-id="a5f2a-162">Enregistrez le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-162">Save the package.</span></span> <span data-ttu-id="a5f2a-163">L'application de test créée par la suite va exécuter le package et extraire directement sa sortie de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-163">The test application created next will run the package and retrieve its output directly from memory.</span></span>

#### <a name="to-create-the-test-application"></a><span data-ttu-id="a5f2a-164">Pour créer l'application de test</span><span class="sxs-lookup"><span data-stu-id="a5f2a-164">To create the test application</span></span>

1.  <span data-ttu-id="a5f2a-165">Créez une nouvelle application Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-165">Create a new Windows Forms application.</span></span>

2.  <span data-ttu-id="a5f2a-166">Ajoutez une référence à l' `Microsoft.SqlServer.Dts.DtsClient` espace de noms en accédant à l’assembly portant le même nom dans **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-166">Add a reference to the `Microsoft.SqlServer.Dts.DtsClient` namespace by browsing to the assembly of the same name in **%ProgramFiles%\Microsoft SQL Server\100\DTS\Binn**.</span></span>

3.  <span data-ttu-id="a5f2a-167">Copiez et collez l'exemple de code suivant dans le module de code pour le formulaire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-167">Copy and paste the following sample code into the code module for the form.</span></span>

4.  <span data-ttu-id="a5f2a-168">Modifiez la valeur de la `dtexecArgs` variable comme requis afin qu’elle contienne les paramètres de ligne de commande requis par **dtexec.exe** pour exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-168">Modify the value of the `dtexecArgs` variable as required so that it contains the command-line parameters required by **dtexec.exe** to run the package.</span></span> <span data-ttu-id="a5f2a-169">L'exemple de code charge le package à partir du système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-169">The sample code loads the package from the file system.</span></span>

5.  <span data-ttu-id="a5f2a-170">Modifiez la valeur de la `dataReaderName` variable comme obligatoire afin qu’elle contienne le nom de la destination DataReader dans le package.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-170">Modify the value of the `dataReaderName` variable as required so that it contains the name of the DataReader destination in the package.</span></span>

6.  <span data-ttu-id="a5f2a-171">Placez un bouton et une zone de texte sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-171">Put a button and a text box on the form.</span></span> <span data-ttu-id="a5f2a-172">L’exemple de code utilise `btnRun` comme nom du bouton et `txtResults` comme nom de la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-172">The sample code uses `btnRun` as the name of the button, and `txtResults` as the name of the text box.</span></span>

7.  <span data-ttu-id="a5f2a-173">Exécutez l'application et cliquez sur le bouton.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-173">Run the application and click the button.</span></span> <span data-ttu-id="a5f2a-174">Après une brève pause pendant l'exécution du package, vous devez voir apparaître la valeur d'agrégation calculée par le package (le nombre de clients au Canada) dans la zone de texte sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-174">After a brief pause while the package runs, you should see the aggregate value calculated by the package (the count of customers in Canada) displayed in the text box on the form.</span></span>

### <a name="sample-code"></a><span data-ttu-id="a5f2a-175">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="a5f2a-175">Sample Code</span></span>

```vb
Imports System.Data
Imports Microsoft.SqlServer.Dts.DtsClient

Public Class Form1

  Private Sub btnRun_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnRun.Click

    Dim dtexecArgs As String
    Dim dataReaderName As String
    Dim countryName As String

    Dim dtsConnection As DtsConnection
    Dim dtsCommand As DtsCommand
    Dim dtsDataReader As IDataReader
    Dim dtsParameter As DtsDataParameter

    Windows.Forms.Cursor.Current = Cursors.WaitCursor

    dtexecArgs = "/FILE ""C:\...\DtsClientWParamPkg.dtsx"""
    dataReaderName = "DataReaderDest"
    countryName = "Canada"

    dtsConnection = New DtsConnection()
    With dtsConnection
      .ConnectionString = dtexecArgs
      .Open()
    End With

    dtsCommand = New DtsCommand(dtsConnection)
    dtsCommand.CommandText = dataReaderName

    dtsParameter = New DtsDataParameter("Country", DbType.String)
    dtsParameter.Direction = ParameterDirection.Input
    dtsCommand.Parameters.Add(dtsParameter)

    dtsParameter.Value = countryName

    dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default)

    With dtsDataReader
      .Read()
      txtResults.Text = .GetInt32(0).ToString("N0")
    End With

    'After reaching the end of data rows,
    ' call the Read method one more time.
    Try
      dtsDataReader.Read()
    Catch ex As Exception
      MessageBox.Show("Exception on final call to Read method:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception on final call to Read method", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    ' The following method is a best practice, and is
    '  required when using DtsDataParameter objects.
    dtsCommand.Dispose()

    Try
      dtsDataReader.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing DataReader:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing DataReader", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Try
      dtsConnection.Close()
    Catch ex As Exception
      MessageBox.Show("Exception closing connection:" & ControlChars.CrLf & _
      ex.Message & ControlChars.CrLf & _
      ex.InnerException.Message, "Exception closing connection", _
      MessageBoxButtons.OK, MessageBoxIcon.Error)
    End Try

    Windows.Forms.Cursor.Current = Cursors.Default

  End Sub

End Class
```

```csharp
using System;
using System.Windows.Forms;
using System.Data;
using Microsoft.SqlServer.Dts.DtsClient;

namespace DtsClientWParamCS
{
  public partial class Form1 : Form
  {
    public Form1()
    {
      InitializeComponent();
      this.btnRun.Click += new System.EventHandler(this.btnRun_Click);
    }

    private void btnRun_Click(object sender, EventArgs e)
    {
      string dtexecArgs;
      string dataReaderName;
      string countryName;

      DtsConnection dtsConnection;
      DtsCommand dtsCommand;
      IDataReader dtsDataReader;
      DtsDataParameter dtsParameter;

      Cursor.Current = Cursors.WaitCursor;

      dtexecArgs = @"/FILE ""C:\...\DtsClientWParamPkg.dtsx""";
      dataReaderName = "DataReaderDest";
      countryName = "Canada";

      dtsConnection = new DtsConnection();
      {
        dtsConnection.ConnectionString = dtexecArgs;
        dtsConnection.Open();
      }

      dtsCommand = new DtsCommand(dtsConnection);
      dtsCommand.CommandText = dataReaderName;

      dtsParameter = new DtsDataParameter("Country", DbType.String);
      dtsParameter.Direction = ParameterDirection.Input;
      dtsCommand.Parameters.Add(dtsParameter);

      dtsParameter.Value = countryName;

      dtsDataReader = dtsCommand.ExecuteReader(CommandBehavior.Default);

      {
        dtsDataReader.Read();
        txtResults.Text = dtsDataReader.GetInt32(0).ToString("N0");
      }

      //After reaching the end of data rows,
      // call the Read method one more time.
      try
      {
        dtsDataReader.Read();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception on final call to Read method:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception on final call to Read method", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      // The following method is a best practice, and is
      //  required when using DtsDataParameter objects.
      dtsCommand.Dispose();

      try
      {
        dtsDataReader.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing DataReader:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing DataReader", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      try
      {
        dtsConnection.Close();
      }
      catch (Exception ex)
      {
        MessageBox.Show(
          "Exception closing connection:\n" + ex.Message + "\n" + ex.InnerException.Message,
          "Exception closing connection", MessageBoxButtons.OK, MessageBoxIcon.Error);
      }

      Cursor.Current = Cursors.Default;

    }
  }
}
```

<span data-ttu-id="a5f2a-176">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a5f2a-176">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a5f2a-177">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="a5f2a-177">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a5f2a-178">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="a5f2a-178">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a5f2a-179">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="a5f2a-179">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5f2a-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5f2a-180">See Also</span></span>
 <span data-ttu-id="a5f2a-181">[Comprendre les différences entre l’exécution locale et l’exécution distante et le](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [chargement et l’exécution d’un package local par](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) programmation pour le [chargement et l’exécution d’un package distant](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span><span class="sxs-lookup"><span data-stu-id="a5f2a-181">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) [Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)</span></span>


