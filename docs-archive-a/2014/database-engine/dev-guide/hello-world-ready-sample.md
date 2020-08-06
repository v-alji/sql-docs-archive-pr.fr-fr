---
title: Exemple de Hello World Ready | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 1cb94266-f702-4a57-a1ae-689a89c98757
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7cc3088af258962a4cec615214147d1f4f09c431
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709871"
---
# <a name="hello-world-ready-sample"></a><span data-ttu-id="a3085-102">Exemple HelloWorldReady</span><span class="sxs-lookup"><span data-stu-id="a3085-102">Hello World Ready Sample</span></span>
  <span data-ttu-id="a3085-103">L'exemple HelloWorldReady présente les opérations de base à effectuer pour créer, déployer et tester une procédure stockée simple basée sur l'intégration du CLR (Common Language Runtime) et adaptée pour un usage international.</span><span class="sxs-lookup"><span data-stu-id="a3085-103">The Hello World Ready sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple world ready common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="a3085-104">Un composant est dit adapté pour un usage international lorsqu'il est possible de le localiser facilement, sans changer son code source, en différentes langues pour divers marchés dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="a3085-104">A world-ready component can be easily localized into different languages for different markets around the world without changing the component's source code.</span></span> <span data-ttu-id="a3085-105">Cet exemple montre également comment retourner des données via un paramètre de sortie et via un enregistrement, qui est construit de manière dynamique par la procédure stockée et est retourné au client. Cet exemple est presque identique à l'exemple Hello World, mais il est beaucoup plus facile et sécurisé de localiser cette application.</span><span class="sxs-lookup"><span data-stu-id="a3085-105">This sample also demonstrates how to return data through an output parameter and through a record, which is dynamically constructed by the stored procedure and returned to the client.This sample is almost identical to the Hello World Sample except that it is much easier and safer to localize this application.</span></span> <span data-ttu-id="a3085-106">La modification du texte localisé nécessite les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3085-106">To change localized text requires the following:</span></span>  
  
1.  <span data-ttu-id="a3085-107">Modification d’un fichier XML (.`resx`</span><span class="sxs-lookup"><span data-stu-id="a3085-107">Changing an XML file (the .`resx`</span></span> <span data-ttu-id="a3085-108">) pour la culture particulière dans le répertoire Resources</span><span class="sxs-lookup"><span data-stu-id="a3085-108">file) for the particular culture in the resources directory</span></span>  
  
2.  <span data-ttu-id="a3085-109">Génération du fichier des ressources de la culture à l'aide de l'utilitaire `resgen`.</span><span class="sxs-lookup"><span data-stu-id="a3085-109">Building the culture's resources file by using `resgen`</span></span>  
  
3.  <span data-ttu-id="a3085-110">Génération de la DLL satellite mise à jour pour cette culture.</span><span class="sxs-lookup"><span data-stu-id="a3085-110">Building the updated satellite DLL for that culture</span></span>  
  
4.  <span data-ttu-id="a3085-111">Suppression et ajout de cet assembly dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3085-111">Dropping and adding that assembly in SQL Server</span></span>  
  
 <span data-ttu-id="a3085-112">Le code source et l'assembly pour la procédure stockée CLR elle-même ne changent pas.</span><span class="sxs-lookup"><span data-stu-id="a3085-112">The source code and assembly for the CLR stored procedure itself does not change.</span></span> <span data-ttu-id="a3085-113">Un script `build.cmd` est fourni, qui montre comment compiler et lier les assemblys de ressource. Bien que le code source pour l'application crée un gestionnaire de ressources basé sur l'assembly en cours d'exécution, vous n'avez pas à incorporer les ressources neutres de culture dans la DLL qui contient la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a3085-113">A `build.cmd` script is provided which demonstrates how to compile and link the resource assemblies.Although the source code for the application creates a resource manager based the currently executing assembly, you do not have to embed the culture neutral resources in the DLL that contains the stored procedure.</span></span> <span data-ttu-id="a3085-114">Le `System.Resources.NeutralResourcesLanguage attribute` permet aux ressources indépendantes de la culture d'exister dans une DLL satellite.</span><span class="sxs-lookup"><span data-stu-id="a3085-114">The `System.Resources.NeutralResourcesLanguage attribute` permits the culture-neutral resources to exist in a satellite DLL.</span></span> <span data-ttu-id="a3085-115">Il est bien plus avantageux d'utiliser une DLL distincte à cet effet, de sorte qu'il ne soit pas nécessaire de modifier la DLL principale contenant la procédure stockée CLR lorsqu'un texte localisé doit être ajouté ou modifié.</span><span class="sxs-lookup"><span data-stu-id="a3085-115">It is much better to use a separate DLL for this purpose so that when localized text needs to be added or changed, the primary DLL that contains the CLR stored procedure does not have to be changed.</span></span> <span data-ttu-id="a3085-116">Cela set particulièrement utile pour les types clr définis par l'utilisateur qui peuvent avoir des colonnes et d'autres dépendances qui rendraient la suppression et le rajout du type difficiles à effectuer. Généralement, les versions de DLL satellites doivent être identiques à la version d'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="a3085-116">This is especially useful for CLR user-defined types that might have columns and other dependencies which would make it difficult to drop and re-add the type.Ordinarily, the satellite DLL versions must be identical to the main assembly version.</span></span> <span data-ttu-id="a3085-117">Toutefois, vous pouvez utiliser l'attribut `SatelliteContractVersion` pour permettre une mise à jour de l'assembly principal sans mise à jour des assemblys satellites.</span><span class="sxs-lookup"><span data-stu-id="a3085-117">However, you can use the `SatelliteContractVersion` attribute to allow the main assembly to be updated without updating the satellite assemblies too.</span></span> <span data-ttu-id="a3085-118">Pour plus d'informations, consultez la classe `ResourceManager` dans la documentation Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="a3085-118">For more information, see the `ResourceManager` class in the Microsoft .NET documentation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3085-119">Prérequis</span><span class="sxs-lookup"><span data-stu-id="a3085-119">Prerequisites</span></span>  
 <span data-ttu-id="a3085-120">Cet exemple fonctionne uniquement avec SQL Server 2005 et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a3085-120">This sample works only with SQL Server 2005 and later versions.</span></span>  
  
 <span data-ttu-id="a3085-121">Pour créer et exécuter ce projet, les logiciels suivants doivent être installés :</span><span class="sxs-lookup"><span data-stu-id="a3085-121">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a3085-122">ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="a3085-122">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="a3085-123">Vous pouvez vous procurer gratuitement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express à partir du site Web [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [(en anglais)](https://www.microsoft.com/sql-server/sql-server-editions-express)</span><span class="sxs-lookup"><span data-stu-id="a3085-123">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="a3085-124">Base de données AdventureWorks qui est disponible sur le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] site Web [du Centre pour les développeurs](https://go.microsoft.com/fwlink/?linkid=62796)</span><span class="sxs-lookup"><span data-stu-id="a3085-124">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="a3085-125">Le Kit de développement logiciel .NET Framework SDK 2.0 ou version ultérieure, ou Microsoft Visual Studio 2005 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="a3085-125">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="a3085-126">Vous pouvez vous procurer gratuitement le Kit de développement logiciel .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="a3085-126">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="a3085-127">De plus, les conditions suivantes doivent être réunies :</span><span class="sxs-lookup"><span data-stu-id="a3085-127">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="a3085-128">L'intégration du CLR doit être activée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="a3085-128">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="a3085-129">Pour activer l'intégration du CLR, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3085-129">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="a3085-130">Activation de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="a3085-130">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="a3085-131">Exécutez les commandes [!INCLUDE[tsql](../../includes/tsql-md.md)] suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3085-131">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3085-132">Pour activer l'intégration du CLR, vous devez disposer de l'autorisation de niveau serveur `ALTER SETTINGS` qui est attribuée implicitement aux membres des rôles serveur fixes `sysadmin` et `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="a3085-132">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="a3085-133">La base de données AdventureWorks doit être installée sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="a3085-133">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="a3085-134">Si vous n’êtes pas administrateur de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance que vous utilisez, vous devez demander à un administrateur de vous accorder l’autorisation **CreateAssembly** pour terminer l’installation.</span><span class="sxs-lookup"><span data-stu-id="a3085-134">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="a3085-135">Génération de l'exemple</span><span class="sxs-lookup"><span data-stu-id="a3085-135">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="a3085-136">Créez et exécutez l'exemple à l'aide des instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3085-136">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="a3085-137">Ouvrez une invite de commandes Visual Studio ou .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3085-137">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="a3085-138">Si nécessaire, créez un répertoire pour votre exemple.</span><span class="sxs-lookup"><span data-stu-id="a3085-138">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="a3085-139">Pour cet exemple, nous utiliserons C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="a3085-139">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="a3085-140">Dans c:\MySample, créez `HelloWorld.vb` (pour l'exemple Visual Basic) ou `HelloWorld.cs` (pour l'exemple C#) et copiez l'exemple de code Visual Basic ou  C# approprié (ci-dessous) dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="a3085-140">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="a3085-141">Dans c:\MySample, créez le fichier `messages.resx` et copiez l'exemple de code C# dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="a3085-141">In c:\MySample, create the file `messages.resx` and copy the sample code into the file.</span></span>  
  
5.  <span data-ttu-id="a3085-142">Dans c:\MySample, créez le fichier `messages.de.resx` en enregistrant le fichier `messages.resx` comme `messages.de.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-142">In c:\MySample, create the file `messages.de.resx` by saving the file `messages.resx` as `messages.de.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-143">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-143">To read</span></span>  
  
    -   `<value xml:space="preserve">Hallo Welt!</value>`  
  
6.  <span data-ttu-id="a3085-144">Dans c:\MySample, créez le fichier `messages.es.resx` en enregistrant le fichier `messages.resx` comme `messages.es.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-144">In c:\MySample, create the file `messages.es.resx` by saving the file `messages.resx` as `messages.es.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-145">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-145">To read</span></span>  
  
    -   `<value xml:space="preserve">Hola a todos</value>`  
  
7.  <span data-ttu-id="a3085-146">Dans c:\MySample, créez le fichier `messages.fr.resx` en enregistrant le fichier `messages.resx` comme `messages.fr.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-146">In c:\MySample, create the file `messages.fr.resx` by saving the file `messages.resx` as `messages.fr.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-147">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-147">To read</span></span>  
  
    -   `<value xml:space="preserve">BonjourÂ !</value>`  
  
8.  <span data-ttu-id="a3085-148">Dans c:\MySample, créez le fichier `messages.fr-FR.resx` en enregistrant le fichier `messages.resx` comme `messages.fr-FR.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-148">In c:\MySample, create the file `messages.fr-FR.resx` by saving the file `messages.resx` as `messages.fr-FR.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-149">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-149">To read</span></span>  
  
    -   `<value xml:space="preserve">Bonjour de France!</value>`  
  
9. <span data-ttu-id="a3085-150">Dans c:\MySample, créez le fichier `messages.it.resx` en enregistrant le fichier `messages.resx` comme `messages.it.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-150">In c:\MySample, create the file `messages.it.resx` by saving the file `messages.resx` as `messages.it.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-151">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-151">To read</span></span>  
  
    -   `<value xml:space="preserve">Buongiorno</value>`  
  
10. <span data-ttu-id="a3085-152">Dans c:\MySample, créez le fichier `messages.ja.resx` en enregistrant le fichier `messages.resx` comme `messages.ja.resx` après avoir modifié la ligne.</span><span class="sxs-lookup"><span data-stu-id="a3085-152">In c:\MySample, create the file `messages.ja.resx` by saving the file `messages.resx` as `messages.ja.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="a3085-153">Pour lire</span><span class="sxs-lookup"><span data-stu-id="a3085-153">To read</span></span>  
  
    -   <span data-ttu-id="a3085-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span><span class="sxs-lookup"><span data-stu-id="a3085-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span></span>  
  
11. <span data-ttu-id="a3085-155">Dans c:\MySample, créez le fichier `build.com` et copiez l'exemple de code dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="a3085-155">In c:\MySample, create the file `build.com` and copy the sample code into the file</span></span>  
  
12. <span data-ttu-id="a3085-156">Générez l'assembly satellite en exécutant la version de fichier à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="a3085-156">Build the satellite assembles by executing the file build at the command prompt.</span></span>  
  
13. <span data-ttu-id="a3085-157">Compilez l'exemple de code de l'invite de ligne de commande en exécutant l'une des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a3085-157">Compile the sample code from the command line prompt by executing the one of the following:</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:HelloWorldReady.dll /target:library HelloWorld.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /out:HelloWorldReady.dll /target:library Hello.csCopy the tsql installation code into a file and save it as Install.sql in the sample directory.`  
  
14. <span data-ttu-id="a3085-158">Si l'exemple est installé dans un répertoire autre que `C:\MySample\`, modifiez le fichier `Install.sql` comme indiqué pour pointer sur cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="a3085-158">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
15. <span data-ttu-id="a3085-159">Déployez l'assembly et la procédure stockée en exécutant</span><span class="sxs-lookup"><span data-stu-id="a3085-159">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
16. <span data-ttu-id="a3085-160">Copiez le script de la commande de test [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `test.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="a3085-160">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
17. <span data-ttu-id="a3085-161">Exécutez le script de test avec la commande suivante</span><span class="sxs-lookup"><span data-stu-id="a3085-161">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
18. <span data-ttu-id="a3085-162">Copiez le script de nettoyage [!INCLUDE[tsql](../../includes/tsql-md.md)] dans un fichier et enregistrez-le sous `cleanup.sql` dans le répertoire d'exemple.</span><span class="sxs-lookup"><span data-stu-id="a3085-162">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
19. <span data-ttu-id="a3085-163">Exécutez le script avec la commande suivante</span><span class="sxs-lookup"><span data-stu-id="a3085-163">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="a3085-164">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="a3085-164">Sample Code</span></span>  
 <span data-ttu-id="a3085-165">Voici les listes de code pour cet exemple.</span><span class="sxs-lookup"><span data-stu-id="a3085-165">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="a3085-166">C#</span><span class="sxs-lookup"><span data-stu-id="a3085-166">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Globalization;  
using System.Threading;  
using System.Resources;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
  
[assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)]  
[assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)]  
[assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance, System.Runtime.ConstrainedExecution.Cer.None)]  
  
    public sealed partial class StoredProcedures  
    {  
        private StoredProcedures()  
        {  
        }  
  
        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1021:AvoidOutParameters"), Microsoft.SqlServer.Server.SqlProcedure]  
        public static void HelloWorldReady(string culture, out string greeting)  
        {  
ResourceManager rm   
= new ResourceManager("Messages",   
Assembly.GetExecutingAssembly());  
  
string message = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture));  
  
            Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 24);  
            SqlDataRecord greetingRecord  
                = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
            greetingRecord.SetString(0, message);  
            SqlContext.Pipe.Send(greetingRecord);  
            greeting = message;  
        }  
    }  
  
```  
  
 <span data-ttu-id="a3085-167">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a3085-167">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Globalization  
Imports System.Resources  
Imports System.Reflection  
Imports System.Runtime.InteropServices  
<Assembly: AssemblyVersion("1.0.*")>   
<Assembly: System.Runtime.InteropServices.ComVisible(False)>   
<Assembly: System.CLSCompliant(True)>   
<Assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)>   
<Assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)>   
<Assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState, Runtime.ConstrainedExecution.Cer.None)>   
  
Partial Public NotInheritable Class StoredProcedures  
    Private Sub New()  
    End Sub  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorldReady(ByVal culture As String, ByRef greeting As String)  
        Dim rm As New ResourceManager("Messages", Assembly.GetExecutingAssembly())  
        Dim message As String = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture))  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 24)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, message)  
        SqlContext.Pipe.Send(greetingRecord)  
        greeting = message  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="a3085-168">Il s'agit de `build.com`, qui génère les assemblys satellites.</span><span class="sxs-lookup"><span data-stu-id="a3085-168">This is `build.com`, which builds the satellite assemblies.</span></span>  
  
```  
resgen Messages.resx  
resgen Messages.de.resx  
resgen Messages.es.resx  
resgen Messages.fr.resx  
resgen Messages.fr-Fr.resx  
resgen Messages.it.resx  
resgen Messages.ja.resx  
if not exist de/ mkdir de  
if not exist es/ mkdir es  
if not exist fr/ mkdir fr  
if not exist fr-FR/ mkdir fr-FR  
if not exist it/ mkdir it  
if not exist ja/ mkdir ja  
al /t:lib /culture:de /embed:Messages.de.resources /out:de\HelloWorldReady.resources.dll  
al /t:lib /culture:es /embed:Messages.es.resources /out:es\HelloWorldReady.resources.dll  
al /t:lib /culture:fr /embed:Messages.fr.resources /out:fr\HelloWorldReady.resources.dll  
al /t:lib /culture:fr-FR /embed:Messages.fr-FR.resources /out:fr-FR\HelloWorldReady.resources.dll  
al /t:lib /culture:it /embed:Messages.it.resources /out:it\HelloWorldReady.resources.dll  
al /t:lib /culture:ja /embed:Messages.ja.resources /out:ja\HelloWorldReady.resources.dll  
al /t:lib /culture:"" /embed:Messages.resources /out:HelloWorldReady.resources.dll  
```  
  
 <span data-ttu-id="a3085-169">Il s'agit du script d'installation [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`), qui déploie les assemblys et crée la procédure stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a3085-169">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assemblies and creates the stored procedure within the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
-- Add the assembly and CLR integration based stored procedure  
  
CREATE ASSEMBLY HelloWorldReady  
FROM @SamplesPath + 'HelloWorldReady.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.neutral]  
FROM @SamplesPath + 'HelloWorldReady.resources.dll'  
WITH permission_set = Safe;   
  
CREATE ASSEMBLY [HelloWorldReady.resources.de]  
FROM @SamplesPath + '\de\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.es]  
FROM @SamplesPath + '\es\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr]  
FROM @SamplesPath + '\fr\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr-FR]  
FROM @SamplesPath + '\fr-FR\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.it]  
FROM @SamplesPath + '\it\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.ja]  
FROM @SamplesPath + '\ja\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorldReady  
(  
@Culture NVarchar(12),  
@Greeting NVarchar(24) OUTPUT  
)  
AS EXTERNAL NAME HelloWorldReady.StoredProcedures.HelloWorldReady;  
GO  
  
USE master;  
GO  
```  
  
 <span data-ttu-id="a3085-170">Il s'agit de `test.sql`, qui teste l'exemple en exécutant les fonctions sur chaque paramètre régional.</span><span class="sxs-lookup"><span data-stu-id="a3085-170">This is `test.sql`, which tests the sample by executing the functions on each locale.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DECLARE @GreetingDe nvarchar(24);  
DECLARE @GreetingDe_CH nvarchar(24);  
DECLARE @GreetingEn nvarchar(24);  
DECLARE @GreetingEs nvarchar(24);  
DECLARE @GreetingFr nvarchar(24);  
DECLARE @GreetingFr_FR nvarchar(24);  
DECLARE @GreetingIt nvarchar(24);  
DECLARE @GreetingJa nvarchar(24);  
  
--German as spoken anywhere in the world (the neutral German culture)  
EXEC usp_HelloWorldReady 'de', @GreetingDe OUTPUT;  
--German as spoken in Switzerland.  Because we don't have a specific assembly  
--for this case, the .NET Framework will automatically fall back to the neutral German culture DLL.  
EXEC usp_HelloWorldReady 'de-CH', @GreetingDe_CH OUTPUT;  
EXEC usp_HelloWorldReady 'en', @GreetingEn OUTPUT;  
EXEC usp_HelloWorldReady 'es', @GreetingEs OUTPUT;  
--French as spoken anywhere in the world (the neutral French culture)  
EXEC usp_HelloWorldReady 'fr', @GreetingFr OUTPUT  
--French as spoken in France.  Since we do have a specific assembly for this case, a specific   
--greeting is provided from that DLL.  The neutral French culture DLL is not used in this case.  
EXEC usp_HelloWorldReady 'fr-FR', @GreetingFr_FR OUTPUT  
EXEC usp_HelloWorldReady 'it', @GreetingIt OUTPUT;  
EXEC usp_HelloWorldReady 'ja', @GreetingJa OUTPUT;  
  
SELECT @GreetingDe AS OUTPUT_PARAMETER_DE;  
SELECT @GreetingDe_CH AS OUTPUT_PARAMETER_De_CH;  
SELECT @GreetingEn AS OUTPUT_PARAMETER_EN;  
SELECT @GreetingEs AS OUTPUT_PARAMETER_ES;  
SELECT @GreetingFr AS OUTPUT_PARAMETER_FR;  
SELECT @GreetingFr_FR AS OUTPUT_PARAMETER_Fr_FR;  
SELECT @GreetingIt AS OUTPUT_PARAMETER_IT;  
SELECT @GreetingJa AS OUTPUT_PARAMETER_JA;  
  
GO  
```  
  
 <span data-ttu-id="a3085-171">Le code [!INCLUDE[tsql](../../includes/tsql-md.md)] suivant supprime les assemblys et la procédure stockée de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a3085-171">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assemblies and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
USE master;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3085-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3085-172">See Also</span></span>  
 [<span data-ttu-id="a3085-173">Scénarios et exemples d’utilisation pour l’intégration du CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="a3085-173">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
