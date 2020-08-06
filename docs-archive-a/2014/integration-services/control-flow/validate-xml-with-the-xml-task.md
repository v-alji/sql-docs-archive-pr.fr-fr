---
title: Effectuer une validation XML avec la tâche XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600154"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="bf5bc-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="bf5bc-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="bf5bc-103">Validez des documents XML et obtenez une sortie d’erreur détaillée en activant la propriété `ValidationDetails` de la tâche XML.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="bf5bc-104">La capture d’écran ci-après affiche l’ **Éditeur de tâche XML** avec les paramètres requis pour l’exécution d’une validation XML avec une sortie d’erreur détaillée.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="bf5bc-105">![Propriétés de la tâche XML dans l’Éditeur de tâche XML](../media/xmltaskproperties.jpg "Propriétés de la tâche XML dans l’Éditeur de tâche XML")</span><span class="sxs-lookup"><span data-stu-id="bf5bc-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="bf5bc-106">Avant que la propriété `ValidationDetails` ne soit disponible, la validation XML par la tâche XML ne renvoyait qu’un résultat true ou false, sans aucune information sur les erreurs ou leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="bf5bc-107">À présent, quand vous définissez `ValidationDetails` sur true, le fichier de sortie contient des informations détaillées sur chaque erreur, notamment le numéro de ligne et la position.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="bf5bc-108">Vous pouvez utiliser ces informations pour comprendre, localiser et corriger les erreurs dans les documents XML.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="bf5bc-109">La fonctionnalité de validation XML s’adapte aisément aux documents XML volumineux et aux nombres d’erreurs élevés.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="bf5bc-110">Étant donné que le fichier de sortie proprement dit présente le format XML, vous pouvez exécuter des requêtes sur la sortie et analyser cette dernière.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="bf5bc-111">Par exemple, si la sortie contient un grand nombre d’erreurs, vous pouvez regrouper les erreurs en exécutant une requête [!INCLUDE[tsql](../../../includes/tsql-md.md)] , comme décrit dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="bf5bc-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) a introduit la `ValidationDetails` propriété dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="bf5bc-113">La propriété est également disponible dans [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] et dans SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="bf5bc-114">Exemple de sortie pour XML valide</span><span class="sxs-lookup"><span data-stu-id="bf5bc-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="bf5bc-115">Voici un exemple de fichier de sortie présentant les résultats de validation d’un fichier XML valide.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="bf5bc-116">Exemple de sortie pour XML non valide</span><span class="sxs-lookup"><span data-stu-id="bf5bc-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="bf5bc-117">Voici un exemple de fichier de sortie présentant les résultats de validation d’un fichier XML contenant un petit nombre d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="bf5bc-118">Le texte des éléments \<error> a été renvoyé à la ligne pour améliorer la lisibilité.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="bf5bc-119">Analyser la sortie de validation XML avec une requête Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bf5bc-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="bf5bc-120">Si le résultat de la validation XML contient un grand nombre d’erreurs, vous pouvez utiliser une requête [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour charger la sortie dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf5bc-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bf5bc-121">Vous pouvez ensuite analyser la liste d’erreurs avec toutes les fonctionnalités du langage T-SQL, notamment WHERE, GROUP BY, ORDER BY, JOIN, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="bf5bc-122">Voici le résultat dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] du second exemple de requête figurant dans le texte précédent.</span><span class="sxs-lookup"><span data-stu-id="bf5bc-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="bf5bc-123">![Erreurs XML de requête sur un groupe dans Management Studio](../media/queryforxmlerrors.jpg "Erreurs XML de requête sur un groupe dans Management Studio")</span><span class="sxs-lookup"><span data-stu-id="bf5bc-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="bf5bc-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bf5bc-124">See Also</span></span>
 <span data-ttu-id="bf5bc-125">Éditeur de tâche XML de [tâche xml](xml-task.md) [&#40;page général&#41;](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="bf5bc-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


