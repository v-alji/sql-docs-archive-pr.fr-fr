---
title: Exécuter des scripts pendant la synchronisation (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601350"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="82d27-102">Exécuter des scripts pendant la synchronisation (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="82d27-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="82d27-103">La réplication prend en charge l'exécution de script à la demande pour les Abonnés à des publications transactionnelles et de fusion.</span><span class="sxs-lookup"><span data-stu-id="82d27-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="82d27-104">Cette fonctionnalité copie le script vers le répertoire de travail de réplication puis utilise **sqlcmd** pour appliquer le script à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="82d27-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="82d27-105">Par défaut, en cas d'échec lors de l'application du script pour un abonnement à une publication transactionnelle, l'Agent de distribution s'arrêtera.</span><span class="sxs-lookup"><span data-stu-id="82d27-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="82d27-106">Vous pouvez spécifier un script [!INCLUDE[tsql](../../includes/tsql-md.md)] à exécuter par programme à l'aide des procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="82d27-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="82d27-107">Pour spécifier un script à exécuter pour tous les Abonnés à une publication d'instantané, transactionnelle ou de fusion</span><span class="sxs-lookup"><span data-stu-id="82d27-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="82d27-108">Composez et testez le script [!INCLUDE[tsql](../../includes/tsql-md.md)] qui sera exécuté à la demande.</span><span class="sxs-lookup"><span data-stu-id="82d27-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="82d27-109">Enregistrez le fichier de script dans un emplacement accessible à l'Agent d'instantané pour la publication.</span><span class="sxs-lookup"><span data-stu-id="82d27-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="82d27-110">Dans la base de données de publication sur le serveur de publication, exécutez [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="82d27-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="82d27-111">Spécifiez \*\* \@ publication**, le nom du fichier de script avec le chemin UNC complet créé à l’étape 2 pour \*\* \@ scriptfile**et l’une des valeurs suivantes pour \*\* \@ SkipError\*\*:</span><span class="sxs-lookup"><span data-stu-id="82d27-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="82d27-112">**0** – l'agent arrêtera d'exécuter le script en cas d'erreur.</span><span class="sxs-lookup"><span data-stu-id="82d27-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="82d27-113">**1** – l'agent enregistrera les erreurs rencontrées et continuera à exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="82d27-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="82d27-114">Le script spécifié sera exécuté sur chaque Abonné lorsque l'agent s'exécutera de nouveau pour synchroniser l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="82d27-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d27-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82d27-115">See Also</span></span>  
 [<span data-ttu-id="82d27-116">Synchroniser les données</span><span class="sxs-lookup"><span data-stu-id="82d27-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
