---
title: Exemple de paramètre de tableau | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 5d7034ca-ce88-4a7e-8dd9-82f867479e7f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b9afbf13c3797239d142642d9dc6e9ddf9690472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701736"
---
# <a name="array-parameter-sample"></a><span data-ttu-id="126ea-102">Exemple de paramètre tableau</span><span class="sxs-lookup"><span data-stu-id="126ea-102">Array Parameter Sample</span></span>
  <span data-ttu-id="126ea-103">Il est parfois utile de créer, de mettre à jour ou de supprimer un ensemble de lignes dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="126ea-103">Sometimes it is useful to create, update, or delete a set of rows in a database.</span></span> <span data-ttu-id="126ea-104">Il existe plusieurs méthodes que vous pouvez utiliser dans ce but.</span><span class="sxs-lookup"><span data-stu-id="126ea-104">There are several approaches you could use to achieve that goal.</span></span> <span data-ttu-id="126ea-105">L'une d'elles consiste à transmettre un tableau d'informations d'un client à une procédure stockée d'intégration CLR (Common Language Runtime) sur le serveur en utilisant un type de données d'intégration du CLR défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="126ea-105">One of them is to pass an array of information from a client to a common language runtime (CLR) integration stored procedure on the server by using a CLR integration user-defined data type.</span></span> <span data-ttu-id="126ea-106">La nature de tels types de données définis par l'utilisateur limite à 8000 octets le volume des données fournies au serveur.</span><span class="sxs-lookup"><span data-stu-id="126ea-106">The nature of such user-defined data types limits the size of the data provided to the server to 8000 bytes.</span></span> <span data-ttu-id="126ea-107">De ce fait, cette méthode n'est pas satisfaisante pour les données volumineuses ou complexes.</span><span class="sxs-lookup"><span data-stu-id="126ea-107">Therefore, this approach is not satisfactory for large or complex data.</span></span> <span data-ttu-id="126ea-108">Si les données manipulées sont simples et de petite taille, cette méthode peut s'avérer beaucoup plus efficace que l'appel d'une procédure stockée pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="126ea-108">If the data that is being manipulated is small and simple, this approach can be much more efficient than calling a stored procedure for each row.</span></span> <span data-ttu-id="126ea-109">En utilisant un tableau, l'ordre des données est préservé pour les applications où l'ordre a de l'importance. Cet exemple contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="126ea-109">By passing an array, the order of data is preserved for those applications where the order is significant.This sample contains the following:</span></span>  
  
1.  <span data-ttu-id="126ea-110">Le type de données défini par l'utilisateur `ContactTypeNames` .</span><span class="sxs-lookup"><span data-stu-id="126ea-110">The `ContactTypeNames` user-defined data type.</span></span> <span data-ttu-id="126ea-111">Ce type de données renferme une liste des noms de type de contact souhaité.</span><span class="sxs-lookup"><span data-stu-id="126ea-111">This contains a list of desired contact type names.</span></span>  
  
2.  <span data-ttu-id="126ea-112">La procédure stockée `usp_EnsureContactTypeNames` implémentée comme une méthode Microsoft Visual C# ou Microsoft Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="126ea-112">The `usp_EnsureContactTypeNames` stored procedure implemented as a Microsoft Visual C# or Microsoft Visual Basic method.</span></span> <span data-ttu-id="126ea-113">Une instance du type de données défini par l'utilisateur `ContactTypeNames` est ainsi acceptée et de nouvelles lignes dans la table `Person.ContactType` sont insérées pour tous les noms de contact contenus dans l'instance du type de données défini par l'utilisateur et qui ne se trouvent pas encore dans cette table.</span><span class="sxs-lookup"><span data-stu-id="126ea-113">This accepts an instance of the `ContactTypeNames` user-defined data type and inserts new rows in the `Person.ContactType` table for any contact names that are contained in the user-defined data type instance which are not already present in the table.</span></span>  
  
3.  <span data-ttu-id="126ea-114">L'application console `TestArrayParameter` .</span><span class="sxs-lookup"><span data-stu-id="126ea-114">The `TestArrayParameter` console application.</span></span> <span data-ttu-id="126ea-115">Une instance du type de données défini par l'utilisateur `ContactTypeNames` est ainsi créée en fonction des paramètres de ligne de commande qui lui sont transmis, puis la procédure stockée `usp_EnsureContactTypeNames` est appelée en passant l'instance du type de données défini par l'utilisateur comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="126ea-115">This creates an instance of the `ContactTypeNames` user-defined data type based on the command line parameters passed in, and then invokes the `usp_EnsureContactTypeNames` stored procedure by passing the user-defined data type instance as a parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="126ea-116">Prérequis</span><span class="sxs-lookup"><span data-stu-id="126ea-116">Prerequisites</span></span>  
 <span data-ttu-id="126ea-117">Pour créer et exécuter ce projet, les logiciels suivants doivent être installés :</span><span class="sxs-lookup"><span data-stu-id="126ea-117">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="126ea-118">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="126ea-118">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="126ea-119">Vous pouvez vous procurer gratuitement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express à partir du site Web [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [(en anglais)](https://www.microsoft.com/download/details.aspx?id=42299)</span><span class="sxs-lookup"><span data-stu-id="126ea-119">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/download/details.aspx?id=42299)</span></span>  
  
-   <span data-ttu-id="126ea-120">Base de données AdventureWorks qui est disponible sur le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site Web [du Centre pour les développeurs](https://archive.codeplex.com/?p=SqlServerSamples)</span><span class="sxs-lookup"><span data-stu-id="126ea-120">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://archive.codeplex.com/?p=SqlServerSamples)</span></span>  
  
-   <span data-ttu-id="126ea-121">Le Kit de développement logiciel .NET Framework SDK 2.0 ou version ultérieure, ou Microsoft Visual Studio 2005 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="126ea-121">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="126ea-122">Vous pouvez vous procurer gratuitement le Kit de développement logiciel .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="126ea-122">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="126ea-123">De plus, les conditions suivantes doivent être réunies :</span><span class="sxs-lookup"><span data-stu-id="126ea-123">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="126ea-124">L'intégration du CLR doit être activée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="126ea-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="126ea-125">Pour activer l'intégration du CLR, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="126ea-125">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="126ea-126">Activation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="126ea-126">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="126ea-127">Exécutez les commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="126ea-127">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="126ea-128">Pour activer l'intégration du CLR, vous devez disposer de l'autorisation de niveau serveur `ALTER SETTINGS` qui est attribuée implicitement aux membres des rôles serveur fixes `sysadmin` et `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="126ea-128">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="126ea-129">La base de données AdventureWorks doit être installée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="126ea-129">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="126ea-130">Si vous n’êtes pas administrateur de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance que vous utilisez, vous devez demander à un administrateur de vous accorder l’autorisation **CreateAssembly** pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="126ea-130">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="126ea-131">Génération de l'exemple</span><span class="sxs-lookup"><span data-stu-id="126ea-131">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="126ea-132">Créez et exécutez l'exemple à l'aide des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="126ea-132">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="126ea-133">Ouvrez une invite de commandes Visual Studio ou .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="126ea-133">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="126ea-134">Si nécessaire, créez un répertoire pour votre exemple.</span><span class="sxs-lookup"><span data-stu-id="126ea-134">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="126ea-135">Pour cet exemple, nous utiliserons C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="126ea-135">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="126ea-136">Dans c:\MySample, créez `ContactTypeNames.vb` (pour l'exemple Visual Basic) ou `ContactTypeNames.cs` (pour l'exemple C#) et copiez l'exemple de code Visual Basic ou  C# approprié (ci-dessous) dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="126ea-136">In c:\MySample, create `ContactTypeNames.vb` (for the Visual Basic sample) or `ContactTypeNames.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="126ea-137">Compilez l'exemple de code dans l'assembly requis à partir de l'invite de ligne de commande en exécutant l'un des éléments suivants, selon le langage choisi.</span><span class="sxs-lookup"><span data-stu-id="126ea-137">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library ContactTypeNames.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library ContactTypeNames.cs`  
  
5.  <span data-ttu-id="126ea-138">Dans c:\MySample, créez `Program.vb` (pour l'exemple Visual Basic) ou `Program.cs` (pour l'exemple C#) et copiez l'exemple de code Visual Basic ou  C# approprié (ci-dessous) dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="126ea-138">In c:\MySample, create `Program.vb` (for the Visual Basic sample) or `Program.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
6.  <span data-ttu-id="126ea-139">Localisez la ligne appropriée dans le programme de fichier (autour de la ligne 24) et remplacez `XXX` par le nom de votre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="126ea-139">Locate the appropriate line in the file Program (around line 24) and replace `XXX` with the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
    -   `Dim connection As New SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI")`  
  
    -   `using (SqlConnection connection = new SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI"))`  
  
7.  <span data-ttu-id="126ea-140">Compilez l'exemple de code dans l'exécutable requis à partir de l'invite de ligne de commande en exécutant l'un des éléments suivants, selon le langage choisi.</span><span class="sxs-lookup"><span data-stu-id="126ea-140">Compile the sample code into the required executable from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Deployment.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Drawing.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Windows.Forms.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll,C:\MySample\ContactTypeNames.dll /out:TestArrayParameter Program.vb`  
  
    -   `Csc /reference:ContactTypeNames.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:TestArrayParameter.exe Program.cs`  
  
8.  <span data-ttu-id="126ea-141">Copiez le code d'installation [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `Install.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="126ea-141">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="126ea-142">Si l'exemple est installé dans un répertoire autre que `C:\MySample\`, modifiez le fichier `Install.sql` comme indiqué pour pointer sur cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="126ea-142">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
10. <span data-ttu-id="126ea-143">Déployez l'assembly, la procédure stockée et les fonctions en exécutant</span><span class="sxs-lookup"><span data-stu-id="126ea-143">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
11. <span data-ttu-id="126ea-144">Testez l'application en exécutant la ligne suivante à l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="126ea-144">Test the application by executing the following line at the command prompt:</span></span>  
  
    -   `TestArrayParameter "Executive Sales Representative" "Executive Sales Manager"`  
  
12. <span data-ttu-id="126ea-145">Copiez le script de nettoyage [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `cleanup.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="126ea-145">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
13. <span data-ttu-id="126ea-146">Exécutez le script avec la commande suivante</span><span class="sxs-lookup"><span data-stu-id="126ea-146">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="126ea-147">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="126ea-147">Sample Code</span></span>  
 <span data-ttu-id="126ea-148">Voici les listes de code pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="126ea-148">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="126ea-149">Il s'agit du code pour la bibliothèque `ContactTypeNames.`</span><span class="sxs-lookup"><span data-stu-id="126ea-149">This is the code for the Library `ContactTypeNames.`</span></span>  
  
 <span data-ttu-id="126ea-150">C#</span><span class="sxs-lookup"><span data-stu-id="126ea-150">C#</span></span>  
  
```  
#region Using directives  
  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Globalization;  
using Microsoft.SqlServer.Server;  
  
#endregion  
  
    // This class is used to demonstrate passing an array of a fairly small number of reasonably small strings  
    // to a CLR integration based stored procedure on the server.  Because a UDT is limited to 8000 bytes  
    // this approach will not work well for large numbers of strings or long strings.  See the contact  
    // creation stored procedure in the AdventureWorks CLR integration sample for an alternative approach  
    // using XML which does not have these limitations.  
    [Serializable]  
    [Microsoft.SqlServer.Server.SqlUserDefinedType(Microsoft.SqlServer.Server.Format.UserDefined, IsByteOrdered = true, MaxByteSize = 8000)]  
    public class ContactTypeNames : INullable, Microsoft.SqlServer.Server.IBinarySerialize  
    {  
  
        #region Constructors  
        private const int maxByteSize = 8000;  
  
        public ContactTypeNames()  
        {  
        }  
  
        public ContactTypeNames(string[] names)  
        {  
            int numberOfCharacters = 0;  
            foreach (string name in names)  
            {  
                if (name.Length == 0)   
                    throw new ArgumentException("Zero length names are not allowed");  
                numberOfCharacters += name.Length;  
            }  
            int dataByteSize = numberOfCharacters*2 //UTF-16 characters take 2 bytes  
                + names.Length*4  //Four byte header for each string  
                + 4                 //Four byte header for null string at end  
                + 1;                //One byte boolean for null flag  
            if (dataByteSize >= maxByteSize)  
                throw new ArgumentException(string.Format(CultureInfo.InvariantCulture, "Data provided occupies {0} bytes but only {1} bytes "  
                    + "are available", dataByteSize, maxByteSize));  
  
            this._names = names;  
        }  
        #endregion  
  
        #region Accessors  
        public string[] GetTypeNameArray()  
        {  
            //Don't let caller modify our copy of the array  
            return (string[])_names.Clone();  
        }  
  
        //This has an odd API because we can only define Transact-SQL functions on static methods.  
        [SqlFunctionAttribute(FillRowMethodName = "FillNameRow")]  
        public static IEnumerable GetContactTypeNames(ContactTypeNames names)  
        {  
            if (names == null)  
                throw new ArgumentNullException("names");  
  
            return names.GetTypeNameArray();  
        }  
  
        public static void FillNameRow(object nameArrayElement, out string contactName)  
        {  
            contactName = (string)nameArrayElement;  
        }  
  
        #endregion  
  
        #region String Conversions  
  
        /// <summary>  
        /// The string format for contact type names is a sequence of names separated by commas  
        /// </summary>  
        /// <param name="s">a string containing contact type names separated by commas</param>  
        /// <returns>An instance of contact type name containing the specified names</returns>  
        [Microsoft.SqlServer.Server.SqlMethod(DataAccess = Microsoft.SqlServer.Server.DataAccessKind.None, IsDeterministic = false, IsMutator = false, IsPrecise = false,  
        SystemDataAccess = Microsoft.SqlServer.Server.SystemDataAccessKind.None)]  
        public static ContactTypeNames Parse(SqlString s)  
        {  
            if (s.IsNull)  
                return Null;  
            return new ContactTypeNames(s.Value.Split(new char[] {','}));  
        }  
  
        /// <summary>  
        /// Convert the contact type names to a string  
        /// </summary>  
        /// <returns>The contact type names separated by commas</returns>  
        public override string ToString()  
        {  
            if (this.IsNull)  
                return null;  
  
            StringBuilder sb = new StringBuilder();  
            foreach (string name in _names)  
            {  
                if (sb.Length > 0) sb.Append(", ");  
                sb.Append(name);  
            }  
  
            return sb.ToString();  
        }  
        #endregion  
  
        #region INullable Members  
  
        public static ContactTypeNames Null  
        {  
            get  
            {  
                return new ContactTypeNames();  
            }  
        }  
        public bool IsNull  
        {  
            get   
            {   
                return _names == null;   
            }  
        }  
  
        #endregion  
  
        #region IBinarySerialize Members  
  
        //Format:   
        //Byte 1: Null flag (boolean) (true = null)  
        //Byte 2 - 7994: Strings with 4 byte length headers,  
        //               last string is a zero length string.  
        //This format is in part dictated by how the BinaryWriter serializes strings.  See  
        //the Microsoft .NET Framework documentation on System.IO.BinaryWriter for more details.  
  
        public void Read(System.IO.BinaryReader r)  
        {  
            if (r.ReadBoolean())  
            {  
                _names = null;  
                return;  
            }  
            List<String> nameList = new List<String>();  
            string name;  
            while ((name = r.ReadString()).Length != 0)  
            {  
                nameList.Add(name);  
            }  
            _names = new string[nameList.Count];  
            nameList.CopyTo(_names);  
        }  
  
        public void Write(System.IO.BinaryWriter w)  
        {  
            if (w == null)  
                throw new ArgumentNullException("w");  
  
            w.Write(this.IsNull);  
            foreach (string name in _names)  
            {  
                w.Write(name);  
            }  
            w.Write(string.Empty);              
        }  
  
        #endregion  
  
        #region Private Implementation  
  
        private string[] _names;  
        #endregion  
    }  
```  
  
 <span data-ttu-id="126ea-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="126ea-151">Visual Basic</span></span>  
  
```  
#Region "Using directives"  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports System.Collections  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.Globalization  
Imports Microsoft.SqlServer.Server  
Imports System.Runtime.InteropServices  
#End Region  
  
' This class is used to demonstrate passing an array of a fairly small number of reasonably small strings  
' to a CLR integration based stored procedure on the server.  Because a UDT is limited to 8000 bytes  
' this approach will not work well for large numbers of strings or long strings.  See the contact  
' creation stored procedure in the AdventureWorks CLR integration sample for an alternative approach  
' using XML which does not have these limitations.  
<Serializable()> _  
<SqlUserDefinedType(Format.UserDefined, IsByteOrdered:=True, maxByteSize:=8000), CLSCompliant(False)> _  
Public Class ContactTypeNames  
    Implements INullable, IBinarySerialize  
  
#Region "Constructors"  
    Private Const maxByteSize As Integer = 8000  
  
    Public Sub New()  
    End Sub  
  
    Public Sub New(ByVal names() As String)  
        Dim numberOfCharacters As Integer = 0  
  
        For Each name As String In names  
            If name.Length = 0 Then  
                Throw New ArgumentException("Zero length names are not allowed")  
            End If  
  
            numberOfCharacters += name.Length  
        Next  
  
        'UTF-16 characters take 2 bytes  
        'Four byte header for each string  
        'Four byte header for null string at end  
        'One byte boolean for null flag  
        Dim dataByteSize As Integer = numberOfCharacters * 2 _  
            + names.Length * 4 _  
            + 4 _  
            + 1  
  
        If dataByteSize >= maxByteSize Then  
            Throw New ArgumentException(String.Format(CultureInfo.InvariantCulture, _  
                "Data provided occupies {0} bytes but only {1} bytes are available", _  
                dataByteSize, maxByteSize))  
        End If  
  
        Me._names = names  
    End Sub  
#End Region  
  
#Region "Accessors"  
  
    Public Function GetTypeNameArray() As String()  
        'Don't let caller modify our copy of the array  
        Return CType(Me._names.Clone(), String())  
    End Function  
  
    'This has an odd API because we can only define Transact-SQL functions on static methods.  
    <SqlFunction(FillRowMethodName:="FillNameRow", TableDefinition:="[Name] [Name]")> _  
    Public Shared Function GetContactTypeNames(ByVal names As ContactTypeNames) As IEnumerable  
        If names Is Nothing Then  
            Throw New ArgumentNullException("names")  
        End If  
  
        Return names.GetTypeNameArray()  
    End Function  
  
    Public Shared Sub FillNameRow(ByVal nameArrayElement As Object, <Out()> ByRef contactName As String)  
        contactName = CStr(nameArrayElement)  
    End Sub  
  
#End Region  
  
#Region "String Conversions"  
  
    ''' <summary>  
    ''' The string format for contact type names is a sequence of names separated by commas  
    ''' </summary>  
    ''' <param name="s">a string containing contact type names separated by commas</param>  
    ''' <returns>An instance of contact type name containing the specified names</returns>  
    <Microsoft.SqlServer.Server.SqlMethod(DataAccess:=Microsoft.SqlServer.Server.DataAccessKind.None, IsDeterministic:=False, IsMutator:=False, IsPrecise:=False, SystemDataAccess:=Microsoft.SqlServer.Server.SystemDataAccessKind.None)> _  
    Public Shared Function Parse(ByVal s As SqlString) As ContactTypeNames  
        If s.IsNull Then  
            Return Nothing  
        End If  
  
        Return New ContactTypeNames(s.Value.Split(New Char() {","c}))  
    End Function  
  
    ''' <summary>  
    ''' Convert the contact type names to a string  
    ''' </summary>  
    ''' <returns>The contact type names separated by commas</returns>  
    Public Overrides Function ToString() As String  
        If Me.IsNull Then  
            Return Nothing  
        End If  
  
        Dim sb As New StringBuilder()  
  
        For Each name As String In Me._names  
            If sb.Length > 0 Then  
                sb.Append(", ")  
            End If  
  
            sb.Append(name)  
        Next name  
  
        Return sb.ToString()  
    End Function  
#End Region  
  
#Region "INullable Members"  
  
    Shared ReadOnly Property Null() As ContactTypeNames  
        Get  
            Return New ContactTypeNames()  
        End Get  
    End Property  
  
    Public ReadOnly Property IsNull() As Boolean Implements INullable.IsNull  
        Get  
            Return Me._names Is Nothing  
        End Get  
    End Property  
  
#End Region  
  
#Region "IBinarySerialize Members"  
  
    'Format:   
    'Byte 1: Null flag (boolean) (true = null)  
    'Byte 2 - 7994: Strings with 4 byte length headers,  
    '               last string is a zero length string.  
    'This format is in part dictated by how the BinaryWriter serializes strings.  See  
    'the Microsoft .NET Framework documentation on System.IO.BinaryWriter for more details.  
    Public Sub Read(ByVal r As System.IO.BinaryReader) Implements IBinarySerialize.Read  
        If r.ReadBoolean() Then  
            Me._names = Nothing  
            Return  
        End If  
  
        Dim nameList As New List(Of String)  
        Dim name As String = r.ReadString()  
        While name.Length <> 0  
            nameList.Add(name)  
            name = r.ReadString()  
        End While  
  
        Me._names = New String(nameList.Count - 1) {}  
        nameList.CopyTo(Me._names)  
    End Sub  
  
    Public Sub Write(ByVal w As System.IO.BinaryWriter) Implements IBinarySerialize.Write  
        If w Is Nothing Then  
            Throw New ArgumentNullException("w")  
        End If  
  
        w.Write(Me.IsNull)  
  
        For Each name As String In Me._names  
            w.Write(name)  
        Next  
  
        w.Write(String.Empty)  
    End Sub  
  
#End Region  
  
#Region "Private Implementation"  
    Private _names() As String  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="126ea-152">Il s'agit du code pour l'exécutable du test.</span><span class="sxs-lookup"><span data-stu-id="126ea-152">This is the code for the test executable.</span></span>  
  
 <span data-ttu-id="126ea-153">C#</span><span class="sxs-lookup"><span data-stu-id="126ea-153">C#</span></span>  
  
```  
#region Using directives  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.IO;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
#endregion  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            if (args.Length == 0)  
            {  
                Console.WriteLine("Usage: TestArrayParameter contactTypeName1 "  
                    + "contactTypeName2 ... contactTypeNamen");  
                return;  
            }  
            using (SqlConnection connection = new SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI"))  
            {  
                connection.Open();  
                ShowTypeNames(connection, "before any inserts");  
  
                SqlCommand command = connection.CreateCommand();  
                command.CommandText = "usp_EnsureContactTypeNames";  
                command.CommandType = CommandType.StoredProcedure;  
                SqlParameter namesParameter = new SqlParameter("@names", SqlDbType.Udt);  
                namesParameter.UdtTypeName = "ContactTypeNames";  
                namesParameter.Value = new ContactTypeNames(args);  
                command.Parameters.Add(namesParameter);  
                command.ExecuteNonQuery();  
  
                ShowTypeNames(connection, "after any inserts");  
  
            }  
  
        }  
  
        private static void ShowTypeNames(SqlConnection connection, string whenRan)  
        {  
            SqlCommand command = connection.CreateCommand();  
            command.CommandText = "SELECT Name FROM Person.ContactType ORDER BY Name";  
            using (SqlDataReader reader = command.ExecuteReader())  
            {  
                Console.BackgroundColor = ConsoleColor.Blue;  
                Console.Write("Contact type names {0}: ", whenRan);  
                Console.ResetColor();  
                bool first = true;  
                while (reader.Read())  
                {  
                    if (!first) Console.Write(", ");  
                    Console.Write(reader[0].ToString());  
                    first = false;  
                }  
                Console.WriteLine("");  
                Console.WriteLine("");  
            }  
  
        }  
    }  
```  
  
 <span data-ttu-id="126ea-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="126ea-154">Visual Basic</span></span>  
  
```  
#Region "Using directives"  
Imports System  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.IO  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports System.Data.SqlClient  
#End Region  
  
Class Program  
  
    Shared Sub Main(ByVal args() As String)  
        If args.Length = 0 Then  
            Console.WriteLine("Usage: TestArrayParameter contactTypeName1 " _  
                + "contactTypeName2 ... contactTypeNamen")  
            Return  
        End If  
  
        Dim connection As New SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI")  
        Try  
            connection.Open()  
            ShowTypeNames(connection, "Before any inserts")  
  
            Dim command As SqlCommand = connection.CreateCommand()  
            command.CommandText = "usp_EnsureContactTypeNames"  
            command.CommandType = CommandType.StoredProcedure  
            Dim namesParameter As New SqlParameter("@names", SqlDbType.Udt)  
            namesParameter.UdtTypeName = "ContactTypeNames"  
            namesParameter.Value = New ContactTypeNames(args)  
            command.Parameters.Add(namesParameter)  
            command.ExecuteNonQuery()  
  
            ShowTypeNames(connection, "After any inserts")  
        Finally  
            connection.Dispose()  
        End Try  
    End Sub  
  
    Private Shared Sub ShowTypeNames(ByVal connection As SqlConnection, ByVal whenRan As String)  
        Dim command As SqlCommand = connection.CreateCommand()  
        command.CommandText = "SELECT [Name] FROM [Person].[ContactType] ORDER BY Name"  
        Dim reader As SqlDataReader = command.ExecuteReader()  
        Try  
            Console.BackgroundColor = ConsoleColor.Blue  
            Console.Write("Contact type names {0}: ", whenRan)  
            Console.ResetColor()  
            Dim first As Boolean = True  
            While reader.Read()  
                If Not first Then  
                    Console.Write(", ")  
                End If  
  
                Console.Write(reader(0).ToString())  
                first = False  
            End While  
  
            Console.WriteLine("")  
            Console.WriteLine("")  
        Finally  
            reader.Dispose()  
        End Try  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="126ea-155">Il s'agit du script d'installation [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), qui déploie l'assembly et crée la procédure stockée et les fonctions dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="126ea-155">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure and functions in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sprocs, type, and assemblies if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_EnsureContactTypeNames')  
DROP PROCEDURE usp_EnsureContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE [name] = N'GetContactTypeNames' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [GetContactTypeNames];  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = 'ContactTypeNames')  
DROP TYPE ContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'ContactTypeNames')  
DROP ASSEMBLY ContactTypeNames;  
GO  
  
-- Add assemblies, type, and sproc  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
set @SamplesPath= 'C:\MySample\'  
CREATE ASSEMBLY ContactTypeNames   
FROM @SamplesPath + 'ContactTypeNames.dll'  
WITH permission_set = Safe;  
  
CREATE TYPE ContactTypeNames  
EXTERNAL NAME ContactTypeNames.ContactTypeNames;  
GO  
  
CREATE FUNCTION GetContactTypeNames  
(  
@names dbo.ContactTypeNames  
)  
RETURNS TABLE  
(  
[Name] [Name]  
)  
AS EXTERNAL NAME [ContactTypeNames].[ContactTypeNames].[GetContactTypeNames];  
GO  
  
CREATE PROCEDURE usp_EnsureContactTypeNames  
(  
@names dbo.ContactTypeNames  
)  
AS  
SET NOCOUNT ON;  
  
INSERT Person.ContactType ([Name])  
SELECT [Name] FROM GetContactTypeNames(@names) AS PotentialNames  
WHERE [Name] NOT IN (SELECT [Name] FROM Person.ContactType);   
GO  
```  
  
 <span data-ttu-id="126ea-156">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant supprime l'assembly et la procédure stockée de la base de données.</span><span class="sxs-lookup"><span data-stu-id="126ea-156">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DELETE Person.ContactType WHERE ContactTypeID > 20;  
GO  
  
-- Drop existing sprocs, type, and assemblies if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_EnsureContactTypeNames')  
DROP PROCEDURE usp_EnsureContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE [name] = N'GetContactTypeNames' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [GetContactTypeNames];  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = 'ContactTypeNames')  
DROP TYPE ContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'ContactTypeNames')  
DROP ASSEMBLY ContactTypeNames;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="126ea-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="126ea-157">See Also</span></span>  
 [<span data-ttu-id="126ea-158">Scénarios et exemples d’utilisation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="126ea-158">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
