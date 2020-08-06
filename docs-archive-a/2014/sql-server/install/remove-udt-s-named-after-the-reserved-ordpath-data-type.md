---
title: Supprimer l’UDT&#39;s nommé après le type de données ORDPATH réservé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710163"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="c0a1e-102">Supprimer l’UDT&#39;s nommé après le type de données ORDPATH réservé</span><span class="sxs-lookup"><span data-stu-id="c0a1e-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="c0a1e-103">Le Conseiller de mise à niveau a détecté un type défini par l'utilisateur (UDT) nommé d'après un terme réservé pour le type de donnée `ORDPATH`.</span><span class="sxs-lookup"><span data-stu-id="c0a1e-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c0a1e-104">Composant</span><span class="sxs-lookup"><span data-stu-id="c0a1e-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c0a1e-105">Description</span><span class="sxs-lookup"><span data-stu-id="c0a1e-105">Description</span></span>  
 <span data-ttu-id="c0a1e-106">Les termes utilisés pour les types de données intégrés ne doivent pas être utilisés comme noms pour le Common Language Runtime (CLR) ou types définis par l'utilisateur (UDT) d'alias.</span><span class="sxs-lookup"><span data-stu-id="c0a1e-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c0a1e-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="c0a1e-107">Corrective Action</span></span>  
 <span data-ttu-id="c0a1e-108">Supprimez le type défini par l'utilisateur qui est nommé d'après le type de données et recrée le type défini par l'utilisateur avec un nom non réservé.</span><span class="sxs-lookup"><span data-stu-id="c0a1e-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c0a1e-109">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="c0a1e-109">External Resources</span></span>  
 [<span data-ttu-id="c0a1e-110">Création d’un type défini par l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c0a1e-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
