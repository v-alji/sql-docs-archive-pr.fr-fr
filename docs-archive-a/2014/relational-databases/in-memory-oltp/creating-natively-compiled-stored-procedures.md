---
title: Création de procédures stockées compilées en mode natif | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602838"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="e4f8e-102">Création de procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="e4f8e-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="e4f8e-103">Les procédures stockées compilées en mode natif n'implémentent pas la surface d'exposition totale de programmabilité et de requête [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e4f8e-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="e4f8e-104">Certaines constructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ne peuvent pas être utilisées dans des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="e4f8e-105">Pour plus d’informations, consultez [constructions prises en charge dans les procédures stockées compilées en mode natif](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span><span class="sxs-lookup"><span data-stu-id="e4f8e-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="e4f8e-106">À l'inverse, plusieurs fonctionnalités [!INCLUDE[tsql](../../includes/tsql-md.md)] ne sont prises en charge que pour les procédures stockées compilées en mode natif :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="e4f8e-107">Blocs Atomic.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-107">Atomic blocks.</span></span> <span data-ttu-id="e4f8e-108">Pour plus d’informations, consultez [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e4f8e-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="e4f8e-109">Contraintes `NOT NULL` sur les paramètres et les variables de procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="e4f8e-110">Vous ne pouvez pas affecter de valeurs `NULL` aux paramètres ou aux variables déclarés en tant que `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="e4f8e-111">Pour plus d’informations, consultez [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4f8e-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="e4f8e-112">Liaison de schéma des procédures stockées compilées en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="e4f8e-113">Les procédures stockées compilées en mode natif sont créées à l’aide de [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e4f8e-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="e4f8e-114">L'exemple suivant illustre une table optimisée en mémoire et une procédure stockée compilée en mode natif utilisée pour insérer des lignes dans la table.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="e4f8e-115">Dans l'exemple de code, `NATIVE_COMPILATION` indique que cette procédure stockée [!INCLUDE[tsql](../../includes/tsql-md.md)] est une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="e4f8e-116">Les options suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-116">The following options are required:</span></span>  
  
|<span data-ttu-id="e4f8e-117">Option</span><span class="sxs-lookup"><span data-stu-id="e4f8e-117">Option</span></span>|<span data-ttu-id="e4f8e-118">Description</span><span class="sxs-lookup"><span data-stu-id="e4f8e-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="e4f8e-119">Les procédures stockées compilées en mode natif doivent être liées au schéma des objets auxquels elle fait référence.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="e4f8e-120">Cela signifie que la table référencée par la procédure ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="e4f8e-121">Les tables référencées dans la procédure doivent inclure leur nom de schéma, et les caractères génériques ( \* ) ne sont pas autorisés dans les requêtes.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="e4f8e-122">`SCHEMABINDING` est uniquement prise en charge pour les procédures stockées compilées en mode natif dans cette version de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f8e-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="e4f8e-123">Les procédures stockées compilées en mode natif ne prennent pas en charge `EXECUTE AS CALLER`, qui est le contexte d'exécution par défaut.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="e4f8e-124">Par conséquent, vous devez spécifier le contexte d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="e4f8e-125">Les options `EXECUTE AS OWNER` , `EXECUTE AS` *User*et `EXECUTE AS SELF` sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="e4f8e-126">Le corps d'une procédure stockée compilée en mode natif doit être un bloc Atomic.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="e4f8e-127">Les blocs Atomic garantissent l'exécution atomique de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="e4f8e-128">Si la procédure est appelée en dehors du contexte d'une transaction active, elle démarre une nouvelle transaction, qui valide la transaction à la fin du bloc Atomic.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="e4f8e-129">Deux options sont obligatoires pour les blocs Atomic dans les procédures stockées compilées en mode natif :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="e4f8e-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="e4f8e-131">Consultez [niveaux](../../database-engine/transaction-isolation-levels.md) d’isolement des transactions pour les niveaux d’isolement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="e4f8e-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-132">`LANGUAGE`.</span></span> <span data-ttu-id="e4f8e-133">Le langage de la procédure stockée doit être défini sur l'un des langages ou des alias de langage disponibles.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="e4f8e-134">En ce qui concerne `EXECUTE AS` et les connexions Windows, une erreur peut se produire en raison de l'emprunt d'identité effectué via `EXECUTE AS`.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="e4f8e-135">Si un compte d'utilisateur utilise l'authentification Windows, il doit y avoir une confiance totale entre le compte de service utilisé pour l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et le domaine de la connexion Windows.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="e4f8e-136">S’il n’existe pas de confiance totale, le message d’erreur suivant est retourné lors de la création d’une procédure stockée compilée en mode natif : MSG 15404, impossible d’obtenir des informations sur l’utilisateur ou le groupe Windows NT’nom_utilisateur', code d’erreur 0X5.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="e4f8e-137">Pour résoudre cette erreur, utilisez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="e4f8e-138">Utilisez un compte du même domaine que l'utilisateur Windows pour le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f8e-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="e4f8e-139">Si [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise un compte d’ordinateur tel que service réseau ou système local, l’ordinateur doit être approuvé par le domaine contenant l’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="e4f8e-140">Utilisez l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4f8e-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="e4f8e-141">L'erreur 15517 s'affiche également lorsque vous créez une procédure stockée compilée en mode natif.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="e4f8e-142">Pour plus d’informations, consultez [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="e4f8e-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="e4f8e-143">Mise à jour d'une procédure stockée compilée en mode natif</span><span class="sxs-lookup"><span data-stu-id="e4f8e-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="e4f8e-144">L'exécution d'opérations de modification (ALTER) sur les procédures stockées compilées en mode natif n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="e4f8e-145">Une méthode pour modifier une procédure stockée compilée en mode natif consiste à supprimer et recréer la procédure stockée :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="e4f8e-146">Générez un script d'autorisations sur la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="e4f8e-147">Éventuellement, générez un script pour la procédure stockée et enregistrez-le comme sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="e4f8e-148">Supprimez la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="e4f8e-149">Créez la procédure stockée modifiée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="e4f8e-150">Réappliquez les autorisations du script à la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="e4f8e-151">L’inconvénient de cette procédure est que l’application est hors connexion dès le début de l’étape 3 jusqu’à la fin de l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="e4f8e-152">Cette opération peut prendre quelques secondes et le client qui utilise l'application peut recevoir des messages d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="e4f8e-153">Une autre méthode pour modifier (efficacement) une procédure stockée compilée en mode natif consiste à créer, dans un premier temps, une nouvelle version de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="e4f8e-154">La procédure stockée compilée en mode natif possède un numéro de version associé.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="e4f8e-155">Nous allons nommer l'ancienne version SP_Vold et la nouvelle SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="e4f8e-156">Générez un script d'autorisations sur SP_Vold</span><span class="sxs-lookup"><span data-stu-id="e4f8e-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="e4f8e-157">Créez SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="e4f8e-158">Appliquez les autorisations de SP_Vold à SP_new.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="e4f8e-159">Mettez à jour les références à SP_Vold de façon à ce qu'elles pointent vers SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="e4f8e-160">Cette opération peut être effectuée de différentes manières, par exemple :</span><span class="sxs-lookup"><span data-stu-id="e4f8e-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="e4f8e-161">Utilisez une procédure stockée (sur disque) de wrapper, et modifiez-la de façon à ce qu'elle pointe vers SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="e4f8e-162">L'inconvénient de cette méthode est l'impact de l'indirection sur les performances.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="e4f8e-163">Supprimez éventuellement SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="e4f8e-164">L'avantage de cette méthode est que l'application n'est pas mise hors connexion.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="e4f8e-165">En revanche, cette méthode nécessite davantage de travail pour gérer les références et veiller à ce qu'elles pointent toujours vers la version la plus récente de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="e4f8e-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f8e-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4f8e-166">See Also</span></span>  
 [<span data-ttu-id="e4f8e-167">Procédures stockées compilées en mode natif</span><span class="sxs-lookup"><span data-stu-id="e4f8e-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
