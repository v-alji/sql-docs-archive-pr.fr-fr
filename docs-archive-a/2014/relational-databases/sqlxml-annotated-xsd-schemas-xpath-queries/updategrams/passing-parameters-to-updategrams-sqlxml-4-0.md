---
title: Passage de paramètres à codes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611695"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="e6396-102">Passage de paramètres aux codes de mise à jour (updategrams) (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e6396-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="e6396-103">Les codes de mise à jour sont des modèles ; par conséquent, vous pouvez leur passer des paramètres.</span><span class="sxs-lookup"><span data-stu-id="e6396-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="e6396-104">Pour plus d’informations sur le passage de paramètres à des modèles, consultez Considérations sur la [sécurité mise à jour &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e6396-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="e6396-105">Les codes de mise à jour vous permettent de passer NULL comme valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="e6396-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="e6396-106">Pour passer la valeur de paramètre NULL, vous spécifiez l'attribut `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="e6396-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="e6396-107">La valeur assignée à l'attribut `nullvalue` est ensuite fournie comme valeur de paramètre.</span><span class="sxs-lookup"><span data-stu-id="e6396-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="e6396-108">Les codes de mise à jour traitent cette valeur comme NULL.</span><span class="sxs-lookup"><span data-stu-id="e6396-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6396-109">Dans `<sql:header>` et `<updg:header>`, vous devez spécifier `nullvalue` comme non qualifié, tandis que dans `<updg:sync>`, vous spécifiez `nullvalue` comme qualifié (par exemple, `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="e6396-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e6396-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="e6396-110">Examples</span></span>  
 <span data-ttu-id="e6396-111">Pour créer des exemples fonctionnels à l’aide des exemples suivants, vous devez respecter les exigences spécifiées dans la [Configuration requise pour l’exécution d’exemples SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e6396-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="e6396-112">Avant d'utiliser les exemples de code de mise à jour, notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="e6396-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="e6396-113">Les exemples utilisent le mappage par défaut (en d'autres termes, aucun schéma de mappage n'est spécifié dans le code de mise à jour (updategram)).</span><span class="sxs-lookup"><span data-stu-id="e6396-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="e6396-114">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e6396-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="e6396-115">R.</span><span class="sxs-lookup"><span data-stu-id="e6396-115">A.</span></span> <span data-ttu-id="e6396-116">Passage de paramètres à un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="e6396-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="e6396-117">Dans cet exemple, le code de mise à jour modifie le nom d'un employé dans la table HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="e6396-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="e6396-118">Deux paramètres sont passés au code de mise à jour : ShiftID, utilisé pour identifier un horaire de travail de manière unique, et Nom.</span><span class="sxs-lookup"><span data-stu-id="e6396-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e6396-119">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="e6396-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e6396-120">Copiez le code de mise à jour ci-dessus dans le Bloc-notes et enregistrez-le sous le nom UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="e6396-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="e6396-121">Préparez le script de test SQLXML 4,0 (Sqlxml4test. vbs) dans [à l’aide d’ADO pour exécuter des requêtes sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) afin d’exécuter le mise à jour en ajoutant les lignes suivantes après `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="e6396-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="e6396-122">B.</span><span class="sxs-lookup"><span data-stu-id="e6396-122">B.</span></span> <span data-ttu-id="e6396-123">Passage de NULL comme valeur de paramètre à un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="e6396-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="e6396-124">Lors de l'exécution d'un code de mise à jour, la valeur « isnull » est assignée au paramètre auquel vous souhaitez affecter la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="e6396-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="e6396-125">Le code de mise à jour convertit la valeur de paramètre « isnull » en NULL et la traite en conséquence.</span><span class="sxs-lookup"><span data-stu-id="e6396-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="e6396-126">Le code de mise à jour suivant affecte la valeur NULL à un titre d'employé :</span><span class="sxs-lookup"><span data-stu-id="e6396-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e6396-127">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="e6396-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e6396-128">Copiez le code de mise à jour ci-dessus dans le Bloc-notes et enregistrez-le sous le nom UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="e6396-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="e6396-129">Préparez le script de test SQLXML 4,0 (Sqlxml4test. vbs) dans [à l’aide d’ADO pour exécuter des requêtes sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) afin d’exécuter le mise à jour en ajoutant les lignes suivantes après `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="e6396-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e6396-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6396-130">See Also</span></span>  
 [<span data-ttu-id="e6396-131">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e6396-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
