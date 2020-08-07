---
title: Transactions entre conteneurs | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5d84b51a-ec17-4c5c-b80e-9e994fc8ae80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28437f0903459616a574e713c0f138e8bb459870
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605700"
---
# <a name="cross-container-transactions"></a><span data-ttu-id="64ce0-102">Transactions entre conteneurs</span><span class="sxs-lookup"><span data-stu-id="64ce0-102">Cross-Container Transactions</span></span>
  <span data-ttu-id="64ce0-103">Les transactions entre conteneurs sont des transactions utilisateur implicites ou explicites qui incluent des appels aux procédures stockées compilées en mode natif ou des opérations sur des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="64ce0-103">Cross-container transactions are either implicit or explicit user transactions that include calls to natively-compiled stored procedures or operations on memory-optimized tables.</span></span>  
  
 <span data-ttu-id="64ce0-104">Dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], les appels aux procédures stockées ne démarrent pas une transaction.</span><span class="sxs-lookup"><span data-stu-id="64ce0-104">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], calls to stored procedures do not initiate a transaction.</span></span> <span data-ttu-id="64ce0-105">Les exécutions de procédures compilées en mode natif qui sont effectuées en mode de validation automatique (hors du contexte d'une transaction utilisateur) ne sont pas considérées comme des transactions entre conteneurs.</span><span class="sxs-lookup"><span data-stu-id="64ce0-105">Executions of natively compiled procedures in autocommit mode (not in the context of a user transaction) are not considered cross-container transactions.</span></span>  
  
 <span data-ttu-id="64ce0-106">Toute requête interprétée référençant des tables mémoire optimisées est considérée comme une partie d'une transaction entre conteneurs, qu'elle soit exécutée à partir d'une transaction explicite ou implicite, ou en mode de validation automatique.</span><span class="sxs-lookup"><span data-stu-id="64ce0-106">Any interpreted query that references memory-optimized tables is considered a part of a cross-container transaction, whether executed from an explicit or implicit transaction or in auto-commit mode.</span></span>  
  
##  <a name="isolation-of-individual-operations"></a><a name="isolation"></a><span data-ttu-id="64ce0-107">Isolement des opérations individuelles</span><span class="sxs-lookup"><span data-stu-id="64ce0-107">Isolation of Individual Operations</span></span>  
 <span data-ttu-id="64ce0-108">Chaque transaction [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] est caractérisée par un niveau d'isolation.</span><span class="sxs-lookup"><span data-stu-id="64ce0-108">Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] transaction has an isolation level.</span></span> <span data-ttu-id="64ce0-109">Le niveau d'isolation par défaut est READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="64ce0-109">The default isolation level is Read Committed.</span></span> <span data-ttu-id="64ce0-110">Pour utiliser un niveau d’isolation différent, vous pouvez définir le niveau d’isolation à l’aide de l' [instruction Set transaction isolation level &#40;&#41;Transact-SQL ](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64ce0-110">To use a different isolation level, you can set the isolation level using [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="64ce0-111">Il est souvent nécessaire d'effectuer des opérations sur les tables mémoire optimisées avec un niveau d'isolation différent des opérations sur les tables sur disque.</span><span class="sxs-lookup"><span data-stu-id="64ce0-111">It is often necessary to perform operations on memory-optimized tables at a different isolation level than operations on disk-based tables.</span></span> <span data-ttu-id="64ce0-112">Dans une transaction, il est possible de définir un niveau d'isolation différent pour un ensemble d'instructions ou pour une opération de lecture individuelle.</span><span class="sxs-lookup"><span data-stu-id="64ce0-112">In a transaction, it is possible to set a different isolation level for a collection of statements or for an individual read operation.</span></span>  
  
### <a name="specifying-the-isolation-level-of-individual-operations"></a><span data-ttu-id="64ce0-113">Spécifier le niveau d'isolation d'opérations individuelles</span><span class="sxs-lookup"><span data-stu-id="64ce0-113">Specifying the Isolation Level of Individual Operations</span></span>  
 <span data-ttu-id="64ce0-114">Pour définir un niveau d'isolation différent pour un ensemble d'instructions dans une transaction, vous pouvez utiliser `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="64ce0-114">To set a different isolation level for a set of statements in a transaction, you can use `SET TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="64ce0-115">L'exemple de transaction suivant utilise le niveau d'isolation SERIALIZABLE comme valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="64ce0-115">The following example of a transaction uses the serializable isolation level as default.</span></span> <span data-ttu-id="64ce0-116">Les opérations d'insertion et de sélection sur t3, t2 et t1 sont exécutées avec l'isolation REPEATABLE READ.</span><span class="sxs-lookup"><span data-stu-id="64ce0-116">The insert and select operations on t3, t2, and t1 are executed under repeatable read isolation.</span></span>  
  
```sql  
set transaction isolation level serializable  
go  
  
begin transaction  
 ......  
  set transaction isolation level repeatable read  
  
  insert t3 select * from t1 join t2 on t1.id=t2.id  
  
  set transaction isolation level serializable  
 ......  
commit  
```  
  
 <span data-ttu-id="64ce0-117">Pour définir un niveau d'isolation pour certaines opérations de lecture différent de la valeur par défaut de la transaction, vous pouvez utiliser un indicateur de table (par exemple, SERIALIZABLE).</span><span class="sxs-lookup"><span data-stu-id="64ce0-117">To set an isolation level for individual read operations that is different from the transaction default, you can use a table hint (for example, serializable).</span></span> <span data-ttu-id="64ce0-118">Chaque sélection correspond à une opération de lecture, et chaque mise à jour et chaque suppression correspondent à une lecture, car la ligne doit toujours être lue avant de pouvoir être mise à jour ou supprimée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-118">Every select corresponds to a read operation and every update and every delete corresponds to a read, because the row always needs to be read before it can be updated or deleted.</span></span> <span data-ttu-id="64ce0-119">Les opérations d'insertion n'ont pas de niveau d'isolation, car les écritures sont toujours isolées dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64ce0-119">Insert operations do not have an isolation level, because writes are always isolated in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="64ce0-120">Dans l'exemple suivant, le niveau d'isolation de la transaction est READ COMMITTED, mais la table t1 est accessible avec l'isolation SERIALIZABLE, et t2 avec l'isolation SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="64ce0-120">In the following example, the default isolation level for the transaction is read committed, but table t1 is accessed under serializable and t2 under snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
 ......  
  
  insert t3 select * from t1 (serializable) join t2 (snapshot) on t1.id=t2.id  
  
  ......  
commit  
```  
  
### <a name="isolation-semantics-for-individual-operations"></a><span data-ttu-id="64ce0-121">Sémantique d'isolation d'opérations individuelles</span><span class="sxs-lookup"><span data-stu-id="64ce0-121">Isolation Semantics for Individual Operations</span></span>  
 <span data-ttu-id="64ce0-122">Une transaction sérialisable T est exécutée avec l'isolation complète.</span><span class="sxs-lookup"><span data-stu-id="64ce0-122">A serializable transaction T is executed in complete isolation.</span></span> <span data-ttu-id="64ce0-123">C'est comme si chaque autre transaction avait été soit validée avant le démarrage de T, soit démarrée après la validation de T.</span><span class="sxs-lookup"><span data-stu-id="64ce0-123">It is as if every other transaction has either committed before T started, or is started after T committed.</span></span> <span data-ttu-id="64ce0-124">Cela devient plus complexe lorsque plusieurs opérations dans une transaction présentent des niveaux d'isolation différents.</span><span class="sxs-lookup"><span data-stu-id="64ce0-124">It becomes more complex when different operations in a transaction have different isolation levels.</span></span>  
  
 <span data-ttu-id="64ce0-125">La sémantique générale des niveaux d’isolation des transactions dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , ainsi que les implications sur le verrouillage, sont expliquées dans [définir le niveau d’isolation des transactions &#40;&#41;Transact-SQL ](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64ce0-125">The general semantics of the transaction isolation levels in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], along with the implications on locking, is explained in [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
 <span data-ttu-id="64ce0-126">Pour les transactions entre conteneurs dans lesquelles les opérations peuvent avoir différents niveaux d'isolation, vous devez comprendre la sémantique de l'isolation des opérations de lecture individuelles.</span><span class="sxs-lookup"><span data-stu-id="64ce0-126">For cross-container transactions where different operations may have different isolation levels, you need to understand the semantics of isolation of individual read operations.</span></span> <span data-ttu-id="64ce0-127">Les opérations d'écriture sont toujours isolées.</span><span class="sxs-lookup"><span data-stu-id="64ce0-127">Write operations are always isolated.</span></span> <span data-ttu-id="64ce0-128">Les écritures effectuées dans des transactions distinctes n'ont aucun impact les unes sur les autres.</span><span class="sxs-lookup"><span data-stu-id="64ce0-128">Writes in different transactions cannot impact each other.</span></span>  
  
 <span data-ttu-id="64ce0-129">Une opération de lecture de données retourne plusieurs lignes répondant à une condition de filtre.</span><span class="sxs-lookup"><span data-stu-id="64ce0-129">A data read operation returns a number of rows that satisfy a filter condition.</span></span>  
  
 <span data-ttu-id="64ce0-130">Les lectures sont effectuées dans le cadre d’une transaction T. les niveaux d’isolation pour les opérations de lecture peuvent être compris en termes de,</span><span class="sxs-lookup"><span data-stu-id="64ce0-130">Reads are performed as part of a transaction T. Isolation levels for read operations can be understood in terms of,</span></span>  
  
 <span data-ttu-id="64ce0-131">État de validation</span><span class="sxs-lookup"><span data-stu-id="64ce0-131">Commit Status</span></span>  
 <span data-ttu-id="64ce0-132">L'état de validation indique si la validation de la lecture de données est garantie.</span><span class="sxs-lookup"><span data-stu-id="64ce0-132">Commit status refers to whether the data read is guaranteed to be committed.</span></span>  
  
 <span data-ttu-id="64ce0-133">Cohérence (Transactions)</span><span class="sxs-lookup"><span data-stu-id="64ce0-133">(Transactional) Consistency</span></span>  
 <span data-ttu-id="64ce0-134">La cohérence transactionnelle pour un ensemble de lectures vérifie si toutes les versions de ligne lues comprennent les mises à jour du même ensemble de transactions précisément.</span><span class="sxs-lookup"><span data-stu-id="64ce0-134">Transactional consistency for a set of reads refers to whether the row versions read are all guaranteed to include updates from precisely the same set of transactions.</span></span>  
  
 <span data-ttu-id="64ce0-135">La stabilité garantit que le système permet à la transaction T de lire les données.</span><span class="sxs-lookup"><span data-stu-id="64ce0-135">Stability guarantees the system gives to transaction T about the data read.</span></span>  
 <span data-ttu-id="64ce0-136">La stabilité fait référence au fait que les lectures de la transaction sont reproductibles.</span><span class="sxs-lookup"><span data-stu-id="64ce0-136">Stability refers to whether the transaction's reads are repeatable.</span></span> <span data-ttu-id="64ce0-137">c'est-à-dire si les lectures renouvelées retournent les mêmes lignes et versions de ligne.</span><span class="sxs-lookup"><span data-stu-id="64ce0-137">That is, if the reads were repeated would they return the same rows and row versions?</span></span>  
  
 <span data-ttu-id="64ce0-138">Certaines garanties font référence à l'heure de fin logique de la transaction.</span><span class="sxs-lookup"><span data-stu-id="64ce0-138">Certain guarantees refer to the logical end time of the transaction.</span></span> <span data-ttu-id="64ce0-139">En général, l'heure de fin logique est l'heure à laquelle la transaction est validée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="64ce0-139">In general, the logical end time is the time the transaction is committed to the database.</span></span> <span data-ttu-id="64ce0-140">Si la transaction accède à des tables mémoire optimisées, l'heure de fin logique correspond techniquement au début de la phase de validation.</span><span class="sxs-lookup"><span data-stu-id="64ce0-140">If memory-optimized tables are accessed by the transaction, the logical end time is technically the beginning of the validation phase.</span></span> <span data-ttu-id="64ce0-141">(Pour plus d’informations, consultez la discussion sur la durée de vie des transactions dans les [tables optimisées en mémoire](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="64ce0-141">(For more information, see the transaction lifetime discussion in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="64ce0-142">Indépendamment du niveau d'isolation, une transaction (T) voit toujours ses propres mises à jour :</span><span class="sxs-lookup"><span data-stu-id="64ce0-142">Regardless of isolation level, a transaction (T) always sees its own updates:</span></span>  
  
 <span data-ttu-id="64ce0-143">READ UNCOMMITTED</span><span class="sxs-lookup"><span data-stu-id="64ce0-143">READ UNCOMMITTED</span></span>  
 <span data-ttu-id="64ce0-144">La lecture de données ne peut être ni validée, ni cohérente, ni stable.</span><span class="sxs-lookup"><span data-stu-id="64ce0-144">The data read may neither be committed, consistent, or stable.</span></span> <span data-ttu-id="64ce0-145">Toutefois, cela inclut les opérations d'écriture effectuées antérieurement par T.</span><span class="sxs-lookup"><span data-stu-id="64ce0-145">However, it will include earlier write operations done by T.</span></span>  
  
 <span data-ttu-id="64ce0-146">READ COMMITTED</span><span class="sxs-lookup"><span data-stu-id="64ce0-146">READ COMMITTED</span></span>  
 <span data-ttu-id="64ce0-147">La lecture de données est validée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-147">The data read will be committed.</span></span>  
  
 <span data-ttu-id="64ce0-148">SNAPSHOT</span><span class="sxs-lookup"><span data-stu-id="64ce0-148">SNAPSHOT</span></span>  
 <span data-ttu-id="64ce0-149">Toutes les opérations de lecture effectuées par T avec l'isolation d'instantané ont la même heure de lecture logique, correspondant au début de la transaction.</span><span class="sxs-lookup"><span data-stu-id="64ce0-149">All read operations performed by T under snapshot isolation have the same logical read time, which is the beginning of the transaction.</span></span> <span data-ttu-id="64ce0-150">La validation et la cohérence de la lecture de données sont garanties à compter de l'heure logique de lecture.</span><span class="sxs-lookup"><span data-stu-id="64ce0-150">The data read is guaranteed to be committed and consistent as of the logical read time.</span></span> <span data-ttu-id="64ce0-151">La répétition d'une lecture à compter de l'heure de lecture d'origine retourne toujours le même résultat.</span><span class="sxs-lookup"><span data-stu-id="64ce0-151">Repeating a read as of the original read time is guaranteed to return the same result.</span></span>  
  
 <span data-ttu-id="64ce0-152">REPEATABLE READ</span><span class="sxs-lookup"><span data-stu-id="64ce0-152">REPEATABLE READ</span></span>  
 <span data-ttu-id="64ce0-153">La validation et la stabilité de la lecture de données sont garanties jusqu'à l'heure de fin logique de la transaction.</span><span class="sxs-lookup"><span data-stu-id="64ce0-153">The data read is guaranteed to be committed and stable up to the logical end time of the transaction.</span></span>  
  
 <span data-ttu-id="64ce0-154">SERIALIZABLE</span><span class="sxs-lookup"><span data-stu-id="64ce0-154">SERIALIZABLE</span></span>  
 <span data-ttu-id="64ce0-155">Toutes les garanties de la lecture renouvelable plus la prévention fantôme et la cohérence transactionnelle en ce qui concerne toutes les opérations de lecture sérialisables effectuées par T. la prévention fantôme signifie que l’opération d’analyse ne peut retourner que des lignes supplémentaires écrites par T, mais aucune ligne écrite par d’autres transactions.</span><span class="sxs-lookup"><span data-stu-id="64ce0-155">All guarantees of REPEATABLE READ plus phantom avoidance and transactional consistency with respect to all serializable read operations performed by T. Phantom avoidance means that the scan operation can only return additional rows that were written by T, but no rows that were written by other transactions.</span></span>  
  
 <span data-ttu-id="64ce0-156">Prenons l'exemple de transaction suivante :</span><span class="sxs-lookup"><span data-stu-id="64ce0-156">Consider the following transaction,</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  -- remove all rows from t3; the related read operation is performed under read committed   
  -- isolation, as this is the default for the transaction  
  delete from t3  
  
  -- copy the contents from t1 to t3; the read on t1 is performed under the serializable   
  -- isolation level  
  insert t3 select * from t1 (serializable)  
  
  -- compare t3 and t1; note: the result set may not be empty, as rows may have been added   
  -- by other transaction before this select, due to the read committed isolation level  
  select * from t3 except t1  
  
  -- compare t1 and t3; note: the result set is empty, as no rows have been added to t1   
  -- since its contents were copied to t1, due to the serializable isolation level  
  select * from t1 except t3  
commit  
```  
  
 <span data-ttu-id="64ce0-157">Cette transaction supprime toutes les lignes de t3 avec l'isolation READ COMMITTED, copie toutes les lignes de t1 à t3 avec l'isolation SERIALIZABLE, puis compare t1 et t3.</span><span class="sxs-lookup"><span data-stu-id="64ce0-157">This transaction deletes all rows from t3 under read committed isolation, copies all rows from t1 to t3 under serializable isolation, and then compares t1 and t3.</span></span> <span data-ttu-id="64ce0-158">Certaines lignes [pas dans t1] peuvent avoir été ajoutées à t3, car la table a été vidée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-158">Some rows [not in t1] may have been added to t3 since the table was emptied.</span></span> <span data-ttu-id="64ce0-159">Aucune ligne n'a été ajoutée à t1, car la copie était sérialisable.</span><span class="sxs-lookup"><span data-stu-id="64ce0-159">No rows were added to t1 as the copy was serializable.</span></span>  
  
 <span data-ttu-id="64ce0-160">Bien que la lecture depuis t1 à la fin de la transaction soit syntaxiquement une lecture validée, elle est en réalité sérialisable, car la même lecture a été exécutée précédemment dans la transaction avec l'isolation sérialisable : la sérialisation garantit que si la lecture est exécutée au niveau d'un point ultérieur de la transaction, les mêmes lignes sont retournées.</span><span class="sxs-lookup"><span data-stu-id="64ce0-160">Although the read from t1 at the end of the transaction is syntactically read committed, it is effectively serializable, because the same read was performed earlier in the transaction under serializable isolation: serializability guarantees that if the read is performed at any later point in the transaction, the same rows are returned.</span></span>  
  
## <a name="cross-container-transactions-and-isolation-levels"></a><span data-ttu-id="64ce0-161">Transactions entre conteneurs et niveaux d'isolation</span><span class="sxs-lookup"><span data-stu-id="64ce0-161">Cross-Container Transactions and Isolation Levels</span></span>  
 <span data-ttu-id="64ce0-162">Une transaction entre conteneurs peut être considérée comme ayant deux côtés : un côté sur disque (pour les opérations sur les tables sur disque) et un côté mémoire optimisé (pour les opérations sur les tables optimisées en mémoire).</span><span class="sxs-lookup"><span data-stu-id="64ce0-162">A cross-container transaction can be seen as having two sides: a disk-based side (for operations on disk-based tables) and a memory-optimized side (for operations on memory-optimized tables).</span></span> <span data-ttu-id="64ce0-163">Ces deux côtés peuvent avoir des niveaux d'isolation différents.</span><span class="sxs-lookup"><span data-stu-id="64ce0-163">These two sides may have different isolation levels.</span></span> <span data-ttu-id="64ce0-164">En fait, les opérations de lecture individuelles réalisées de chaque côté peuvent avoir des niveaux d'isolation différents.</span><span class="sxs-lookup"><span data-stu-id="64ce0-164">In fact, individual read operations on each side may have different isolation levels.</span></span>  
  
 <span data-ttu-id="64ce0-165">Le côté sur disque d'une transaction T atteint un certain niveau d'isolation X si au moins une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="64ce0-165">The disk-based side of a given transaction T reaches a certain isolation level X if one of the following conditions is met:</span></span>  
  
-   <span data-ttu-id="64ce0-166">Il commence par X. Autrement dit, la valeur par défaut de la session était X, soit parce que vous avez exécuté `SET TRANSACTION ISOLATION LEVEL` , soit il s’agit de la [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="64ce0-166">It starts in X. That is, the session default was X, either because you executed `SET TRANSACTION ISOLATION LEVEL`, or it is the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] default.</span></span>  
  
-   <span data-ttu-id="64ce0-167">Pendant la transaction, le niveau d'isolation est remplacé par X à l'aide de `SET TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="64ce0-167">During the transaction, the default isolation level is changed to X using `SET TRANSACTION ISOLATION LEVEL`.</span></span>  
  
-   <span data-ttu-id="64ce0-168">Une opération de lecture dans une table sur disque est exécutée avec le niveau d'isolation X, à l'aide de la syntaxe `WITH (X)`.</span><span class="sxs-lookup"><span data-stu-id="64ce0-168">A read operation on a disk-based table is executed under isolation level X, using the syntax `WITH (X)`.</span></span>  
  
 <span data-ttu-id="64ce0-169">Le côté mémoire optimisé de T atteint le niveau d'isolation Y si, pendant l'exécution de T, l'une des opérations de lecture dans une table mémoire optimisée ou l'une des procédures stockées compilées en mode natif est exécutée avec le niveau d'isolation Y.</span><span class="sxs-lookup"><span data-stu-id="64ce0-169">The memory-optimized side of T reaches an isolation level Y if during execution of T, any read operation on a memory-optimized table or any natively compiled stored procedure is executed under isolation level Y.</span></span>  
  
 <span data-ttu-id="64ce0-170">Prenons l'exemple de la transaction suivante.</span><span class="sxs-lookup"><span data-stu-id="64ce0-170">Consider the following transaction as an example.</span></span> <span data-ttu-id="64ce0-171">Ici, t1 et t2 sont des tables sur disque, et t3 et t4 sont des tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="64ce0-171">Here, t1 and t2 are disk-based tables and t3 and t4 are memory-optimized tables.</span></span>  
  
 <span data-ttu-id="64ce0-172">Le côté sur disque de la transaction atteint le niveau d'isolation READ COMMITTED, car il commence dans ce niveau.</span><span class="sxs-lookup"><span data-stu-id="64ce0-172">The disk-based side of the transaction reaches the isolation level read committed, because it starts in that level.</span></span> <span data-ttu-id="64ce0-173">Il atteint également le niveau REPEATABLE READ, car la première opération de lecture est exécutée avec ce niveau d'isolation.</span><span class="sxs-lookup"><span data-stu-id="64ce0-173">The disk-based side also reaches repeatable read, because the first read operation is executed under that isolation level.</span></span> <span data-ttu-id="64ce0-174">La suppression à la fin de la transaction est exécutée avec le niveau d'isolation READ COMMITTED, et n'introduit donc pas de nouveau niveau d'isolation.</span><span class="sxs-lookup"><span data-stu-id="64ce0-174">The delete at the end of the transaction is executed under read committed isolation level, and so does not introduce a new isolation level.</span></span>  
  
 <span data-ttu-id="64ce0-175">Le côté mémoire optimisé de la transaction peut atteindre l'un des deux niveaux d'isolation suivants : si la condition 1 est « True », il atteint le niveau SERIALIZABLE, tandis que si elle est « False », il n'atteint que le niveau SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="64ce0-175">The memory-optimized side of the transaction can reach one of two levels: if condition1 is true, it reaches serializable, while if it is false, the memory-optimized side reaches only snapshot isolation.</span></span>  
  
```sql  
set transaction isolation level read committed  
go  
  
begin transaction  
  select * from t1 (repeatableread)  
  
  if condition1 begin  
    insert t3 select * from t4 (serializable)  
  end  
  else begin  
    insert t3 select * from t4 (snapshot)  
  end  
  
  delete from t1  
commit  
```  
  
### <a name="supported-isolation-levels-for-cross-container-transactions"></a><span data-ttu-id="64ce0-176">Niveaux d'isolation pris en charge pour les transactions entre conteneurs</span><span class="sxs-lookup"><span data-stu-id="64ce0-176">Supported Isolation Levels for Cross-Container Transactions</span></span>  
 <span data-ttu-id="64ce0-177">Certaines limitations s'appliquent aux niveaux d'isolation utilisés pour les opérations sur des tables mémoire optimisées dans les transactions entre conteneurs.</span><span class="sxs-lookup"><span data-stu-id="64ce0-177">There are limitations on the isolation levels used with operations on memory-optimized tables in cross-container transactions.</span></span>  
  
 <span data-ttu-id="64ce0-178">Les tables mémoire optimisées prennent en charge les niveaux d'isolation SNAPSHOT, REPEATABLE READ et SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="64ce0-178">Memory-optimized tables support the isolation levels SNAPSHOT, REPEATABLE READ, and SERIALIZABLE.</span></span> <span data-ttu-id="64ce0-179">Pour les transactions validées automatiquement, les tables mémoire optimisées prennent en charge le niveau d'isolation READ COMMITTED.</span><span class="sxs-lookup"><span data-stu-id="64ce0-179">For autocommit transactions, memory-optimized tables support the isolation level READ COMMITTED.</span></span>  
  
 <span data-ttu-id="64ce0-180">Les scénarios suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="64ce0-180">The following scenarios are supported:</span></span>  
  
-   <span data-ttu-id="64ce0-181">Les transactions entre conteneurs READ UNCOMMITTED, READ COMMITTED et READ_COMMITTED_SNAPSHOT peuvent accéder aux tables mémoire optimisées avec les niveaux d'isolation SNAPSHOT, REPEATABLE READ et SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="64ce0-181">READ UNCOMMITTED, READ COMMITTED, and READ_COMMITTED_SNAPSHOT cross-container transactions can access memory-optimized tables under SNAPSHOT, REPEATABLE READ, and SERIALIZABLE isolation.</span></span> <span data-ttu-id="64ce0-182">La garantie READ COMMITTED protège la transaction, car toutes les lignes lues par la transaction ont été validées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="64ce0-182">The READ COMMITTED guarantee holds for the transaction; all rows read by the transaction have been committed to the database.</span></span>  
  
-   <span data-ttu-id="64ce0-183">Les transactions REPEATABLE READ et SERIALIZABLE peuvent accéder aux tables mémoire optimisées avec l'isolation SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="64ce0-183">REPEATABLE READ and SERIALIZABLE transactions can access memory-optimized tables under SNAPSHOT isolation.</span></span>  
  
## <a name="read-only-cross-container-transactions"></a><span data-ttu-id="64ce0-184">Transactions en lecture seule entre conteneurs</span><span class="sxs-lookup"><span data-stu-id="64ce0-184">Read-only Cross-Container Transactions</span></span>  
 <span data-ttu-id="64ce0-185">La plupart des transactions en lecture seule dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sont restaurées au moment de la validation.</span><span class="sxs-lookup"><span data-stu-id="64ce0-185">Most read-only transactions in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] are rolled back at commit time.</span></span> <span data-ttu-id="64ce0-186">Étant donné qu'il n'y a aucune modification à valider sur la base de données, le système libère simplement les ressources utilisées par la transaction.</span><span class="sxs-lookup"><span data-stu-id="64ce0-186">Because there are no changes to commit to the database, the system simply frees the resources used by the transaction.</span></span> <span data-ttu-id="64ce0-187">Pour les transactions sur disque en lecture seule, tous les verrous pris par la transaction sont libérés à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="64ce0-187">For read-only disk-based transactions, all locks taken by the transaction are released at this time.</span></span> <span data-ttu-id="64ce0-188">Dans le cas des transactions mémoire optimisées qui sont en lecture seule et qui incluent une seule exécution de procédure stockée compilée en mode natif, aucune validation n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-188">For read-only memory-optimized transactions that span a single natively compiled procedure execution, no validation is performed.</span></span>  
  
 <span data-ttu-id="64ce0-189">Les transactions en lecture seule entre conteneurs qui sont exécutées en mode de validation automatique sont simplement restaurées une fois leur exécution terminée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-189">Cross-container, read-only transactions in autocommit mode are simply rolled back at the end of the transaction.</span></span> <span data-ttu-id="64ce0-190">Aucune validation n'est effectuée.</span><span class="sxs-lookup"><span data-stu-id="64ce0-190">No validation is performed.</span></span>  
  
 <span data-ttu-id="64ce0-191">Les transactions en lecture seule, explicites ou implicites, entre conteneurs exécutent la validation à l'heure prédéfinie si elles accèdent aux tables mémoire optimisées avec l'isolation REPEATABLE READ ou SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="64ce0-191">Explicit or implicit cross-container, read-only transactions perform validation at commit time if the transaction accesses memory-optimized tables under REPEATABLE READ or SERIALIZABLE isolation.</span></span> <span data-ttu-id="64ce0-192">Pour plus d’informations sur la validation, consultez la section sur la détection de conflit, la validation et les vérifications de dépendance de validation dans les [transactions dans les tables mémoire optimisées](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="64ce0-192">For details about validation see the section on Conflict Detection, Validation, and Commit Dependency Checks in [Transactions in Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ce0-193">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64ce0-193">See Also</span></span>  
 <span data-ttu-id="64ce0-194">[Fonctionnement des transactions sur les tables optimisées en mémoire](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="64ce0-194">[Understanding Transactions on Memory-Optimized Tables](../../2014/database-engine/understanding-transactions-on-memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="64ce0-195">[Instructions relatives aux niveaux d’isolation des transactions avec des tables mémoire optimisées](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="64ce0-195">[Guidelines for Transaction Isolation Levels with Memory-Optimized Tables](../../2014/database-engine/guidelines-for-transaction-isolation-levels-with-memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="64ce0-196">Instructions pour la logique de nouvelle tentative des transactions sur des tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="64ce0-196">Guidelines for Retry Logic for Transactions on Memory-Optimized Tables</span></span>](../../2014/database-engine/guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
  
