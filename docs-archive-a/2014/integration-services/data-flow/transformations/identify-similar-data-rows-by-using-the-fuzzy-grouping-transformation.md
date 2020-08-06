---
title: Identifier des lignes de données semblables à l’aide de la transformation de regroupement probable | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613060"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="85723-102">Identifier des lignes de données semblables à l'aide de la transformation de regroupement probable</span><span class="sxs-lookup"><span data-stu-id="85723-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="85723-103">Pour ajouter et configurer une transformation de regroupement probable, le package doit déjà inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="85723-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="85723-104">Pour implémenter une transformation de regroupement probable dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="85723-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="85723-105">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="85723-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="85723-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="85723-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="85723-107">Cliquez sur l’onglet **Flux de données** puis, à partir de la **Boîte à outils**, faites glisser la transformation de regroupement probable sur la surface de dessin.</span><span class="sxs-lookup"><span data-stu-id="85723-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="85723-108">Connectez la transformation de regroupement probable au flux de données en faisant glisser le connecteur à partir de la source de données ou d'une transformation précédente vers la transformation de regroupement probable.</span><span class="sxs-lookup"><span data-stu-id="85723-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="85723-109">Double-cliquez sur la transformation de regroupement probable.</span><span class="sxs-lookup"><span data-stu-id="85723-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="85723-110">Dans la boîte de dialogue **Éditeur de transformation de regroupement probable** , sous l’onglet **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions OLE DB qui établit une connexion à une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85723-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85723-111">La transformation requiert une connexion à une base de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour permettre la création de tables et d’index temporaires.</span><span class="sxs-lookup"><span data-stu-id="85723-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="85723-112">Cliquez sur l’onglet **Colonnes** et, dans la liste **Colonnes d’entrée disponibles** , cochez la case des colonnes d’entrée à utiliser pour identifier des lignes semblables dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="85723-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="85723-113">Cochez la case dans la colonne **Transfert direct** pour identifier les colonnes d’entrée comme devant être transférées directement vers la sortie de transformation.</span><span class="sxs-lookup"><span data-stu-id="85723-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="85723-114">Les colonnes à transfert direct ne sont pas incluses dans le processus d'identification des lignes dupliquées.</span><span class="sxs-lookup"><span data-stu-id="85723-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85723-115">Les colonnes d'entrée utilisées pour le regroupement sont sélectionnées automatiquement comme colonnes à transfert direct et elles ne peuvent pas être désélectionnées tant qu'elles sont utilisées pour le regroupement.</span><span class="sxs-lookup"><span data-stu-id="85723-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="85723-116">Mettez éventuellement à jour les noms des colonnes de sortie dans la colonne **Alias de sortie** .</span><span class="sxs-lookup"><span data-stu-id="85723-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="85723-117">Vous pouvez également mettre à jour les noms des colonnes nettoyées dans la colonne **Alias de sortie de groupe** .</span><span class="sxs-lookup"><span data-stu-id="85723-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85723-118">Les noms par défaut des colonnes sont les noms des colonnes d'entrée avec un suffixe « _clean ».</span><span class="sxs-lookup"><span data-stu-id="85723-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="85723-119">Mettez éventuellement à jour le type de correspondance à utiliser dans la colonne **Type de correspondance** .</span><span class="sxs-lookup"><span data-stu-id="85723-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85723-120">Au moins une colonne doit utiliser la correspondance approximative.</span><span class="sxs-lookup"><span data-stu-id="85723-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="85723-121">Spécifiez les colonnes de niveau de similarité minimale dans la colonne **Similarité minimale** .</span><span class="sxs-lookup"><span data-stu-id="85723-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="85723-122">Elle doit être comprise entre 0 et 1.</span><span class="sxs-lookup"><span data-stu-id="85723-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="85723-123">Plus la valeur est proche de 1, plus les valeurs des colonnes d'entrée doivent être similaires pour former un groupe.</span><span class="sxs-lookup"><span data-stu-id="85723-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="85723-124">Une similarité minimale de 1 indique une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="85723-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="85723-125">Mettez éventuellement à jour les noms des colonnes de similarité dans la colonne **Alias de sortie de similarité** .</span><span class="sxs-lookup"><span data-stu-id="85723-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="85723-126">Pour spécifier la gestion des nombres dans les valeurs de données, mettez à jour les valeurs dans la colonne **Chiffres** .</span><span class="sxs-lookup"><span data-stu-id="85723-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="85723-127">Pour spécifier la manière dont la transformation compare les données de chaîne dans une colonne, modifiez la sélection par défaut des options de comparaison dans la colonne **Indicateurs de comparaison** .</span><span class="sxs-lookup"><span data-stu-id="85723-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="85723-128">Cliquez sur l’onglet **Avancé** pour modifier les noms des colonnes que la transformation ajoute à la sortie pour l’identificateur de ligne unique (_key_in), l’identificateur de ligne dupliquée (_key_out) et la valeur de similarité (_score).</span><span class="sxs-lookup"><span data-stu-id="85723-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="85723-129">Ajustez éventuellement le seuil de similarité en déplaçant le curseur.</span><span class="sxs-lookup"><span data-stu-id="85723-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="85723-130">Désactivez éventuellement les cases à cocher de séparateurs de jetons pour ignorer les séparateurs dans les données.</span><span class="sxs-lookup"><span data-stu-id="85723-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="85723-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="85723-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="85723-132">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="85723-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85723-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="85723-133">See Also</span></span>  
 <span data-ttu-id="85723-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="85723-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="85723-135">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="85723-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="85723-136">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="85723-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="85723-137">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="85723-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
