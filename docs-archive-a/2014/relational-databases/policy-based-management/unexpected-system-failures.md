---
title: Défaillances inattendues du système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1679bf9e-a2ef-4f90-8907-a002f7341a7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b791ba0e3f709288a4e2c5b6add4e74e15d56dee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603438"
---
# <a name="unexpected-system-failures"></a><span data-ttu-id="475d8-102">Défaillances inattendues du système</span><span class="sxs-lookup"><span data-stu-id="475d8-102">Unexpected System Failures</span></span>
  <span data-ttu-id="475d8-103">Cette règle recherche l'événement système 6008 dans le journal des événements de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="475d8-103">This rule checks for SYSTEM Event 6008 in the computer event log.</span></span> <span data-ttu-id="475d8-104">Cet événement indique un arrêt inattendu du système.</span><span class="sxs-lookup"><span data-stu-id="475d8-104">This event indicates an unexpected system shutdown.</span></span> <span data-ttu-id="475d8-105">Il est possible que le système soit instable et qu'il ne présente pas la stabilité et l'intégrité qui sont requises pour héberger une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="475d8-105">The system might be unstable and might not provide the stability and integrity that is required to host an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="475d8-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="475d8-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="475d8-107">Résolvez immédiatement le problème à l'origine du redémarrage inattendu du serveur ou déplacez l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="475d8-107">Immediately address the cause of the unexpected server restarts, or move the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to another computer.</span></span>  
  
  
