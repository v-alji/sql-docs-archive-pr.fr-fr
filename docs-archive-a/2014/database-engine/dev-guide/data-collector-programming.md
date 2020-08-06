---
title: Programmation du collecteur de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709900"
---
# <a name="data-collector-programming"></a><span data-ttu-id="8a474-102">Programmation du collecteur de données</span><span class="sxs-lookup"><span data-stu-id="8a474-102">Data Collector Programming</span></span>
  <span data-ttu-id="8a474-103">L'API du collecteur de données, dans <xref:Microsoft.SqlServer.Management.Collector>, autorise le contrôle par programmation de toutes les opérations de configuration par le biais du modèle objet.</span><span class="sxs-lookup"><span data-stu-id="8a474-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="8a474-104">Par ailleurs, la plupart des opérations de collecte de données qui utilisent l'API sont implémentées en tant que procédures stockées installées sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="8a474-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="8a474-105">L'illustration suivante montre des éléments clés du modèle objet du collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="8a474-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="8a474-106">![Modèle objet du collecteur de données](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "Modèle objet du collecteur de données")</span><span class="sxs-lookup"><span data-stu-id="8a474-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>


