---
title: Utilitaire SqlLocalDB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694916"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="356d9-102">Utilitaire SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="356d9-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="356d9-103">Utilisez l' `SqlLocalDB` utilitaire pour créer une instance de base de données locale [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="356d9-104">L' `SqlLocalDB` utilitaire (SqlLocalDB.exe) est un outil de ligne de commande simple pour permettre aux utilisateurs et aux développeurs de créer et de gérer une instance de base de données locale [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="356d9-105">Pour plus d’informations sur l’utilisation de la **base de données locale, consultez** [SQL Server 2014 Express](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span><span class="sxs-lookup"><span data-stu-id="356d9-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="356d9-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="356d9-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="356d9-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="356d9-107">Arguments</span></span>  
 <span data-ttu-id="356d9-108">[ **créer** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="356d9-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="356d9-109">Crée une instance de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="356d9-110">`SqlLocalDB`utilise la version des [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] fichiers binaires spécifiée par l' *\<instance-version>* argument.</span><span class="sxs-lookup"><span data-stu-id="356d9-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="356d9-111">Le numéro de version est spécifié au format numérique avec au moins une décimale.</span><span class="sxs-lookup"><span data-stu-id="356d9-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="356d9-112">Les numéros de version secondaire (Service Packs) sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="356d9-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="356d9-113">Par exemple, les deux numéros de version suivants sont acceptables : 11.0 ou 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="356d9-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="356d9-114">La version spécifiée doit être installée sur l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="356d9-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="356d9-115">S’il n’est pas spécifié, le numéro de version est défini par défaut sur la version de l' `SqlLocalDB` utilitaire.</span><span class="sxs-lookup"><span data-stu-id="356d9-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="356d9-116">L’ajout de **-s** permet de démarrer la nouvelle instance de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="356d9-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="356d9-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="356d9-118">Partage l’instance privée spécifiée de **LocalDB** à l’aide du nom partagé spécifié.</span><span class="sxs-lookup"><span data-stu-id="356d9-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="356d9-119">Si le SID ou le nom de compte de l'utilisateur est omis, il prend par défaut la valeur de l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="356d9-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="356d9-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="356d9-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="356d9-121">Arrête le partage de l’instance partagée spécifiée de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="356d9-122">[ **supprimer** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="356d9-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="356d9-123">Supprime l’instance spécifiée de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="356d9-124">[**démarrer** | **s**] « *\<instance-name>*  »</span><span class="sxs-lookup"><span data-stu-id="356d9-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="356d9-125">Démarre l’instance spécifiée de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="356d9-126">En cas de réussite de l'opération, l'instruction retourne l'adresse du canal nommé de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="356d9-127">[**Arrêter** | **p**] *\<instance-name>* [ **-i**] [ **-k**]</span><span class="sxs-lookup"><span data-stu-id="356d9-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="356d9-128">Arrête l’instance spécifiée de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="356d9-129">Ajout **de-i** demande l’arrêt de l’instance avec l' `NOWAIT` option.</span><span class="sxs-lookup"><span data-stu-id="356d9-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="356d9-130">L’ajout de **-k** met fin au processus de l’instance sans le contacter.</span><span class="sxs-lookup"><span data-stu-id="356d9-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="356d9-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="356d9-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="356d9-132">Répertorie toutes les instances de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** détenues par l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="356d9-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="356d9-133">*\<instance-name>* retourne le nom, la version, l’état (En cours d’exécution ou Arrêté), la dernière heure de début de l’instance spécifiée de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** et le nom du canal local de **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="356d9-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="356d9-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="356d9-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="356d9-135">**trace on** active le suivi des `SqlLocalDB` appels d’API pour l’utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="356d9-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="356d9-136">**trace off** désactive le suivi.</span><span class="sxs-lookup"><span data-stu-id="356d9-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="356d9-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="356d9-137">**-?**</span></span>  
 <span data-ttu-id="356d9-138">Retourne une brève description de chaque `SqlLocalDB` option.</span><span class="sxs-lookup"><span data-stu-id="356d9-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="356d9-139">Notes</span><span class="sxs-lookup"><span data-stu-id="356d9-139">Remarks</span></span>  
 <span data-ttu-id="356d9-140">L’argument *instance name* doit respecter les règles applicables aux identificateurs [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou il doit être placé entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="356d9-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="356d9-141">L’exécution de SqlLocalDB sans arguments retourne le texte d’aide.</span><span class="sxs-lookup"><span data-stu-id="356d9-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="356d9-142">Les opérations autres que le démarrage peuvent être exécutées sur une instance appartenant à l'utilisateur actuellement connecté.</span><span class="sxs-lookup"><span data-stu-id="356d9-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="356d9-143">Exemples</span><span class="sxs-lookup"><span data-stu-id="356d9-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="356d9-144">R.</span><span class="sxs-lookup"><span data-stu-id="356d9-144">A.</span></span> <span data-ttu-id="356d9-145">Création d'une instance de LocalDB</span><span class="sxs-lookup"><span data-stu-id="356d9-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="356d9-146">L’exemple suivant crée une instance de [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** nommée `DEPARTMENT` utilisant les binaires [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] et démarre l’instance.</span><span class="sxs-lookup"><span data-stu-id="356d9-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="356d9-147">B.</span><span class="sxs-lookup"><span data-stu-id="356d9-147">B.</span></span> <span data-ttu-id="356d9-148">Utilisation d'une instance partagée de LocalDB</span><span class="sxs-lookup"><span data-stu-id="356d9-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="356d9-149">Ouvrez une invite de commandes en utilisant des autorisations d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="356d9-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="356d9-150">Exécutez le code suivant pour vous connecter à l'instance partagée de **LocalDB** à l'aide de la connexion `NewLogin` .</span><span class="sxs-lookup"><span data-stu-id="356d9-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="356d9-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="356d9-151">See Also</span></span>  
 [<span data-ttu-id="356d9-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="356d9-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
