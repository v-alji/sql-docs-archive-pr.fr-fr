---
title: Créer la stratégie Nom financier | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601411"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="04ffe-102">Créer la stratégie Nom financier</span><span class="sxs-lookup"><span data-stu-id="04ffe-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="04ffe-103"> Dans cette tâche, vous allez créer une base de données nommée Finance, puis créer une condition qui exige que toutes les tables commencent par les lettres **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="04ffe-104">Ensuite, vous allez créer une stratégie et une catégorie de stratégies afin d'appliquer une norme d'affectation de noms pour les tables dans la base de données Finance.</span><span class="sxs-lookup"><span data-stu-id="04ffe-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="04ffe-105">Pour créer la base de données Finance</span><span class="sxs-lookup"><span data-stu-id="04ffe-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="04ffe-106">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ouvrez une fenêtre de requête et exécutez l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="04ffe-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="04ffe-107">Dans l’Explorateur d’objets, cliquez sur **Bases de données**, puis appuyez sur la touche F5 pour actualiser la liste de bases de données.</span><span class="sxs-lookup"><span data-stu-id="04ffe-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="04ffe-108">Pour créer la condition Tables de finance</span><span class="sxs-lookup"><span data-stu-id="04ffe-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="04ffe-109">Dans l’Explorateur d’objets, développez **Gestion**, **Gestion de la stratégie**, cliquez avec le bouton droit sur **Conditions**, puis cliquez sur **Nouvelle condition**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="04ffe-110">Dans la boîte de dialogue **Créer une nouvelle condition** , dans la zone **Nom** , tapez **Tables de finance**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="04ffe-111">Dans la liste **Facette** , sélectionnez **Nom en plusieurs parties**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="04ffe-112">Dans la zone **expression** , dans la **zone champ** , sélectionnez \*\* \@ Name\*\*. dans la zone **opérateur** , sélectionnez **Like**; et dans la zone **valeur** , tapez **'fintbl% '** pour forcer tous les noms de tables à commencer par les lettres **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="04ffe-113">Dans la page **Description** , tapez **Les noms des tables de finance doivent commencer par fintbl**, puis cliquez sur **OK** pour créer la condition.</span><span class="sxs-lookup"><span data-stu-id="04ffe-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="04ffe-114">Pour créer la stratégie Nom financier</span><span class="sxs-lookup"><span data-stu-id="04ffe-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="04ffe-115">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur **Stratégies**, puis cliquez sur **Nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="04ffe-116">Dans la boîte de dialogue **Créer une nouvelle stratégie** , dans la zone **Nom** , tapez **Nom financier**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="04ffe-117">Dans la liste **Vérifier la condition** , sélectionnez **Tables de finance**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="04ffe-118">Cette zone se trouve dans la zone **Nom en plusieurs parties** .</span><span class="sxs-lookup"><span data-stu-id="04ffe-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="04ffe-119">Dans la zone **Par rapport à** est affichée une liste des objets de base de données qui pourraient appliquer cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="04ffe-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="04ffe-120">Cochez la case **Toutes les tables**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="04ffe-121">Dans la zone **Toutes les bases de données** , développez **Toutes les**, puis cliquez sur **Nouvelle condition**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="04ffe-122">Dans la boîte de dialogue **Créer une nouvelle condition** , dans la zone **Nom** , tapez **Base de données de finance**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="04ffe-123">Dans la zone **expression** , complétez l’expression pour inclure \*\* \@ Name = « finance »\*\*, puis cliquez sur **OK** pour fermer la page de condition.</span><span class="sxs-lookup"><span data-stu-id="04ffe-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="04ffe-124">Vous devrez peut-être quitter la zone **Valeur** pour activer le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="04ffe-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="04ffe-125">Dans la liste **Mode d’évaluation** , sélectionnez **Sur modification : empêcher**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="04ffe-126">Cela applique la stratégie en créant un déclencheur de base de données sur la base de données Finance.</span><span class="sxs-lookup"><span data-stu-id="04ffe-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="04ffe-127">Sélectionnez la liste **Activé** .</span><span class="sxs-lookup"><span data-stu-id="04ffe-127">Select the **Enabled** list.</span></span> <span data-ttu-id="04ffe-128">(La case **Activé** ne s’applique pas aux stratégies **À la demande** .)</span><span class="sxs-lookup"><span data-stu-id="04ffe-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="04ffe-129">Dans la liste **Restriction sur le serveur** , sélectionnez **Aucune**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="04ffe-130">Pour créer la catégorie de stratégies Finance</span><span class="sxs-lookup"><span data-stu-id="04ffe-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="04ffe-131">Dans l’Explorateur d’objets, développez **Gestion**, cliquez avec le bouton droit sur **Gestion de la stratégie**, puis cliquez sur **Gérer les catégories**.</span><span class="sxs-lookup"><span data-stu-id="04ffe-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="04ffe-132">Dans la boîte de dialogue **gérer les catégories de stratégie** , sous **nom**, tapez `Finance` dans la zone vide, puis désactivez **abonnements à la base de données**autorisée.</span><span class="sxs-lookup"><span data-stu-id="04ffe-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="04ffe-133">**Abonnements à la base de données autorisée** force chaque base de données de l’instance à s’abonner aux stratégies appartenant à cette catégorie de stratégie.</span><span class="sxs-lookup"><span data-stu-id="04ffe-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="04ffe-134">Dans le cadre de cette leçon, seule la base de données Finance doit s'abonner à la stratégie Nom financier.</span><span class="sxs-lookup"><span data-stu-id="04ffe-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="04ffe-135">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="04ffe-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="04ffe-136">Vérifier et s'abonner à la stratégie Nom financier</span><span class="sxs-lookup"><span data-stu-id="04ffe-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
