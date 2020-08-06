---
title: Effectuer une mise à jour factice pour un article de fusion (programmation Transact-SQL de la réplication) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705091"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="ffb24-102">Exécuter une mise à jour factice pour un article de fusion (programmation Transact-SQL de la réplication)</span><span class="sxs-lookup"><span data-stu-id="ffb24-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="ffb24-103">La réplication de fusion utilise des déclencheurs dans le cadre du processus de réplication ; lorsqu'une mise à jour est effectuée sur la table publiée, un déclencheur de mise à jour est exécuté.</span><span class="sxs-lookup"><span data-stu-id="ffb24-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="ffb24-104">Dans certains cas, les données peuvent être mises à jour sans exécution du déclencheur, comme lors des opérations WRITETEXT et UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="ffb24-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="ffb24-105">Dans ces cas-là, vous devez ajouter explicitement une instruction UPDATE factice pour répliquer la modification.</span><span class="sxs-lookup"><span data-stu-id="ffb24-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="ffb24-106">Vous pouvez ajouter une instruction UPDATE factice à l'aide de procédures stockées de réplication.</span><span class="sxs-lookup"><span data-stu-id="ffb24-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="ffb24-107">Pour ajouter une instruction UPDATE factice</span><span class="sxs-lookup"><span data-stu-id="ffb24-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="ffb24-108">Exécutez l'opération (par exemple, UPDATETEXT) sur une ligne d'une table de fusion publiée qui requiert une mise à jour factice.</span><span class="sxs-lookup"><span data-stu-id="ffb24-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="ffb24-109">Sur le serveur (serveur de publication ou Abonné) de la base de données où la modification a été effectuée, exécutez [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ffb24-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="ffb24-110">Spécifiez la table sur laquelle la modification a été apportée **@source_object** et l’identificateur unique de la ligne modifiée pour **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="ffb24-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="ffb24-111">Synchronisez l'abonnement pour répliquer la ligne modifiée.</span><span class="sxs-lookup"><span data-stu-id="ffb24-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
