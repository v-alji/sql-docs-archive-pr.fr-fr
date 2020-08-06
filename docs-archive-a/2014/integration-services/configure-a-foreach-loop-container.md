---
title: Configurer un conteneur de boucles Foreach | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601618"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="af8b9-102">Configurer un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="af8b9-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="af8b9-103">Cette procédure décrit comment configurer un conteneur de boucles Foreach, notamment les expressions de la propriété au niveau de l'énumérateur et du conteneur.</span><span class="sxs-lookup"><span data-stu-id="af8b9-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="af8b9-104">Pour configurer le conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="af8b9-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="af8b9-105">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="af8b9-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="af8b9-106">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la boucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="af8b9-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="af8b9-107">Dans la boîte de dialogue **Éditeur de boucle Foreach** , cliquez sur **Général** et, si vous le souhaitez, modifiez le nom et la description de la boucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="af8b9-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="af8b9-108">Cliquez sur **Collection** , puis sélectionnez un type d’énumérateur dans la liste **Énumérateur** .</span><span class="sxs-lookup"><span data-stu-id="af8b9-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="af8b9-109">Indiquez un énumérateur et définissez ses options de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="af8b9-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="af8b9-110">Pour utiliser l’énumérateur Foreach File, indiquez le dossier contenant les fichiers à énumérer, spécifiez un filtre pour le nom et le type de fichier, et indiquez si le nom de fichier complet doit être retourné.</span><span class="sxs-lookup"><span data-stu-id="af8b9-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="af8b9-111">Indiquez enfin si les fichiers des sous-dossiers doivent également être énumérés.</span><span class="sxs-lookup"><span data-stu-id="af8b9-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="af8b9-112">Pour utiliser l’énumérateur Foreach Item, cliquez sur **Colonnes**et, dans la boîte de dialogue **Colonnes For Each Item** , cliquez sur **Ajouter** pour ajouter des colonnes.</span><span class="sxs-lookup"><span data-stu-id="af8b9-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="af8b9-113">Sélectionnez un type de données dans la liste **Type de données** pour chaque colonne, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="af8b9-114">Tapez des valeurs dans les colonnes ou sélectionnez des valeurs dans les listes.</span><span class="sxs-lookup"><span data-stu-id="af8b9-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="af8b9-115">Pour ajouter une nouvelle ligne, cliquez n'importe où en dehors de la cellule dans laquelle vous avez tapé une valeur.</span><span class="sxs-lookup"><span data-stu-id="af8b9-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="af8b9-116">Si une valeur n'est pas compatible avec le type de données de la colonne, le texte est mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="af8b9-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="af8b9-117">Pour utiliser l’énumérateur ADO Foreach, sélectionnez une variable existante ou cliquez sur **Nouvelle variable** dans la liste **Variable source de l’objet ADO** pour spécifier la variable contenant le nom de l’objet ADO à énumérer et sélectionnez une option de mode d’énumération.</span><span class="sxs-lookup"><span data-stu-id="af8b9-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="af8b9-118">Si vous créez une variable, définissez ses propriétés dans la boîte de dialogue **Ajouter une variable** .</span><span class="sxs-lookup"><span data-stu-id="af8b9-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="af8b9-119">Pour utiliser l’énumérateur d’ensemble de lignes du schéma ADO.NET Foreach, sélectionnez une connexion ADO.NET existante ou cliquez sur **Nouvelle connexion** dans la liste **Connexion** , puis sélectionnez un schéma.</span><span class="sxs-lookup"><span data-stu-id="af8b9-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="af8b9-120">Si vous le souhaitez, cliquez sur **Définir les restrictions** et sélectionnez des restrictions de schéma, sélectionnez la variable qui contient la valeur de restriction ou tapez cette valeur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="af8b9-121">Pour utiliser l’énumérateur Foreach à partir d’une variable, sélectionnez une variable dans la liste **Variable** .</span><span class="sxs-lookup"><span data-stu-id="af8b9-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="af8b9-122">Pour utiliser l’énumérateur Foreach NodeList, cliquez sur DocumentSourceType et sélectionnez le type de source dans la liste, puis cliquez sur DocumentSource.</span><span class="sxs-lookup"><span data-stu-id="af8b9-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="af8b9-123">En fonction de la valeur sélectionnée pour DocumentSourceType, sélectionnez une variable ou une connexion de fichier dans la liste, créez une variable ou une connexion de fichier, ou tapez la source XML dans **l’Éditeur de source de document**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="af8b9-124">Cliquez ensuite sur EnumerationType et sélectionnez un type d’énumération dans la liste.</span><span class="sxs-lookup"><span data-stu-id="af8b9-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="af8b9-125">Si la valeur pour EnumerationType est **Navigator, Node ou NodeText**, cliquez sur OuterXPathStringSourceType et sélectionnez le type de source, puis cliquez sur OuterXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="af8b9-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="af8b9-126">En fonction de la valeur définie pour OuterXPathStringSourceType, sélectionnez une variable ou une connexion de fichier dans la liste, créez une variable ou une connexion de fichier, ou tapez la chaîne de l’expression XPath (XML Path Language) externe.</span><span class="sxs-lookup"><span data-stu-id="af8b9-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="af8b9-127">Si la valeur pour EnumerationType est **ElementCollection**, définissez OuterXPathStringSourceType et OuterXPathString conformément aux instructions ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="af8b9-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="af8b9-128">Cliquez ensuite sur InnerElementType, sélectionnez un type d’énumération pour les éléments internes, puis cliquez sur InnerXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="af8b9-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="af8b9-129">En fonction de la valeur définie pour InnerXPathStringSourceType, sélectionnez une variable ou une connexion de fichier, créez une variable ou une connexion de fichier, ou tapez la chaîne de l’expression XPath interne.</span><span class="sxs-lookup"><span data-stu-id="af8b9-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="af8b9-130">Pour utiliser l’énumérateur SMO Foreach, sélectionnez une connexion ADO.NET existante ou cliquez sur **Nouvelle connexion** dans la liste **Connexion** , puis tapez la chaîne à utiliser ou cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="af8b9-131">Si vous cliquez sur **Parcourir**, dans la boîte de dialogue **Sélectionner l’énumération SMO** , sélectionnez le type d’objet à énumérer et le type d’énumération, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="af8b9-132">Si vous le souhaitez, cliquez sur le bouton Parcourir **(...)** dans la zone de texte **Expressions** de la page **Collection** pour créer des expressions qui mettent à jour les valeurs des propriétés.</span><span class="sxs-lookup"><span data-stu-id="af8b9-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="af8b9-133">Pour plus d’informations, consultez [Ajouter ou modifier une Expression de propriété](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="af8b9-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="af8b9-134">Les propriétés énumérées dans la liste **Propriété** varient en fonction de l’énumérateur.</span><span class="sxs-lookup"><span data-stu-id="af8b9-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="af8b9-135">Si vous le souhaitez, cliquez sur **Mappage de variables** pour mapper des propriétés d’objets à la valeur de la collection, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="af8b9-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="af8b9-136">Sélectionnez une variable dans la liste **Variables** ou cliquez sur **\<New Variable>** pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="af8b9-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="af8b9-137">Si vous ajoutez une nouvelle variable, définissez ses propriétés dans la boîte de dialogue **Ajouter une variable** et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="af8b9-138">Si vous utilisez l’énumérateur Foreach Item, vous pouvez mettre à jour la valeur de l’index dans la liste **Index** .</span><span class="sxs-lookup"><span data-stu-id="af8b9-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="af8b9-139">La valeur de l'index indique quelle colonne de l'élément mapper à la variable.</span><span class="sxs-lookup"><span data-stu-id="af8b9-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="af8b9-140">Seul l'énumérateur For Each Item peut utiliser une valeur d'index autre que 0.</span><span class="sxs-lookup"><span data-stu-id="af8b9-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="af8b9-141">Si vous le souhaitez, cliquez sur **Expressions** et, dans la page **Expressions** , créez des expressions de propriété pour les propriétés du conteneur de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="af8b9-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="af8b9-142">Pour plus d’informations, consultez [Ajouter ou modifier une Expression de propriété](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="af8b9-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="af8b9-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="af8b9-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af8b9-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af8b9-144">See Also</span></span>  
 [<span data-ttu-id="af8b9-145">Conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="af8b9-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
