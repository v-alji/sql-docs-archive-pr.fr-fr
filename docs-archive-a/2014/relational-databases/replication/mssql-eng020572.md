---
title: MSSQL_ENG020572 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020572 error
ms.assetid: 636566db-ffcf-4109-8c11-15b8c7cb9cd9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5762f160e119012f4fdc0ca1a205ba0ecf690378
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614541"
---
# <a name="mssql_eng020572"></a><span data-ttu-id="64302-102">MSSQL_ENG020572</span><span class="sxs-lookup"><span data-stu-id="64302-102">MSSQL_ENG020572</span></span>
    
## <a name="message-details"></a><span data-ttu-id="64302-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="64302-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="64302-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="64302-104">Product Name</span></span>|<span data-ttu-id="64302-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="64302-105">SQL Server</span></span>|  
|<span data-ttu-id="64302-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="64302-106">Event ID</span></span>|<span data-ttu-id="64302-107">20572</span><span class="sxs-lookup"><span data-stu-id="64302-107">20572</span></span>|  
|<span data-ttu-id="64302-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="64302-108">Event Source</span></span>|<span data-ttu-id="64302-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="64302-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="64302-110">Composant</span><span class="sxs-lookup"><span data-stu-id="64302-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="64302-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="64302-111">Symbolic Name</span></span>||  
|<span data-ttu-id="64302-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="64302-112">Message Text</span></span>|<span data-ttu-id="64302-113">L'Abonné '%s' avec un abonnement à l'article '%s' de la publication '%s' a été réinitialisé après l'échec de la validation.</span><span class="sxs-lookup"><span data-stu-id="64302-113">Subscriber '%s' subscription to article '%s' in publication '%s' has been reinitialized after a validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="64302-114">Explication</span><span class="sxs-lookup"><span data-stu-id="64302-114">Explanation</span></span>  
 <span data-ttu-id="64302-115">Lors de la validation des données de l'Abonné par rapport aux données du serveur de publication, les données ne correspondaient pas, par conséquent la validation a échoué.</span><span class="sxs-lookup"><span data-stu-id="64302-115">The data at the Subscriber was validated against the data at the Publisher, and the data did not match; therefore validation failed.</span></span> <span data-ttu-id="64302-116">Lorsque vous avez spécifié qu'il était nécessaire d'effectuer la validation, vous avez sélectionné l'option selon laquelle un abonnement devait être réinitialisé en cas d'échec de la validation.</span><span class="sxs-lookup"><span data-stu-id="64302-116">When you specified that validation should be performed, you selected the option that a subscription should be reinitialized if validation failed.</span></span> <span data-ttu-id="64302-117">La réinitialisation d'un abonnement implique d'appliquer un nouvel instantané à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="64302-117">Reinitializing a subscription involves applying a new snapshot at the Subscriber.</span></span> <span data-ttu-id="64302-118">Pour plus d'informations sur la validation, consultez [Validate Replicated Data](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="64302-118">For more information about validation, see [Validate Replicated Data](validate-data-at-the-subscriber.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="64302-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="64302-119">User Action</span></span>  
 <span data-ttu-id="64302-120">Les données du serveur de publication et de l'Abonné concorderont une fois que le nouvel instantané sera appliqué à l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="64302-120">Data at the Publisher and Subscriber will match after the new snapshot is applied at the Subscriber.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64302-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64302-121">See Also</span></span>  
 [<span data-ttu-id="64302-122">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="64302-122">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
