---
title: Extraire des données à l’aide de la source XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709788"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="56b2e-102">Extraire des données à l'aide de la source XML</span><span class="sxs-lookup"><span data-stu-id="56b2e-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="56b2e-103">Pour pouvoir ajouter et configurer une source XML, le package doit inclure au moins une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="56b2e-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="56b2e-104">Pour extraire des données à l'aide d'une source XML</span><span class="sxs-lookup"><span data-stu-id="56b2e-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="56b2e-105">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="56b2e-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="56b2e-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="56b2e-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="56b2e-107">Cliquez sur l’onglet **Flux de données** puis, dans la **Boîte à outils**, faites glisser la source XML vers l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="56b2e-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="56b2e-108">Double-cliquez sur la source XML.</span><span class="sxs-lookup"><span data-stu-id="56b2e-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="56b2e-109">Dans **Éditeur de source XML**, dans la page **Gestionnaire de connexions** , sélectionnez un mode d’accès aux données :</span><span class="sxs-lookup"><span data-stu-id="56b2e-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="56b2e-110">Pour le mode d’accès **Emplacement du fichier XML** , cliquez sur **Parcourir** et recherchez le dossier qui contient le fichier XML.</span><span class="sxs-lookup"><span data-stu-id="56b2e-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="56b2e-111">Pour le mode d’accès **Fichier XML à partir d’une variable** , sélectionnez la variable définie par l’utilisateur qui contient le chemin du fichier XML.</span><span class="sxs-lookup"><span data-stu-id="56b2e-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="56b2e-112">Pour le mode d’accès **Données XML à partir d’une variable** , sélectionnez la variable définie par l’utilisateur qui contient les données XML.</span><span class="sxs-lookup"><span data-stu-id="56b2e-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56b2e-113">Les variables doivent être définies dans la même étendue que la tâche de flux de données qui contient la source XML ou dans la même étendue que le package. Par ailleurs, les données de la variable doivent être de type string.</span><span class="sxs-lookup"><span data-stu-id="56b2e-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="56b2e-114">Si vous le souhaitez, sélectionnez **Utiliser le schéma inclus** pour indiquer que le document XML inclut des informations de schéma.</span><span class="sxs-lookup"><span data-stu-id="56b2e-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="56b2e-115">Pour spécifier une schéma XSD (XML Schema definition language) externe pour le fichier XML, procédez de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="56b2e-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="56b2e-116">Cliquez sur **Parcourir** pour rechercher un fichier XSD existant.</span><span class="sxs-lookup"><span data-stu-id="56b2e-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="56b2e-117">Cliquez sur **Créer XSD** pour créer un fichier XSD à partir du fichier XML.</span><span class="sxs-lookup"><span data-stu-id="56b2e-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="56b2e-118">Pour mettre à jour le nom des colonnes de sortie, cliquez sur **Colonnes** et modifiez les valeurs dans la liste **Colonne de sortie** .</span><span class="sxs-lookup"><span data-stu-id="56b2e-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="56b2e-119">Pour configurer l'affichage des erreurs, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="56b2e-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="56b2e-120">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="56b2e-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="56b2e-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b2e-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="56b2e-122">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="56b2e-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b2e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="56b2e-123">See Also</span></span>  
 <span data-ttu-id="56b2e-124">[Source XML](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="56b2e-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="56b2e-125">[Transformations Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="56b2e-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="56b2e-126">[Chemins Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="56b2e-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="56b2e-127">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="56b2e-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
