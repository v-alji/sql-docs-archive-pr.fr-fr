---
title: Supprimer l’UDT&#39;s nommées après les types de données de DATE et d’heure réservés | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612099"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="2d6c8-102">Supprimer l’UDT&#39;s nommées après les types de données de DATE et d’heure réservés</span><span class="sxs-lookup"><span data-stu-id="2d6c8-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="2d6c8-103">Le Conseiller de mise à niveau a détecté un type défini par l'utilisateur (UDT) nommé d'après un terme a réservé pour les types de donnée `date` ou `time`.</span><span class="sxs-lookup"><span data-stu-id="2d6c8-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2d6c8-104">Composant</span><span class="sxs-lookup"><span data-stu-id="2d6c8-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2d6c8-105">Description</span><span class="sxs-lookup"><span data-stu-id="2d6c8-105">Description</span></span>  
 <span data-ttu-id="2d6c8-106">Les termes utilisés pour les types de données ne doivent pas être utilisés comme noms pour le Common Language Runtime (CLR) ou les types définis par l'utilisateur (UDT) d'alias.</span><span class="sxs-lookup"><span data-stu-id="2d6c8-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2d6c8-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="2d6c8-107">Corrective Action</span></span>  
 <span data-ttu-id="2d6c8-108">Supprimez le type défini par l'utilisateur qui est nommé d'après le type de données et recrée le type défini par l'utilisateur avec un nom non réservé.</span><span class="sxs-lookup"><span data-stu-id="2d6c8-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
