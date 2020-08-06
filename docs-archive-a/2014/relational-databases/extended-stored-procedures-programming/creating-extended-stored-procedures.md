---
title: Création de procédures stockées étendues | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612350"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="1a428-102">Création de procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="1a428-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1a428-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="1a428-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="1a428-104">Une procédure stockée étendue est une fonction avec un prototype :</span><span class="sxs-lookup"><span data-stu-id="1a428-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="1a428-105">*Xp_extendedProcName* SRVRETCODE **(** SRVPROC \*\* \* );\*\*</span><span class="sxs-lookup"><span data-stu-id="1a428-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="1a428-106">L'utilisation du préfixe xp_ est facultative.</span><span class="sxs-lookup"><span data-stu-id="1a428-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="1a428-107">Les noms de procédures stockées étendues respectent la casse lorsqu'ils sont référencés dans des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)], indépendamment de la page de codes/de l'ordre de tri sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1a428-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="1a428-108">Lorsque vous générez une DLL :</span><span class="sxs-lookup"><span data-stu-id="1a428-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="1a428-109">Si un point d'entrée est nécessaire, écrivez une fonction DllMain.</span><span class="sxs-lookup"><span data-stu-id="1a428-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="1a428-110">Cette fonction est facultative ; si vous ne la fournissez pas dans le code source, le compilateur lie sa propre version, qui ne fait rien d'autre que de retourner TRUE.</span><span class="sxs-lookup"><span data-stu-id="1a428-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="1a428-111">Si vous fournissez une fonction DllMain, le système d'exploitation appelle cette fonction lorsqu'un thread ou un processus est attaché à la DLL ou détaché de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="1a428-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="1a428-112">Toutes les fonctions appelées hors de la DLL (toutes les procédures stockées étendues Efunctions) doivent être exportées.</span><span class="sxs-lookup"><span data-stu-id="1a428-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="1a428-113">Vous pouvez exporter une fonction en répertoriant son nom dans la section EXPORTS d’un fichier. def, ou vous pouvez faire précéder le nom de la fonction dans le code source de __declspec (dllexport), une extension du compilateur Microsoft (Notez que \_ _declspec () commence par deux traits de soulignement).</span><span class="sxs-lookup"><span data-stu-id="1a428-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="1a428-114">Ces fichiers sont requis pour la création d'une DLL de procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="1a428-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="1a428-115">Fichier</span><span class="sxs-lookup"><span data-stu-id="1a428-115">File</span></span>|<span data-ttu-id="1a428-116">Description</span><span class="sxs-lookup"><span data-stu-id="1a428-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1a428-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="1a428-117">Srv.h</span></span>|<span data-ttu-id="1a428-118">Fichier d'en-tête de l'API de procédure stockée étendue</span><span class="sxs-lookup"><span data-stu-id="1a428-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="1a428-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="1a428-119">Opends60.lib</span></span>|<span data-ttu-id="1a428-120">Bibliothèque d'importation pour Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="1a428-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="1a428-121">Pour créer une DLL de procédure stockée étendue, créez un projet de type bibliothèque de liens dynamiques.</span><span class="sxs-lookup"><span data-stu-id="1a428-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="1a428-122">Pour plus d'informations sur la création d'une DLL, consultez la documentation relative à l'environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="1a428-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="1a428-123">Il est fortement recommandé que toutes les DLL de procédures stockées étendues implémentent et exportent la fonction suivante :</span><span class="sxs-lookup"><span data-stu-id="1a428-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="1a428-124">__declspec(dllexport) est une extension du compilateur spécifique à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a428-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="1a428-125">Si votre compilateur ne prend pas en charge cette directive, vous devez exporter cette fonction dans votre fichier DEF sous la section EXPORTS.</span><span class="sxs-lookup"><span data-stu-id="1a428-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="1a428-126">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est démarré avec l’indicateur de trace-T260 ou si un utilisateur disposant de privilèges d’administrateur système exécute DBCC TRACEON (260) et si la dll de procédure stockée étendue ne prend pas en charge __GetXpVersion (), un message d’avertissement (erreur 8131 : la dll de procédure stockée étendue'% 'n’exporte pas \_ _GetXpVersion ()) est imprimé dans le journal des erreurs</span><span class="sxs-lookup"><span data-stu-id="1a428-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="1a428-127">(Notez que \_ _GetXpVersion () commence par deux traits de soulignement.)</span><span class="sxs-lookup"><span data-stu-id="1a428-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="1a428-128">Si la DLL de procédure stockée étendue exporte __GetXpVersion(), mais que la version retournée par la fonction est antérieure à celle requise par le serveur, un message d'avertissement indiquant la version retournée par la fonction et la version attendue par le serveur est écrit dans le journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="1a428-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="1a428-129">Si vous recevez ce message, vous retournez une valeur incorrecte à partir de \_ _GetXpVersion () ou vous compilez avec une version antérieure de SRV. h.</span><span class="sxs-lookup"><span data-stu-id="1a428-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1a428-130">SetErrorMode (fonction [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32) ne doit pas être appelé dans les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="1a428-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="1a428-131">Il est recommandé que toute procédure stockée étendue dont l'exécution est longue, appelle périodiquement srv_got_attention afin que la procédure puisse se terminer si la connexion est arrêtée ou si le lot est abandonné.</span><span class="sxs-lookup"><span data-stu-id="1a428-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="1a428-132">Pour déboguer une DLL de procédure stockée étendue, copiez-la vers le répertoire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="1a428-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="1a428-133">Pour spécifier le fichier exécutable de la session de débogage, entrez le chemin d’accès et le nom du fichier [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécutable (par exemple, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span><span class="sxs-lookup"><span data-stu-id="1a428-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="1a428-134">Pour plus d’informations sur les arguments sqlservr, consultez la rubrique [application sqlservr](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="1a428-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a428-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a428-135">See Also</span></span>  
 [<span data-ttu-id="1a428-136">srv_got_attention &#40;API de procédure stockée étendue&#41;</span><span class="sxs-lookup"><span data-stu-id="1a428-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
