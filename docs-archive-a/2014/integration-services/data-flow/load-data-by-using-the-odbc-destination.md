---
title: Charger des données à l’aide de la destination ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700097"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="cb141-102">Charger des données à l'aide de la destination ODBC</span><span class="sxs-lookup"><span data-stu-id="cb141-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="cb141-103">Cette procédure montre comment charger des données à l'aide de la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="cb141-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="cb141-104">Pour pouvoir ajouter et configurer une destination ODBC, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="cb141-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="cb141-105">Pour charger des données à l'aide d'une destination ODBC</span><span class="sxs-lookup"><span data-stu-id="cb141-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="cb141-106">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] souhaité.</span><span class="sxs-lookup"><span data-stu-id="cb141-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="cb141-107">Cliquez sur l'onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la destination ODBC sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="cb141-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="cb141-108">Faites glisser une sortie disponible d'un composant de flux de données dans l'entrée de la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="cb141-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="cb141-109">Double-cliquez sur la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="cb141-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="cb141-110">Dans la boîte de dialogue **Éditeur de destination ODBC** , dans la page **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions ODBC existant ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="cb141-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="cb141-111">Sélectionnez la méthode d'accès aux données.</span><span class="sxs-lookup"><span data-stu-id="cb141-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="cb141-112">**Nom de la table - Lot**: sélectionnez cette option pour configurer la destination ODBC de manière à utiliser le mode de traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="cb141-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="cb141-113">Lorsque vous sélectionnez cette option, vous pouvez définir **Taille du lot**.</span><span class="sxs-lookup"><span data-stu-id="cb141-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="cb141-114">**Nom de la table - Ligne par ligne**: sélectionnez cette option pour configurer la destination ODBC de manière à insérer les lignes de la table de destination une par une.</span><span class="sxs-lookup"><span data-stu-id="cb141-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="cb141-115">Lorsque vous sélectionnez cette option, les données sont chargées dans la table une ligne à la fois.</span><span class="sxs-lookup"><span data-stu-id="cb141-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="cb141-116">Dans le champ **Nom de la table ou de la vue** , sélectionnez une table ou une vue disponible de la base de données dans la liste ou tapez une expression régulière pour identifier la table. Cette liste contient les 1 000 premières tables uniquement.</span><span class="sxs-lookup"><span data-stu-id="cb141-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="cb141-117">Si votre base de données contient plus de 1 000 tables, vous pouvez taper le début du nom d'une table ou utiliser le caractère générique (\*) pour entrer une partie du nom afin d'afficher la table ou les tables que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="cb141-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="cb141-118">Vous pouvez cliquer sur **Aperçu** pour afficher jusqu'à 200 lignes de données de la table sélectionnée dans la destination ODBC.</span><span class="sxs-lookup"><span data-stu-id="cb141-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="cb141-119">Cliquez sur **Mappages** , puis mappez les colonnes de la liste **Colonnes d'entrée disponibles** aux colonnes de la liste **Colonnes de destination disponibles** en faisant glisser les colonnes d'une liste à l'autre.</span><span class="sxs-lookup"><span data-stu-id="cb141-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="cb141-120">Pour configurer l'affichage des erreurs, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="cb141-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="cb141-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb141-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="cb141-122">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="cb141-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb141-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb141-123">See Also</span></span>  
 <span data-ttu-id="cb141-124">[Éditeur de destination ODBC &#40;page Gestionnaire de connexions&#41;](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="cb141-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="cb141-125">[Éditeur de destination ODBC &#40;page Mappages&#41;](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="cb141-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="cb141-126">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="cb141-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
