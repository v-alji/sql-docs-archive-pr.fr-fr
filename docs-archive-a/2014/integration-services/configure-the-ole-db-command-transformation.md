---
title: Configurer la transformation de commande OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706664"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="08744-102">Configurer la transformation de commande OLE DB</span><span class="sxs-lookup"><span data-stu-id="08744-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="08744-103">Pour ajouter et configurer une transformation de commande OLE DB, le package doit déjà contenir au moins une tâche de flux de données et une source telle qu'une source de fichier plat ou une source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="08744-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="08744-104">Cette transformation est en général utilisée pour l'exécution de requêtes paramétrables.</span><span class="sxs-lookup"><span data-stu-id="08744-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="08744-105">Pour configurer la transformation de commande OLE DB</span><span class="sxs-lookup"><span data-stu-id="08744-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="08744-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="08744-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="08744-107">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="08744-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="08744-108">Cliquez sur l'onglet **Flux de données** puis, à partir de la **Boîte à outils**, faites glisser la transformation de commande OLE DB sur la surface de dessin.</span><span class="sxs-lookup"><span data-stu-id="08744-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="08744-109">Connectez la transformation de commande OLE DB au flux de données en faisant glisser un connecteur (la flèche verte ou rouge) à partir d’une source de données ou d’une transformation précédente vers la transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="08744-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="08744-110">Cliquez avec le bouton droit sur le composant et sélectionnez Modifier ou Afficher l’ **éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="08744-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="08744-111">Sous l'onglet **Gestionnaires de connexions** , sélectionnez un gestionnaire de connexions OLE DB dans la liste **Gestionnaires de connexions** .</span><span class="sxs-lookup"><span data-stu-id="08744-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="08744-112">Pour plus d’informations, consultez [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="08744-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="08744-113">Cliquez sur l’onglet **Propriétés du composant**, puis sur les points de suspension **(...)** dans la zone **SqlCommand**.</span><span class="sxs-lookup"><span data-stu-id="08744-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="08744-114">Dans l’ **Éditeur de valeur de chaîne**, tapez l’instruction SQL paramétrable avec un point d’interrogation (?) comme marqueur de paramètre pour chaque paramètre.</span><span class="sxs-lookup"><span data-stu-id="08744-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="08744-115">Cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="08744-115">Click **Refresh**.</span></span> <span data-ttu-id="08744-116">Quand vous cliquez sur **Actualiser**, la transformation crée une colonne pour chaque paramètre de la collection Colonnes externes et définit la propriété DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="08744-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="08744-117">Cliquez sur l'onglet **Propriétés d'entrée et de sortie** .</span><span class="sxs-lookup"><span data-stu-id="08744-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="08744-118">Développez **Entrée de commande OLE DB**, puis **Colonnes externes**.</span><span class="sxs-lookup"><span data-stu-id="08744-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="08744-119">Vérifiez que **Colonnes externes** contient une colonne pour chaque paramètre de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="08744-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="08744-120">Les noms des colonnes sont **Param_0**, **Param_1**et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="08744-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="08744-121">Vous ne devez pas modifier les noms des colonnes.</span><span class="sxs-lookup"><span data-stu-id="08744-121">You should not change the column names.</span></span> <span data-ttu-id="08744-122">Si vous modifiez les noms des colonnes, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] génère une erreur de validation pour la transformation de commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="08744-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="08744-123">De même, vous ne devez pas modifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="08744-123">Also, you should not change the data type.</span></span> <span data-ttu-id="08744-124">La propriété DataType de chaque colonne est définie avec le type de données correct.</span><span class="sxs-lookup"><span data-stu-id="08744-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="08744-125">Si **Colonnes externes** ne répertorie aucune colonne, vous devez les ajouter manuellement.</span><span class="sxs-lookup"><span data-stu-id="08744-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="08744-126">Cliquez une fois sur **Ajouter une colonne** pour chaque paramètre de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="08744-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="08744-127">Mettez à jour les noms des colonnes comme suit : **Param_0**, **Param_1**et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="08744-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="08744-128">Spécifiez une valeur dans la propriété DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="08744-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="08744-129">La valeur doit correspondre à une valeur de l'énumération OLE DB DBPARAMFLAGSENUM.</span><span class="sxs-lookup"><span data-stu-id="08744-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="08744-130">Pour plus d'informations, consultez la documentation de référence OLE DB.</span><span class="sxs-lookup"><span data-stu-id="08744-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="08744-131">Spécifiez le type de données de la colonne et, en fonction du type de données, spécifiez la page de codes, la longueur, la précision et l'échelle de la colonne.</span><span class="sxs-lookup"><span data-stu-id="08744-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="08744-132">Pour supprimer un paramètre inutilisé, sélectionnez-le dans **Colonnes externes**, puis cliquez sur **Supprimer une colonne**.</span><span class="sxs-lookup"><span data-stu-id="08744-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="08744-133">Cliquez sur **Mappage de colonnes** et mappez les colonnes de la liste **Colonnes d'entrée disponibles** à des paramètres de la liste **Colonnes de destination disponibles** .</span><span class="sxs-lookup"><span data-stu-id="08744-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="08744-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="08744-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="08744-135">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="08744-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08744-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08744-136">See Also</span></span>  
 <span data-ttu-id="08744-137">[Transformation de commande OLE DB](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="08744-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="08744-138">[Transformations Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="08744-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="08744-139">[Chemins Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="08744-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="08744-140">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="08744-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
