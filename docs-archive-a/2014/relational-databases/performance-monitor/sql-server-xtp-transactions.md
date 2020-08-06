---
title: Transactions XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698033"
---
# <a name="xtp-transactions"></a><span data-ttu-id="8d8be-102">Transactions XTP</span><span class="sxs-lookup"><span data-stu-id="8d8be-102">XTP Transactions</span></span>
  <span data-ttu-id="8d8be-103">L'objet de performance Transactions XTP contient des compteurs connexes aux transactions du moteur XTP dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d8be-103">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8d8be-104">Ce tableau décrit les compteurs **Transactions XTP** .</span><span class="sxs-lookup"><span data-stu-id="8d8be-104">This table describes the **XTP Transactions** counters.</span></span>  
  
|<span data-ttu-id="8d8be-105">Compteur</span><span class="sxs-lookup"><span data-stu-id="8d8be-105">Counter</span></span>|<span data-ttu-id="8d8be-106">Description</span><span class="sxs-lookup"><span data-stu-id="8d8be-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d8be-107">**Abandons en cascade par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-107">**Cascading aborts/sec**</span></span>|<span data-ttu-id="8d8be-108">Nombre de transactions restaurées en raison d'une restauration de dépendance de validation (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-108">The number of transactions that rolled back to due a commit dependency rollback (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-109">**Dépendances de validation prises par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-109">**Commit dependencies taken/sec**</span></span>|<span data-ttu-id="8d8be-110">Nombre de dépendances de validation prises par des transactions (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-110">The number of commit dependencies taken by transactions (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-111">**Transactions en lecture seule préparées par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-111">**Read-only transactions prepared/sec**</span></span>|<span data-ttu-id="8d8be-112">Nombre de transactions en lecture seule qui ont été préparées pour le traitement de validation, par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-112">The number of read-only transactions that were prepared for commit processing, per second.</span></span>|  
|<span data-ttu-id="8d8be-113">**Actualisations de point de sauvegarde par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-113">**Save point refreshes/sec**</span></span>|<span data-ttu-id="8d8be-114">Nombre de fois qu'un point de sauvegarde a été « actualisé » (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-114">The number of times a savepoint was "refreshed", (on average), per second.</span></span> <span data-ttu-id="8d8be-115">Une actualisation de point de sauvegarde se produit lorsqu'un point de sauvegarde existant est réinitialisé au point actuel dans la durée de vie de la transaction.</span><span class="sxs-lookup"><span data-stu-id="8d8be-115">A savepoint refresh is when an existing savepoint is reset to the current point in the transaction's lifetime.</span></span>|  
|<span data-ttu-id="8d8be-116">**Restaurations de point de sauvegarde par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-116">**Save point rollbacks/sec**</span></span>|<span data-ttu-id="8d8be-117">Nombre de fois qu'une transaction a été restaurée à un point de sauvegarde (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-117">The number of times a transaction rolled back to a save point (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-118">**Points de sauvegarde créés par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-118">**Save points created /sec**</span></span>|<span data-ttu-id="8d8be-119">Nombre de points de sauvegarde créés (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-119">The number of save points created (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-120">**Échec de validation des transactions par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-120">**Transaction validation failure/sec**</span></span>|<span data-ttu-id="8d8be-121">Nombre de transactions ayant échoué lors du traitement de validation (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-121">The number of transactions that failed validation processing (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-122">**Transactions abandonnées par l'utilisateur par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-122">**Transactions aborted by user/sec**</span></span>|<span data-ttu-id="8d8be-123">Nombre de transactions abandonnées par l'utilisateur (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-123">The number of transactions that were aborted by the user (on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-124">**Transactions abandonnées par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-124">**Transactions aborted/sec**</span></span>|<span data-ttu-id="8d8be-125">Nombre de transactions abandonnées par l'utilisateur et par le système (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-125">The number of transactions that aborted (both by the user and the system, on average), per second.</span></span>|  
|<span data-ttu-id="8d8be-126">**Transactions créées par seconde**</span><span class="sxs-lookup"><span data-stu-id="8d8be-126">**Transactions created/sec**</span></span>|<span data-ttu-id="8d8be-127">Nombre de transactions créées dans le système (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="8d8be-127">The number of transactions created in the system (on average), per second.</span></span><br /><br /> <span data-ttu-id="8d8be-128">Les transactions XTP sont comptées différemment que les transactions sur disque (comme obtenu par réflexion dans Databases:Transactions/sec).</span><span class="sxs-lookup"><span data-stu-id="8d8be-128">XTP transactions are counted differently than disk-based transactions (as reflected in Databases:Transactions/sec).</span></span> <span data-ttu-id="8d8be-129">Par exemple, les transactions created/sec comptent les transactions read/only, contrairement à Databases:Transactions/sec.</span><span class="sxs-lookup"><span data-stu-id="8d8be-129">For example, Transactions created/sec counts read/only transactions, while Databases:Transactions/sec does not.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d8be-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d8be-130">See Also</span></span>  
 [<span data-ttu-id="8d8be-131">Les compteurs de performances de l’OLTP en mémoire &#40;de XTP&#41;</span><span class="sxs-lookup"><span data-stu-id="8d8be-131">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
