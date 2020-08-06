---
title: Ajout d’une procédure stockée étendue à SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612352"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="adf4e-102">Ajout d'une procédure stockée étendue à SQL Server</span><span class="sxs-lookup"><span data-stu-id="adf4e-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="adf4e-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="adf4e-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="adf4e-104">Une DLL qui contient des fonctions de procédure stockée étendue joue le rôle d'extension pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adf4e-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="adf4e-105">Pour installer la DLL, copiez le fichier dans un répertoire, tel que celui qui contient les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichiers dll standard (C:\Program Files\Microsoft SQL Server\MSSQL12.0.\* x\*\MSSQL\Binn par défaut).</span><span class="sxs-lookup"><span data-stu-id="adf4e-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="adf4e-106">Une fois la DLL de procédure stockée étendue copiée vers le serveur, un administrateur système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit inscrire dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] chaque fonction de procédure stockée étendue dans la DLL.</span><span class="sxs-lookup"><span data-stu-id="adf4e-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="adf4e-107">Vous devez pour cela utiliser la procédure stockée système sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="adf4e-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="adf4e-108">Il est conseillé à l'administrateur système de vérifier minutieusement la procédure stockée étendue afin de s'assurer qu'elle ne contient aucun code nuisible ou malveillant avant de l'ajouter au serveur et d'accorder à d'autres utilisateurs des autorisations d'exécution.</span><span class="sxs-lookup"><span data-stu-id="adf4e-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="adf4e-109">Validez toutes les entrées utilisateur.</span><span class="sxs-lookup"><span data-stu-id="adf4e-109">Validate all user input.</span></span> <span data-ttu-id="adf4e-110">Ne concaténez pas les entrées utilisateur avant de les valider.</span><span class="sxs-lookup"><span data-stu-id="adf4e-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="adf4e-111">N'exécutez jamais une commande élaborée à partir d'une entrée utilisateur non validée.</span><span class="sxs-lookup"><span data-stu-id="adf4e-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="adf4e-112">Le premier paramètre de sp_addextendedproc spécifie le nom de la fonction et le deuxième paramètre spécifie le nom de la DLL dans laquelle cette fonction réside.</span><span class="sxs-lookup"><span data-stu-id="adf4e-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="adf4e-113">Il est recommandé de spécifier le chemin complet d'accès à la DLL.</span><span class="sxs-lookup"><span data-stu-id="adf4e-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="adf4e-114">Les DLL existantes qui n'ont pas été inscrites avec un chemin d'accès complet ne fonctionneront plus après une mise à niveau vers SQL Server 2005 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="adf4e-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="adf4e-115">Pour corriger ce problème, utilisez sp_dropextendedproc pour annuler l'inscription de la DLL, puis inscrivez-la de nouveau avec la procédure sp_addextendedproc, en spécifiant le chemin d'accès complet.</span><span class="sxs-lookup"><span data-stu-id="adf4e-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="adf4e-116">Le nom de la fonction spécifié dans `sp_addextendedproc` doit être exactement identique (y compris la casse) au nom de la fonction dans la DLL.</span><span class="sxs-lookup"><span data-stu-id="adf4e-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="adf4e-117">Par exemple, cette commande inscrit une fonction `xp_hello,` située dans une DLL nommée `xp_hello.dll`, en tant que procédure stockée étendue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="adf4e-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="adf4e-118">Si le nom de la fonction spécifié dans `sp_addextendedproc` ne correspond pas exactement au nom de fonction dans la DLL, le nouveau nom sera inscrit dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais le nom ne sera pas utilisable.</span><span class="sxs-lookup"><span data-stu-id="adf4e-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="adf4e-119">Par exemple, même si `xp_Hello` est inscrit en tant que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procédure stockée étendue située dans, ne pourra `xp_hello.dll` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pas trouver la fonction dans la dll si vous utilisez `xp_Hello` pour appeler la fonction ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="adf4e-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="adf4e-120">Si le nom de la fonction spécifié dans `sp_addextendedproc` correspond exactement au nom de fonction dans la DLL et que le classement de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas sensible à la casse, l'utilisateur peut appeler la procédure stockée étendue à l'aide de toute combinaison de lettres minuscules et majuscules du nom.</span><span class="sxs-lookup"><span data-stu-id="adf4e-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="adf4e-121">Lorsque le classement de l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] respecte la casse, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne sera pas en mesure d'appeler la procédure stockée étendue (même si elle a été inscrite avec exactement les mêmes nom et classement que la fonction dans la DLL) si la procédure est appelée avec une casse différente.</span><span class="sxs-lookup"><span data-stu-id="adf4e-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="adf4e-122">Il n'est pas nécessaire d'arrêter et de redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adf4e-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf4e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="adf4e-123">See Also</span></span>  
 <span data-ttu-id="adf4e-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="adf4e-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="adf4e-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="adf4e-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
