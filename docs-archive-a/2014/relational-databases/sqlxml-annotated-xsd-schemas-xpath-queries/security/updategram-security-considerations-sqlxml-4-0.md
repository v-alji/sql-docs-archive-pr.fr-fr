---
title: Considérations sur la sécurité mise à jour (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612728"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="3df36-102">Considérations de sécurité relatives au code de mise à jour (updategram) (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3df36-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="3df36-103">Vous trouverez ci-après des instructions de sécurité relatives à l'utilisation des codes de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="3df36-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="3df36-104">Évitez d'utiliser le mappage par défaut lorsque vous utilisez des codes de mise à jour pour mettre à jour des données.</span><span class="sxs-lookup"><span data-stu-id="3df36-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="3df36-105">Lorsque vous utilisez le mappage par défaut, un nom d'élément dans un code de mise à jour mappe à un nom de table et un nom d'attribut mappe à une colonne.</span><span class="sxs-lookup"><span data-stu-id="3df36-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="3df36-106">Cela expose les informations de colonnes et de tables dans la base de données, ce qui constitue un problème de sécurité potentiel.</span><span class="sxs-lookup"><span data-stu-id="3df36-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="3df36-107">Au lieu de cela, si vous spécifiez un schéma de mappage séparé qui mappe les éléments et attributs dans un code de mise à jour aux tables et colonnes de base de données, vos noms d'attributs et d'éléments de code de mise à jour peuvent être arbitraires et le schéma effectue un mappage nécessaire de ces noms aux tables et colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="3df36-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="3df36-108">Ainsi, les informations sur la base de données ne sont pas exposées dans un code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3df36-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="3df36-109">N'autorisez pas les utilisateurs à créer et exécuter leurs codes de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3df36-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="3df36-110">Il est recommandé de faire en sorte que les codes de mise à jour résident en tant que modèles sur un serveur, plutôt que les créer de manière dynamique dans des applications de type ASP, ce qui pourraient exposer les données de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3df36-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="3df36-111">Le fait d'autoriser les utilisateurs à accéder uniquement aux données par le biais des codes de mise à jour fournis en tant que modèles peut éliminer ce risque.</span><span class="sxs-lookup"><span data-stu-id="3df36-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df36-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3df36-112">See Also</span></span>  
 [<span data-ttu-id="3df36-113">Utilisation de codes de mise à jour (updategrams) pour modifier des données dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="3df36-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
