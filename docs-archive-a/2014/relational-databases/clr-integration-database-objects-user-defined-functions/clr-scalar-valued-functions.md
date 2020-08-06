---
title: Fonctions scalaires CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- SVF
- scalar-valued functions
ms.assetid: 20dcf802-c27d-4722-9cd3-206b1e77bee0
author: rothja
ms.author: jroth
ms.openlocfilehash: be8f9616fb285d6a68d6734924874ded06fb3bd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698315"
---
# <a name="clr-scalar-valued-functions"></a><span data-ttu-id="b1bc2-102">Fonctions scalaires CLR</span><span class="sxs-lookup"><span data-stu-id="b1bc2-102">CLR Scalar-Valued Functions</span></span>
  <span data-ttu-id="b1bc2-103">Une fonction scalaire (SVF) retourne une valeur unique, telle qu'une chaîne, un entier ou une valeur binaire. Vous pouvez créer des fonctions scalaires définies par l'utilisateur en code managé à l'aide de tout langage de programmation .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-103">A scalar-valued function (SVF) returns a single value, such as a string, integer, or bit value.You can create scalar-valued user-defined functions in managed code using any .NET Framework programming language.</span></span> <span data-ttu-id="b1bc2-104">Ces fonctions sont accessibles au code [!INCLUDE[tsql](../../includes/tsql-md.md)] ou autre code managé.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-104">These functions are accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span> <span data-ttu-id="b1bc2-105">Pour plus d’informations sur les avantages de l’intégration du CLR et le choix entre le code managé et [!INCLUDE[tsql](../../includes/tsql-md.md)] , consultez [vue d’ensemble de l’intégration du CLR](../clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b1bc2-105">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="requirements-for-clr-scalar-valued-functions"></a><span data-ttu-id="b1bc2-106">Spécifications relatives aux fonctions scalaires CLR</span><span class="sxs-lookup"><span data-stu-id="b1bc2-106">Requirements for CLR Scalar-Valued Functions</span></span>  
 <span data-ttu-id="b1bc2-107">Les fonctions scalaires .NET Framework sont implémentées en tant que méthodes d'une classe dans un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-107">.NET Framework SVFs are implemented as methods on a class in a .NET Framework assembly.</span></span> <span data-ttu-id="b1bc2-108">Les paramètres d’entrée et le type retourné à partir d’un SVF peuvent être n’importe lequel des types de données scalaires pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , à l’exception de,,,,,,, `varchar` `char` `rowversion` `text` `ntext` `image` `timestamp` `table` ou `cursor` .</span><span class="sxs-lookup"><span data-stu-id="b1bc2-108">The input parameters and the type returned from a SVF can be any of the scalar data types supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], except `varchar`, `char`, `rowversion`, `text`, `ntext`, `image`, `timestamp`, `table`, or `cursor`.</span></span> <span data-ttu-id="b1bc2-109">Les fonctions scalaires doivent garantir une correspondance entre le type de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le type de données de retour de la méthode d'implémentation.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-109">SVFs must ensure a match between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type and the return data type of the implementation method.</span></span> <span data-ttu-id="b1bc2-110">Pour plus d’informations sur les conversions de type, consultez [mappage des données de paramètres CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span><span class="sxs-lookup"><span data-stu-id="b1bc2-110">For more information about type conversions, see [Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md).</span></span>  
  
 <span data-ttu-id="b1bc2-111">Lors de l'implémentation d'une fonction scalaire .NET Framework dans un langage .NET Framework, l'attribut personnalisé `SqlFunction` peut être spécifié de façon à inclure des informations supplémentaires à propos de la fonction.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-111">When implementing a .NET Framework SVF in a .NET Framework language, the `SqlFunction` custom attribute can be specified to include additional information about the function.</span></span> <span data-ttu-id="b1bc2-112">L'attribut `SqlFunction` indique si la fonction accède ou modifie des données, si elle est déterministe et si elle implique des opérations de virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-112">The `SqlFunction` attribute indicates whether or not the function accesses or modifies data, if it is deterministic, and if the function involves floating point operations.</span></span>  
  
 <span data-ttu-id="b1bc2-113">Les fonctions scalaires définies par l'utilisateur peuvent être déterministes ou non déterministes.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-113">Scalar-valued user-defined functions may be deterministic or non-deterministic.</span></span> <span data-ttu-id="b1bc2-114">Une fonction déterministe retourne toujours le même résultat lorsqu'elle est appelée avec un jeu de paramètres d'entrée spécifique.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-114">A deterministic function always returns the same result when it is called with a specific set of input parameters.</span></span> <span data-ttu-id="b1bc2-115">Une fonction non déterministe peut retourner des résultats différents lorsqu'elle est appelée avec un jeu de paramètres d'entrée spécifique.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-115">A non-deterministic function may return different results when it is called with a specific set of input parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1bc2-116">Ne marquez pas une fonction comme étant déterministe si elle ne produit pas toujours les mêmes valeurs de sortie à partir des mêmes valeurs d'entrée et du même état de base de données.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-116">Do not mark a function as deterministic if the function does not always produces the same output values, given the same input values and the same database state.</span></span> <span data-ttu-id="b1bc2-117">Le marquage d'une fonction comme étant déterministe alors que cette dernière ne l'est pas vraiment peut provoquer une altération des vues indexées et des colonnes calculées.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-117">Marking a function as deterministic, when the function isn't truly deterministic can result in corrupted indexed views and computed columns.</span></span> <span data-ttu-id="b1bc2-118">Pour marquer une fonction comme déterministe, vous devez affecter la valeur « true » à la propriété `IsDeterministic`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-118">You mark a function as deterministic by setting the `IsDeterministic` property to true.</span></span>  
  
### <a name="table-valued-parameters"></a><span data-ttu-id="b1bc2-119">Paramètres table</span><span class="sxs-lookup"><span data-stu-id="b1bc2-119">Table-Valued Parameters</span></span>  
 <span data-ttu-id="b1bc2-120">Les paramètres table (types de tables définis par l'utilisateur et passés dans une procédure ou une fonction) offrent un moyen efficace pour passer plusieurs lignes de données au serveur.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-120">Table-valued parameters (TVPs), user-defined table types that are passed into a procedure or function, provide an efficient way to pass multiple rows of data to the server.</span></span> <span data-ttu-id="b1bc2-121">Ils procurent une fonctionnalité semblable aux tableaux de paramètres, mais offrent une meilleure souplesse et une intégration plus étroite à [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bc2-121">TVPs provide similar functionality to parameter arrays, but offer greater flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1bc2-122">Ils sont également susceptibles de générer de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-122">They also provide the potential for better performance.</span></span> <span data-ttu-id="b1bc2-123">Les paramètres table aident également à réduire le nombre d'allers-retours au serveur.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-123">TVPs also help reduce the number of round trips to the server.</span></span> <span data-ttu-id="b1bc2-124">Au lieu d'envoyer plusieurs demandes au serveur, comme avec une liste de paramètres scalaires, les données peuvent être envoyées au serveur en tant que paramètres table.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-124">Instead of sending multiple requests to the server, such as with a list of scalar parameters, data can be sent to the server as a TVP.</span></span> <span data-ttu-id="b1bc2-125">Un type de table défini par l'utilisateur ne peut pas être passé en tant que paramètre table à une fonction ou à une procédure stockée managée s'exécutant dans le processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ni être retourné à partir de ces dernières.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-125">A user-defined table type cannot be passed as a table-valued parameter to, or be returned from, a managed stored procedure or function executing in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="b1bc2-126">Pour plus d’informations sur TVP, consultez [utiliser des paramètres Table &#40;Moteur de base de données&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="b1bc2-126">For more information about TVPs, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
## <a name="example-of-a-clr-scalar-valued-function"></a><span data-ttu-id="b1bc2-127">Exemple de fonction scalaire CLR</span><span class="sxs-lookup"><span data-stu-id="b1bc2-127">Example of a CLR Scalar-Valued Function</span></span>  
 <span data-ttu-id="b1bc2-128">Voici une fonction scalaire simple qui accède à des données et renvoie une valeur entière :</span><span class="sxs-lookup"><span data-stu-id="b1bc2-128">Here is a simple SVF that accesses data and returns an integer value:</span></span>  
  
```csharp  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public class T  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static int ReturnOrderCount()  
    {  
        using (SqlConnection conn   
            = new SqlConnection("context connection=true"))  
        {  
            conn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
            return (int)cmd.ExecuteScalar();  
        }  
    }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public Class T  
    <SqlFunction(DataAccess:=DataAccessKind.Read)> _  
    Public Shared Function ReturnOrderCount() As Integer  
        Using conn As New SqlConnection("context connection=true")  
            conn.Open()  
            Dim cmd As New SqlCommand("SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
            Return CType(cmd.ExecuteScalar(), Integer)  
        End Using  
    End Function  
End Class  
```  
  
 <span data-ttu-id="b1bc2-129">La première ligne de code fait référence à `Microsoft.SqlServer.Server` afin d'accéder à des attributs et à `System.Data.SqlClient` afin d'accéder à l'espace de noms ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-129">The first line of code references `Microsoft.SqlServer.Server` to access attributes and `System.Data.SqlClient` to access the ADO.NET namespace.</span></span> <span data-ttu-id="b1bc2-130">(Cet espace de noms contient `SqlClient`, le fournisseur de données .NET Framework pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="b1bc2-130">(This namespace contains `SqlClient`, the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
 <span data-ttu-id="b1bc2-131">Ensuite, la fonction reçoit l'attribut personnalisé `SqlFunction`, qui se trouve dans l'espace de noms `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-131">Next, the function receives the `SqlFunction` custom attribute, which is found in the `Microsoft.SqlServer.Server` namespace.</span></span> <span data-ttu-id="b1bc2-132">L'attribut personnalisé indique si la fonction définie par l'utilisateur utilise le fournisseur in-process pour lire les données sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-132">The custom attribute indicates whether or not the user-defined function (UDF) uses the in-process provider to read data in the server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1bc2-133">n'autorise pas les fonctions définies par l'utilisateur à mettre à jour, insérer ou supprimer des données.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-133">does not allow UDFs to update, insert, or delete data.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1bc2-134">peut optimiser l'exécution d'une fonction définie par l'utilisateur qui n'utilise pas le fournisseur in-process.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-134">can optimize execution of a UDF that does not use the in-process provider.</span></span> <span data-ttu-id="b1bc2-135">Cela est indiqué en affectant la valeur `DataAccessKind` à `DataAccessKind.None`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-135">This is indicated by setting `DataAccessKind` to `DataAccessKind.None`.</span></span> <span data-ttu-id="b1bc2-136">Sur la ligne suivante, la méthode cible est une méthode statique publique (partagée dans Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="b1bc2-136">On the next line, the target method is a public static (shared in Visual Basic .NET).</span></span>  
  
 <span data-ttu-id="b1bc2-137">La classe `SqlContext`, située dans l'espace de noms `Microsoft.SqlServer.Server`, peut ensuite accéder à un objet `SqlCommand` avec une connexion à l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] déjà configurée.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-137">The `SqlContext` class, located in the `Microsoft.SqlServer.Server` namespace, can then access a `SqlCommand` object with a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is already set up.</span></span> <span data-ttu-id="b1bc2-138">Bien qu'il ne soit pas utilisé ici, le contexte de transaction actuel est également disponible par le biais de l'API `System.Transactions`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-138">Although not used here, the current transaction context is also available through the `System.Transactions` application programming interface (API).</span></span>  
  
 <span data-ttu-id="b1bc2-139">La plupart des lignes de code dans le corps de la fonction doivent sembler familières aux développeurs ayant écrit des applications clientes qui utilisent les types de l'espace de noms `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-139">Most of the lines of code in the function body should look familiar to developers who have written client applications that use the types found in the `System.Data.SqlClient` namespace.</span></span>  
  
 <span data-ttu-id="b1bc2-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="b1bc2-140">[C#]</span></span>  
  
```  
using(SqlConnection conn = new SqlConnection("context connection=true"))   
{  
   conn.Open();  
   SqlCommand cmd = new SqlCommand(  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn);  
   return (int) cmd.ExecuteScalar();  
}    
```  
  
 <span data-ttu-id="b1bc2-141">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="b1bc2-141">[Visual Basic]</span></span>  
  
```  
Using conn As New SqlConnection("context connection=true")  
   conn.Open()  
   Dim cmd As New SqlCommand( _  
        "SELECT COUNT(*) AS 'Order Count' FROM SalesOrderHeader", conn)  
   Return CType(cmd.ExecuteScalar(), Integer)  
End Using  
```  
  
 <span data-ttu-id="b1bc2-142">Le texte de commande approprié est spécifié en initialisant l'objet `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-142">The appropriate command text is specified by initializing the `SqlCommand` object.</span></span> <span data-ttu-id="b1bc2-143">L'exemple précédent compte le nombre de lignes dans la table `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-143">The previous example counts the number of rows in table `SalesOrderHeader`.</span></span> <span data-ttu-id="b1bc2-144">Ensuite, la méthode `ExecuteScalar` de l'objet `cmd` est appelée.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-144">Next, the `ExecuteScalar` method of the `cmd` object is called.</span></span> <span data-ttu-id="b1bc2-145">Elle retourne une valeur de type `int` basée sur la requête.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-145">This returns a value of type `int` based on the query.</span></span> <span data-ttu-id="b1bc2-146">Pour finir, le nombre de commandes (« order count ») est retourné à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-146">Finally, the order count is returned to the caller.</span></span>  
  
 <span data-ttu-id="b1bc2-147">Si ce code est enregistré dans un fichier nommé FirstUdf.cs, il peut être compilé dans un assembly comme suit :</span><span class="sxs-lookup"><span data-stu-id="b1bc2-147">If this code is saved in a file called FirstUdf.cs, it could be compiled into as assembly as follows:</span></span>  
  
 <span data-ttu-id="b1bc2-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="b1bc2-148">[C#]</span></span>  
  
```  
csc.exe /t:library /out:FirstUdf.dll FirstUdf.cs   
```  
  
 <span data-ttu-id="b1bc2-149">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="b1bc2-149">[Visual Basic]</span></span>  
  
```  
vbc.exe /t:library /out:FirstUdf.dll FirstUdf.vb  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b1bc2-150">`/t:library` indique qu'une bibliothèque, plutôt qu'un fichier exécutable, doit être produite.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-150">`/t:library` indicates that a library, rather than an executable, should be produced.</span></span> <span data-ttu-id="b1bc2-151">Les fichiers exécutables ne peuvent pas être inscrits dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bc2-151">Executables cannot be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b1bc2-152">Les objets de base de données Visual C++ compilés avec `/clr:pure` ne sont pas pris en charge pour l'exécution sur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1bc2-152">Visual C++ database objects compiled with `/clr:pure` are not supported for execution on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b1bc2-153">Il s'agit par exemple d'objets de base de données tels que des fonctions scalaires.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-153">For example, such database objects include scalar-valued functions.</span></span>  
  
 <span data-ttu-id="b1bc2-154">Voici la requête [!INCLUDE[tsql](../../includes/tsql-md.md)] et un exemple d'appel pour inscrire l'assembly et la fonction définie par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="b1bc2-154">The [!INCLUDE[tsql](../../includes/tsql-md.md)] query and a sample invocation to register the assembly and UDF are:</span></span>  
  
```  
CREATE ASSEMBLY FirstUdf FROM 'FirstUdf.dll';  
GO  
  
CREATE FUNCTION CountSalesOrderHeader() RETURNS INT   
AS EXTERNAL NAME FirstUdf.T.ReturnOrderCount;   
GO  
  
SELECT dbo.CountSalesOrderHeader();  
GO  
  
```  
  
 <span data-ttu-id="b1bc2-155">Notez qu'il n'est pas obligatoire que le nom de fonction tel qu'exposé dans [!INCLUDE[tsql](../../includes/tsql-md.md)] corresponde au nom de la méthode statique publique cible.</span><span class="sxs-lookup"><span data-stu-id="b1bc2-155">Note that the function name as exposed in [!INCLUDE[tsql](../../includes/tsql-md.md)] does not need to match the name of the target public static method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1bc2-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1bc2-156">See Also</span></span>  
 <span data-ttu-id="b1bc2-157">[Mappage des données de paramètres CLR](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span><span class="sxs-lookup"><span data-stu-id="b1bc2-157">[Mapping CLR Parameter Data](../clr-integration-database-objects-types-net-framework/mapping-clr-parameter-data.md) </span></span>  
 <span data-ttu-id="b1bc2-158">[Vue d’ensemble des attributs personnalisés d’intégration du CLR](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="b1bc2-158">[Overview of CLR Integration Custom Attributes](../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md) </span></span>  
 <span data-ttu-id="b1bc2-159">[Fonctions définies par l’utilisateur](../user-defined-functions/user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="b1bc2-159">[User-Defined Functions](../user-defined-functions/user-defined-functions.md) </span></span>  
 [<span data-ttu-id="b1bc2-160">Accès aux données à partir d'objets de base de données CLR</span><span class="sxs-lookup"><span data-stu-id="b1bc2-160">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
