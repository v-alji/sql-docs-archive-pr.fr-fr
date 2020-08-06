---
title: 'Tâche 6 : vérifier que l’attribut basé sur un domaine est créé à l’aide de la Data Manager maître | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6e90517a-910c-4c33-8f11-92ac3cff4fdc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ea26202ca9e607058b1e385957be3ea3d04038b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600383"
---
# <a name="task-6-verify-that-the-domain-based-attribute-is-created-using-master-data-manager"></a><span data-ttu-id="3c873-102">Tâche 6 : Tâche 6 : Vérification que l’attribut basé sur un domaine est créé à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="3c873-102">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>
  <span data-ttu-id="3c873-103">Dans cette tâche, vous allez vérifier que l’entité **État** est créée dans **MDS** et que l’attribut **État** de l’entité **Fournisseur** est un attribut basé sur un domaine qui dépend de l’entité **État** à l’aide de **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="3c873-103">In this task, you verify that the **State** entity is created in **MDS** and the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on the **State** entity by using **Master Data Manager**.</span></span>

1.  <span data-ttu-id="3c873-104">Basculez vers l’application web **Master Data Manger**.</span><span class="sxs-lookup"><span data-stu-id="3c873-104">Switch to the **Master Data Manger** web application.</span></span>

2.  <span data-ttu-id="3c873-105">Cliquez sur **SQL Server 2012 Master Data Services** en haut pour accéder à la page d’accueil.</span><span class="sxs-lookup"><span data-stu-id="3c873-105">Click **SQL Server 2012 Master Data Services** at the top to get to the home page.</span></span>

3.  <span data-ttu-id="3c873-106">Vérifiez que le modèle **Fournisseurs** est sélectionné et cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="3c873-106">Ensure that **Suppliers** model is selected and click **Explorer**.</span></span> <span data-ttu-id="3c873-107">Vous pouvez actualiser la page si **l’Explorateur** est déjà ouvert.</span><span class="sxs-lookup"><span data-stu-id="3c873-107">You could refresh the page if you already had **Explorer** open.</span></span>

4.  <span data-ttu-id="3c873-108">Pointez votre souris sur **Entités** dans la barre de menus et notez qu’il y a maintenant deux entités : **Fournisseur** et **État**.</span><span class="sxs-lookup"><span data-stu-id="3c873-108">Hover your mouse over **Entities** on the menu bar and notice that now there are two entities: **Supplier** and **State**.</span></span>

     <span data-ttu-id="3c873-109">![Menu Entités avec État et Fournisseur](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Menu Entités avec État et Fournisseur")</span><span class="sxs-lookup"><span data-stu-id="3c873-109">![Entities Menu with State and Supplier](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-01.jpg "Entities Menu with State and Supplier")</span></span>

5.  <span data-ttu-id="3c873-110">Cliquez sur **État** si l’entité n’est pas déjà ouverte.</span><span class="sxs-lookup"><span data-stu-id="3c873-110">Click **State** if the entity is not open already.</span></span>

6.  <span data-ttu-id="3c873-111">Sélectionnez **GA** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3c873-111">Select **GA** from the list.</span></span>

7.  <span data-ttu-id="3c873-112">Dans le volet **Détails** à droite, remplacez le **Nom** par **Géorgie** dans le **volet droit**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c873-112">In the **Details** pane to the right, change the **Name** to **Georgia** in the **right pane**, and click **OK**.</span></span>

8.  <span data-ttu-id="3c873-113">Répétez les étapes précédentes pour les autres États.</span><span class="sxs-lookup"><span data-stu-id="3c873-113">Repeat the previous steps for other states.</span></span>

    |<span data-ttu-id="3c873-114">Code</span><span class="sxs-lookup"><span data-stu-id="3c873-114">Code</span></span>|<span data-ttu-id="3c873-115">Nom</span><span class="sxs-lookup"><span data-stu-id="3c873-115">Name</span></span>|
    |----------|----------|
    |<span data-ttu-id="3c873-116">CA</span><span class="sxs-lookup"><span data-stu-id="3c873-116">CA</span></span>|<span data-ttu-id="3c873-117">Californie</span><span class="sxs-lookup"><span data-stu-id="3c873-117">California</span></span>|
    |<span data-ttu-id="3c873-118">CO</span><span class="sxs-lookup"><span data-stu-id="3c873-118">CO</span></span>|<span data-ttu-id="3c873-119">Colorado</span><span class="sxs-lookup"><span data-stu-id="3c873-119">Colorado</span></span>|
    |<span data-ttu-id="3c873-120">IL</span><span class="sxs-lookup"><span data-stu-id="3c873-120">IL</span></span>|<span data-ttu-id="3c873-121">Illinois</span><span class="sxs-lookup"><span data-stu-id="3c873-121">Illinois</span></span>|
    |<span data-ttu-id="3c873-122">DC</span><span class="sxs-lookup"><span data-stu-id="3c873-122">DC</span></span>|<span data-ttu-id="3c873-123">District de Columbia</span><span class="sxs-lookup"><span data-stu-id="3c873-123">District of Columbia</span></span>|
    |<span data-ttu-id="3c873-124">FL</span><span class="sxs-lookup"><span data-stu-id="3c873-124">FL</span></span>|<span data-ttu-id="3c873-125">Floride</span><span class="sxs-lookup"><span data-stu-id="3c873-125">Florida</span></span>|
    |<span data-ttu-id="3c873-126">AL</span><span class="sxs-lookup"><span data-stu-id="3c873-126">AL</span></span>|<span data-ttu-id="3c873-127">Alabama</span><span class="sxs-lookup"><span data-stu-id="3c873-127">Alabama</span></span>|
    |<span data-ttu-id="3c873-128">KY</span><span class="sxs-lookup"><span data-stu-id="3c873-128">KY</span></span>|<span data-ttu-id="3c873-129">Kentucky</span><span class="sxs-lookup"><span data-stu-id="3c873-129">Kentucky</span></span>|
    |<span data-ttu-id="3c873-130">MA</span><span class="sxs-lookup"><span data-stu-id="3c873-130">MA</span></span>|<span data-ttu-id="3c873-131">Massachusetts</span><span class="sxs-lookup"><span data-stu-id="3c873-131">Massachusetts</span></span>|
    |<span data-ttu-id="3c873-132">AZ</span><span class="sxs-lookup"><span data-stu-id="3c873-132">AZ</span></span>|<span data-ttu-id="3c873-133">Arizona</span><span class="sxs-lookup"><span data-stu-id="3c873-133">Arizona</span></span>|
    |<span data-ttu-id="3c873-134">MI</span><span class="sxs-lookup"><span data-stu-id="3c873-134">MI</span></span>|<span data-ttu-id="3c873-135">Michigan</span><span class="sxs-lookup"><span data-stu-id="3c873-135">Michigan</span></span>|
    |<span data-ttu-id="3c873-136">MN</span><span class="sxs-lookup"><span data-stu-id="3c873-136">MN</span></span>|<span data-ttu-id="3c873-137">Minnesota</span><span class="sxs-lookup"><span data-stu-id="3c873-137">Minnesota</span></span>|
    |<span data-ttu-id="3c873-138">NJ</span><span class="sxs-lookup"><span data-stu-id="3c873-138">NJ</span></span>|<span data-ttu-id="3c873-139">New Jersey</span><span class="sxs-lookup"><span data-stu-id="3c873-139">New Jersey</span></span>|
    |<span data-ttu-id="3c873-140">NV</span><span class="sxs-lookup"><span data-stu-id="3c873-140">NV</span></span>|<span data-ttu-id="3c873-141">Nevada</span><span class="sxs-lookup"><span data-stu-id="3c873-141">Nevada</span></span>|
    |<span data-ttu-id="3c873-142">NY</span><span class="sxs-lookup"><span data-stu-id="3c873-142">NY</span></span>|<span data-ttu-id="3c873-143">New York</span><span class="sxs-lookup"><span data-stu-id="3c873-143">New York</span></span>|
    |<span data-ttu-id="3c873-144">OH</span><span class="sxs-lookup"><span data-stu-id="3c873-144">OH</span></span>|<span data-ttu-id="3c873-145">Ohio</span><span class="sxs-lookup"><span data-stu-id="3c873-145">Ohio</span></span>|
    |<span data-ttu-id="3c873-146">OK</span><span class="sxs-lookup"><span data-stu-id="3c873-146">OK</span></span>|<span data-ttu-id="3c873-147">Oklahoma</span><span class="sxs-lookup"><span data-stu-id="3c873-147">Oklahoma</span></span>|
    |<span data-ttu-id="3c873-148">OU</span><span class="sxs-lookup"><span data-stu-id="3c873-148">OR</span></span>|<span data-ttu-id="3c873-149">Oregon</span><span class="sxs-lookup"><span data-stu-id="3c873-149">Oregon</span></span>|
    |<span data-ttu-id="3c873-150">PA</span><span class="sxs-lookup"><span data-stu-id="3c873-150">PA</span></span>|<span data-ttu-id="3c873-151">Pennsylvanie</span><span class="sxs-lookup"><span data-stu-id="3c873-151">Pennsylvania</span></span>|
    |<span data-ttu-id="3c873-152">SC</span><span class="sxs-lookup"><span data-stu-id="3c873-152">SC</span></span>|<span data-ttu-id="3c873-153">Caroline du Sud</span><span class="sxs-lookup"><span data-stu-id="3c873-153">South Carolina</span></span>|
    |<span data-ttu-id="3c873-154">KS</span><span class="sxs-lookup"><span data-stu-id="3c873-154">KS</span></span>|<span data-ttu-id="3c873-155">Kansas</span><span class="sxs-lookup"><span data-stu-id="3c873-155">Kansas</span></span>|
    |<span data-ttu-id="3c873-156">TN</span><span class="sxs-lookup"><span data-stu-id="3c873-156">TN</span></span>|<span data-ttu-id="3c873-157">Tennessee</span><span class="sxs-lookup"><span data-stu-id="3c873-157">Tennessee</span></span>|
    |<span data-ttu-id="3c873-158">TX</span><span class="sxs-lookup"><span data-stu-id="3c873-158">TX</span></span>|<span data-ttu-id="3c873-159">Texas</span><span class="sxs-lookup"><span data-stu-id="3c873-159">Texas</span></span>|
    |<span data-ttu-id="3c873-160">UT</span><span class="sxs-lookup"><span data-stu-id="3c873-160">UT</span></span>|<span data-ttu-id="3c873-161">Utah</span><span class="sxs-lookup"><span data-stu-id="3c873-161">Utah</span></span>|
    |<span data-ttu-id="3c873-162">VA</span><span class="sxs-lookup"><span data-stu-id="3c873-162">VA</span></span>|<span data-ttu-id="3c873-163">Virginie</span><span class="sxs-lookup"><span data-stu-id="3c873-163">Virginia</span></span>|
    |<span data-ttu-id="3c873-164">WA</span><span class="sxs-lookup"><span data-stu-id="3c873-164">WA</span></span>|<span data-ttu-id="3c873-165">Washington</span><span class="sxs-lookup"><span data-stu-id="3c873-165">Washington</span></span>|
    |<span data-ttu-id="3c873-166">WI</span><span class="sxs-lookup"><span data-stu-id="3c873-166">WI</span></span>|<span data-ttu-id="3c873-167">Wisconsin</span><span class="sxs-lookup"><span data-stu-id="3c873-167">Wisconsin</span></span>|
    |<span data-ttu-id="3c873-168">HI</span><span class="sxs-lookup"><span data-stu-id="3c873-168">HI</span></span>|<span data-ttu-id="3c873-169">Hawaii</span><span class="sxs-lookup"><span data-stu-id="3c873-169">Hawaii</span></span>|
    |<span data-ttu-id="3c873-170">MD</span><span class="sxs-lookup"><span data-stu-id="3c873-170">MD</span></span>|<span data-ttu-id="3c873-171">Maryland</span><span class="sxs-lookup"><span data-stu-id="3c873-171">Maryland</span></span>|
    |<span data-ttu-id="3c873-172">CT</span><span class="sxs-lookup"><span data-stu-id="3c873-172">CT</span></span>|<span data-ttu-id="3c873-173">Connecticut</span><span class="sxs-lookup"><span data-stu-id="3c873-173">Connecticut</span></span>|

9. <span data-ttu-id="3c873-174">Sélectionnez l’une des entrées d’État et cliquez sur **Afficher les transactions** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="3c873-174">Select any of the state entries and click **View Transactions** from the Toolbar.</span></span> <span data-ttu-id="3c873-175">Vous devriez voir la transaction que vous venez de mettre à jour dans la liste des transactions.</span><span class="sxs-lookup"><span data-stu-id="3c873-175">You should see the transaction for the update you just made is in the list of transactions.</span></span>

10. <span data-ttu-id="3c873-176">Pointez la souris sur **Entités** dans le menu et cliquez sur **Fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="3c873-176">Hover the mouse over **Entities** menu and click **Supplier**.</span></span>

11. <span data-ttu-id="3c873-177">Maintenant, notez qu’une valeur du champ **État** peut être modifiée dans le volet **Détails** à l’aide de la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3c873-177">Now, notice that a value for the **State** field can be changed in the **Details** pane by using the drop-down list.</span></span> <span data-ttu-id="3c873-178">Remarquez également que, dans la liste à gauche et dans la liste déroulante du volet **Détails**, le code est affiché en premier, suivi par le nom entre accolades.</span><span class="sxs-lookup"><span data-stu-id="3c873-178">You can also see that, in the list to the left and in the drop-down list in the **Details** pane, code is displayed first and then the name in curly braces.</span></span> <span data-ttu-id="3c873-179">Vous pouvez également modifier d’autres valeurs dans le volet **Détails**.</span><span class="sxs-lookup"><span data-stu-id="3c873-179">You can also change any other value in the **Details** pane.</span></span>

     <span data-ttu-id="3c873-180">![Attribute d'état avec codes et noms mis au jour](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "Attribute d'état avec codes et noms mis au jour")</span><span class="sxs-lookup"><span data-stu-id="3c873-180">![State Attribute with Updated Code and Names](../../2014/tutorials/media/et-verifythatthedbaiscreatedusingmdm-02.jpg "State Attribute with Updated Code and Names")</span></span>

## <a name="next-step"></a><span data-ttu-id="3c873-181">étape suivante</span><span class="sxs-lookup"><span data-stu-id="3c873-181">Next Step</span></span>
 [<span data-ttu-id="3c873-182">Tâche 7 : Affichage des mises à jour effectuées à l’aide de Master Data Manager dans Excel</span><span class="sxs-lookup"><span data-stu-id="3c873-182">Task 7: Viewing Updates Made using Master Data Manager in Excel</span></span>](../../2014/tutorials/task-7-viewing-updates-made-using-master-data-manager-in-excel.md)


