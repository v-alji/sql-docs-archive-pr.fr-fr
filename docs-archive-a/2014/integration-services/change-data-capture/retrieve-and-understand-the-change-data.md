---
title: Récupérer et comprendre les données modifiées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],retrieving data
ms.assetid: af366697-6942-42bb-aea5-18fdef018965
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62f60bf4a79c39b4f0cb7d1ba8fb3f52680a1f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704348"
---
# <a name="retrieve-and-understand-the-change-data"></a><span data-ttu-id="61f3f-102">Récupérer et comprendre les données modifiées</span><span class="sxs-lookup"><span data-stu-id="61f3f-102">Retrieve and Understand the Change Data</span></span>
  <span data-ttu-id="61f3f-103">Dans le flux de données d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue un chargement incrémentiel des données modifiées, la première tâche consiste à exécuter la requête qui récupère les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="61f3f-103">In the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the first task is to run the query that retrieves the change data.</span></span> <span data-ttu-id="61f3f-104">Vous exécutez cette requête dans un composant source dans une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="61f3f-104">You execute this query inside a source component in a Data Flow task.</span></span> <span data-ttu-id="61f3f-105">Vous pouvez ensuite utiliser des transformations et des destinations en aval pour appliquer les données modifiées à votre destination.</span><span class="sxs-lookup"><span data-stu-id="61f3f-105">You can then use downstream transformations and destinations to apply the change data to your destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61f3f-106">La création d'une requête qui contient une fonction table est la troisième étape du processus de création d'un package qui effectue un chargement incrémentiel des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="61f3f-106">The creation of a query that contains a table-valued function is the third step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="61f3f-107">Pour plus d’informations sur cette requête, consultez [Créer la fonction de récupération des données modifiées](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="61f3f-107">For more information about this query, see, [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span> <span data-ttu-id="61f3f-108">Pour obtenir une description du processus global de création d’un package qui effectue un chargement incrémentiel des données modifiées, consultez [Capture des données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="61f3f-108">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="adding-the-data-flow-task"></a><span data-ttu-id="61f3f-109">Ajout de la tâche de flux de données</span><span class="sxs-lookup"><span data-stu-id="61f3f-109">Adding the Data Flow Task</span></span>  
 <span data-ttu-id="61f3f-110">Dans le flux de données du package, vous récupérez les données modifiées, vous séparez les lignes en fonction du type de modification ayant eu lieu, puis vous appliquez les modifications à la destination.</span><span class="sxs-lookup"><span data-stu-id="61f3f-110">In the data flow of the package, you retrieve the change data, separate the rows based on the type of change that occurred, and then apply the changes to the destination.</span></span>  
  
#### <a name="to-add-a-data-flow-task-to-the-package"></a><span data-ttu-id="61f3f-111">Pour ajouter une tâche de flux de données au package</span><span class="sxs-lookup"><span data-stu-id="61f3f-111">To add a Data Flow task to the package</span></span>  
  
1.  <span data-ttu-id="61f3f-112">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Flux de contrôle** , ajoutez une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="61f3f-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Control Flow** tab, add a Data Flow task.</span></span>  
  
2.  <span data-ttu-id="61f3f-113">Connectez la tâche précédente de préparation de la chaîne de requête à la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="61f3f-113">Connect the preceding task that prepared the query string to the Data Flow task.</span></span>  
  
## <a name="configuring-the-source-component-to-query-for-changes"></a><span data-ttu-id="61f3f-114">Configuration du composant source pour rechercher les modifications</span><span class="sxs-lookup"><span data-stu-id="61f3f-114">Configuring the Source Component to Query for Changes</span></span>  
 <span data-ttu-id="61f3f-115">Le composant source utilise la chaîne de requête qui a été préparée et stockée dans une variable pour appeler la fonction table qui récupère les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="61f3f-115">The source component uses the query string that was prepared and stored in a variable to calls the table-valued function that retrieves the changed data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="61f3f-116">Pour plus d’informations sur la chaîne de requête qui a été préparée et stockée dans une variable, consultez [Préparer la recherche des données modifiées](prepare-to-query-for-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="61f3f-116">For more information about the query string that was prepared and stored in a variable, see [Prepare to Query for the Change Data](prepare-to-query-for-the-change-data.md).</span></span> <span data-ttu-id="61f3f-117">Pour plus d’informations sur la fonction table qui récupère les données modifiées, consultez [Créer la fonction de récupération des données modifiées](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="61f3f-117">For more information about the table-valued function that retrieves the change data, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
#### <a name="to-configure-an-ole-db-source-to-retrieve-the-change-data"></a><span data-ttu-id="61f3f-118">Pour configurer une source OLE DB pour récupérer les données modifiées</span><span class="sxs-lookup"><span data-stu-id="61f3f-118">To configure an OLE DB source to retrieve the change data</span></span>  
  
1.  <span data-ttu-id="61f3f-119">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], sous l’onglet **Flux de données** , ajoutez une source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="61f3f-119">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Data Flow** tab, add an OLE DB source.</span></span>  
  
2.  <span data-ttu-id="61f3f-120">Dans **l’Éditeur de source OLE DB**, dans la page **Gestionnaire de connexions** , sélectionnez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="61f3f-120">In the **OLE DB Source Editor**, on the **Connection Manager** page, select the following options:</span></span>  
  
    1.  <span data-ttu-id="61f3f-121">Configurez une connexion valide à la base de données source.</span><span class="sxs-lookup"><span data-stu-id="61f3f-121">Configure a valid connection to the source database.</span></span>  
  
    2.  <span data-ttu-id="61f3f-122">Pour **Mode d’accès aux données**, sélectionnez **Commande SQL à partir d’une variable**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-122">For **Data access mode**, select **SQL command from variable**.</span></span>  
  
    3.  <span data-ttu-id="61f3f-123">Pour **Nom de variable**, sélectionnez **User::SqlDataQuery**.</span><span class="sxs-lookup"><span data-stu-id="61f3f-123">For **Variable name**, select **User::SqlDataQuery**.</span></span>  
  
3.  <span data-ttu-id="61f3f-124">Dans **l’Éditeur de source OLE DB**, dans la page **Colonnes** , vérifiez que toutes les colonnes souhaitées sont mappées à des colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="61f3f-124">In the **OLE DB Source Editor**, on the **Columns** page, make sure that all the columns that you want are mapped to output columns.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="61f3f-125">étape suivante</span><span class="sxs-lookup"><span data-stu-id="61f3f-125">Next Step</span></span>  
 <span data-ttu-id="61f3f-126">Après avoir configuré une source OLE DB pour récupérer les données modifiées, l'étape suivante consiste à commencer à concevoir le flux de données dans le package.</span><span class="sxs-lookup"><span data-stu-id="61f3f-126">After you have configured an OLE DB source to retrieve the change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="61f3f-127">**Rubrique suivante :** [Traiter les insertions, les mises à jour et les suppressions](process-inserts-updates-and-deletes.md)</span><span class="sxs-lookup"><span data-stu-id="61f3f-127">**Next topic:** [Process Inserts, Updates, and Deletes](process-inserts-updates-and-deletes.md)</span></span>  
  
  
