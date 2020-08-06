---
title: Utilisation de System. transactions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TransactionScope class
- Dispose method
- System.Transactions namespace
ms.assetid: 79656ce5-ce46-4c5e-9540-cf9869bd774b
author: rothja
ms.author: jroth
ms.openlocfilehash: 277edd75ea0437dc532ed5672e3c7b8a0569af8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709644"
---
# <a name="using-systemtransactions"></a><span data-ttu-id="c6dfc-102">Utilisation de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="c6dfc-102">Using System.Transactions</span></span>
  <span data-ttu-id="c6dfc-103">L'espace de noms `System.Transactions` fournit une infrastructure de transaction qui s'intègre entièrement à ADO.NET et au CLR (Common Language Runtime) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6dfc-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="c6dfc-104">La classe `System.Transactions.TransactionScope` crée un bloc de code transactionnel en inscrivant implicitement les connexions dans une transaction distribuée.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-104">The `System.Transactions.TransactionScope` class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="c6dfc-105">Vous devez appeler la méthode `Complete` à la fin du bloc de code marqué par `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-105">You must call the `Complete` method at the end of the code block marked by the `TransactionScope`.</span></span> <span data-ttu-id="c6dfc-106">La méthode `Dispose` est appelée lorsque l'exécution du programme laisse un bloc de code, ce qui provoque une interruption de la transaction si la méthode `Complete` n'est pas appelée.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-106">The `Dispose` method is invoked when program execution leaves a code block, causing the transaction to be discontinued if the `Complete` method is not called.</span></span> <span data-ttu-id="c6dfc-107">Si une exception a été levée qui provoque l'abandon de l'étendue par le code, la transaction est considérée comme supprimée.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-107">If an exception has been thrown that causes the code to leave scope, the transaction is considered to be discontinued.</span></span>  
  
 <span data-ttu-id="c6dfc-108">Nous vous recommandons d'employer un bloc `using` pour garantir que la méthode `Dispose` est appelée sur l'objet `TransactionScope` à la sortie du bloc `using`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-108">We recommend that you employ a `using` block to ensure that the `Dispose` method is called on the `TransactionScope` object when the `using` block is exited.</span></span> <span data-ttu-id="c6dfc-109">L'impossibilité de valider ou d'annuler les transactions en attente peut dégrader sérieusement les performances parce que le délai d'expiration par défaut de `TransactionScope` est une minute.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-109">Failure to commit or roll back pending transactions can seriously degrade performance because the default time-out for the `TransactionScope` is one minute.</span></span> <span data-ttu-id="c6dfc-110">Si vous n'utilisez pas une instruction `using`, vous devez effectuer tout le travail dans un bloc `Try` et appeler explicitement la méthode `Dispose` dans le bloc `Finally`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-110">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the `Dispose` method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="c6dfc-111">Si une exception se produit dans `TransactionScope`, la transaction est marquée comme non cohérente et est abandonnée.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-111">If an exception occurs within the `TransactionScope`, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="c6dfc-112">Elle est annulée quand `TransactionScope` est supprimé.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-112">It is rolled back when the `TransactionScope` is disposed.</span></span> <span data-ttu-id="c6dfc-113">Si aucune exception ne se produit, les transactions sont validées.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-113">If no exception occurs, participating transactions commit.</span></span>  
  
 <span data-ttu-id="c6dfc-114">`TransactionScope` doit être utilisé uniquement en cas d'accès des sources de données locales et distantes ou des gestionnaires de ressources externes.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-114">`TransactionScope` should be used only when local and remote data sources or external resource managers are being accessed.</span></span> <span data-ttu-id="c6dfc-115">La raison en est que `TransactionScope` provoque toujours une promotion de la transaction, même si elle n'est utilisé que dans une connexion de contexte.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-115">This is because `TransactionScope` always causes transactions to promote, even if it is being used only within a context connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6dfc-116">La classe `TransactionScope` crée par défaut une transaction avec un `System.Transactions.Transaction.IsolationLevel` ayant la valeur `Serializable`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-116">The `TransactionScope` class creates a transaction with a `System.Transactions.Transaction.IsolationLevel` of `Serializable` by default.</span></span> <span data-ttu-id="c6dfc-117">Selon votre application, vous pouvez envisager de baisser le niveau d'isolation pour éviter une contention élevée au sein de votre application.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-117">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6dfc-118">Nous vous recommandons de n'effectuer que des mises à jour, des insertions et des suppressions dans les transactions distribuées sur des serveurs distants parce qu'ils consomment d'importantes ressources de base de données.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-118">We recommend that you perform only updates, inserts, and deletes within distributed transactions against remote servers because they consume significant database resources.</span></span> <span data-ttu-id="c6dfc-119">Si l'opération est effectuée sur le serveur local, une transaction distribuée n'est pas nécessaire et une transaction locale suffit.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-119">If the operation is going to be performed on the local server, a distributed transaction is not necessary and a local transaction will suffice.</span></span> <span data-ttu-id="c6dfc-120">Les instructions SELECT peuvent verrouiller les ressources de base de données inutilement et, dans certains scénarios, il peut être nécessaire d'utiliser des transactions pour les sélections.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-120">SELECT statements may lock database resources unnecessarily, and in some scenarios it may be necessary to use transactions for selects.</span></span> <span data-ttu-id="c6dfc-121">Tout travail autre que celui sur une base de données doit être exécuté en dehors de la portée de la transaction, à moins qu'il n'implique d'autres gestionnaires de ressources transactionnels.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-121">Any non-database work should be done outside of the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="c6dfc-122">Bien qu'une exception dans la portée de la transaction empêche la transaction d'être validée, la classe `TransactionScope` n'a aucune provision pour annuler les modifications apportées par votre code à l'extérieur de la portée de la transaction elle-même.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-122">Although an exception within the scope of the transaction prevents the transaction from committing, the `TransactionScope` class has no provision for rolling back any changes your code has made outside of the scope of the transaction itself.</span></span> <span data-ttu-id="c6dfc-123">Si une mesure doit être prise lorsque la transaction est annulée, vous devez écrire votre propre implémentation de l'interface `System.Transactions.IEnlistmentNotification` et l'inscrire explicitement dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-123">If you need to take some action when the transaction is rolled back, you must write your own implementation of the `System.Transactions.IEnlistmentNotification` interface, and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6dfc-124">Exemple</span><span class="sxs-lookup"><span data-stu-id="c6dfc-124">Example</span></span>  
 <span data-ttu-id="c6dfc-125">Pour utiliser `System.Transactions`, vous devez avoir une référence au fichier System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-125">To work with `System.Transactions`, you must have a reference to the System.Transactions.dll file.</span></span>  
  
 <span data-ttu-id="c6dfc-126">Le code suivant montre comment créer une transaction qui peut être promue par rapport à deux instances différentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6dfc-126">The following code demonstrates how to create a transaction that can be promoted against two different instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6dfc-127">Ces instances sont représentées par deux objets `System.Data.SqlClient.SqlConnection` différents, encapsulés dans un bloc `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-127">These instances are represented by two different `System.Data.SqlClient.SqlConnection` objects, which are wrapped in a `TransactionScope` block.</span></span> <span data-ttu-id="c6dfc-128">Le code crée le bloc `TransactionScope` avec une instruction `using` et ouvre la première connexion, qui automatiquement l'inscrit dans `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-128">The code creates the `TransactionScope` block with a `using` statement, and opens the first connection, which automatically enlists it in the `TransactionScope`.</span></span> <span data-ttu-id="c6dfc-129">La transaction est inscrite initialement comme transaction légère, et non comme transaction distribuée complète.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-129">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="c6dfc-130">Le code présume l'existence d'une logique conditionnelle (laquelle a été omise pour des raisons de concision).</span><span class="sxs-lookup"><span data-stu-id="c6dfc-130">The code assumes the existence of conditional logic (which has been omitted for brevity).</span></span> <span data-ttu-id="c6dfc-131">Il ouvre la deuxième connexion uniquement si nécessaire, en l'inscrivant dans `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-131">It opens the second connection only if it is needed, enlisting it in the `TransactionScope`.</span></span> <span data-ttu-id="c6dfc-132">Lorsque la connexion est ouverte, la transaction est automatiquement promue en transaction distribuée complète.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-132">When the connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="c6dfc-133">Le code appelle ensuite `TransactionScope.Complete`, qui valide la transaction.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-133">The code then invokes `TransactionScope.Complete`, which commits the transaction.</span></span> <span data-ttu-id="c6dfc-134">Le code supprime les deux connexions à la sortie des instructions `using`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-134">The code disposes of the two connections when exiting the `using` statements for the connections.</span></span> <span data-ttu-id="c6dfc-135">La méthode `TransactionScope.Dispose` pour le `TransactionScope` est appelée automatiquement à la fin du bloc `using` pour le `TransactionScope`.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-135">The `TransactionScope.Dispose` method for the `TransactionScope` is automatically called at the termination of the `using` block for the `TransactionScope`.</span></span> <span data-ttu-id="c6dfc-136">Si une exception a été levée à un point quelconque du bloc `TransactionScope`, l'appel de `Complete` n'a pas lieu et la transaction distribuée est annulée quand `TransactionScope` est supprimé.</span><span class="sxs-lookup"><span data-stu-id="c6dfc-136">If an exception has been thrown at any point in the `TransactionScope` block, `Complete` does not get called, and the distributed transaction will roll back when the `TransactionScope` is disposed.</span></span>  
  
 <span data-ttu-id="c6dfc-137">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6dfc-137">Visual Basic</span></span>  
  
```  
Using transScope As New TransactionScope()  
    Using connection1 As New SqlConnection(connectString1)  
        ' Opening connection1 automatically enlists it in the   
        ' TransactionScope as a lightweight transaction.  
        connection1.Open()  
  
        ' Do work in the first connection.  
  
        ' Assumes conditional logic in place where the second  
        ' connection will only be opened as needed.  
        Using connection2 As New SqlConnection(connectString2)  
            ' Open the second connection, which enlists the   
            ' second connection and promotes the transaction to  
            ' a full distributed transaction.  
            connection2.Open()  
  
            ' Do work in the second connection.  
  
        End Using  
    End Using  
  
    ' Commit the transaction.  
    transScope.Complete()  
End Using  
```  
  
 <span data-ttu-id="c6dfc-138">C#</span><span class="sxs-lookup"><span data-stu-id="c6dfc-138">C#</span></span>  
  
```  
using (TransactionScope transScope = new TransactionScope())  
{  
    using (SqlConnection connection1 = new   
       SqlConnection(connectString1))  
    {  
        // Opening connection1 automatically enlists it in the   
        // TransactionScope as a lightweight transaction.  
        connection1.Open();  
  
        // Do work in the first connection.  
  
        // Assumes conditional logic in place where the second  
        // connection will only be opened as needed.  
        using (SqlConnection connection2 = new   
            SqlConnection(connectString2))  
        {  
            // Open the second connection, which enlists the   
            // second connection and promotes the transaction to  
            // a full distributed transaction.   
            connection2.Open();  
  
            // Do work in the second connection.  
        }  
    }  
    //  The Complete method commits the transaction.  
    transScope.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6dfc-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6dfc-139">See Also</span></span>  
 [<span data-ttu-id="c6dfc-140">Intégration et transactions du CLR</span><span class="sxs-lookup"><span data-stu-id="c6dfc-140">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
