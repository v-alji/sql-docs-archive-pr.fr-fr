---
title: DDL d’exécution de SQL Server Analysis Services, tâche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.f1
helpviewer_keywords:
- Analysis Services Execute DDL task
- DDL
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a75bae174c816cdabd07ce688e068cbadb016b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605662"
---
# <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="86878-102">Tâche DDL d'exécution de SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="86878-102">Analysis Services Execute DDL Task</span></span>
  <span data-ttu-id="86878-103">La tâche DDL d'exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] exécute des instructions DDL (Data Definition Language) qui peuvent créer, supprimer ou modifier des modèles d'exploration de données et des objets multidimensionnels tels que des cubes et des dimensions.</span><span class="sxs-lookup"><span data-stu-id="86878-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task runs data definition language (DDL) statements that can create, drop, or alter mining models and multidimensional objects such as cubes and dimensions.</span></span> <span data-ttu-id="86878-104">Par exemple, une instruction DDL peut créer une partition dans le cube **Adventure Works** ou supprimer une dimension dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], l’exemple de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inclus dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86878-104">For example, a DDL statement can create a partition in the **Adventure Works** cube, or delete a dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="86878-105">La tâche DDL d'exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise un gestionnaire de connexions [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour se connecter à une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou à un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86878-105">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="86878-106">Pour plus d'informations, consultez [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="86878-106">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="86878-107">comprend une série de tâches qui effectuent des opérations de Business Intelligence, telles que le traitement des objets analytiques et l’exécution des requêtes de prédiction d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="86878-107">includes a number of tasks that perform business intelligence operations, such as processing analytic objects and running data mining prediction queries.</span></span>  
  
 <span data-ttu-id="86878-108">Pour plus d'informations sur les tâches Business Intelligence associées, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="86878-108">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="86878-109">Tâche de traitement d’Analysis Services</span><span class="sxs-lookup"><span data-stu-id="86878-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
-   [<span data-ttu-id="86878-110">Tâche de requête d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="86878-110">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="ddl-statements"></a><span data-ttu-id="86878-111">Instructions DDL</span><span class="sxs-lookup"><span data-stu-id="86878-111">DDL Statements</span></span>  
 <span data-ttu-id="86878-112">Les instructions DDL sont représentées en tant qu'instructions en langage ASSL ( [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language) et insérées dans une commande XMLA (XML for Analysis).</span><span class="sxs-lookup"><span data-stu-id="86878-112">The DDL statements are represented as statements in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL), and framed in an XML for Analysis (XMLA) command.</span></span>  
  
-   <span data-ttu-id="86878-113">Le langage ASSL permet de définir et de décrire une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , ainsi que les bases de données et les objets de base de données qu’elle contient.</span><span class="sxs-lookup"><span data-stu-id="86878-113">ASSL is used to define and describe an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and the databases and database objects it contains.</span></span> <span data-ttu-id="86878-114">Pour plus d’informations, consultez [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="86878-114">For more information, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
-   <span data-ttu-id="86878-115">XMLA est un langage de commande qui permet d'envoyer des commandes d'action, telles que Create, Alter ou Process, à une instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86878-115">XMLA is a command language that is used to send action commands, such as Create, Alter, or Process, to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="86878-116">Pour plus d’informations, consultez [Référence XML for Analysis &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="86878-116">For more information, see [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="86878-117">Si le code DDL est stocké dans un fichier distinct, la tâche DDL d’exécution de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilise un gestionnaire de connexions de fichiers pour spécifier le chemin du fichier.</span><span class="sxs-lookup"><span data-stu-id="86878-117">If the DDL code is stored in a separate file, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses a File connection manager to specify the path of the file.</span></span> <span data-ttu-id="86878-118">Pour plus d’informations, consultez [File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="86878-118">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="86878-119">Étant donné que les instructions DDL peuvent contenir des mots de passe et d'autres informations sensibles, un package qui comporte une ou plusieurs tâches DDL d'exécution [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] doit utiliser le niveau de protection de package `EncryptAllWithUserKey` ou `EncryptAllWithPassword`.</span><span class="sxs-lookup"><span data-stu-id="86878-119">Because DDL statements can contain passwords and other sensitive information, a package that contains one or more [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL tasks should use the package protection level `EncryptAllWithUserKey` or `EncryptAllWithPassword`.</span></span> <span data-ttu-id="86878-120">Pour plus d’informations, consultez [Integration Services &#40;SSIS&#41;, packages](../integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="86878-120">For more information, see [Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md).</span></span>  
  
### <a name="ddl-examples"></a><span data-ttu-id="86878-121">Exemples d'instructions DDL</span><span class="sxs-lookup"><span data-stu-id="86878-121">DDL Examples</span></span>  
 <span data-ttu-id="86878-122">Les trois instructions DDL suivantes ont été générées en créant des scripts d’objets dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86878-122">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="86878-123">L’instruction DDL suivante supprime la dimension **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="86878-123">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="86878-124">L'instruction DDL suivante traite le cube [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86878-124">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="86878-125">L’instruction DDL suivante crée le modèle d’exploration de données **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="86878-125">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 <span data-ttu-id="86878-126">Les trois instructions DDL suivantes ont été générées en créant des scripts d’objets dans [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], la base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] incluse dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86878-126">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="86878-127">L’instruction DDL suivante supprime la dimension **Promotion** .</span><span class="sxs-lookup"><span data-stu-id="86878-127">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="86878-128">L'instruction DDL suivante traite le cube [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86878-128">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="86878-129">L’instruction DDL suivante crée le modèle d’exploration de données **Forecasting** .</span><span class="sxs-lookup"><span data-stu-id="86878-129">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## <a name="configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="86878-130">Configuration de la tâche DDL d'exécution d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="86878-130">Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="86878-131">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="86878-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="86878-132">Pour plus d'informations sur les propriétés définissables dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="86878-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="86878-133">Éditeur de tâche DDL d’exécution Analysis Services &#40;page Général&#41;</span><span class="sxs-lookup"><span data-stu-id="86878-133">Analysis Services Execute DDL Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="86878-134">Éditeur de tâche DDL d’exécution Analysis Services &#40;page DDL&#41;</span><span class="sxs-lookup"><span data-stu-id="86878-134">Analysis Services Execute DDL Task Editor &#40;DDL Page&#41;</span></span>](../analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [<span data-ttu-id="86878-135">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="86878-135">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="86878-136">Pour plus d'informations sur la définition de ces propriétés dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="86878-136">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="86878-137">Définir les propriétés d'une tâche ou d'un conteneur</span><span class="sxs-lookup"><span data-stu-id="86878-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="86878-138">Configuration par programmation de la tâche DDL d'exécution d'Analysis Services</span><span class="sxs-lookup"><span data-stu-id="86878-138">Programmatic Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="86878-139">Pour plus d'informations sur la définition par programme de ces propriétés, cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="86878-139">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  
