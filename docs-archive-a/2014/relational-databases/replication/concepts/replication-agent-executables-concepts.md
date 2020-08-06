---
title: Concepts des exécutables de l’agent de réplication | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: reference
helpviewer_keywords:
- programming interfaces [SQL Server replication]
- programming [SQL Server replication], agents
- replication [SQL Server], agents and profiles
- agents [SQL Server replication], executables
- command prompt [SQL Server replication]
ms.assetid: cba476df-d4ea-44c9-bb86-81488971e328
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73f9fe0d1a98fa1afc813cd113dcced685b4f98a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709215"
---
# <a name="replication-agent-executables-concepts"></a><span data-ttu-id="88c5e-102">Concepts des exécutables de l'agent de réplication</span><span class="sxs-lookup"><span data-stu-id="88c5e-102">Replication Agent Executables Concepts</span></span>
  <span data-ttu-id="88c5e-103">Il est possible de contrôler par programme les agents de réplication de différentes manières :</span><span class="sxs-lookup"><span data-stu-id="88c5e-103">Replication agents can be controlled programmatically in the following ways:</span></span>  
  
-   <span data-ttu-id="88c5e-104">en utilisant les interfaces de programmation d'agent managé dans l'espace de noms <xref:Microsoft.SqlServer.Replication> ;</span><span class="sxs-lookup"><span data-stu-id="88c5e-104">Using the managed agent programming interfaces in the <xref:Microsoft.SqlServer.Replication> Namespace.</span></span>  
  
-   <span data-ttu-id="88c5e-105">En appelant les fichiers exécutables de l'agent à partir de l'invite de commandes avec des paramètres définis.</span><span class="sxs-lookup"><span data-stu-id="88c5e-105">Invoking agent executable files from the command prompt with a supplied set of parameters.</span></span>  
  
 <span data-ttu-id="88c5e-106">Lorsque les agents de réplication sont directement appelés à partir de l'invite de commandes, il est possible d'accéder par programme aux agents à partir de scripts dans des fichiers de commandes.</span><span class="sxs-lookup"><span data-stu-id="88c5e-106">Directly invoking replication agents from the command prompt enables agents to be programmatically accessed from command-line scripting in batch files.</span></span> <span data-ttu-id="88c5e-107">Lorsqu'un agent est appelé à partir de l'invite de commandes, il s'exécute sous le compte de sécurité [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows de l'utilisateur qui a appelé l'agent ou qui a lancé le fichier de commandes.</span><span class="sxs-lookup"><span data-stu-id="88c5e-107">When an agent is invoked from the command prompt, it runs under the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows security account of the user that invoked the agent or started the batch file.</span></span>  
  
 <span data-ttu-id="88c5e-108">Il est possible d'exécuter des instances des agents de réplication suivants à l'aide de fichiers exécutables.</span><span class="sxs-lookup"><span data-stu-id="88c5e-108">Instances of the following replication agents can be run using executable files.</span></span>  
  
-   [<span data-ttu-id="88c5e-109">Replication Distribution Agent</span><span class="sxs-lookup"><span data-stu-id="88c5e-109">Replication Distribution Agent</span></span>](../agents/replication-distribution-agent.md)  
  
-   [<span data-ttu-id="88c5e-110">Agent de lecture du journal des réplications</span><span class="sxs-lookup"><span data-stu-id="88c5e-110">Replication Log Reader Agent</span></span>](../agents/replication-log-reader-agent.md)  
  
-   [<span data-ttu-id="88c5e-111">Replication Merge Agent</span><span class="sxs-lookup"><span data-stu-id="88c5e-111">Replication Merge Agent</span></span>](../agents/replication-merge-agent.md)  
  
-   [<span data-ttu-id="88c5e-112">Agent de lecture de la file d’attente de réplication</span><span class="sxs-lookup"><span data-stu-id="88c5e-112">Replication Queue Reader Agent</span></span>](../agents/replication-queue-reader-agent.md)  
  
-   [<span data-ttu-id="88c5e-113">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="88c5e-113">Replication Snapshot Agent</span></span>](../agents/replication-snapshot-agent.md)  
  
 <span data-ttu-id="88c5e-114">Lorsque vous appelez des agents de réplication, vous pouvez utiliser des profils de performances pour transmettre automatiquement un jeu défini de paramètres au fichier exécutable de l'agent.</span><span class="sxs-lookup"><span data-stu-id="88c5e-114">When invoking replication agents, you can use performance profiles to automatically pass a defined set of parameters to the agent executable.</span></span> <span data-ttu-id="88c5e-115">Pour plus d'informations, voir [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="88c5e-115">For more information, see [Replication Agent Profiles](../agents/replication-agent-profiles.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="88c5e-116">Exemples</span><span class="sxs-lookup"><span data-stu-id="88c5e-116">Examples</span></span>  
 <span data-ttu-id="88c5e-117">Les exemples suivants décrivent comment appeler les agents de réplication à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="88c5e-117">The following examples show how to invoke replication agents from the command prompt.</span></span> <span data-ttu-id="88c5e-118">Il est également possible d'appeler les agents de réplication au moyen de Replication Management Objects.</span><span class="sxs-lookup"><span data-stu-id="88c5e-118">Replication agents can also be invoked using Replication Management Objects (RMO).</span></span> <span data-ttu-id="88c5e-119">Pour plus d’informations, consultez [Synchroniser des abonnements &#40;réplication&#41;](../synchronize-data.md).</span><span class="sxs-lookup"><span data-stu-id="88c5e-119">For more information, see [Synchronize Subscriptions &#40;Replication&#41;](../synchronize-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88c5e-120">Les sauts de ligne figurant dans ces exemples ont été ajoutés afin d'améliorer la lisibilité.</span><span class="sxs-lookup"><span data-stu-id="88c5e-120">Line breaks in these examples were added to improve readability.</span></span> <span data-ttu-id="88c5e-121">Dans un fichier de commandes, les commandes doivent figurer sur une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="88c5e-121">In a batch file, commands must be made in a single line.</span></span>  
  
### <a name="running-the-snapshot-agent"></a><span data-ttu-id="88c5e-122">Exécution de l'Agent d'instantané</span><span class="sxs-lookup"><span data-stu-id="88c5e-122">Running the Snapshot Agent</span></span>  
 <span data-ttu-id="88c5e-123">Cet exemple de fichier de commandes appelle l’Agent d’instantané à partir de l’invite de commandes afin de générer un instantané pour la publication **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="88c5e-123">This example batch file invokes the Snapshot Agent from the command prompt to generate a snapshot for the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare variables  
SET Publisher=%InstanceName%;  
SET PublicationDB=AdventureWorks2012;   
SET Publication=AdvWorksSalesOrdersMerge;   
  
REM --Start the Snapshot Agent to generate the snapshot for AdvWorksSalesOrdersMerge.  
"C:\Program Files\Microsoft SQL Server\120\COM\SNAPSHOT.EXE" -Publication %Publication%   
-Publisher %Publisher% -Distributor %Publisher% -PublisherDB %PublicationDB%   
-ReplicationType 2 -OutputVerboseLevel 1 -DistributorSecurityMode 1 ;  
  
```  
  
### <a name="running-the-distribution-agent"></a><span data-ttu-id="88c5e-124">Exécution de l'Agent de distribution</span><span class="sxs-lookup"><span data-stu-id="88c5e-124">Running the Distribution Agent</span></span>  
 <span data-ttu-id="88c5e-125">Cet exemple de fichier de commandes appelle l’Agent de distribution à partir de l’invite de commandes afin de répliquer en continu les modifications de la publication **AdvWorksProductTran** sur un abonné pour un abonnement par émission de données.</span><span class="sxs-lookup"><span data-stu-id="88c5e-125">This example batch file invokes the Distribution Agent from the command prompt to continuously replicate changes from the **AdvWorksProductTran** publication to a push subscriber.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksProductsTran;  
  
REM -- Start the Distribution Agent with four subscription streams.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\DISTRIB.EXE" -Subscriber %Subscriber%   
-SubscriberDB %SubscriptionDB% -SubscriberSecurityMode 1 -Publication %Publication%   
-Publisher %Publisher% -PublisherDB %PublicationDB% -Distributor %Publisher%   
-DistributorSecurityMode 1 -Continuous -SubscriptionType 0 -SubscriptionStreams 4 ;  
  
```  
  
### <a name="running-the-merge-agent"></a><span data-ttu-id="88c5e-126">Exécution de l'Agent de fusion</span><span class="sxs-lookup"><span data-stu-id="88c5e-126">Running the Merge Agent</span></span>  
 <span data-ttu-id="88c5e-127">Cet exemple de fichier de commandes appelle l’Agent de fusion à partir de l’invite de commandes afin de synchroniser un abonnement par extraction de données avec la publication **AdvWorksSalesOrdersMerge**.</span><span class="sxs-lookup"><span data-stu-id="88c5e-127">This example batch file invokes the Merge Agent from the command prompt to synchronize a pull subscription to the **AdvWorksSalesOrdersMerge** publication.</span></span>  
  
```  
REM -- Declare the variables.  
SET Publisher=%instancename%;  
SET Subscriber=%instancename%;  
SET PublicationDB=AdventureWorks2012;  
SET SubscriptionDB=AdventureWorks2012Replica;   
SET Publication=AdvWorksSalesOrdersMerge;  
  
REM --Start the Merge Agent with concurrent upload and download processes.  
REM -- The following command must be supplied without line breaks.  
"C:\Program Files\Microsoft SQL Server\120\COM\REPLMERG.EXE" -Publication %Publication%    
-Publisher %Publisher%  -Subscriber  %Subscriber%  -Distributor %Publisher%    
-PublisherDB %PublicationDB%  -SubscriberDB %SubscriptionDB% -PublisherSecurityMode 1    
-OutputVerboseLevel 2  -SubscriberSecurityMode 1  -SubscriptionType 1 -DistributorSecurityMode 1    
-Validate 3  -ParallelUploadDownload 1 ;  
  
```  
  
  
