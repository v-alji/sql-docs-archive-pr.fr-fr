---
title: Comparer des tables répliquées pour identifier les différences (programmation de réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709263"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="29252-102">Comparer des tables répliquées pour identifier les différences (programmation de réplication)</span><span class="sxs-lookup"><span data-stu-id="29252-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="29252-103">La validation d'article est utilisée pour déterminer si les données publiées pour les articles de table sur le serveur de publication et sur l'Abonné ne sont pas identiques, ce qui peut indiquer une non-convergence.</span><span class="sxs-lookup"><span data-stu-id="29252-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="29252-104">Pour plus d’informations, consultez [Valider des données répliquées](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="29252-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="29252-105">Toutefois, la validation retourne uniquement des informations de succès ou d'échec et ne fournit pas d'informations sur les différences entre les tables sources et les tables cibles.</span><span class="sxs-lookup"><span data-stu-id="29252-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="29252-106">L’utilitaire d’invite de commandes **tablediff** retourne des informations détaillées sur les différences entre les deux tables et peut même générer un script [!INCLUDE[tsql](../../../includes/tsql-md.md)] pour établir la convergence de l’abonnement avec les données sur le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="29252-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29252-107">L’utilitaire **tablediff** est pris en charge uniquement pour les serveurs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29252-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="29252-108">Pour comparer les différences des tables répliquées à l'aide de tablediff</span><span class="sxs-lookup"><span data-stu-id="29252-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="29252-109">À partir de l'invite de commandes sur un serveur quelconque d'une topologie de réplication, exécutez l' [tablediff Utility](../../../tools/tablediff-utility.md).</span><span class="sxs-lookup"><span data-stu-id="29252-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="29252-110">Spécifiez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="29252-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="29252-111">**-sourceserver** - nom du serveur sur lequel les données sont reconnues comme correctes, habituellement le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="29252-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="29252-112">**-sourcedatabase** - nom de la base de données contenant les données correctes.</span><span class="sxs-lookup"><span data-stu-id="29252-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="29252-113">**-sourcetable** - nom de la table source pour l'article comparé.</span><span class="sxs-lookup"><span data-stu-id="29252-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="29252-114">(Facultatif) **-sourceschema** - propriétaire du schéma de la table source, sinon le schéma par défaut.</span><span class="sxs-lookup"><span data-stu-id="29252-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="29252-115">(Facultatif) **-sourceuser** et **-sourcepassword** en cas d'utilisation de l'authentification SQL Server pour se connecter au serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="29252-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="29252-116">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="29252-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="29252-117">Si vous devez utiliser l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , invitez les utilisateurs à entrer les informations d'identification de sécurité pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="29252-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="29252-118">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="29252-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="29252-119">**-destinationserver** - nom du serveur sur lequel les données sont comparées, habituellement un Abonné.</span><span class="sxs-lookup"><span data-stu-id="29252-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="29252-120">**-destinationdatabase** - nom de la base de données en cours de comparaison.</span><span class="sxs-lookup"><span data-stu-id="29252-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="29252-121">**-destinationtable** - nom de la table qui est comparée.</span><span class="sxs-lookup"><span data-stu-id="29252-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="29252-122">(Facultatif) **-destinationschema** - propriétaire du schéma de la table cible, sinon le schéma par défaut.</span><span class="sxs-lookup"><span data-stu-id="29252-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="29252-123">(Facultatif) **-destinationuser** et **-destinationpassword** en cas d'utilisation de l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour se connecter à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="29252-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="29252-124">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="29252-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="29252-125">Si vous devez utiliser l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , invitez les utilisateurs à entrer les informations d'identification de sécurité pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="29252-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="29252-126">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="29252-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="29252-127">(Facultatif) Utilisez **-c** pour faire une comparaison au niveau des colonnes.</span><span class="sxs-lookup"><span data-stu-id="29252-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="29252-128">(Facultatif) Utilisez **- q** pour faire une comparaison rapide du nombre de lignes et du schéma uniquement.</span><span class="sxs-lookup"><span data-stu-id="29252-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="29252-129">(Facultatif) Spécifiez un nom de fichier et un chemin d'accès pour **-o** pour générer la sortie des résultats dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="29252-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="29252-130">(Facultatif) Spécifiez une table de la base de données d'abonnement dans laquelle insérer les résultats pour **-et**.</span><span class="sxs-lookup"><span data-stu-id="29252-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="29252-131">Si la table existe déjà, spécifiez **-dt** pour supprimer d'abord la table.</span><span class="sxs-lookup"><span data-stu-id="29252-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="29252-132">(Facultatif) Utilisez **-f** pour générer un fichier [!INCLUDE[tsql](../../../includes/tsql-md.md)] et corriger les données sur l'Abonné afin qu'elles correspondent à celles du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="29252-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="29252-133">Utilisez **-df** pour spécifier le nombre d'instructions [!INCLUDE[tsql](../../../includes/tsql-md.md)] dans chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="29252-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="29252-134">(Facultatif) Utilisez **-rc** et **-ri** pour spécifier le nombre de tentatives autorisées pour une opération et l'intervalle avant chaque nouvelle tentative.</span><span class="sxs-lookup"><span data-stu-id="29252-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="29252-135">(Facultatif) Utilisez **-strict** pour mettre en vigueur la comparaison stricte de schémas entre les tables sources et les tables cibles.</span><span class="sxs-lookup"><span data-stu-id="29252-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29252-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29252-136">See Also</span></span>  
 [<span data-ttu-id="29252-137">Valider des données sur l’abonné</span><span class="sxs-lookup"><span data-stu-id="29252-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  
