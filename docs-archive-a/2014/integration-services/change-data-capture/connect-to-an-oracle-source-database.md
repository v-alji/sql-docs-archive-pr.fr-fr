---
title: Connexion à une base de données source Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704352"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="d7a88-102">Connexion à une base de données source Oracle</span><span class="sxs-lookup"><span data-stu-id="d7a88-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="d7a88-103">La page Source Oracle permet de fournir les informations nécessaires pour la connexion à la base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="d7a88-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="d7a88-104">L'instance de capture de données modifiées lit les journaux de restauration par progression de la base de données Oracle à laquelle vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="d7a88-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="d7a88-105">**Chaîne de connexion Oracle**</span><span class="sxs-lookup"><span data-stu-id="d7a88-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="d7a88-106">Entrez la chaîne de connexion Oracle à l'ordinateur sur lequel est installée la base de données Oracle que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="d7a88-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="d7a88-107">La chaîne de connexion est entrée de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7a88-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="d7a88-108">La chaîne de connexion peut également spécifier un descripteur de connexion Oracle Net, par exemple, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="d7a88-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="d7a88-109">Si vous utilisez un serveur d'annuaire ou des noms TNS, la chaîne de connexion peut être le nom de la connexion.</span><span class="sxs-lookup"><span data-stu-id="d7a88-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="d7a88-110">**Authentification pour l'exploration de données de journaux Oracle**</span><span class="sxs-lookup"><span data-stu-id="d7a88-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="d7a88-111">Pour entrer les informations d'identification de l'utilisateur de la base de données Oracle qui est autorisé à explorer les données de journaux, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7a88-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="d7a88-112">**Authentification Windows**: sélectionnez cette option pour utiliser les informations d'identification actuelles de domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="d7a88-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="d7a88-113">Vous ne pouvez utiliser cette option que si la base de données Oracle est configurée pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="d7a88-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="d7a88-114">**Authentification Oracle**: si vous sélectionnez cette option, vous devez taper le **Nom d'utilisateur** et le **Mot de passe** de l'utilisateur dans la base de données Oracle à laquelle vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="d7a88-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7a88-115">Un utilisateur doit avoir les privilèges suivants dans la base de données Oracle de façon à être un utilisateur d'exploration de données de journaux.</span><span class="sxs-lookup"><span data-stu-id="d7a88-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="d7a88-116">SELECT sur \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="d7a88-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="d7a88-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="d7a88-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="d7a88-118">EXECUTE sur DBMS_LOGMNR</span><span class="sxs-lookup"><span data-stu-id="d7a88-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="d7a88-119">SELECT sur V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="d7a88-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="d7a88-120">SELECT sur V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="d7a88-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="d7a88-121">SELECT sur V$LOG</span><span class="sxs-lookup"><span data-stu-id="d7a88-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="d7a88-122">SELECT sur V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="d7a88-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="d7a88-123">SELECT sur V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="d7a88-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="d7a88-124">SELECT sur V$THREAD</span><span class="sxs-lookup"><span data-stu-id="d7a88-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="d7a88-125">SELECT sur ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="d7a88-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="d7a88-126">SELECT sur ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="d7a88-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="d7a88-127">SELECT sur DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="d7a88-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="d7a88-128">SELECT sur ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="d7a88-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="d7a88-129">Si l'un de ces privilèges ne peut pas être accordé à V$xxx, alors accordez-les à V_S$xxx.</span><span class="sxs-lookup"><span data-stu-id="d7a88-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="d7a88-130">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="d7a88-130">**Test Connection**</span></span>  
 <span data-ttu-id="d7a88-131">Cliquez sur **Tester la connexion** pour déterminer si vous avez établi une connexion avec l’ordinateur distant sur lequel la base de données Oracle est installée.</span><span class="sxs-lookup"><span data-stu-id="d7a88-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="d7a88-132">Une boîte de dialogue s'ouvre pour vous indiquer si la connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="d7a88-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d7a88-133">En raison d'un problème connu, la connexion à la base de données source Oracle peut échouer si le concepteur CDC n'est pas exécuté en tant qu'administrateur.</span><span class="sxs-lookup"><span data-stu-id="d7a88-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="d7a88-134">Si la connexion échoue, fermez et redémarrez le concepteur CDC à l'aide de l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="d7a88-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="d7a88-135">Une fois les informations entrées sur cette page, cliquez sur **Suivant** pour [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d7a88-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a88-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7a88-136">See Also</span></span>  
 <span data-ttu-id="d7a88-137">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d7a88-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="d7a88-138">Modifier les propriétés d’une instance</span><span class="sxs-lookup"><span data-stu-id="d7a88-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
