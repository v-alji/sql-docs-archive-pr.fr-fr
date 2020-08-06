---
title: Convertir des données en un type de données différent à l’aide de la transformation de conversion de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611195"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="e7a64-102">Convertir des données en un type différent à l'aide de la transformation de conversion de données</span><span class="sxs-lookup"><span data-stu-id="e7a64-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="e7a64-103">Pour pouvoir ajouter et configurer une transformation de conversion de données, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="e7a64-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="e7a64-104">Pour convertir des données en un type différent</span><span class="sxs-lookup"><span data-stu-id="e7a64-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="e7a64-105">Dans [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="e7a64-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e7a64-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="e7a64-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e7a64-107">Cliquez sur l’onglet **Flux de données** et, dans la **boîte à outils**, faites glisser la transformation de conversion de données sur l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="e7a64-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="e7a64-108">Connectez la transformation de conversion de données au flux de données en faisant glisser un connecteur à partir de la source ou de la transformation précédente vers la transformation de conversion de données.</span><span class="sxs-lookup"><span data-stu-id="e7a64-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="e7a64-109">Double-cliquez sur la transformation de conversion de données.</span><span class="sxs-lookup"><span data-stu-id="e7a64-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="e7a64-110">Dans la boîte de dialogue **Éditeur de transformation de conversion de données** , dans la table **Colonnes d’entrée disponibles** , cochez la case en regard des colonnes dont vous voulez convertir le type de données.</span><span class="sxs-lookup"><span data-stu-id="e7a64-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e7a64-111">Vous pouvez appliquer plusieurs conversions de données à une colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="e7a64-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="e7a64-112">Si vous le souhaitez, modifiez les valeurs par défaut de la colonne **Alias de sortie** .</span><span class="sxs-lookup"><span data-stu-id="e7a64-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="e7a64-113">Dans la liste **Type de données** , sélectionnez le nouveau type de données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="e7a64-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="e7a64-114">Le type de données par défaut est celui de la colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="e7a64-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="e7a64-115">Si vous le souhaitez et selon le type de données sélectionné, mettez à jour les valeurs des colonnes **Longueur**, **Précision**, **Échelle**et **Page de codes** .</span><span class="sxs-lookup"><span data-stu-id="e7a64-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="e7a64-116">Pour configurer la sortie d’erreur, cliquez sur **Configurer la sortie d’erreur**.</span><span class="sxs-lookup"><span data-stu-id="e7a64-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="e7a64-117">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e7a64-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="e7a64-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7a64-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="e7a64-119">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="e7a64-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a64-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7a64-120">See Also</span></span>  
 <span data-ttu-id="e7a64-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="e7a64-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="e7a64-122">[Transformations Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e7a64-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="e7a64-123">[Chemins Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e7a64-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="e7a64-124">[Types de données d’Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="e7a64-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="e7a64-125">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="e7a64-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
