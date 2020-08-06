---
title: Codage de types définis par l’utilisateur | Microsoft Docs
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
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602167"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="35b3d-102">Codage de types définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="35b3d-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="35b3d-103">Lorsque vous codez votre définition de type défini par l'utilisateur (UDT, User-Defined Type), vous devez implémenter différentes fonctionnalités, selon que vous implémentez le type défini par l'utilisateur comme classe ou comme structure, et selon les options de format et de sérialisation que vous avez choisies.</span><span class="sxs-lookup"><span data-stu-id="35b3d-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="35b3d-104">L'exemple de cette section illustre l'implémentation d'un type défini par l'utilisateur `Point` en tant que `struct` (ou `Structure` dans Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="35b3d-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="35b3d-105">Le type défini par l'utilisateur `Point` consiste en coordonnées X et Y implémentées comme procédures de propriété.</span><span class="sxs-lookup"><span data-stu-id="35b3d-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="35b3d-106">Les espaces de noms suivants sont requis lors de la définition d'un type défini par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="35b3d-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="35b3d-107">L'espace de noms `Microsoft.SqlServer.Server` contient les objets requis pour différents attributs de votre type défini par l'utilisateur et l'espace de noms `System.Data.SqlTypes` contient les classes qui représentent les types de données natifs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibles à l'assembly.</span><span class="sxs-lookup"><span data-stu-id="35b3d-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="35b3d-108">Il se peut bien sûr que le bon fonctionnement de votre assembly requiert des espaces de noms supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="35b3d-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="35b3d-109">Le type défini par l'utilisateur `Point` utilise également l'espace de noms `System.Text` pour manipuler des chaînes.</span><span class="sxs-lookup"><span data-stu-id="35b3d-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35b3d-110">Les objets de base de données Visual C++, comme les types définis par l'utilisateur, compilés avec `/clr:pure` ne sont pas pris en charge pour l'exécution.</span><span class="sxs-lookup"><span data-stu-id="35b3d-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="35b3d-111">Spécification d'attributs</span><span class="sxs-lookup"><span data-stu-id="35b3d-111">Specifying Attributes</span></span>  
 <span data-ttu-id="35b3d-112">Les attributs déterminent la façon dont la sérialisation est utilisée pour construire la représentation de stockage des types définis par l'utilisateur et pour transmettre des types définis par l'utilisateur par valeur au client.</span><span class="sxs-lookup"><span data-stu-id="35b3d-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="35b3d-113">L'attribut `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` est requis.</span><span class="sxs-lookup"><span data-stu-id="35b3d-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="35b3d-114">L'attribut `Serializable` est facultatif.</span><span class="sxs-lookup"><span data-stu-id="35b3d-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="35b3d-115">Vous pouvez également spécifier l'attribut `Microsoft.SqlServer.Server.SqlFacetAttribute` pour fournir des informations à propos du type de retour d'un type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="35b3d-116">Pour plus d’informations, consultez [Attributs personnalisés pour les routines CLR](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)</span><span class="sxs-lookup"><span data-stu-id="35b3d-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="35b3d-117">Attributs du type défini par l'utilisateur Point</span><span class="sxs-lookup"><span data-stu-id="35b3d-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="35b3d-118">L'attribut `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` définit le format de stockage pour le type défini par l'utilisateur `Point` à `Native`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="35b3d-119">`IsByteOrdered` a la valeur `true`, ce qui garantit que les résultats des comparaisons dans SQL Server sont les mêmes que si les comparaisons avaient eu lieu dans le code managé.</span><span class="sxs-lookup"><span data-stu-id="35b3d-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="35b3d-120">Le type défini par l'utilisateur implémente l'interface `System.Data.SqlTypes.INullable` pour rendre le type défini par l'utilisateur compatible avec la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="35b3d-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="35b3d-121">Le fragment de code suivant montre les attributs pour le type défini par l'utilisateur `Point`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="35b3d-122">Implémentation de la possibilité de valeur NULL</span><span class="sxs-lookup"><span data-stu-id="35b3d-122">Implementing Nullability</span></span>  
 <span data-ttu-id="35b3d-123">En plus de spécifier correctement les attributs pour vos assemblys, votre type défini par l'utilisateur doit également prendre en charge la possibilité de valeur Null.</span><span class="sxs-lookup"><span data-stu-id="35b3d-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="35b3d-124">Les types définis par l'utilisateur chargés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont compatibles avec la valeur Null, mais pour reconnaître une valeur Null, le type défini par l'utilisateur doit implémenter l'interface `System.Data.SqlTypes.INullable`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="35b3d-125">Vous devez créer une propriété nommée `IsNull`, nécessaire pour déterminer si une valeur est Null dans le code CLR.</span><span class="sxs-lookup"><span data-stu-id="35b3d-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="35b3d-126">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trouve une instance Null d'un type défini par l'utilisateur, celui-ci est rendu persistant à l'aide de méthodes de gestion de valeur Null ordinaires.</span><span class="sxs-lookup"><span data-stu-id="35b3d-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="35b3d-127">Le serveur ne perd pas de temps à sérialiser ou désérialiser le type défini par l'utilisateur si cela n'est pas nécessaire et il ne gaspille pas d'espace pour stocker un type défini par l'utilisateur Null.</span><span class="sxs-lookup"><span data-stu-id="35b3d-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="35b3d-128">Ce contrôle des valeurs Null est effectué chaque fois qu'un type défini par l'utilisateur est rapporté du CLR, ce qui signifie que l'utilisation de la construction [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL pour vérifier le caractère Null des types définis par l'utilisateur doit toujours fonctionner.</span><span class="sxs-lookup"><span data-stu-id="35b3d-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="35b3d-129">La propriété `IsNull` est également utilisée par le serveur pour tester si une instance est Null.</span><span class="sxs-lookup"><span data-stu-id="35b3d-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="35b3d-130">Une fois que le serveur a détermine que le type défini par l'utilisateur est Null, il peut utiliser sa gestion Null native.</span><span class="sxs-lookup"><span data-stu-id="35b3d-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="35b3d-131">La méthode `get()` de `IsNull` ne représente en aucune façon un cas spécial.</span><span class="sxs-lookup"><span data-stu-id="35b3d-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="35b3d-132">Si une variable `Point``@p` est `Null`, `@p.IsNull` est évalué par défaut à « Null », et non à « 1 ».</span><span class="sxs-lookup"><span data-stu-id="35b3d-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="35b3d-133">Cela est dû au fait que l'attribut `SqlMethod(OnNullCall)` de la méthode `IsNull get()` a par défaut la valeur « false ».</span><span class="sxs-lookup"><span data-stu-id="35b3d-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="35b3d-134">L'objet étant `Null`, lorsque la propriété est demandée, l'objet n'est pas désérialisé, la méthode n'est pas appelée et une valeur par défaut de « Null » est renvoyée.</span><span class="sxs-lookup"><span data-stu-id="35b3d-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="35b3d-135">Exemple</span><span class="sxs-lookup"><span data-stu-id="35b3d-135">Example</span></span>  
 <span data-ttu-id="35b3d-136">Dans l'exemple suivant, la variable `is_Null` est privée et contient l'état de Null pour l'instance du type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="35b3d-137">Votre code doit maintenir une valeur appropriée pour `is_Null`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="35b3d-138">Le type défini par l'utilisateur doit également avoir une propriété statique nommée `Null` qui retourne une instance de valeur Null du type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="35b3d-139">Cela permet au type défini par l'utilisateur de renvoyer une valeur Null si l'instance est en effet Null dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="35b3d-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="35b3d-140">Comparaison de IS NULL et de IsNull</span><span class="sxs-lookup"><span data-stu-id="35b3d-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="35b3d-141">Considérez une table qui contient le schéma Points(id int, location Point), où `Point` est un type défini par l'utilisateur CLR, et les requêtes suivantes :</span><span class="sxs-lookup"><span data-stu-id="35b3d-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="35b3d-142">Les deux requêtes retournent les ID de points avec des emplacements non-`Null`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="35b3d-143">Dans la Requête 1, la gestion de Null normale est utilisée et là aucune désérialisation du type défini par l'utilisateur n'est requise.</span><span class="sxs-lookup"><span data-stu-id="35b3d-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="35b3d-144">La Requête 2, en revanche, doit désérialiser chaque objet non-`Null` et appeler le CLR pour obtenir la valeur de la propriété `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="35b3d-145">Il est clair que l'utilisation de `IS NULL` donnera de meilleures performances et il ne devrait jamais y avoir de raison de lire la propriété `IsNull` d'un type défini par l'utilisateur à partir de code [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3d-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="35b3d-146">Par conséquent, quelle est l'utilité de la propriété `IsNull` ?</span><span class="sxs-lookup"><span data-stu-id="35b3d-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="35b3d-147">En premier lieu, elle est nécessaire pour déterminer si une valeur est `Null` à partir du code CLR.</span><span class="sxs-lookup"><span data-stu-id="35b3d-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="35b3d-148">Ensuite, le serveur a besoin d'une méthode pour tester si une instance est `Null` ; il utilise par conséquent cette propriété.</span><span class="sxs-lookup"><span data-stu-id="35b3d-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="35b3d-149">Après avoir déterminé que l'instance est `Null`, il peut utiliser sa gestion Null native pour la gérer.</span><span class="sxs-lookup"><span data-stu-id="35b3d-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="35b3d-150">Implémentation de la méthode Parse</span><span class="sxs-lookup"><span data-stu-id="35b3d-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="35b3d-151">Les méthodes `Parse` et `ToString` permettent d'effectuer des conversions vers et à partir de représentations de chaîne du type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="35b3d-152">La méthode `Parse` permet de convertir une chaîne en un type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="35b3d-153">Elle doit être déclarée comme `static` (ou `Shared` dans Visual Basic) et accepter un paramètre de type `System.Data.SqlTypes.SqlString`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="35b3d-154">Le code suivant implémente la méthode `Parse` pour le type défini par l'utilisateur `Point`, qui sépare les coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="35b3d-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="35b3d-155">La méthode `Parse` a un argument unique de type `System.Data.SqlTypes.SqlString` et suppose que les valeurs X et Y sont fournies en tant que chaîne délimitée par des virgules.</span><span class="sxs-lookup"><span data-stu-id="35b3d-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="35b3d-156">L'affectation de la valeur `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` à l'attribut `false` empêche la méthode `Parse` d'être appelée à partir d'une instance Null de Point.</span><span class="sxs-lookup"><span data-stu-id="35b3d-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="35b3d-157">Implémentation de la méthode ToString</span><span class="sxs-lookup"><span data-stu-id="35b3d-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="35b3d-158">La méthode `ToString` convertit le type défini par l'utilisateur `Point` en valeur de chaîne.</span><span class="sxs-lookup"><span data-stu-id="35b3d-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="35b3d-159">Dans ce cas, la chaîne « NULL » est retournée pour une instance Null du type `Point`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="35b3d-160">La méthode `ToString` inverse la méthode `Parse` en utilisant un `System.Text.StringBuilder` pour retourner un `System.String` délimité par des virgules qui consiste en valeurs de coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="35b3d-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="35b3d-161">Étant donné que **InvokeIfReceiverIsNull** prend par défaut la valeur false, la vérification d’une instance null de `Point` est inutile.</span><span class="sxs-lookup"><span data-stu-id="35b3d-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="35b3d-162">Exposition de propriétés de type défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="35b3d-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="35b3d-163">Le type défini par l'utilisateur `Point` expose des coordonnées X et Y implémentées comme propriétés en lecture-écriture publiques de type `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="35b3d-164">Validation de valeurs de type défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="35b3d-164">Validating UDT Values</span></span>  
 <span data-ttu-id="35b3d-165">Lors de l'utilisation de données de type défini par l'utilisateur, le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] convertit automatiquement les valeurs binaires en valeurs de type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="35b3d-166">Ce processus de conversion nécessite de vérifier que les valeurs sont adaptées au format de sérialisation du type et de s'assurer que la valeur peut être désérialisée correctement.</span><span class="sxs-lookup"><span data-stu-id="35b3d-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="35b3d-167">Cela permet de garantir que la valeur peut être reconvertie au format binaire.</span><span class="sxs-lookup"><span data-stu-id="35b3d-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="35b3d-168">Dans le cas des types définis par l'utilisateur ordonnés par octet, cela permet de s'assurer également que la valeur binaire résultante correspond à la valeur binaire d'origine.</span><span class="sxs-lookup"><span data-stu-id="35b3d-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="35b3d-169">Cela empêche des valeurs non valides d'être rendues persistantes dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="35b3d-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="35b3d-170">Dans certains cas, ce niveau de contrôle peut être inadéquat.</span><span class="sxs-lookup"><span data-stu-id="35b3d-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="35b3d-171">Une validation supplémentaire peut être requise lorsque les valeurs de type défini par l'utilisateur doivent se trouver dans un domaine ou une plage attendu(e).</span><span class="sxs-lookup"><span data-stu-id="35b3d-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="35b3d-172">Par exemple, un type défini par l'utilisateur qui implémente une date peut exiger que la valeur de jour soit un nombre positif compris dans une certaine plage de valeurs valides.</span><span class="sxs-lookup"><span data-stu-id="35b3d-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="35b3d-173">La propriété `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` de l'attribut `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` vous permet de fournir le nom d'une méthode de validation exécutée par le serveur lorsque des données sont assignées à un type défini par l'utilisateur ou converties en un type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="35b3d-174">`ValidationMethodName` est également appelé pendant l'exécution de l'utilitaire bcp et des opérations BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, requête distribuée et RPC (Remote Procedure Call) TDS (Tabular Data Stream).</span><span class="sxs-lookup"><span data-stu-id="35b3d-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="35b3d-175">La valeur par défaut de `ValidationMethodName` est Null, ce qui indique qu'il n'y a aucune méthode de validation.</span><span class="sxs-lookup"><span data-stu-id="35b3d-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="35b3d-176">Exemple</span><span class="sxs-lookup"><span data-stu-id="35b3d-176">Example</span></span>  
 <span data-ttu-id="35b3d-177">Le fragment de code suivant illustre la déclaration de la classe `Point`, qui spécifie un `ValidationMethodName` de `ValidatePoint`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="35b3d-178">Si une méthode de validation est spécifiée, elle doit avoir une signature qui ressemble au fragment de code suivant.</span><span class="sxs-lookup"><span data-stu-id="35b3d-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="35b3d-179">La méthode de validation peut avoir une portée quelconque et doit retourner `true` si la valeur est valide et `false` dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="35b3d-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="35b3d-180">Si la méthode retourne `false` ou lève une exception, la valeur est traitée comme non valide et une erreur est déclenchée.</span><span class="sxs-lookup"><span data-stu-id="35b3d-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="35b3d-181">Dans l'exemple ci-dessous, le code autorise uniquement des valeurs de zéro ou plus pour les coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="35b3d-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="35b3d-182">Limitations de méthode de validation</span><span class="sxs-lookup"><span data-stu-id="35b3d-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="35b3d-183">Le serveur appelle la méthode de validation lorsqu'il effectue des conversions, et non lorsque des données sont insérées en définissant des propriétés individuelles ou à l'aide d'une instruction INSERT [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3d-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="35b3d-184">Vous devez appeler explicitement la méthode de validation à partir des accesseurs set de propriété et la `Parse` méthode si vous souhaitez que la méthode de validation s’exécute dans toutes les situations.</span><span class="sxs-lookup"><span data-stu-id="35b3d-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="35b3d-185">Cela n'est pas obligatoire, et dans certains cas peut ne pas être souhaitable.</span><span class="sxs-lookup"><span data-stu-id="35b3d-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="35b3d-186">Exemple de validation Parse</span><span class="sxs-lookup"><span data-stu-id="35b3d-186">Parse Validation Example</span></span>  
 <span data-ttu-id="35b3d-187">Pour vous assurer que la `ValidatePoint` méthode est appelée dans la `Point` classe, vous devez l’appeler à partir de la `Parse` méthode et des procédures de propriété qui définissent les valeurs des coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="35b3d-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="35b3d-188">Le fragment de code suivant montre comment appeler la `ValidatePoint` méthode de validation à partir de la `Parse` fonction.</span><span class="sxs-lookup"><span data-stu-id="35b3d-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="35b3d-189">Exemple de validation de propriété</span><span class="sxs-lookup"><span data-stu-id="35b3d-189">Property Validation Example</span></span>  
 <span data-ttu-id="35b3d-190">Le fragment de code suivant montre comment appeler la `ValidatePoint` méthode de validation à partir des procédures de propriété qui définissent les coordonnées X et Y.</span><span class="sxs-lookup"><span data-stu-id="35b3d-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="35b3d-191">Codage de méthodes UDT</span><span class="sxs-lookup"><span data-stu-id="35b3d-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="35b3d-192">Lors du codage de méthodes UDT, considérez si l'algorithme utilisé pourrait changer avec le temps.</span><span class="sxs-lookup"><span data-stu-id="35b3d-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="35b3d-193">Si c'est le cas, vous pourriez envisager de créer une classe séparée pour les méthodes utilisées par votre type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="35b3d-194">Si l'algorithme change, vous pouvez recompiler la classe avec le nouveau code et charger l'assembly dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sans affecter le type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="35b3d-195">Dans de nombreux cas, les types définis par l'utilisateur peuvent être rechargés à l'aide de l'instruction  [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY, mais cela pourrait provoquer des problèmes avec les données existantes.</span><span class="sxs-lookup"><span data-stu-id="35b3d-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="35b3d-196">Par exemple, le `Currency` type défini par l’utilisateur (UDT) inclus dans l’exemple de base de données **AdventureWorks** utilise une fonction **ConvertCurrency** pour convertir les valeurs monétaires, qui est implémentée dans une classe distincte.</span><span class="sxs-lookup"><span data-stu-id="35b3d-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="35b3d-197">Il est possible que les algorithmes de conversion puissent changer de manière imprévisible dans le futur, ou que de nouvelles fonctionnalités soient requises.</span><span class="sxs-lookup"><span data-stu-id="35b3d-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="35b3d-198">La séparation de la fonction **ConvertCurrency** de l' `Currency` implémentation UDT offre une plus grande souplesse lors de la planification des modifications ultérieures.</span><span class="sxs-lookup"><span data-stu-id="35b3d-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="35b3d-199">Exemple</span><span class="sxs-lookup"><span data-stu-id="35b3d-199">Example</span></span>  
 <span data-ttu-id="35b3d-200">La `Point` classe contient trois méthodes simples pour le calcul de la distance : **distance**, **DistanceFrom** et **DistanceFromXY**.</span><span class="sxs-lookup"><span data-stu-id="35b3d-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="35b3d-201">Chacune retourne un `double` qui calcule la distance de `Point` à zéro, la distance d'un point spécifié à `Point` et la distance des coordonnées X et Y spécifiées à `Point`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="35b3d-202">**Distance** et **DistanceFrom** chaque appel à **DistanceFromXY**, et montrent comment utiliser différents arguments pour chaque méthode.</span><span class="sxs-lookup"><span data-stu-id="35b3d-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="35b3d-203">Utilisation d'attributs SqlMethod</span><span class="sxs-lookup"><span data-stu-id="35b3d-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="35b3d-204">La classe `Microsoft.SqlServer.Server.SqlMethodAttribute` fournit des attributs personnalisés pouvant être utilisés pour marquer des définitions de méthode afin de spécifier le déterminisme, pour le comportement d'appel Null, et de spécifier si une méthode est un mutateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="35b3d-205">Les valeurs par défaut de ces propriétés sont assumées et l'attribut personnalisé est utilisé uniquement lorsqu'une valeur non définie par défaut est exigée.</span><span class="sxs-lookup"><span data-stu-id="35b3d-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35b3d-206">La classe `SqlMethodAttribute` hérite de la classe `SqlFunctionAttribute` ; par conséquent, `SqlMethodAttribute` hérite des champs `FillRowMethodName` et `TableDefinition` de `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="35b3d-207">Cela implique qu'il est possible d'écrire une méthode table, ce qui n'est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="35b3d-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="35b3d-208">La méthode Compile et l’assembly est déployé, mais une erreur sur le `IEnumerable` type de retour est levée au moment de l’exécution avec le message suivant : « la méthode, la propriété ou le champ « » \<name> dans la classe « \<class> » dans l’assembly « \<assembly> » possède un type de retour non valide.»</span><span class="sxs-lookup"><span data-stu-id="35b3d-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="35b3d-209">Le tableau suivant décrit quelques-unes des propriétés `Microsoft.SqlServer.Server.SqlMethodAttribute` pertinentes qui peuvent être utilisées dans les méthodes UDT et répertorie leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="35b3d-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="35b3d-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="35b3d-210">DataAccess</span></span>  
 <span data-ttu-id="35b3d-211">Indique si la fonction implique l'accès aux données utilisateur stockées dans l'instance locale de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3d-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="35b3d-212">La valeur par défaut est `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="35b3d-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="35b3d-213">IsDeterministic</span></span>  
 <span data-ttu-id="35b3d-214">Indique si la fonction produit les mêmes valeurs de sortie étant donné les mêmes valeurs d'entrée et le même état de la base de données.</span><span class="sxs-lookup"><span data-stu-id="35b3d-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="35b3d-215">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="35b3d-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="35b3d-216">IsMutator</span></span>  
 <span data-ttu-id="35b3d-217">Indique si la méthode provoque une modification d'état dans l'instance de type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="35b3d-218">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="35b3d-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="35b3d-219">IsPrecise</span></span>  
 <span data-ttu-id="35b3d-220">Indique si la fonction implique des calculs imprécis, tels que des opérations à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="35b3d-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="35b3d-221">La valeur par défaut est `false`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="35b3d-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="35b3d-222">OnNullCall</span></span>  
 <span data-ttu-id="35b3d-223">Indique si la méthode est appelée lorsque des arguments d'entrée de référence nulle sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="35b3d-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="35b3d-224">La valeur par défaut est `true`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="35b3d-225">Exemple</span><span class="sxs-lookup"><span data-stu-id="35b3d-225">Example</span></span>  
 <span data-ttu-id="35b3d-226">La propriété `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` vous permet de marquer une méthode qui autorise une modification de l'état d'une instance d'un type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="35b3d-227">ne vous permet pas de définir deux propriétés de type défini par l'utilisateur dans la clause SET d'une instruction UPDATE.</span><span class="sxs-lookup"><span data-stu-id="35b3d-227">does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="35b3d-228">Toutefois, vous pouvez avoir une méthode marquée comme mutateur qui modifie les deux membres.</span><span class="sxs-lookup"><span data-stu-id="35b3d-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="35b3d-229">Les méthodes mutateurs ne sont pas autorisés dans les requêtes.</span><span class="sxs-lookup"><span data-stu-id="35b3d-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="35b3d-230">Elles peuvent être appelées uniquement dans les instructions d'assignation ou les instructions de modification de données.</span><span class="sxs-lookup"><span data-stu-id="35b3d-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="35b3d-231">Si une méthode marquée comme mutateur ne retourne pas `void` (ou n'est pas un `Sub` dans Visual Basic), CREATE TYPE échoue avec une erreur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="35b3d-232">L'instruction suivante suppose l'existence d'un type défini par l'utilisateur `Triangles` qui a une méthode `Rotate`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="35b3d-233">L'instruction UPDATE [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante appelle la méthode `Rotate` :</span><span class="sxs-lookup"><span data-stu-id="35b3d-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="35b3d-234">La méthode `Rotate` est décorée avec le paramètre d'attribut `SqlMethod``IsMutator` à `true` afin que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puisse marquer la méthode comme méthode mutateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="35b3d-235">Le code affecte également la valeur `OnNullCall` à `false`, ce qui indique au serveur que la méthode retourne une référence Null (`Nothing` dans Visual Basic) si l'un des paramètres d'entrée est une référence Null.</span><span class="sxs-lookup"><span data-stu-id="35b3d-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="35b3d-236">Implémentation d'un type défini par l'utilisateur avec un format défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="35b3d-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="35b3d-237">Lors de l'implémentation d'un type défini par l'utilisateur avec un format défini par l'utilisateur, vous devez implémenter des méthodes `Read` et `Write` qui implémentent l'interface Microsoft.SqlServer.Server.IBinarySerialize pour gérer la sérialisation et désérialisation des données UDT.</span><span class="sxs-lookup"><span data-stu-id="35b3d-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="35b3d-238">Vous devez également spécifier la propriété `MaxByteSize` de l'attribut `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="35b3d-239">Le type défini par l'utilisateur Currency</span><span class="sxs-lookup"><span data-stu-id="35b3d-239">The Currency UDT</span></span>  
 <span data-ttu-id="35b3d-240">Le type défini par l'utilisateur `Currency` est fourni avec les exemples de CLR qui peuvent être installés avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], à compter de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3d-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="35b3d-241">Le type défini par l'utilisateur `Currency` prend en charge la gestion des sommes d'argent dans le système monétaire d'une culture particulière.</span><span class="sxs-lookup"><span data-stu-id="35b3d-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="35b3d-242">Vous devez définir deux champs : un `string` pour `CultureInfo`, qui spécifie qui a publié la monnaie (en-us, par exemple) et un `decimal` pour `CurrencyValue`, la somme d'argent.</span><span class="sxs-lookup"><span data-stu-id="35b3d-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="35b3d-243">Bien qu'il ne soit pas utilisé par le serveur pour effectuer des comparaisons, le type défini par l'utilisateur `Currency` implémente l'interface `System.IComparable`, qui expose une méthode unique, `System.IComparable.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="35b3d-244">Celle-ci est utilisée du côté client dans les situations où il est souhaitable de comparer ou d'ordonner précisément des valeurs monétaire dans des cultures.</span><span class="sxs-lookup"><span data-stu-id="35b3d-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="35b3d-245">Le code qui s'exécute dans le CLR compare la culture séparément de la valeur monétaire.</span><span class="sxs-lookup"><span data-stu-id="35b3d-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="35b3d-246">Pour le code [!INCLUDE[tsql](../../includes/tsql-md.md)], les actions suivantes déterminent la comparaison :</span><span class="sxs-lookup"><span data-stu-id="35b3d-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="35b3d-247">Affectez la valeur « true » à l'attribut `IsByteOrdered`, ce qui indique à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qu'il faut utiliser la représentation binaire persistante sur disque à des fins de comparaison.</span><span class="sxs-lookup"><span data-stu-id="35b3d-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="35b3d-248">Utilisez la méthode `Write` pour le type défini par l'utilisateur `Currency` afin de déterminer la façon dont il est rendu persistant sur disque et par conséquent la façon dont les valeurs UDT sont comparées et ordonnées pour les opérations [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35b3d-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="35b3d-249">Enregistrez le type défini par l'utilisateur `Currency` à l'aide du format binaire suivant :</span><span class="sxs-lookup"><span data-stu-id="35b3d-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="35b3d-250">Enregistrez la culture en tant que chaîne encodée UTF-16 pour les octets 0-19, avec un remplissage à droite avec des caractères Null.</span><span class="sxs-lookup"><span data-stu-id="35b3d-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="35b3d-251">Utilisez les octets 20 et plus pour contenir la valeur décimale de la monnaie.</span><span class="sxs-lookup"><span data-stu-id="35b3d-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="35b3d-252">L'objectif du remplissage est de s'assurer que la culture est complètement séparée de la valeur monétaire, de sorte que lorsque deux types définis par l'utilisateur sont comparés dans le code [!INCLUDE[tsql](../../includes/tsql-md.md)], les octets de culture soient comparés à des octets de culture et les valeurs d'octets de monnaie soient comparées à des valeurs d'octets de monnaie.</span><span class="sxs-lookup"><span data-stu-id="35b3d-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="35b3d-253">Pour obtenir la liste complète du code pour le type défini par l’utilisateur `Currency` , suivez les instructions d’installation des exemples CLR dans [SQL Server moteur de base de données exemples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="35b3d-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="35b3d-254">Attributs Currency</span><span class="sxs-lookup"><span data-stu-id="35b3d-254">Currency Attributes</span></span>  
 <span data-ttu-id="35b3d-255">Le type défini par l'utilisateur `Currency` est défini avec les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="35b3d-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="35b3d-256">Création de méthodes Read et Write avec IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="35b3d-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="35b3d-257">Lorsque vous choisissez le format de sérialisation `UserDefined`, vous devez également implémenter l'interface `IBinarySerialize` et créer vos propres méthodes `Read` et `Write`.</span><span class="sxs-lookup"><span data-stu-id="35b3d-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="35b3d-258">Les procédures suivantes du type défini par l'utilisateur `Currency` utilisent `System.IO.BinaryReader` et `System.IO.BinaryWriter` pour lire et écrire dans le type défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35b3d-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="35b3d-259">Pour obtenir la liste complète du code pour le type défini par l’utilisateur `Currency` , consultez [SQL Server moteur de base de données des exemples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="35b3d-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b3d-260">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35b3d-260">See Also</span></span>  
 [<span data-ttu-id="35b3d-261">Création d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="35b3d-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
