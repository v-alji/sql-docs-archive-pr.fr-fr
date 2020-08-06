---
title: 'Leçon 2 : Spécification des informations de connexion (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 54405a3a-d7fa-4d95-8963-9aa224e5901e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c187f0abdc4b277a5f1428407b5c42ca4fd6fee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699329"
---
# <a name="lesson-2-specifying-connection-information-reporting-services"></a><span data-ttu-id="78cc6-102">Leçon 2 : Spécification des informations de connexion (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="78cc6-102">Lesson 2: Specifying Connection Information (Reporting Services)</span></span>
  <span data-ttu-id="78cc6-103">Après avoir ajouté un rapport au projet Didacticiel, vous devez définir une *source de données*, qui sont des informations de connexion que le rapport utilise pour accéder aux données à partir d’une base de données relationnelle, d’une base de données multidimensionnelle ou d’une autre ressource.</span><span class="sxs-lookup"><span data-stu-id="78cc6-103">After you add a report to the Tutorial project, you need to define a *data source*, which is connection information the report uses to access data from either a relational database, multidimensional database, or other resource.</span></span>  
  
 <span data-ttu-id="78cc6-104">Dans cette leçon, vous allez utiliser l'exemple de base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] comme source de données.</span><span class="sxs-lookup"><span data-stu-id="78cc6-104">In this lesson, you will use the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database as your data source.</span></span> <span data-ttu-id="78cc6-105">Ce didacticiel part du principe que cette base de données se trouve dans une instance par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] qui est installée sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="78cc6-105">This tutorial assumes that this database is located in a default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed on your local computer.</span></span>  
  
### <a name="to-set-up-a-connection"></a><span data-ttu-id="78cc6-106">Pour configurer une connexion</span><span class="sxs-lookup"><span data-stu-id="78cc6-106">To set up a connection</span></span>  
  
1.  <span data-ttu-id="78cc6-107">Dans le volet **données du rapport** , cliquez sur **nouveau** , puis sur **source de données...**.</span><span class="sxs-lookup"><span data-stu-id="78cc6-107">In the **Report Data** pane, click **New** and then click **Data Source...**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78cc6-108">Si le volet **Données du rapport** n’est pas visible, cliquez sur **Données du rapport** dans le menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="78cc6-108">If the **Report Data** pane is not visible, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="78cc6-109">Dans **Nom**, tapez [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78cc6-109">In **Name**, type [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)].</span></span>  
  
3.  <span data-ttu-id="78cc6-110">Vérifiez que l’option **Connexion incorporée** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="78cc6-110">Make sure **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="78cc6-111">Dans **Type**, sélectionnez **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="78cc6-111">In **Type**, select **Microsoft SQL Server**.</span></span>  
  
5.  <span data-ttu-id="78cc6-112">Dans **Chaîne de connexion**, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="78cc6-112">In **Connection string**, type the following:</span></span>  
  
    ```  
    Data source=localhost; initial catalog=AdventureWorks2012  
    ```  
  
     <span data-ttu-id="78cc6-113">Cette chaîne de connexion part du principe que [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], le serveur de rapports et la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sont tous installés sur l’ordinateur local et que vous êtes autorisé à ouvrir une session sur la base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78cc6-113">This connection string assumes that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the report server, and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database are all installed on the local computer and that you have permission to log on to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78cc6-114">Si vous utilisez [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services ou une instance nommée, la chaîne de connexion doit comporter des informations sur l'instance :</span><span class="sxs-lookup"><span data-stu-id="78cc6-114">If you are using [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services or a named instance, the connection string must include instance information:</span></span>  
    >   
    >  `Data source=localhost\SQLEXPRESS; initial catalog=AdventureWorks2012`  
    >   
    >  <span data-ttu-id="78cc6-115">Pour plus d’informations sur les chaînes de connexion, consultez [connexions de données, sources de données et chaînes de connexion dans Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) et [boîte de dialogue Propriétés de la source de données, général](data-source-properties-dialog-box-general.md).</span><span class="sxs-lookup"><span data-stu-id="78cc6-115">For more information about connection strings, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](data-connections-data-sources-and-connection-strings-in-reporting-services.md) and [Data Source Properties Dialog Box, General](data-source-properties-dialog-box-general.md).</span></span>  
  
6.  <span data-ttu-id="78cc6-116">Cliquez sur **Informations d’identification** dans le volet gauche, puis sur **Utiliser l’authentification Windows (sécurité intégrée)**.</span><span class="sxs-lookup"><span data-stu-id="78cc6-116">Click **Credentials** in the left pane and click **Use Windows Authentication (integrated security)**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="78cc6-117">la source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] de données est ajoutée au volet des **données de rapport** .</span><span class="sxs-lookup"><span data-stu-id="78cc6-117">data source [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] is added to the **Report Data** pane.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="78cc6-118">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="78cc6-118">Next Task</span></span>  
 <span data-ttu-id="78cc6-119">Vous avez défini avec succès une connexion à l’exemple de base de données [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78cc6-119">You have successfully defined a connection to the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="78cc6-120">Vous allez ensuite créer un rapport.</span><span class="sxs-lookup"><span data-stu-id="78cc6-120">Next, you will create the report.</span></span> <span data-ttu-id="78cc6-121">Consultez [Leçon 3 : Définition d’un dataset destiné à un rapport de table &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="78cc6-121">See [Lesson 3: Defining a Dataset for the Table Report &#40;Reporting Services&#41;](lesson-3-defining-a-dataset-for-the-table-report-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78cc6-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78cc6-122">See Also</span></span>  
 [<span data-ttu-id="78cc6-123">Connexions de données, sources de données et chaînes de connexion dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="78cc6-123">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
