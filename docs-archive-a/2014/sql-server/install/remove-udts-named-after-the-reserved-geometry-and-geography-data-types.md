---
title: Supprimer les UDT nommés d’après les types de données GEOMETRy et GEOGRAPHY | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], UDTs
- geography data type [SQL Server], UDTs
ms.assetid: a167ce3a-50b4-4e77-a884-adb23b586c72
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4977d45d53e1114edc8e04ad504963bae0b9eb9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710160"
---
# <a name="remove-udts-named-after-the-reserved-geometry-and-geography-data-types"></a><span data-ttu-id="1fbb4-102">Supprimer des types définis par l'utilisateur nommés d'après les types de données réservés GEOMETRY et GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="1fbb4-102">Remove UDTs named after the reserved GEOMETRY and GEOGRAPHY data types</span></span>
  <span data-ttu-id="1fbb4-103">Le Conseiller de mise à niveau a détecté un type défini par l'utilisateur (UDT) nommé d'après un terme a réservé pour les types de donnée `geometry` ou `geography`.</span><span class="sxs-lookup"><span data-stu-id="1fbb4-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `geometry` or the `geography` data types.</span></span> <span data-ttu-id="1fbb4-104">Les types de données `geometry` et `geography` font partie de la nouvelle fonctionnalité de données spatiales.</span><span class="sxs-lookup"><span data-stu-id="1fbb4-104">The `geometry` and `geography` data types are part of the spatial data feature.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1fbb4-105">Composant</span><span class="sxs-lookup"><span data-stu-id="1fbb4-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1fbb4-106">Description</span><span class="sxs-lookup"><span data-stu-id="1fbb4-106">Description</span></span>  
 <span data-ttu-id="1fbb4-107">Les termes utilisés pour les types de données spatiales ne doivent pas être utilisés comme noms pour le Common Language Runtime (CLR) ou types définis par l'utilisateur (UDT) d'alias.</span><span class="sxs-lookup"><span data-stu-id="1fbb4-107">The terms used for spatial data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1fbb4-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="1fbb4-108">Corrective Action</span></span>  
 <span data-ttu-id="1fbb4-109">Supprimez le type défini par l'utilisateur qui est nommé d'après le type de données et recrée le type défini par l'utilisateur avec un nom non réservé.</span><span class="sxs-lookup"><span data-stu-id="1fbb4-109">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="1fbb4-110">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="1fbb4-110">External Resources</span></span>  
 [<span data-ttu-id="1fbb4-111">Création d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1fbb4-111">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
 [<span data-ttu-id="1fbb4-112">Présentation des types de données spatiales</span><span class="sxs-lookup"><span data-stu-id="1fbb4-112">Spatial Data Types Overview</span></span>](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
