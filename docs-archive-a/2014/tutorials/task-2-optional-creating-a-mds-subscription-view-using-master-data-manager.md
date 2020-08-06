---
title: 'Tâche 2 (facultatif) : création d’une vue d’abonnement MDS à l’aide du Data Manager maître | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704431"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="a1008-102">Tâche 2 (facultatif) : Création d’une vue d’abonnement MDS à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="a1008-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="a1008-103">Dans cette tâche, vous allez créer une vue d’abonnement pour exposer l’entité **fournisseur** du modèle **fournisseurs** à d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="a1008-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="a1008-104">Vous n'allez pas utiliser cette vue dans cette version du didacticiel.</span><span class="sxs-lookup"><span data-stu-id="a1008-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="a1008-105">Basculez vers la page principale du **Data Manager maître** ( `http://localhost/MDS` ) en cliquant sur **SQL Server Master Data Services 2012** en haut.</span><span class="sxs-lookup"><span data-stu-id="a1008-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="a1008-106">Cliquez sur gestion de l' **intégration**.</span><span class="sxs-lookup"><span data-stu-id="a1008-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="a1008-107">Dans la barre de menus, cliquez sur **créer des vues** .</span><span class="sxs-lookup"><span data-stu-id="a1008-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="a1008-108">![Bouton Ajouter une nouvelle vue d'abonnement](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Bouton Ajouter une nouvelle vue d'abonnement")</span><span class="sxs-lookup"><span data-stu-id="a1008-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="a1008-109">Cliquez sur l’icône **+ (plus)** dans la barre d’outils pour créer une vue d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="a1008-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="a1008-110">Dans le volet **créer une vue d’abonnement** , tapez **Suppliers** pour nom de la **vue d’abonnement**.</span><span class="sxs-lookup"><span data-stu-id="a1008-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="a1008-111">Sélectionnez **Suppliers** pour **Model**.</span><span class="sxs-lookup"><span data-stu-id="a1008-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="a1008-112">Sélectionnez **Version_1** pour **version**.</span><span class="sxs-lookup"><span data-stu-id="a1008-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="a1008-113">Sélectionnez **fournisseur** pour **entité**.</span><span class="sxs-lookup"><span data-stu-id="a1008-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="a1008-114">Sélectionnez **les membres feuille** pour le **format**.</span><span class="sxs-lookup"><span data-stu-id="a1008-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="a1008-115">![Bouton Enregistrer vue d'abonnement](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Bouton Enregistrer vue d'abonnement")</span><span class="sxs-lookup"><span data-stu-id="a1008-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="a1008-116">Cliquez sur **Enregistrer** dans la barre d’outils pour enregistrer la vue d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="a1008-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="a1008-117">Cette action crée une vue dans SQL Server **fournisseurs**nommés.</span><span class="sxs-lookup"><span data-stu-id="a1008-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="a1008-118">Vous pouvez vérifier cela à l'aide de SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="a1008-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="a1008-119">étape suivante</span><span class="sxs-lookup"><span data-stu-id="a1008-119">Next Step</span></span>  
 [<span data-ttu-id="a1008-120">Tâche 3 &#40;&#41; facultative : examen des vues d’abonnement</span><span class="sxs-lookup"><span data-stu-id="a1008-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
