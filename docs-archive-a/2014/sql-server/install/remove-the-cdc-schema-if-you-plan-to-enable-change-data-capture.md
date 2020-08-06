---
title: Supprimer le schéma CDC si vous envisagez d’activer la capture de données modifiées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- cdc schema
- change data capture
ms.assetid: 6a84aa25-0f31-4be3-b2dd-4f249b8254ae
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: abdb33fa3d1ff022a65ed569f19d48bcf4468501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612100"
---
# <a name="remove-the-cdc-schema-if-you-plan-to-enable-change-data-capture"></a><span data-ttu-id="460c9-102">Supprimez le schéma cdc si vous envisagez d'activer la capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="460c9-102">Remove the cdc schema if you plan to enable change data capture</span></span>
  <span data-ttu-id="460c9-103">Une base de données contient déjà un schéma cdc.</span><span class="sxs-lookup"><span data-stu-id="460c9-103">A database already contains a cdc schema.</span></span> <span data-ttu-id="460c9-104">Si vous envisagez d'activer la capture de données modifiées après la mise à niveau, vous devez préalablement abandonner ce schéma cdc.</span><span class="sxs-lookup"><span data-stu-id="460c9-104">If you plan to enable change data capture after upgrade, you must first drop this cdc schema.</span></span> <span data-ttu-id="460c9-105">Lorsque vous permettez la capture de données modifiées pour une base de données, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] créera un nouveau schéma nommé cdc.</span><span class="sxs-lookup"><span data-stu-id="460c9-105">When you enable a database for change data capture, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create a new schema named cdc.</span></span>  
  
  
