---
title: Vérifier et s’abonner à la stratégie Nom financier | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600841"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="12253-102">Vérifier et s'abonner à la stratégie Nom financier</span><span class="sxs-lookup"><span data-stu-id="12253-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="12253-103">Dans cette tâche, vous allez configurer la base de données Finance de manière à l'abonner à la catégorie de stratégies Finance.</span><span class="sxs-lookup"><span data-stu-id="12253-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="12253-104">Ensuite, vous allez tester la stratégie Nom financier.</span><span class="sxs-lookup"><span data-stu-id="12253-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="12253-105">Pour abonner la base de données à la catégorie de stratégies Finance</span><span class="sxs-lookup"><span data-stu-id="12253-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="12253-106">Dans l’Explorateur d’objets, développez **bases de données**, cliquez avec le bouton droit `Finance` , pointez sur **stratégies**, puis cliquez sur **catégories**.</span><span class="sxs-lookup"><span data-stu-id="12253-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="12253-107">Activez la case à cocher **abonné** pour la `Finance` catégorie.</span><span class="sxs-lookup"><span data-stu-id="12253-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="12253-108">Pour tester l'application de la stratégie Nom financier</span><span class="sxs-lookup"><span data-stu-id="12253-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="12253-109">Dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], ouvrez une fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="12253-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="12253-110">Exécutez les instructions suivantes qui essaient de créer une table qui enfreint la stratégie **Nom financier** .</span><span class="sxs-lookup"><span data-stu-id="12253-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="12253-111">La table enfreint la stratégie car le nom de table ne commence pas par les lettres **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="12253-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="12253-112">Remarquez que la stratégie empêche la création de la table et retourne un message d'information qui indique le nom de la stratégie.</span><span class="sxs-lookup"><span data-stu-id="12253-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="12253-113">Pour fournir un nom valide, modifiez le code comme suit et réexécutez l'instruction.</span><span class="sxs-lookup"><span data-stu-id="12253-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="12253-114">Cette fois-ci, la table est créée.</span><span class="sxs-lookup"><span data-stu-id="12253-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="12253-115">Pour appliquer la stratégie à tout le serveur</span><span class="sxs-lookup"><span data-stu-id="12253-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="12253-116">Actuellement, seule la base de données Finance est abonnée à la catégorie de stratégie Finance.</span><span class="sxs-lookup"><span data-stu-id="12253-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="12253-117">Dans de nombreux cas, il est plus facile d'appliquer la catégorie de stratégie à l'ensemble du serveur.</span><span class="sxs-lookup"><span data-stu-id="12253-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="12253-118">Dans l’Explorateur d’objets, développez **Gestion**, cliquez avec le bouton droit sur **Gestion de la stratégie**, puis cliquez sur **Gérer les catégories**.</span><span class="sxs-lookup"><span data-stu-id="12253-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="12253-119">Dans la boîte de dialogue **Administration des catégories de stratégie** , recherchez la catégorie Finance et cochez la case **Abonnements à la base de données autorisée** pour la catégorie Finance.</span><span class="sxs-lookup"><span data-stu-id="12253-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="12253-120">Désormais, la catégorie Finance s’applique à toutes les bases de données, mais la condition que vous avez créée restreint la stratégie Nom financier à la base de données Finance.</span><span class="sxs-lookup"><span data-stu-id="12253-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="12253-121">Cela démontre la manière dont vous pouvez utiliser des combinaisons de conditions complexes pour cibler des stratégies pour une application correcte sur de nombreux serveurs.</span><span class="sxs-lookup"><span data-stu-id="12253-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="12253-122">Récapitulatif</span><span class="sxs-lookup"><span data-stu-id="12253-122">Summary</span></span>  
 <span data-ttu-id="12253-123">Ce didacticiel vous a montré comment créer des conditions, des stratégies et des groupes de stratégies de la Gestion basée sur des stratégies et comment appliquer des filtres et vérifier la conformité des cibles de la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="12253-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="12253-124">Suivant</span><span class="sxs-lookup"><span data-stu-id="12253-124">Next</span></span>  
 <span data-ttu-id="12253-125">Ce didacticiel est terminé.</span><span class="sxs-lookup"><span data-stu-id="12253-125">This tutorial is finished.</span></span> <span data-ttu-id="12253-126">Pour revenir au début, cliquez sur [Didacticiel : Administration de serveurs à l’aide de la Gestion basée sur des stratégies](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="12253-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="12253-127">Pour obtenir la liste des didacticiels, consultez [les didacticiels pour SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="12253-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12253-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12253-128">See Also</span></span>  
 [<span data-ttu-id="12253-129">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="12253-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
