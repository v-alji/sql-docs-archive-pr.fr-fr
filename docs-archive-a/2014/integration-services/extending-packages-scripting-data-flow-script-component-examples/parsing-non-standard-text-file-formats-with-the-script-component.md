---
title: Analyse de formats de fichiers texte non standard à l’aide du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- text file reading [Integration Services]
- Script component [Integration Services], non-standard text file formats
- transformations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: 1fda034d-09e4-4647-9a9f-e8d508c2cc8f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a0ca1a0d10bdad40d39a366864a07d2b0a61d13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696996"
---
# <a name="parsing-non-standard-text-file-formats-with-the-script-component"></a><span data-ttu-id="00b01-102">Analyse de formats de fichiers texte non standard à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="00b01-102">Parsing Non-Standard Text File Formats with the Script Component</span></span>
  <span data-ttu-id="00b01-103">Lorsque vos données sources sont organisées dans un format non standard, il peut être plus pratique de consolider l'ensemble de la logique d'analyse en un seul script au lieu de chaîner plusieurs transformations [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] pour parvenir au même résultat.</span><span class="sxs-lookup"><span data-stu-id="00b01-103">When your source data is arranged in a non-standard format, you may find it more convenient to consolidate all your parsing logic in a single script than to chain together multiple [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] transformations to achieve the same result.</span></span>  
  
 [<span data-ttu-id="00b01-104">Exemple 1 : analyse d’enregistrements délimités par des lignes</span><span class="sxs-lookup"><span data-stu-id="00b01-104">Example 1: Parsing Row-Delimited Records</span></span>](#example1)  
  
 [<span data-ttu-id="00b01-105">Exemple 2 : fractionnement d’enregistrements parents et enfants</span><span class="sxs-lookup"><span data-stu-id="00b01-105">Example 2: Splitting Parent and Child Records</span></span>](#example2)  
  
> [!NOTE]  
>  <span data-ttu-id="00b01-106">Si vous souhaitez créer un composant que vous pouvez réutiliser plus facilement dans plusieurs tâches de flux de données et plusieurs packages, utilisez le code présenté dans cet exemple de composant Script comme point de départ pour un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="00b01-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="00b01-107">Pour plus d’informations, consultez [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="00b01-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
##  <a name="example-1-parsing-row-delimited-records"></a><a name="example1"></a> <span data-ttu-id="00b01-108">Exemple 1 : analyse d’enregistrements délimités par des lignes</span><span class="sxs-lookup"><span data-stu-id="00b01-108">Example 1: Parsing Row-Delimited Records</span></span>  
 <span data-ttu-id="00b01-109">Cet exemple montre comment analyser un fichier texte, dans lequel chaque colonne de données figure sur une ligne séparée, dans une table de destination, à l'aide du composant Script.</span><span class="sxs-lookup"><span data-stu-id="00b01-109">This example shows how to take a text file in which each column of data appears on a separate line and parse it into a destination table by using the Script component.</span></span>  
  
 <span data-ttu-id="00b01-110">Pour plus d’informations sur la configuration du composant script pour une utilisation en tant que transformation dans le workflow, consultez [création d’une transformation synchrone avec le composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)et [création d’une transformation asynchrone à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="00b01-110">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="00b01-111">Pour configurer cet exemple de composant Script</span><span class="sxs-lookup"><span data-stu-id="00b01-111">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="00b01-112">Créez et enregistrez un fichier texte nommé **rowdelimiteddata.txt** contenant les données sources suivantes :</span><span class="sxs-lookup"><span data-stu-id="00b01-112">Create and save a text file named **rowdelimiteddata.txt** that contains the following source data:</span></span>  
  
    ```  
    FirstName: Nancy  
    LastName: Davolio  
    Title: Sales Representative  
    City: Seattle  
    StateProvince: WA  
  
    FirstName: Andrew  
    LastName: Fuller  
    Title: Vice President, Sales  
    City: Tacoma  
    StateProvince: WA  
  
    FirstName: Steven  
    LastName: Buchanan  
    Title: Sales Manager  
    City: London  
    StateProvince:  
  
    ```  
  
2.  <span data-ttu-id="00b01-113">Ouvrez [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b01-113">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="00b01-114">Sélectionnez une base de données de destination et ouvrez une nouvelle fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="00b01-114">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="00b01-115">Dans la fenêtre de requête, exécutez le script suivant pour créer la table de destination :</span><span class="sxs-lookup"><span data-stu-id="00b01-115">In the query window, execute the following script to create the destination table:</span></span>  
  
    ```  
    create table RowDelimitedData  
    (  
    FirstName varchar(32),  
    LastName varchar(32),  
    Title varchar(32),  
    City varchar(32),  
    StateProvince varchar(32)  
    )  
  
    ```  
  
4.  <span data-ttu-id="00b01-116">Ouvrez [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] et créez un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nommé ParseRowDelim.dtsx.</span><span class="sxs-lookup"><span data-stu-id="00b01-116">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named ParseRowDelim.dtsx.</span></span>  
  
5.  <span data-ttu-id="00b01-117">Ajoutez un gestionnaire de connexions de fichiers plats au package, nommez-le RowDelimitedData et configurez-le pour qu'il se connecte au fichier rowdelimiteddata.txt créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="00b01-117">Add a Flat File connection manager to the package, name it RowDelimitedData, and configure it to connect to the rowdelimiteddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="00b01-118">Ajoutez un gestionnaire de connexions OLE DB au package et configurez-le pour qu'il se connecte à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et à la base de données dans laquelle vous avez créé la table de destination.</span><span class="sxs-lookup"><span data-stu-id="00b01-118">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination table.</span></span>  
  
7.  <span data-ttu-id="00b01-119">Ajoutez une tâche de flux de données au package, puis cliquez sur l’onglet **Flux de données** du concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="00b01-119">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="00b01-120">Ajoutez une source de fichier plat au flux de données et configurez-la pour qu'elle utilise le gestionnaire de connexions RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="00b01-120">Add a Flat File Source to the data flow and configure it to use the RowDelimitedData connection manager.</span></span> <span data-ttu-id="00b01-121">Dans la page **Colonnes** de l’**Éditeur de source de fichier plat**, sélectionnez la seule colonne externe disponible.</span><span class="sxs-lookup"><span data-stu-id="00b01-121">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="00b01-122">Ajoutez un composant Script au flux de données et configurez-le en tant que transformation.</span><span class="sxs-lookup"><span data-stu-id="00b01-122">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="00b01-123">Connectez la sortie de la source de fichier plat au composant Script.</span><span class="sxs-lookup"><span data-stu-id="00b01-123">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="00b01-124">Double-cliquez sur le composant Script pour afficher l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="00b01-124">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="00b01-125">Dans la page **Colonnes d’entrée** de l’**Éditeur de transformation de script**, sélectionnez la seule colonne d’entrée disponible.</span><span class="sxs-lookup"><span data-stu-id="00b01-125">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="00b01-126">Dans la page **entrées et sorties** de l **'éditeur de transformation de script**, sélectionnez sortie 0 et définissez sa valeur `SynchronousInputID` aucun.</span><span class="sxs-lookup"><span data-stu-id="00b01-126">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0 and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="00b01-127">Créez 5 colonnes de sortie, de type String [DT_STR] et de longueur 32 :</span><span class="sxs-lookup"><span data-stu-id="00b01-127">Create 5 output columns, all of type string [DT_STR] with a length of 32:</span></span>  
  
    -   <span data-ttu-id="00b01-128">FirstName</span><span class="sxs-lookup"><span data-stu-id="00b01-128">FirstName</span></span>  
  
    -   <span data-ttu-id="00b01-129">LastName</span><span class="sxs-lookup"><span data-stu-id="00b01-129">LastName</span></span>  
  
    -   <span data-ttu-id="00b01-130">Intitulé</span><span class="sxs-lookup"><span data-stu-id="00b01-130">Title</span></span>  
  
    -   <span data-ttu-id="00b01-131">City</span><span class="sxs-lookup"><span data-stu-id="00b01-131">City</span></span>  
  
    -   <span data-ttu-id="00b01-132">StateProvince</span><span class="sxs-lookup"><span data-stu-id="00b01-132">StateProvince</span></span>  
  
13. <span data-ttu-id="00b01-133">Dans la page **script** de l **'éditeur de transformation de script**, cliquez sur **modifier le script** et entrez le code affiché dans la `ScriptMain` classe de l’exemple.</span><span class="sxs-lookup"><span data-stu-id="00b01-133">On the **Script** page of the **Script Transformation Editor**, click **Edit Script** and enter the code shown in the `ScriptMain` class of the example.</span></span> <span data-ttu-id="00b01-134">Fermez l’environnement de développement de script et l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="00b01-134">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
14. <span data-ttu-id="00b01-135">Ajoutez une destination pour SQL Server au flux de données.</span><span class="sxs-lookup"><span data-stu-id="00b01-135">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="00b01-136">Configurez-la pour qu'elle utilise le gestionnaire de connexions OLE DB et la table RowDelimitedData.</span><span class="sxs-lookup"><span data-stu-id="00b01-136">Configure it to use the OLE DB connection manager and the RowDelimitedData table.</span></span> <span data-ttu-id="00b01-137">Connectez la sortie du composant Script à cette destination.</span><span class="sxs-lookup"><span data-stu-id="00b01-137">Connect the output of the Script Component to this destination.</span></span>  
  
15. <span data-ttu-id="00b01-138">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="00b01-138">Run the package.</span></span> <span data-ttu-id="00b01-139">Après l'exécution du package, examinez les enregistrements dans la table de destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b01-139">After the package has finished, examine the records in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination table.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Dim columnName As String  
    Dim columnValue As String  
  
    ' Check for an empty row.  
    If Row.Column0.Trim.Length > 0 Then  
        columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"))  
        ' Check for an empty value after the colon.  
        If Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd.Length > 1 Then  
            ' Extract the column value from after the colon and space.  
            columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2)  
            Select Case columnName  
                Case "FirstName"  
                    ' The FirstName value indicates a new record.  
                    Me.Output0Buffer.AddRow()  
                    Me.Output0Buffer.FirstName = columnValue  
                Case "LastName"  
                    Me.Output0Buffer.LastName = columnValue  
                Case "Title"  
                    Me.Output0Buffer.Title = columnValue  
                Case "City"  
                    Me.Output0Buffer.City = columnValue  
                Case "StateProvince"  
                    Me.Output0Buffer.StateProvince = columnValue  
            End Select  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
        string columnName;  
        string columnValue;  
  
        // Check for an empty row.  
        if (Row.Column0.Trim().Length > 0)  
        {  
            columnName = Row.Column0.Substring(0, Row.Column0.IndexOf(":"));  
            // Check for an empty value after the colon.  
            if (Row.Column0.Substring(Row.Column0.IndexOf(":")).TrimEnd().Length > 1)  
            // Extract the column value from after the colon and space.  
            {  
                columnValue = Row.Column0.Substring(Row.Column0.IndexOf(":") + 2);  
                switch (columnName)  
                {  
                    case "FirstName":  
                        // The FirstName value indicates a new record.  
                        this.Output0Buffer.AddRow();  
                        this.Output0Buffer.FirstName = columnValue;  
                        break;  
                    case "LastName":  
                        this.Output0Buffer.LastName = columnValue;  
                        break;  
                    case "Title":  
                        this.Output0Buffer.Title = columnValue;  
                        break;  
                    case "City":  
                        this.Output0Buffer.City = columnValue;  
                        break;  
                    case "StateProvince":  
                        this.Output0Buffer.StateProvince = columnValue;  
                        break;  
                }  
            }  
        }  
  
    }  
```  
  
##  <a name="example-2-splitting-parent-and-child-records"></a><a name="example2"></a> <span data-ttu-id="00b01-140">Exemple 2 : fractionnement d’enregistrements parents et enfants</span><span class="sxs-lookup"><span data-stu-id="00b01-140">Example 2: Splitting Parent and Child Records</span></span>  
 <span data-ttu-id="00b01-141">Cet exemple montre comment analyser un fichier texte, dans lequel une ligne de séparateur précède une ligne d'enregistrement parente suivie d'un nombre indéfini de lignes d'enregistrement enfants, dans des tables de destination parentes et enfants correctement normalisées, à l'aide du composant Script.</span><span class="sxs-lookup"><span data-stu-id="00b01-141">This example shows how to take a text file, in which a separator row precedes a parent record row that is followed by an indefinite number of child record rows, and parse it into properly normalized parent and child destination tables by using the Script component.</span></span> <span data-ttu-id="00b01-142">Cet exemple simple pourrait être facilement adapté aux fichiers sources qui utilisent plusieurs lignes ou colonnes pour chaque enregistrement parent et enfant, tant qu'il est possible d'identifier le début et la fin de chaque enregistrement.</span><span class="sxs-lookup"><span data-stu-id="00b01-142">This simple example could easily be adapted for source files that use more than one row or column for each parent and child record, as long as there is some way to identify the beginning and end of each record.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="00b01-143">Cet exemple est fourni à titre de démonstration uniquement.</span><span class="sxs-lookup"><span data-stu-id="00b01-143">This sample is intended for demonstration purposes only.</span></span> <span data-ttu-id="00b01-144">Si vous exécutez l'exemple plusieurs fois, il insère des valeurs de clé dupliquées dans la table de destination.</span><span class="sxs-lookup"><span data-stu-id="00b01-144">If you run the sample more than once, it inserts duplicate key values into the destination table.</span></span>  
  
 <span data-ttu-id="00b01-145">Pour plus d’informations sur la configuration du composant script pour une utilisation en tant que transformation dans le workflow, consultez [création d’une transformation synchrone avec le composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)et [création d’une transformation asynchrone à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="00b01-145">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="00b01-146">Pour configurer cet exemple de composant Script</span><span class="sxs-lookup"><span data-stu-id="00b01-146">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="00b01-147">Créez et enregistrez un fichier texte nommé **parentchilddata.txt** contenant les données sources suivantes :</span><span class="sxs-lookup"><span data-stu-id="00b01-147">Create and save a text file named **parentchilddata.txt** that contains the following source data:</span></span>  
  
    ```  
    **********  
    PARENT 1 DATA  
    child 1 data  
    child 2 data  
    child 3 data  
    child 4 data  
    **********  
    PARENT 2 DATA  
    child 5 data  
    child 6 data  
    child 7 data  
    child 8 data  
    **********  
  
    ```  
  
2.  <span data-ttu-id="00b01-148">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b01-148">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="00b01-149">Sélectionnez une base de données de destination et ouvrez une nouvelle fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="00b01-149">Select a destination database, and open a new query window.</span></span> <span data-ttu-id="00b01-150">Dans la fenêtre de requête, exécutez le script suivant pour créer les tables de destination :</span><span class="sxs-lookup"><span data-stu-id="00b01-150">In the query window, execute the following script to create the destination tables:</span></span>  
  
    ```  
    CREATE TABLE [dbo].[Parents]([ParentID] [int] NOT NULL,  
    [ParentRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Parents] PRIMARY KEY CLUSTERED   
    ([ParentID] ASC))  
    GO  
    CREATE TABLE [dbo].[Children]([ChildID] [int] NOT NULL,  
    [ParentID] [int] NOT NULL,  
    [ChildRecord] [varchar](32) NOT NULL,  
     CONSTRAINT [PK_Children] PRIMARY KEY CLUSTERED   
    ([ChildID] ASC))  
    GO  
    ALTER TABLE [dbo].[Children] ADD CONSTRAINT [FK_Children_Parents] FOREIGN KEY([ParentID])  
    REFERENCES [dbo].[Parents] ([ParentID])  
  
    ```  
  
4.  <span data-ttu-id="00b01-151">Ouvrez [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] et créez un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nommé SplitParentChild.dtsx.</span><span class="sxs-lookup"><span data-stu-id="00b01-151">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package named SplitParentChild.dtsx.</span></span>  
  
5.  <span data-ttu-id="00b01-152">Ajoutez un gestionnaire de connexions de fichiers plats au package, nommez-le ParentChildData et configurez-le pour qu'il se connecte au fichier parentchilddata.txt créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="00b01-152">Add a Flat File connection manager to the package, name it ParentChildData, and configure it to connect to the parentchilddata.txt file that you created in a previous step.</span></span>  
  
6.  <span data-ttu-id="00b01-153">Ajoutez un gestionnaire de connexions OLE DB au package et configurez-le pour qu'il se connecte à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et à la base de données dans laquelle vous avez créé les tables de destination.</span><span class="sxs-lookup"><span data-stu-id="00b01-153">Add an OLE DB connection manager to the package and configure it to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the database in which you created the destination tables.</span></span>  
  
7.  <span data-ttu-id="00b01-154">Ajoutez une tâche de flux de données au package, puis cliquez sur l’onglet **Flux de données** du concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="00b01-154">Add a Data Flow task to the package and click the **Data Flow** tab of SSIS Designer.</span></span>  
  
8.  <span data-ttu-id="00b01-155">Ajoutez une source de fichier plat au flux de données et configurez-la pour qu'elle utilise le gestionnaire de connexions ParentChildData.</span><span class="sxs-lookup"><span data-stu-id="00b01-155">Add a Flat File Source to the data flow and configure it to use the ParentChildData connection manager.</span></span> <span data-ttu-id="00b01-156">Dans la page **Colonnes** de l’**Éditeur de source de fichier plat**, sélectionnez la seule colonne externe disponible.</span><span class="sxs-lookup"><span data-stu-id="00b01-156">On the **Columns** page of the **Flat File Source Editor**, select the single available external column.</span></span>  
  
9. <span data-ttu-id="00b01-157">Ajoutez un composant Script au flux de données et configurez-le en tant que transformation.</span><span class="sxs-lookup"><span data-stu-id="00b01-157">Add a Script Component to the data flow and configure it as a transformation.</span></span> <span data-ttu-id="00b01-158">Connectez la sortie de la source de fichier plat au composant Script.</span><span class="sxs-lookup"><span data-stu-id="00b01-158">Connect the output of the Flat File Source to the Script Component.</span></span>  
  
10. <span data-ttu-id="00b01-159">Double-cliquez sur le composant Script pour afficher l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="00b01-159">Double-click the Script component to display the **Script Transformation Editor**.</span></span>  
  
11. <span data-ttu-id="00b01-160">Dans la page **Colonnes d’entrée** de l’**Éditeur de transformation de script**, sélectionnez la seule colonne d’entrée disponible.</span><span class="sxs-lookup"><span data-stu-id="00b01-160">On the **Input Columns** page of the **Script Transformation Editor**, select the single available input column.</span></span>  
  
12. <span data-ttu-id="00b01-161">Dans la page **entrées et sorties** de l **'éditeur de transformation de script**, sélectionnez sortie 0, renommez-le ParentRecords et définissez sa `SynchronousInputID` sur aucun.</span><span class="sxs-lookup"><span data-stu-id="00b01-161">On the **Inputs and Outputs** page of the **Script Transformation Editor**, select Output 0, rename it to ParentRecords, and set its `SynchronousInputID` to None.</span></span> <span data-ttu-id="00b01-162">Créez 2 colonnes de sortie :</span><span class="sxs-lookup"><span data-stu-id="00b01-162">Create 2 output columns:</span></span>  
  
    -   <span data-ttu-id="00b01-163">ParentID (la clé primaire), de type entier signé (4 bits) [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="00b01-163">ParentID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="00b01-164">ParentRecord, de type String [DT_STR] et de longueur 32</span><span class="sxs-lookup"><span data-stu-id="00b01-164">ParentRecord, of type string [DT_STR] with a length of 32.</span></span>  
  
13. <span data-ttu-id="00b01-165">Créez une deuxième sortie et nommez-la ChildRecords.</span><span class="sxs-lookup"><span data-stu-id="00b01-165">Create a second output and name it ChildRecords.</span></span> <span data-ttu-id="00b01-166">Le `SynchronousInputID` de la nouvelle sortie a déjà la valeur Aucune.</span><span class="sxs-lookup"><span data-stu-id="00b01-166">The `SynchronousInputID` of the new output is already set to None.</span></span> <span data-ttu-id="00b01-167">Créez 3 colonnes de sortie :</span><span class="sxs-lookup"><span data-stu-id="00b01-167">Create 3 output columns:</span></span>  
  
    -   <span data-ttu-id="00b01-168">ChildID (la clé primaire), de type entier signé (4 bits) [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="00b01-168">ChildID (the primary key), of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="00b01-169">ParentID (la clé étrangère), également de type entier signé (4 bits) [DT_I4]</span><span class="sxs-lookup"><span data-stu-id="00b01-169">ParentID (the foreign key), also of type four-byte signed integer [DT_I4]</span></span>  
  
    -   <span data-ttu-id="00b01-170">ChildRecord, de type String [DT_STR] et de longueur 50</span><span class="sxs-lookup"><span data-stu-id="00b01-170">ChildRecord, of type string [DT_STR] with a length of 50</span></span>  
  
14. <span data-ttu-id="00b01-171">Dans la page **Script** de l’**Éditeur de transformation de script**, cliquez sur **Modifier le script**.</span><span class="sxs-lookup"><span data-stu-id="00b01-171">On the **Script** page of the **Script Transformation Editor**, click **Edit Script**.</span></span> <span data-ttu-id="00b01-172">Dans la classe `ScriptMain`, entrez le code présenté dans l'exemple.</span><span class="sxs-lookup"><span data-stu-id="00b01-172">In the `ScriptMain` class, enter the code shown in the example.</span></span> <span data-ttu-id="00b01-173">Fermez l’environnement de développement de script et l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="00b01-173">Close the script development environment and the **Script Transformation Editor**.</span></span>  
  
15. <span data-ttu-id="00b01-174">Ajoutez une destination pour SQL Server au flux de données.</span><span class="sxs-lookup"><span data-stu-id="00b01-174">Add a SQL Server Destination to the data flow.</span></span> <span data-ttu-id="00b01-175">Connectez la sortie ParentRecords du composant Script à cette destination. Configurez-la pour qu'elle utilise le gestionnaire de connexions OLE DB et la table Parents.</span><span class="sxs-lookup"><span data-stu-id="00b01-175">Connect the ParentRecords output of the Script Component to this destination.Configure it to use the OLE DB connection manager and the Parents table.</span></span>  
  
16. <span data-ttu-id="00b01-176">Ajoutez une autre destination pour SQL Server au flux de données.</span><span class="sxs-lookup"><span data-stu-id="00b01-176">Add another SQL Server Destination to the data flow.</span></span> <span data-ttu-id="00b01-177">Connectez la sortie ChildRecords du composant Script à cette destination.</span><span class="sxs-lookup"><span data-stu-id="00b01-177">Connect the ChildRecords output of the Script Component to this destination.</span></span> <span data-ttu-id="00b01-178">Configurez-la pour qu'elle utilise le gestionnaire de connexions OLE DB et la table Children.</span><span class="sxs-lookup"><span data-stu-id="00b01-178">Configure it to use the OLE DB connection manager and the Children table.</span></span>  
  
17. <span data-ttu-id="00b01-179">Exécutez le package.</span><span class="sxs-lookup"><span data-stu-id="00b01-179">Run the package.</span></span> <span data-ttu-id="00b01-180">Après l'exécution du package, examinez les enregistrements parents et enfants dans les deux tables de destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00b01-180">After the package has finished, examine the parent and child records in the two [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination tables.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
    Static nextRowIsParent As Boolean = False  
    Static parentCounter As Integer = 0  
    Static childCounter As Integer = 0  
  
    ' If current row starts with separator characters,  
    '  then following row contains new parent record.  
    If Row.Column0.StartsWith("***") Then  
        nextRowIsParent = True  
    Else  
        If nextRowIsParent Then  
            ' Current row contains parent record.  
            parentCounter += 1  
            Me.ParentRecordsBuffer.AddRow()  
            Me.ParentRecordsBuffer.ParentID = parentCounter  
            Me.ParentRecordsBuffer.ParentRecord = Row.Column0  
            nextRowIsParent = False  
        Else  
            ' Current row contains child record.  
            childCounter += 1  
            Me.ChildRecordsBuffer.AddRow()  
            Me.ChildRecordsBuffer.ChildID = childCounter  
            Me.ChildRecordsBuffer.ParentID = parentCounter  
            Me.ChildRecordsBuffer.ChildRecord = Row.Column0  
        End If  
    End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
    int static_Input0_ProcessInputRow_childCounter = 0;  
    int static_Input0_ProcessInputRow_parentCounter = 0;  
    bool static_Input0_ProcessInputRow_nextRowIsParent = false;  
  
        // If current row starts with separator characters,   
        // then following row contains new parent record.   
        if (Row.Column0.StartsWith("***"))  
        {  
            static_Input0_ProcessInputRow_nextRowIsParent = true;  
        }  
        else  
        {  
            if (static_Input0_ProcessInputRow_nextRowIsParent)  
            {  
                // Current row contains parent record.   
                static_Input0_ProcessInputRow_parentCounter += 1;  
                this.ParentRecordsBuffer.AddRow();  
                this.ParentRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ParentRecordsBuffer.ParentRecord = Row.Column0;  
                static_Input0_ProcessInputRow_nextRowIsParent = false;  
            }  
            else  
            {  
                // Current row contains child record.   
                static_Input0_ProcessInputRow_childCounter += 1;  
                this.ChildRecordsBuffer.AddRow();  
                this.ChildRecordsBuffer.ChildID = static_Input0_ProcessInputRow_childCounter;  
                this.ChildRecordsBuffer.ParentID = static_Input0_ProcessInputRow_parentCounter;  
                this.ChildRecordsBuffer.ChildRecord = Row.Column0;  
            }  
        }  
  
    }  
```  
  
<span data-ttu-id="00b01-181">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="00b01-181">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="00b01-182">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="00b01-182">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="00b01-183">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="00b01-183">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="00b01-184">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="00b01-184">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b01-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00b01-185">See Also</span></span>  
 [<span data-ttu-id="00b01-186">Création d'une transformation synchrone à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="00b01-186">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)  
 [<span data-ttu-id="00b01-187">Création d’une transformation asynchrone à l’aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="00b01-187">Creating an Asynchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md)  
  
  
