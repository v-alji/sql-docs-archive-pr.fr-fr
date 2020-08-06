---
title: Traiter les insertions, les mises à jour et les suppressions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601031"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="8443c-102">Traiter les insertions, les mises à jour et les suppressions</span><span class="sxs-lookup"><span data-stu-id="8443c-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="8443c-103">Dans le flux de données d'un package Integration Services qui effectue un chargement incrémentiel des données modifiées, la deuxième tâche consiste à séparer les insertions, les mises à jour et les suppressions.</span><span class="sxs-lookup"><span data-stu-id="8443c-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="8443c-104">Ensuite, vous pouvez utiliser des commandes appropriées pour les appliquer à la destination.</span><span class="sxs-lookup"><span data-stu-id="8443c-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8443c-105">La première tâche pour concevoir le flux de données d'un package qui effectue un chargement incrémentiel des données modifiées consiste à configurer le composant source qui exécute la requête qui récupère les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="8443c-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="8443c-106">Pour plus d’informations sur ce composant, consultez [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="8443c-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="8443c-107">Pour obtenir une description du processus global de création d’un package qui effectue un chargement incrémentiel des données modifiées, consultez [Capture des données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="8443c-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="8443c-108">Association de valeurs conviviales pour séparer des insertions, des mises à jour et des suppressions</span><span class="sxs-lookup"><span data-stu-id="8443c-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="8443c-109">Dans l’exemple de requête qui récupère les données modifiées, la fonction **cdc.fn_cdc_get_net_changes_<capture_instance>** retourne uniquement la colonne de métadonnées nommée **__$operation**.</span><span class="sxs-lookup"><span data-stu-id="8443c-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="8443c-110">Cette colonne de métadonnées contient une valeur ordinale qui indique l'opération ayant entraîné la modification.</span><span class="sxs-lookup"><span data-stu-id="8443c-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8443c-111">Pour plus d’informations sur la requête qui utilise la fonction **cdc.fn_cdc_get_net_changes_<capture_instance>** , consultez [Créer la fonction de récupération des données modifiées](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="8443c-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="8443c-112">La mise en correspondance d'une valeur ordinale à son opération associée n'est pas aussi facile que d'utiliser un mnémonique de l'opération.</span><span class="sxs-lookup"><span data-stu-id="8443c-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="8443c-113">Par exemple, 'D' peut facilement représenter une opération de suppression (Delete) et 'I' une opération d'insertion.</span><span class="sxs-lookup"><span data-stu-id="8443c-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="8443c-114">L’exemple de requête créé dans la rubrique [Création de la fonction de récupération des données modifiées](create-the-function-to-retrieve-the-change-data.md)effectue cette conversion d’une valeur ordinale en valeur de chaîne conviviale qui est retournée dans une nouvelle colonne.</span><span class="sxs-lookup"><span data-stu-id="8443c-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="8443c-115">Le segment de code suivant illustre cette conversion :</span><span class="sxs-lookup"><span data-stu-id="8443c-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="8443c-116">Configuration d'une transformation de fractionnement conditionnel pour diriger des insertions, des mises à jour et des suppressions</span><span class="sxs-lookup"><span data-stu-id="8443c-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="8443c-117">Pour diriger des lignes de données modifiées vers l'une des trois sorties, la transformation de fractionnement conditionnel est idéale.</span><span class="sxs-lookup"><span data-stu-id="8443c-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="8443c-118">La transformation vérifie simplement la valeur de la colonne **CDC_OPERATION** dans chaque ligne et détermine si cette modification est une insertion, une mise à jour ou une suppression.</span><span class="sxs-lookup"><span data-stu-id="8443c-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8443c-119">La colonne CDC_OPERATION contient une valeur de chaîne conviviale dérivée de la valeur numérique dans la colonne **__$operation** .</span><span class="sxs-lookup"><span data-stu-id="8443c-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="8443c-120">Pour fractionner des insertions, des mises à jour et des suppressions à des fins de traitement à l'aide d'une transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8443c-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="8443c-121">Sous l’onglet **Flux de données** , ajoutez une transformation de fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="8443c-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="8443c-122">Connectez la sortie de la source OLE DB à la transformation de fractionnement conditionnel.</span><span class="sxs-lookup"><span data-stu-id="8443c-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="8443c-123">Dans **Éditeur de transformation de fractionnement conditionnel**, dans le volet inférieur de l’éditeur, entrez les trois lignes suivantes pour désigner les trois sorties.</span><span class="sxs-lookup"><span data-stu-id="8443c-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="8443c-124">Entrez une ligne avec la condition `CDC_OPERATION == "I"` pour diriger des lignes insérées vers la sortie pour les insertions.</span><span class="sxs-lookup"><span data-stu-id="8443c-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="8443c-125">Entrez une ligne avec la condition `CDC_OPERATION == "U"` pour diriger des lignes mises à jours vers la sortie pour des mises à jours.</span><span class="sxs-lookup"><span data-stu-id="8443c-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="8443c-126">Entrez une ligne avec la condition `CDC_OPERATION == "D"` pour diriger des lignes supprimées vers la sortie pour des suppressions.</span><span class="sxs-lookup"><span data-stu-id="8443c-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8443c-127">étape suivante</span><span class="sxs-lookup"><span data-stu-id="8443c-127">Next Step</span></span>  
 <span data-ttu-id="8443c-128">Après avoir fractionné les lignes à des fins de traitement, l'étape suivante consiste à appliquer les modifications à la destination.</span><span class="sxs-lookup"><span data-stu-id="8443c-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="8443c-129">**Rubrique suivante :** [Appliquer les modifications à la destination](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="8443c-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8443c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8443c-130">See Also</span></span>  
 <span data-ttu-id="8443c-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="8443c-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="8443c-132">Fractionner un dataset à l'aide de la transformation de fractionnement conditionnel</span><span class="sxs-lookup"><span data-stu-id="8443c-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
