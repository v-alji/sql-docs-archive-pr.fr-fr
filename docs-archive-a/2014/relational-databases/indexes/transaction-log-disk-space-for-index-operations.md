---
title: Espace disque du journal des transactions pour les opérations d’index | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707519"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="9a563-102">Espace disque du journal des transactions pour les opérations d'index</span><span class="sxs-lookup"><span data-stu-id="9a563-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="9a563-103">Les opérations d'index à grande échelle peuvent générer des chargements de données volumineux susceptibles de saturer le journal des transactions rapidement.</span><span class="sxs-lookup"><span data-stu-id="9a563-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="9a563-104">Pour que l'opération d'index puisse être restaurée, le journal des transactions ne peut pas être tronqué avant la fin de celle-ci ; toutefois, il peut être sauvegardé pendant l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="9a563-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="9a563-105">Par conséquent, le journal des transactions doit posséder suffisamment de place pour stocker les transactions de l'opération d'index et toutes les transactions utilisateur concurrentes qui interviennent pendant celle-ci.</span><span class="sxs-lookup"><span data-stu-id="9a563-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="9a563-106">Cela concerne à la fois les opérations d'index hors ligne et les opérations d'index en ligne.</span><span class="sxs-lookup"><span data-stu-id="9a563-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="9a563-107">Étant donné que les tables sous-jacentes sont inaccessibles pendant une opération d'index hors ligne, le nombre de transactions utilisateur peut être faible et le journal ne peut pas croître rapidement.</span><span class="sxs-lookup"><span data-stu-id="9a563-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="9a563-108">Les opérations d'index en ligne n'empêchent pas l'activité utilisateur concurrente ; par conséquent, les opérations d'index en ligne à grande échelle combinées à des transactions utilisateur concurrentes significatives peuvent provoquer une croissance continue du journal des transactions en l'absence d'option permettant de le tronquer.</span><span class="sxs-lookup"><span data-stu-id="9a563-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="9a563-109">Recommandations</span><span class="sxs-lookup"><span data-stu-id="9a563-109">Recommendations</span></span>  
 <span data-ttu-id="9a563-110">Lorsque vous exécutez des opérations d'index à grande échelle, tenez compte des recommandations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9a563-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="9a563-111">Assurez-vous que le journal des transactions a été sauvegardé et tronqué avant d'exécuter des opérations d'index à grande échelle en ligne et qu'il possède suffisamment d'espace pour stocker l'index et les transactions utilisateur projetés.</span><span class="sxs-lookup"><span data-stu-id="9a563-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="9a563-112">Pensez à attribuer la valeur ON à l'option SORT_IN_TEMPDB pour l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="9a563-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="9a563-113">Cela permet de séparer les transactions d'index des transactions utilisateur concurrentes.</span><span class="sxs-lookup"><span data-stu-id="9a563-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="9a563-114">Les transactions d’index seront stockées dans le journal des transactions **tempdb** tandis que les transactions utilisateur concurrentes seront stockées dans le journal des transactions de la base de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9a563-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="9a563-115">Le cas échéant, cela permet de tronquer le journal des transactions de la base de données utilisateur pendant l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="9a563-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="9a563-116">En outre, si le journal **tempdb** ne se trouve pas sur le même disque que le journal de la base de données utilisateur, les deux journaux ne sont pas en concurrence pour le même espace disque.</span><span class="sxs-lookup"><span data-stu-id="9a563-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9a563-117">Vérifiez que la base de données **tempdb** et le journal des transactions possèdent suffisamment d’espace disque pour gérer l’opération d’index.</span><span class="sxs-lookup"><span data-stu-id="9a563-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="9a563-118">Le journal des transactions **tempdb** ne peut pas être tronqué avant la fin de l’opération d’index.</span><span class="sxs-lookup"><span data-stu-id="9a563-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="9a563-119">Utilisez un mode de récupération de base de données qui permet une journalisation minimale de l'opération d'index.</span><span class="sxs-lookup"><span data-stu-id="9a563-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="9a563-120">Cela peut réduire la taille du journal et empêcher celui-ci de saturer l'espace journal.</span><span class="sxs-lookup"><span data-stu-id="9a563-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="9a563-121">N'exécutez pas l'opération d'index en ligne dans une transaction explicite.</span><span class="sxs-lookup"><span data-stu-id="9a563-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="9a563-122">Le journal n'est pas tronqué avant la fin de la transaction explicite.</span><span class="sxs-lookup"><span data-stu-id="9a563-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="9a563-123">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="9a563-123">Related Content</span></span>  
 [<span data-ttu-id="9a563-124">Espace disque nécessaire pour les opérations DDL d’index</span><span class="sxs-lookup"><span data-stu-id="9a563-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="9a563-125">Exemple d'espace disque d'un index</span><span class="sxs-lookup"><span data-stu-id="9a563-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
