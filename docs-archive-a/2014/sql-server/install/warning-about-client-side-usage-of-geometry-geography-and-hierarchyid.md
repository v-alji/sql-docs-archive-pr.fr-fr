---
title: Avertissement concernant l’utilisation côté client de GEOMETRy, GEOGRAPHY et HIERARCHYID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604857"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="a80bc-102">Avertissement sur l'utilisation du côté client de GEOMETRY, de la GÉOGRAPHIE et du HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="a80bc-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="a80bc-103">L’assembly **Microsoft.SqlServer.Types.dll**, qui contient les types de données spatiales, a été mis à niveau de la version 10,0 vers la version 11,0.</span><span class="sxs-lookup"><span data-stu-id="a80bc-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="a80bc-104">Les applications personnalisées qui font référence à cet assembly peuvent échouer lorsque certaines conditions sont vraies.</span><span class="sxs-lookup"><span data-stu-id="a80bc-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a80bc-105">Composant</span><span class="sxs-lookup"><span data-stu-id="a80bc-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a80bc-106">Description</span><span class="sxs-lookup"><span data-stu-id="a80bc-106">Description</span></span>  
 <span data-ttu-id="a80bc-107">L’assembly **Microsoft.SqlServer.Types.dll**, qui contient les types de données spatiales, a été mis à niveau de la version 10,0 vers la version 11,0.</span><span class="sxs-lookup"><span data-stu-id="a80bc-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="a80bc-108">Les applications personnalisées qui font référence à cet assembly peuvent échouer lorsque les conditions suivantes sont remplies.</span><span class="sxs-lookup"><span data-stu-id="a80bc-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="a80bc-109">Lorsque vous déplacez une application personnalisée à partir d’un ordinateur sur lequel [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] est installé sur un ordinateur sur lequel seul [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] est installé, l’application échoue, car la version référencée 10,0 de l’assembly **SqlTypes** n’est pas présente.</span><span class="sxs-lookup"><span data-stu-id="a80bc-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="a80bc-110">Ce message d'erreur peut s'afficher : `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="a80bc-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="a80bc-111">Lorsque vous référencez l’assembly **SqlTypes** version 11,0 et que la version 10,0 est également installée, le message d’erreur suivant peut s’afficher :`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="a80bc-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="a80bc-112">Quand vous référencez la version 11,0 de l’assembly **SqlTypes** à partir d’une application personnalisée qui cible .net 3,5, 4 ou 4,5, l’application échoue, car SqlClient par conception charge la version 10,0 de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="a80bc-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="a80bc-113">Cette erreur se produit lorsque l'application appelle l'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a80bc-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="a80bc-114">méthode `GetValue` de la classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a80bc-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a80bc-115">méthode `GetValues` de la classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a80bc-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a80bc-116">opérateur d'index de crochets [] de la classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a80bc-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a80bc-117">méthode `ExecuteScalar` de la classe `SqlCommand`</span><span class="sxs-lookup"><span data-stu-id="a80bc-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a80bc-118">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a80bc-118">Corrective Action</span></span>  
 <span data-ttu-id="a80bc-119">Vous pouvez contourner ce problème en utilisant l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a80bc-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="a80bc-120">Vous pouvez contourner ce problème dans votre code en appelant la méthode `GetSqlBytes`, au lieu des méthodes Get répertoriées ci-dessus, pour extraire les types de systèmes CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="a80bc-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="a80bc-121">Vous pouvez contourner ce problème en utilisant la redirection d'assembly dans le fichier de configuration de l'application, comme le montre l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="a80bc-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="a80bc-122">Vous pouvez contourner ce problème dans votre chaîne de connexion en spécifiant la valeur « SQL Server 2012 » pour que de l'attribut « Type System Version » force SqlClient à charger la version 11.0 de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a80bc-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="a80bc-123">Cet attribut de chaîne de connexion est uniquement disponible dans le .NET 4.5 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a80bc-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80bc-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a80bc-124">See Also</span></span>  
 <span data-ttu-id="a80bc-125">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a80bc-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a80bc-126">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="a80bc-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
