---
title: 'Leçon 1 : création d’un exemple de base de données de l’abonné | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 47a882b7-efe5-4ee6-bef4-06118eb56903
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6ee49f0858b28c0c4b00fd391b0db7b4d2c54b16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710271"
---
# <a name="lesson-1-creating-a-sample-subscriber-database"></a><span data-ttu-id="3150b-102">Leçon 1 : Création d'un exemple de base de données de l'abonné</span><span class="sxs-lookup"><span data-stu-id="3150b-102">Lesson 1: Creating a Sample Subscriber Database</span></span>
  <span data-ttu-id="3150b-103">Avant de pouvoir définir un abonnement piloté par les données, vous devez disposer d'une source de données qui fournit les données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="3150b-103">Before you can define a data-driven subscription, you must have a data source that provides subscription data.</span></span> <span data-ttu-id="3150b-104">Au cours de cette étape, vous allez créer une petite base de données pour y stocker les données d'abonnement qui seront utilisées dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="3150b-104">In this step, you will create a small database to store the subscription data used in this tutorial.</span></span> <span data-ttu-id="3150b-105">Ensuite, une fois l'abonnement traité, le serveur de rapports extrait ces données et les utilise pour personnaliser le résultat du rapport, les options de remise et le format de présentation du rapport.</span><span class="sxs-lookup"><span data-stu-id="3150b-105">Later, when the subscription is processed, the report server retrieves this data and uses it to customize report output, delivery options, and report presentation format.</span></span>  
  
 <span data-ttu-id="3150b-106">Cette leçon suppose que vous utilisez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] pour créer une [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="3150b-106">This lesson assumes you are using [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to create a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span>  
  
### <a name="to-create-a-sample-subscriber-database"></a><span data-ttu-id="3150b-107">Pour créer une base de données d'abonnés exemple</span><span class="sxs-lookup"><span data-stu-id="3150b-107">To create a sample Subscriber database</span></span>  
  
1.  <span data-ttu-id="3150b-108">Démarrez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], puis ouvrez une connexion à un [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3150b-108">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and open a connection to a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3150b-109">Cliquez avec le bouton droit sur Bases de données, puis sélectionnez **Nouvelle base de données**.</span><span class="sxs-lookup"><span data-stu-id="3150b-109">Right-click on Databases, select **New Database...**.</span></span>  
  
3.  <span data-ttu-id="3150b-110">Dans la boîte de dialogue nouvelle base de données, dans nom de la base de données, tapez *abonnés*.</span><span class="sxs-lookup"><span data-stu-id="3150b-110">In the New Database dialog box, in Database Name, type *Subscribers*.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="3150b-111">Cliquez sur le bouton **Nouvelle requête** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="3150b-111">Click the **New Query** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="3150b-112">Copiez les instructions [!INCLUDE[tsql](../includes/tsql-md.md)] suivantes dans la requête vide :</span><span class="sxs-lookup"><span data-stu-id="3150b-112">Copy the following [!INCLUDE[tsql](../includes/tsql-md.md)] statements into the empty query:</span></span>  
  
    ```  
    Use Subscribers  
    CREATE TABLE [dbo].[OrderInfo] (  
        [SubscriptionID] [int] NOT NULL PRIMARY KEY ,  
        [Order] [nvarchar] (20) NOT NULL,  
        [FileType] [bit],  
        [Format] [nvarchar] (20) NOT NULL ,  
    ) ON [PRIMARY]  
    GO  
  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('1', 'so43659', '1', 'IMAGE')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('2', 'so43664', '1', 'MHTML')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('3', 'so43668', '1', 'PDF')  
    INSERT INTO [dbo].[OrderInfo] (SubscriptionID, [Order], FileType, Format)   
    VALUES ('4', 'so71949', '1', 'Excel')  
    GO  
    ```  
  
6.  <span data-ttu-id="3150b-113">Cliquez sur **! Exécuter** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="3150b-113">Click **! Execute** on the toolbar.</span></span>  
  
7.  <span data-ttu-id="3150b-114">Utilisez une instruction SELECT pour vérifier que votre table comporte bien trois lignes de données.</span><span class="sxs-lookup"><span data-stu-id="3150b-114">Use a SELECT statement to verify that you have three rows of data.</span></span> <span data-ttu-id="3150b-115">Par exemple : `select * from OrderInfo`</span><span class="sxs-lookup"><span data-stu-id="3150b-115">For example: `select * from OrderInfo`</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3150b-116">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="3150b-116">Next Steps</span></span>  
 <span data-ttu-id="3150b-117">Vous avez créé les données d'abonnement sur lesquelles seront basées la distribution des rapports et en fonction desquelles les résultats des rapports varieront pour chaque abonné.</span><span class="sxs-lookup"><span data-stu-id="3150b-117">You have successfully created the subscription data that will drive report distribution and vary the report output for each subscriber.</span></span> <span data-ttu-id="3150b-118">Ensuite, vous allez modifier les propriétés de la source de données du rapport que vous distribuerez aux abonnés.</span><span class="sxs-lookup"><span data-stu-id="3150b-118">Next, you will modify the data source properties of the report you will distribute to subscribers.</span></span> <span data-ttu-id="3150b-119">La modification des propriétés de la source de données est destinée à préparer le rapport pour la remise de l'abonnement piloté par les données.</span><span class="sxs-lookup"><span data-stu-id="3150b-119">Modifying the data source properties is done to prepare the report for data-driven subscription delivery.</span></span> <span data-ttu-id="3150b-120">Vous allez également modifier la conception du rapport afin d'inclure un paramètre que l'abonnement utilisera avec les données d'abonné.</span><span class="sxs-lookup"><span data-stu-id="3150b-120">You will also modify the report design to include a parameter that the subscription will use with the subscriber data.</span></span> <span data-ttu-id="3150b-121">[Leçon 2 : modification des propriétés de la source de données du rapport](lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3150b-121">[Lesson 2: Modifying the Report Data Source Properties](lesson-2-modifying-the-report-data-source-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3150b-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3150b-122">See Also</span></span>  
 <span data-ttu-id="3150b-123">[Créer un abonnement piloté par les données &#40;didacticiel SSRS&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="3150b-123">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="3150b-124">[Créer une base de données](../relational-databases/databases/create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="3150b-124">[Create a Database](../relational-databases/databases/create-a-database.md) </span></span>  
 [<span data-ttu-id="3150b-125">Créer un rapport de tableau de base &#40;Didacticiel SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3150b-125">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
