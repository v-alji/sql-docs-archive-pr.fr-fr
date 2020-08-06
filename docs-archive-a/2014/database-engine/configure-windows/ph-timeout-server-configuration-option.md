---
title: PH timeout (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- time limit for protocol handler wait [SQL Server]
- timeout options [SQL Server], ph timeout option
- protocols [SQL Server], timing out
- ph timeout option
ms.assetid: ed19a07c-83fe-4582-9c9e-41b1ce571850
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 515ed74a4b92259d53770bf6d970626eba686453
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697159"
---
# <a name="ph-timeout-server-configuration-option"></a><span data-ttu-id="0eda4-102">PH timeout (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="0eda4-102">PH timeout Server Configuration Option</span></span>
  <span data-ttu-id="0eda4-103">Utilisez l’option ph timeout pour spécifier le délai, en secondes, dont dispose le gestionnaire de protocole de texte intégral pour se connecter à une base de données. La valeur par défaut est 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="0eda4-103">Use the PH timeout option to specify the time, in seconds, that the full-text protocol handler should wait to connect to a database before timing out. The default value is 60 seconds.</span></span> <span data-ttu-id="0eda4-104">Augmentez la valeur de ph timeout si vos tentatives de connexion dépassent ce délai en raison de problèmes réseau temporaires.</span><span class="sxs-lookup"><span data-stu-id="0eda4-104">Increase the ph timeout value when connection attempts are timing out due to temporary network issues.</span></span>  
  
 <span data-ttu-id="0eda4-105">Le gestionnaire de protocole de texte intégral est hébergé dans l'hôte de démon de filtre et sert à rechercher dans SQL Server les données à indexer en texte intégral.</span><span class="sxs-lookup"><span data-stu-id="0eda4-105">The full-text protocol handler is hosted in the filter daemon host and is used to fetch from SQL Server the data to be full-text indexed.</span></span> <span data-ttu-id="0eda4-106">Pour plus d’informations sur les composants de la recherche en texte intégral, consultez [Recherche en texte intégral](../../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="0eda4-106">For more information about full-text search components, see [Full-Text Search](../../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="0eda4-107">Lorsque vous tentez d'extraire une ligne de données, si le gestionnaire de protocole ne peut pas se connecter à SQL Server dans le délai spécifié, il émet une erreur de temporisation pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="0eda4-107">When attempting to fetch a data row, if the protocol handler cannot connect to SQL Server within the specified time, it reports a time-out error for that row.</span></span> <span data-ttu-id="0eda4-108">L'outil d'extraction de texte intégral réessaiera ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="0eda4-108">The full-text gatherer will retry the row later.</span></span> <span data-ttu-id="0eda4-109">Pour plus d’informations sur l’outil d’extraction de texte intégral, consultez [Alimenter des index de recherche en texte intégral](../../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="0eda4-109">For more information about the full-text gatherer, see [Populate Full-Text Indexes](../../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eda4-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0eda4-110">See Also</span></span>  
 <span data-ttu-id="0eda4-111">[Recherche en texte intégral](../../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="0eda4-111">[Full-Text Search](../../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="0eda4-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0eda4-112">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="0eda4-113">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0eda4-113">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="0eda4-114">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0eda4-114">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
