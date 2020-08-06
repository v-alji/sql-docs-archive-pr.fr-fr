---
title: Extraire des données à l’aide de la source OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709791"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="2c621-102">Extraire des données à l'aide de la source OLE DB</span><span class="sxs-lookup"><span data-stu-id="2c621-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="2c621-103">Pour pouvoir ajouter et configurer une source OLE DB, le package doit inclure au moins une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="2c621-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="2c621-104">Pour extraire des données à l'aide d'une source OLE DB</span><span class="sxs-lookup"><span data-stu-id="2c621-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="2c621-105">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="2c621-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="2c621-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="2c621-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2c621-107">Cliquez sur l'onglet **Flux de données** , puis dans la **Boîte à outils**, faites glisser la source OLE DB sur l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="2c621-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="2c621-108">Double-cliquez sur la source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2c621-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="2c621-109">Dans la boîte de dialogue **Éditeur de source OLE DB** , dans la page **Gestionnaire de connexions** , sélectionnez un gestionnaire de connexions OLE DB existant ou cliquez sur **Nouveau** pour créer un gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="2c621-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="2c621-110">Pour plus d’informations, consultez [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2c621-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="2c621-111">Sélectionnez la méthode d'accès aux données :</span><span class="sxs-lookup"><span data-stu-id="2c621-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="2c621-112">**Table ou vue** Sélectionnez une table ou une vue dans la base de données à laquelle le gestionnaire de connexions OLE DB se connecte.</span><span class="sxs-lookup"><span data-stu-id="2c621-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="2c621-113">**Variable de nom de table ou de vue** Sélectionnez la variable définie par l’utilisateur contenant le nom d’une table ou d’une vue dans la base de données à laquelle le gestionnaire de connexions OLE DB se connecte.</span><span class="sxs-lookup"><span data-stu-id="2c621-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="2c621-114">**Commande SQL** Tapez une commande SQL ou cliquez sur **Générer la requête** pour écrire une commande SQL à l’aide du **Générateur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="2c621-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2c621-115">La commande peut inclure des paramètres.</span><span class="sxs-lookup"><span data-stu-id="2c621-115">The command can include parameters.</span></span> <span data-ttu-id="2c621-116">Pour plus d’informations, consultez [Mapper des paramètres de requête à des variables dans un composant de flux de données](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2c621-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="2c621-117">**Commande SQL à partir d’une variable** Sélectionnez la variable définie par l’utilisateur contenant la commande SQL.</span><span class="sxs-lookup"><span data-stu-id="2c621-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2c621-118">Les variables doivent être définies dans la même étendue que la tâche de flux de données qui contient la source OLE DB ou dans la même étendue que le package. Par ailleurs, les données de la variable doivent être de type string.</span><span class="sxs-lookup"><span data-stu-id="2c621-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="2c621-119">Pour mettre à jour le mappage entre les colonnes externes et les colonnes de sortie, cliquez sur **Colonnes** et sélectionnez des colonnes dans la liste **Colonne externe** .</span><span class="sxs-lookup"><span data-stu-id="2c621-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="2c621-120">Si vous le souhaitez, mettez à jour les noms des colonnes de sortie en modifiant des valeurs dans la liste **Colonne de sortie** .</span><span class="sxs-lookup"><span data-stu-id="2c621-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="2c621-121">Pour configurer l'affichage des erreurs, cliquez sur **Sortie d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="2c621-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="2c621-122">Pour plus d’informations, consultez [Configurer une sortie d’erreur dans un composant de flux de données](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2c621-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="2c621-123">Vous pouvez cliquer sur **Aperçu** pour afficher jusqu’à 200 lignes de données extraites par la source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2c621-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="2c621-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c621-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="2c621-125">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="2c621-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c621-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c621-126">See Also</span></span>  
 <span data-ttu-id="2c621-127">[Source OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="2c621-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="2c621-128">[Transformations Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="2c621-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="2c621-129">[Chemins Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="2c621-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="2c621-130">tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="2c621-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
