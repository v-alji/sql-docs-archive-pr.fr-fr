---
title: Charger des données à l’aide de la destination OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700091"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="0300d-102">Charger des données à l'aide de la destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="0300d-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="0300d-103">Pour pouvoir ajouter et configurer une destination OLE DB, le package doit inclure au moins une tâche de flux de données et une source.</span><span class="sxs-lookup"><span data-stu-id="0300d-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="0300d-104">Pour charger des données à l'aide d'une destination OLE DB</span><span class="sxs-lookup"><span data-stu-id="0300d-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="0300d-105">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="0300d-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0300d-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="0300d-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0300d-107">Cliquez sur l’onglet **Flux de données** puis, dans la **Boîte à outils**, faites glisser la destination OLE DB vers l’aire de conception.</span><span class="sxs-lookup"><span data-stu-id="0300d-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="0300d-108">Connectez la destination OLE DB au flux de données en faisant glisser le connecteur à partir d'une source de données ou d'une transformation précédente vers la destination.</span><span class="sxs-lookup"><span data-stu-id="0300d-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="0300d-109">Double-cliquez sur la destination OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0300d-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="0300d-110">Dans la boîte de dialogue **Éditeur de destination OLE DB** , dans la page **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions OLE DB existant ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="0300d-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="0300d-111">Pour plus d’informations, consultez [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="0300d-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="0300d-112">Sélectionnez la méthode d'accès aux données :</span><span class="sxs-lookup"><span data-stu-id="0300d-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="0300d-113">**Table ou vue** : sélectionnez une table ou une vue dans la base de données qui contient les données.</span><span class="sxs-lookup"><span data-stu-id="0300d-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="0300d-114">**Table ou vue - chargement rapide** : sélectionnez une table ou une vue dans la base de données qui contient les données, puis définissez les options de chargement rapide : **Conserver l’identité**, **Conserver les valeurs NULL**, **Verrou de table**, **Contrainte de validation**, **Lignes par lot**ou **Taille de validation d’insertion maximale**.</span><span class="sxs-lookup"><span data-stu-id="0300d-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="0300d-115">**Variable de nom de table ou de vue** : sélectionnez la variable définie par l’utilisateur qui contient le nom d’une table ou d’une vue dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0300d-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="0300d-116">**Variable de nom de table ou de vue - chargement rapide** : sélectionnez une variable définie par l’utilisateur qui contient le nom d’une table ou d’une vue dans la base de données qui contient les données, puis définissez les options de chargement rapide.</span><span class="sxs-lookup"><span data-stu-id="0300d-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="0300d-117">**Commande SQL** : tapez une commande SQL ou cliquez sur **Générer la requête** pour écrire une commande SQL à l’aide du **Générateur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="0300d-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="0300d-118">Cliquez sur **Mappages** , puis mappez les colonnes de la liste **Colonnes d'entrée disponibles** aux colonnes de la liste **Colonnes de destination disponibles** en faisant glisser les colonnes d'une liste à l'autre.</span><span class="sxs-lookup"><span data-stu-id="0300d-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0300d-119">La destination OLE DB mappe automatiquement les colonnes portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="0300d-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="0300d-120">Pour configurer l'affichage des erreurs, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="0300d-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="0300d-121">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0300d-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="0300d-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0300d-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="0300d-123">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="0300d-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0300d-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0300d-124">See Also</span></span>  
 <span data-ttu-id="0300d-125">[Destination OLE DB](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="0300d-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="0300d-126">[Transformations Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="0300d-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="0300d-127">[Chemins Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="0300d-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="0300d-128">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="0300d-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
