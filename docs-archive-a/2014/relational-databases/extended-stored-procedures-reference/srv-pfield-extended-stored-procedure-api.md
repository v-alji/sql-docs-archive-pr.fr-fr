---
title: srv_pfield (API de procédure stockée étendue) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709480"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="bbff0-102">srv_pfield (API de procédure stockée étendue)</span><span class="sxs-lookup"><span data-stu-id="bbff0-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="bbff0-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="bbff0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="bbff0-104">Retourne des informations sur une connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="bbff0-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbff0-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bbff0-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="bbff0-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="bbff0-106">Arguments</span></span>  
 <span data-ttu-id="bbff0-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="bbff0-107">*srvproc*</span></span>  
 <span data-ttu-id="bbff0-108">Pointeur identifiant une connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="bbff0-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="bbff0-109">*case*</span><span class="sxs-lookup"><span data-stu-id="bbff0-109">*field*</span></span>  
 <span data-ttu-id="bbff0-110">Spécifie des données sur la connexion à retourner.</span><span class="sxs-lookup"><span data-stu-id="bbff0-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="bbff0-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="bbff0-111">Value</span></span>|<span data-ttu-id="bbff0-112">Retours</span><span class="sxs-lookup"><span data-stu-id="bbff0-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="bbff0-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="bbff0-113">SRV_APPLNAME</span></span>|<span data-ttu-id="bbff0-114">Nom d'application fourni par le client au moment d'établir la connexion.</span><span class="sxs-lookup"><span data-stu-id="bbff0-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="bbff0-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="bbff0-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="bbff0-116">Indicateur possédant la valeur TRUE si le client prépare une opération de copie en bloc ou la valeur FALSE dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="bbff0-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="bbff0-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="bbff0-117">SRV_CLIB</span></span>|<span data-ttu-id="bbff0-118">Nom de la bibliothèque permettant au client de communiquer avec un serveur.</span><span class="sxs-lookup"><span data-stu-id="bbff0-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="bbff0-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="bbff0-119">SRV_CPID</span></span>|<span data-ttu-id="bbff0-120">ID de processus client sur l'ordinateur source client.</span><span class="sxs-lookup"><span data-stu-id="bbff0-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="bbff0-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="bbff0-121">SRV_HOST</span></span>|<span data-ttu-id="bbff0-122">Nom de l'ordinateur client fourni par le client au moment d'établir la connexion.</span><span class="sxs-lookup"><span data-stu-id="bbff0-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="bbff0-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="bbff0-123">SRV_LIBVERS</span></span>|<span data-ttu-id="bbff0-124">Version de la bibliothèque cliente.</span><span class="sxs-lookup"><span data-stu-id="bbff0-124">The version of the client library.</span></span>|  
|<span data-ttu-id="bbff0-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="bbff0-125">SRV_LSECURE</span></span>|<span data-ttu-id="bbff0-126">Indicateur.</span><span class="sxs-lookup"><span data-stu-id="bbff0-126">A flag.</span></span> <span data-ttu-id="bbff0-127">Possède la valeur TRUE si la connexion a été établie au moyen de la sécurité intégrée.</span><span class="sxs-lookup"><span data-stu-id="bbff0-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="bbff0-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="bbff0-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="bbff0-129">Nom de la DLL Net-Library utilisée par la connexion.</span><span class="sxs-lookup"><span data-stu-id="bbff0-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="bbff0-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="bbff0-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="bbff0-131">Version de la DLL Net-Library utilisée par la connexion.</span><span class="sxs-lookup"><span data-stu-id="bbff0-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="bbff0-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="bbff0-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="bbff0-133">Chaîne de connexion passée à la DLL Net-library employée pour la connexion *srvproc* actuelle.</span><span class="sxs-lookup"><span data-stu-id="bbff0-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="bbff0-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="bbff0-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="bbff0-135">Chaîne contenant le handle de canal d'un client connecté ou la valeur NULL si le client est connecté sur un réseau qui n'utilise pas de canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="bbff0-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="bbff0-136">Pour utiliser ce handle comme handle de canal valide avec [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convertissez cette chaîne en entier.</span><span class="sxs-lookup"><span data-stu-id="bbff0-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="bbff0-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="bbff0-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="bbff0-138">Serveur à partir duquel le processus client est connecté.</span><span class="sxs-lookup"><span data-stu-id="bbff0-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="bbff0-139">Si la connexion provient d'un client, cette valeur est une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="bbff0-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="bbff0-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="bbff0-140">SRV_ROWSENT</span></span>|<span data-ttu-id="bbff0-141">Nombre de lignes déjà transmises par *srvproc* pour le jeu de résultats actuel.</span><span class="sxs-lookup"><span data-stu-id="bbff0-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="bbff0-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="bbff0-142">SRV_SPID</span></span>|<span data-ttu-id="bbff0-143">ID de thread sur le serveur de *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="bbff0-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="bbff0-144">Pour les procédures stockées étendues, cette valeur est la même que celle de la colonne **kpid** de **sys.sysprocesses** et peut changer par la suite.</span><span class="sxs-lookup"><span data-stu-id="bbff0-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="bbff0-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="bbff0-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="bbff0-146">Page de codes employée par le serveur pour interpréter des données multioctets.</span><span class="sxs-lookup"><span data-stu-id="bbff0-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="bbff0-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="bbff0-147">SRV_STATUS</span></span>|<span data-ttu-id="bbff0-148">État actuel de *srvproc* : en cours d’exécution ou fermé.</span><span class="sxs-lookup"><span data-stu-id="bbff0-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="bbff0-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="bbff0-149">SRV_TYPE</span></span>|<span data-ttu-id="bbff0-150">Type de connexion de *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="bbff0-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="bbff0-151">Si le serveur est retourné, *srvproc* provient d’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbff0-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bbff0-152">Si le client est retourné, *srvproc* provient d’une bibliothèque de bases de données ou d’un client ODBC.</span><span class="sxs-lookup"><span data-stu-id="bbff0-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="bbff0-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="bbff0-153">SRV_USER</span></span>|<span data-ttu-id="bbff0-154">Nom de l'utilisateur de la connexion.</span><span class="sxs-lookup"><span data-stu-id="bbff0-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="bbff0-155">*Len*</span><span class="sxs-lookup"><span data-stu-id="bbff0-155">*len*</span></span>  
 <span data-ttu-id="bbff0-156">Pointeur vers une variable **int** contenant la longueur de la valeur *field* retournée.</span><span class="sxs-lookup"><span data-stu-id="bbff0-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="bbff0-157">Si *len* a la valeur NULL; la longueur de la chaîne n’est pas retournée.</span><span class="sxs-lookup"><span data-stu-id="bbff0-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="bbff0-158">Retours</span><span class="sxs-lookup"><span data-stu-id="bbff0-158">Returns</span></span>  
 <span data-ttu-id="bbff0-159">Pointeur vers une chaîne terminée par le caractère NULL contenant la valeur actuelle du champ spécifié dans la structure SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="bbff0-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="bbff0-160">Si le champ est vide, un pointeur valide vers une chaîne vide est retourné et *len* contient la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="bbff0-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="bbff0-161">Si le champ est inconnu, la valeur NULL est retournée et *len* contient la valeur -1.</span><span class="sxs-lookup"><span data-stu-id="bbff0-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bbff0-162">Il est préférable d'examiner avec soin le code source des procédures stockées étendues et de tester les DLL compilées avant de les installer sur un serveur de production.</span><span class="sxs-lookup"><span data-stu-id="bbff0-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="bbff0-163">Pour plus d’informations sur cet examen et sur les tests de sécurité, consultez le site [TechCenter sur la sécurité](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="bbff0-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
