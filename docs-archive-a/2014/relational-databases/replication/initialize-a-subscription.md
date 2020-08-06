---
title: Initialiser un abonnement | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- snapshot replication [SQL Server], initializing subscriptions
- transactional replication, initializing subscriptions
- initializing subscriptions [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], about initializing subscriptions
- merge replication [SQL Server replication], initializing subscriptions
ms.assetid: d6013845-cb7a-4203-8e21-edce32f1d330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1f024d360fdeab477ace09970b4f140a97696c2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601330"
---
# <a name="initialize-a-subscription"></a><span data-ttu-id="53c70-102">Initialiser un abonnement</span><span class="sxs-lookup"><span data-stu-id="53c70-102">Initialize a Subscription</span></span>
  <span data-ttu-id="53c70-103">Les Abonnés dans une topologie de réplication doivent être initialisés, de façon à ce qu'ils aient une copie du schéma de chaque article de la publication à laquelle ils se sont abonnés et tous les objets de réplication requis, tels que des procédures stockées, des déclencheurs et des tables de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="53c70-103">Subscribers in a replication topology must be initialized, so that they have a copy of the schema from each article in the publication they have subscribed to and any replication objects that are required, such as stored procedures, triggers, and metadata tables.</span></span> <span data-ttu-id="53c70-104">De plus, l'Abonné reçoit généralement un jeu de données initial.</span><span class="sxs-lookup"><span data-stu-id="53c70-104">In addition, the Subscriber typically receives an initial dataset.</span></span> <span data-ttu-id="53c70-105">La méthode d'initialisation par défaut utilise un instantané complet qui comprend le schéma, les objets de réplication et des données, mais les publications peuvent aussi être initialisées sans instantané complet.</span><span class="sxs-lookup"><span data-stu-id="53c70-105">The default initialization method uses a full snapshot that includes schema, replication objects, and data, but publications can also be initialized without a full snapshot.</span></span>  
  
 <span data-ttu-id="53c70-106">Pour plus d'informations, consultez [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) et [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="53c70-106">For more information, see [Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) and [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
  
