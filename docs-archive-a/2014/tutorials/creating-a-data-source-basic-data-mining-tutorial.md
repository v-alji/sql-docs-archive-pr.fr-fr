---
title: Création d’une source de données (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603738"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="e1673-102">Création d'une source de données (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="e1673-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="e1673-103">Une *source de données* est une connexion de données qui est enregistrée et gérée dans votre projet et déployée dans votre [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="e1673-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="e1673-104">La source de données contient les noms du serveur et de la base de données où vos données sources résident, en plus des éventuelles propriétés de connexion requises.</span><span class="sxs-lookup"><span data-stu-id="e1673-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e1673-105">Le nom de la base de données est [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1673-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="e1673-106">Si vous n’avez pas encore installé cette base de données, consultez la page [exemples de bases de données Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .</span><span class="sxs-lookup"><span data-stu-id="e1673-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="e1673-107">Pour créer une source de données</span><span class="sxs-lookup"><span data-stu-id="e1673-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="e1673-108">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur le dossier **sources de données** et sélectionnez **nouvelle source de données**.</span><span class="sxs-lookup"><span data-stu-id="e1673-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="e1673-109">Sur la page **Bienvenue dans l'Assistant Sources de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1673-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="e1673-110">Sur la page **Sélectionner la méthode de définition de la connexion** , cliquez sur **nouveau** pour ajouter une connexion à la [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="e1673-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="e1673-111">Dans la liste **fournisseur** du **Gestionnaire de connexions**, sélectionnez **Native OLE DB\SQL Server Native Client 11,0**.</span><span class="sxs-lookup"><span data-stu-id="e1673-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="e1673-112">Dans la zone **nom du serveur** , tapez ou sélectionnez le nom du serveur sur lequel vous avez installé [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e1673-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="e1673-113">Par exemple, tapez **localhost** si la base de données est hébergée sur le serveur local.</span><span class="sxs-lookup"><span data-stu-id="e1673-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="e1673-114">Dans le **Journal sur le** groupe de serveurs, sélectionnez **utiliser l’authentification Windows**.</span><span class="sxs-lookup"><span data-stu-id="e1673-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e1673-115">Dans la mesure du possible, les implémenteurs doivent utiliser l'authentification Windows car elle fournit une méthode d'authentification plus sécurisée que l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1673-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="e1673-116">Cependant, l'authentification SQL Server est fournie dans le but d'assurer la compatibilité ascendante.</span><span class="sxs-lookup"><span data-stu-id="e1673-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="e1673-117">Pour plus d’informations sur les méthodes d’authentification, consultez [configuration de moteur de base de données-approvisionnement de comptes](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="e1673-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="e1673-118">Dans la liste **Sélectionner ou entrer un nom de base de données** , sélectionnez, [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1673-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e1673-119">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1673-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="e1673-120">Sur la page **informations d’emprunt d’identité** , cliquez sur **utiliser le compte de service**, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e1673-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="e1673-121">Dans la page **fin de l’Assistant** , Notez que, par défaut, la source de données est nommée Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="e1673-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="e1673-122">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="e1673-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="e1673-123">La nouvelle source de données, Adventure Works DW 2012, apparaît dans le dossier **sources de données** de Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="e1673-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e1673-124">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="e1673-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e1673-125">Création d’une vue de source de données &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="e1673-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="e1673-126">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="e1673-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="e1673-127">Création d’un projet Analysis Services &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="e1673-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1673-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1673-128">See Also</span></span>  
 <span data-ttu-id="e1673-129">[Créer une source de données &#40;SSAS multidimensionnel&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="e1673-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="e1673-130">[Définition d’une source de données](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="e1673-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="e1673-131">Définir les options d’emprunt d’identité &#40;SSAS - Multidimensionnel&#41;</span><span class="sxs-lookup"><span data-stu-id="e1673-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
