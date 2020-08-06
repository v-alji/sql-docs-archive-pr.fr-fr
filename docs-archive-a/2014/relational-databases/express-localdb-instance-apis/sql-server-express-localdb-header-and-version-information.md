---
title: Informations sur la version et l’en-tête de base de données locale | SQL Server Express Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614078"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="8969c-102">En-tête et informations de version SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="8969c-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="8969c-103">Il n'y a aucun fichier d'en-tête distinct pour l'API de l'instance de base de données locale SQL Server Express (LocalDB) ; les signatures de la fonction et les codes d'erreur de LocalDB sont définis dans le fichier d'en-tête SQL Server Native Client (sqlncli.h).</span><span class="sxs-lookup"><span data-stu-id="8969c-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="8969c-104">Pour utiliser l'API d'instance de LocalDB, vous devez inclure le fichier d'en-tête sqlncli.h dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="8969c-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="8969c-105">Contrôle de version de LocalDB</span><span class="sxs-lookup"><span data-stu-id="8969c-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="8969c-106">L'installation de LocalDB utilise un jeu unique de binaires par version principale de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8969c-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="8969c-107">Ces versions de LocalDB sont conservées et des correctifs de logiciel sont appliqués indépendamment.</span><span class="sxs-lookup"><span data-stu-id="8969c-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="8969c-108">Cela signifie que l'utilisateur doit spécifier la version de base de LocalDB (autrement dit, la version principale de SQL Server) qu'il utilisera.</span><span class="sxs-lookup"><span data-stu-id="8969c-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="8969c-109">La version est spécifiée dans le format de version standard défini par la classe .NET Framework **System. version** :</span><span class="sxs-lookup"><span data-stu-id="8969c-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="8969c-110">*Major. minor [. Build [. Revision]]*</span><span class="sxs-lookup"><span data-stu-id="8969c-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="8969c-111">Les deux premiers nombres dans la chaîne de version (*major* et *Minor*) sont obligatoires.</span><span class="sxs-lookup"><span data-stu-id="8969c-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="8969c-112">Les deux derniers nombres dans la chaîne de version (*Build* et *révision*) sont facultatifs et la valeur par défaut est zéro si l’utilisateur les quitte. Cela signifie que si l’utilisateur spécifie uniquement « 12,2 » comme numéro de version de base de données locale, il est traité comme si l’utilisateur avait spécifié « 12.2.0.0 ».</span><span class="sxs-lookup"><span data-stu-id="8969c-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="8969c-113">La version pour l'installation de LocalDB est définie dans la clé de Registre MSSQLServer\CurrentVersion sous la clé de Registre de l'instance de SQL Server, par exemple :</span><span class="sxs-lookup"><span data-stu-id="8969c-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="8969c-114">Plusieurs versions de LocalDB sur la même station de travail sont prises en charge côte à côte.</span><span class="sxs-lookup"><span data-stu-id="8969c-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="8969c-115">Toutefois, le code utilisateur utilise toujours la dernière dll **SQLUserInstance** disponible sur l’ordinateur local pour se connecter aux instances de base de données locale.</span><span class="sxs-lookup"><span data-stu-id="8969c-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="8969c-116">Recherche de la DLL SQLUserInstance</span><span class="sxs-lookup"><span data-stu-id="8969c-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="8969c-117">Pour localiser la dll **SQLUserInstance** , le fournisseur client utilise la clé de Registre suivante :</span><span class="sxs-lookup"><span data-stu-id="8969c-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="8969c-118">Sous cette clé il existe une liste des clés, une pour chaque version de LocalDB installée sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8969c-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="8969c-119">Chacune de ces clés est nommée avec le numéro de version de la base de données locale au format *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="8969c-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="8969c-120">(par exemple, la clé de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] est nommée 12,0).</span><span class="sxs-lookup"><span data-stu-id="8969c-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="8969c-121">Sous chaque clé de version il existe des paires nom-valeur de `InstanceAPIPath` qui définissent le chemin d'accès complet au fichier de SQLUserInstance.dll installé avec cette version.</span><span class="sxs-lookup"><span data-stu-id="8969c-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="8969c-122">L'exemple suivant illustre les entrées de Registre d'un ordinateur sur lequel les versions 11.0 et 12.0 de LocalDB sont installées :</span><span class="sxs-lookup"><span data-stu-id="8969c-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="8969c-123">Le fournisseur client doit trouver la version la plus récente parmi toutes les versions installées et charger le fichier dll **SQLUserInstance** à partir de la `InstanceAPIPath` valeur associée.</span><span class="sxs-lookup"><span data-stu-id="8969c-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="8969c-124">Mode WOW64 sur Windows 64 bits</span><span class="sxs-lookup"><span data-stu-id="8969c-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="8969c-125">Les installations 64 bits de LocalDB ont un jeu supplémentaire de clés de Registre pour permettre aux applications 32 bits s'exécutant en mode Windows-32-on-Windows-64 (WOW64) d'utiliser LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8969c-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="8969c-126">En particulier, sur Windows 64 bits, le fichier MSI de LocalDB crée les clés de Registre suivantes :</span><span class="sxs-lookup"><span data-stu-id="8969c-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="8969c-127">les programmes 64 bits qui lisent la `Installed Versions` clé voient les valeurs pointant vers les versions 64 bits de la dll **SQLUserInstance** , tandis que les programmes 32 bits (exécutés sur des fenêtres 64 bits en mode WOW64) sont automatiquement redirigés vers une `Installed Versions` clé située sous la `Wow6432Node` ruche.</span><span class="sxs-lookup"><span data-stu-id="8969c-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="8969c-128">Cette clé contient des valeurs qui pointent vers les versions 32 bits de la dll **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="8969c-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="8969c-129">Utilisation de LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="8969c-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="8969c-130">L’API d’instance de base de données locale définit une constante nommée LOCALDB_DEFINE_PROXY_FUNCTIONS qui automatise la découverte et le chargement de la dll **SqlUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="8969c-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="8969c-131">La section de code activée par cette constante fournit une implémentation des proxys pour chacune des API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8969c-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="8969c-132">Les implémentations de proxy utilisent une fonction commune pour la liaison aux points d’entrée dans la dernière dll **SqlUserInstance** installée, puis transfèrent les requêtes.</span><span class="sxs-lookup"><span data-stu-id="8969c-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="8969c-133">Les fonctions de proxy ne sont activées que si la constante LOCALDB_DEFINE_PROXY_FUNCTIONS est définie dans le code utilisateur avant d'inclure le fichier sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="8969c-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="8969c-134">La constante doit être définie dans un seul module source (fichier .cpp), car elle définit les noms de fonctions externes pour tous les points d'entrée d'API.</span><span class="sxs-lookup"><span data-stu-id="8969c-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="8969c-135">Elle fournit une implémentation des proxys pour chacune des API de LocalDB.</span><span class="sxs-lookup"><span data-stu-id="8969c-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="8969c-136">L'exemple de code suivant montre comment utiliser la macro du code C++ natif :</span><span class="sxs-lookup"><span data-stu-id="8969c-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
