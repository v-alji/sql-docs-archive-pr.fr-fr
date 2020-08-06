---
title: Ajouter une visionneuse de données à un Workflow | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data viewers [Integration Services]
- data flow [Integration Services], data viewers
- adding data viewers
ms.assetid: 5e573274-a170-4132-bfc8-a8ff3a8411e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7abd76417552ec50da736afe024a5ae36ee6a2ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601042"
---
# <a name="add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="45c4e-102">Ajouter une visionneuse de données à un flux de données</span><span class="sxs-lookup"><span data-stu-id="45c4e-102">Add a Data Viewer to a Data Flow</span></span>
  <span data-ttu-id="45c4e-103">Cette rubrique explique comment ajouter et configurer une visionneuse de données dans un flux de données.</span><span class="sxs-lookup"><span data-stu-id="45c4e-103">This topic describes how to add and configure a data viewer in a data flow.</span></span> <span data-ttu-id="45c4e-104">Une visionneuse de données affiche des données déplacées entre deux composants de flux de données</span><span class="sxs-lookup"><span data-stu-id="45c4e-104">A data viewer displays data that is moving between two data flow components.</span></span> <span data-ttu-id="45c4e-105">Par exemple, une visionneuse de données peut afficher les données extraites d'une source de données avant qu'une transformation dans le flux de données modifie les données.</span><span class="sxs-lookup"><span data-stu-id="45c4e-105">For example, a data viewer can display the data that is extracted from a data source before a transformation in the data flow modifies the data.</span></span>  
  
 <span data-ttu-id="45c4e-106">Un chemin d'accès connecte des composants d'un flux de données en reliant la sortie d'un composant à l'entrée d'un autre composant.</span><span class="sxs-lookup"><span data-stu-id="45c4e-106">A path connects components in a data flow by connecting the output of one data flow component to the input of another component.</span></span>  
  
 <span data-ttu-id="45c4e-107">Avant que vous puissiez ajouter des visionneuses de données à un package, celui-ci doit inclure une tâche de flux de données et au moins deux composants de flux de données connectés.</span><span class="sxs-lookup"><span data-stu-id="45c4e-107">Before you can add data viewers to a package, the package must include a Data Flow task and at least two data flow components that are connected.</span></span>  
  
### <a name="to-add-a-data-viewer-to-a-data-flow"></a><span data-ttu-id="45c4e-108">Pour ajouter une visionneuse de données à un flux de données</span><span class="sxs-lookup"><span data-stu-id="45c4e-108">To add a data viewer to a data flow</span></span>  
  
1.  <span data-ttu-id="45c4e-109">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="45c4e-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="45c4e-110">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="45c4e-110">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="45c4e-111">Cliquez sur l'onglet **Flux de contrôle** , s'il n'est pas déjà sélectionné.</span><span class="sxs-lookup"><span data-stu-id="45c4e-111">Click the **Control Flow** tab, if it is not already active.</span></span>  
  
4.  <span data-ttu-id="45c4e-112">Cliquez sur la tâche de flux de données au flux de données de laquelle vous voulez joindre une visionneuse de données, puis cliquez sur l'onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="45c4e-112">Click the Data Flow task to whose data flow you want to attach a data viewer and then click the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="45c4e-113">Cliquez avec le bouton droit sur un chemin entre deux composants de flux de données, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="45c4e-113">Right-click a path between two data flow components, and click **Edit**.</span></span>  
  
6.  <span data-ttu-id="45c4e-114">Dans la page **Général** , vous pouvez afficher et modifier les propriétés du chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="45c4e-114">On the **General** page, you can view and edit path properties.</span></span> <span data-ttu-id="45c4e-115">Par exemple, dans la liste déroulante **PathAnnotation** , vous pouvez sélectionner l’annotation qui apparaît en regard du chemin.</span><span class="sxs-lookup"><span data-stu-id="45c4e-115">For example, from the **PathAnnotation** drop-down list you can select the annotation that appears next to the path.</span></span>  
  
7.  <span data-ttu-id="45c4e-116">Dans la page **Métadonnées** , vous pouvez afficher les métadonnées de la colonne et les copier dans le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="45c4e-116">On the **Metadata** page, you can view the column metadata and copy the metadata to the Clipboard.</span></span>  
  
8.  <span data-ttu-id="45c4e-117">Dans la page **Visionneuse de données** , cliquez sur **Activer la visionneuse de données**.</span><span class="sxs-lookup"><span data-stu-id="45c4e-117">On the **Data Viewer** page, click **Enable data viewer**.</span></span>  
  
9. <span data-ttu-id="45c4e-118">Dans la zone Colonnes à afficher, sélectionnez les colonnes à afficher dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="45c4e-118">In the Columns to display area, select the columns you want to display in the data viewer.</span></span> <span data-ttu-id="45c4e-119">Par défaut, toutes les colonnes disponibles sont sélectionnées et figurent dans la liste **Colonnes affichées** .</span><span class="sxs-lookup"><span data-stu-id="45c4e-119">By default, all the available columns are selected and listed in the **Displayed Columns** list.</span></span> <span data-ttu-id="45c4e-120">Déplacez les colonnes que vous ne voulez pas utiliser dans la liste **Colonnes inutilisées** en les sélectionnant et en cliquant sur la flèche gauche.</span><span class="sxs-lookup"><span data-stu-id="45c4e-120">Move columns that you do not want to use to the **Unused Column** list by selecting them and then clicking the left arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45c4e-121">Dans la grille, les valeurs qui représentent les types de données DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2 et DT_DBTIMESTAMPOFFSET apparaissent sous forme de chaînes au format ISO 8601 et un espace de séparation remplace le séparateur `T`.</span><span class="sxs-lookup"><span data-stu-id="45c4e-121">In the grid, values that represent the DT_DATE, DT_DBTIME2, DT_FILETIME, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types appear as ISO 8601 formatted strings and a space separator replaces the `T` separator.</span></span> <span data-ttu-id="45c4e-122">Les valeurs qui représentent les types de données DT_DATE et DT_FILETIME incluent sept chiffres pour les fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="45c4e-122">Values that represent the DT_DATE and DT_FILETIME data types include seven digits for fractional seconds.</span></span> <span data-ttu-id="45c4e-123">Étant donné que le type de données DT_FILETIME stocke uniquement trois chiffres pour les fractions de seconde, la grille affiche des zéros pour les quatre chiffres restants.</span><span class="sxs-lookup"><span data-stu-id="45c4e-123">Because the DT_FILETIME data type stores only three digits of fractional seconds, the grid displays zeros for the remaining four digits.</span></span> <span data-ttu-id="45c4e-124">Les valeurs qui représentent le type de données DT_DBTIMESTAMP incluent trois chiffres pour les fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="45c4e-124">Values that represent the DT_DBTIMESTAMP data type include three digits for fractional seconds.</span></span> <span data-ttu-id="45c4e-125">Pour les valeurs qui représentent les types de données DT_DBTIME2, DT_DBTIMESTAMP2 et DT_DBTIMESTAMPOFFSET, le nombre de chiffres pour les fractions de seconde correspond à l'échelle spécifiée pour le type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="45c4e-125">For values that represent the DT_DBTIME2, DT_DBTIMESTAMP2, and DT_DBTIMESTAMPOFFSET data types, the number of digits for fractional seconds corresponds to the scale specified for the column's data type.</span></span> <span data-ttu-id="45c4e-126">Pour plus d'informations sur les formats ISO 8601, consultez [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="45c4e-126">For more information about ISO 8601 formats, see [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span> <span data-ttu-id="45c4e-127">Pour plus d'informations sur les types de données, consultez [Integration Services Data Types](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="45c4e-127">For more information about data types, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
10. <span data-ttu-id="45c4e-128">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="45c4e-128">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c4e-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45c4e-129">See Also</span></span>  
 <span data-ttu-id="45c4e-130">[Transformations Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="45c4e-130">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="45c4e-131">[Chemins Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="45c4e-131">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 <span data-ttu-id="45c4e-132">[Flux de données](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="45c4e-132">[Data Flow](data-flow/data-flow.md) </span></span>  
 [<span data-ttu-id="45c4e-133">Débogage d’un flux de données</span><span class="sxs-lookup"><span data-stu-id="45c4e-133">Debugging Data Flow</span></span>](troubleshooting/debugging-data-flow.md)  
  
  
