---
title: Longueur des noms de catalogues de texte intégral limités à 120 caractères | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614986"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="7519c-102">Les noms de catalogues de texte intégral sont limités à 120 caractères</span><span class="sxs-lookup"><span data-stu-id="7519c-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="7519c-103">La longueur des noms de catalogues de texte intégral est limitée à 120 caractères, et non plus à 128 comme dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7519c-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="7519c-104">Description</span><span class="sxs-lookup"><span data-stu-id="7519c-104">Description</span></span>  
 <span data-ttu-id="7519c-105">Cette modification n'affecte pas les noms de catalogues existants ; toutefois, les scripts qui créent des catalogues de texte intégral avec des noms dépassant 120 caractères provoquent une erreur.</span><span class="sxs-lookup"><span data-stu-id="7519c-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="7519c-106">Les noms de catalogues servent à générer des noms de fichiers logiques correspondant aux catalogues.</span><span class="sxs-lookup"><span data-stu-id="7519c-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7519c-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="7519c-107">Corrective Action</span></span>  
 <span data-ttu-id="7519c-108">Modifiez tous les scripts qui créent des catalogues de texte intégral afin de vous assurer qu'ils limitent les noms de catalogues à 120 caractères.</span><span class="sxs-lookup"><span data-stu-id="7519c-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7519c-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7519c-109">See Also</span></span>  
 [<span data-ttu-id="7519c-110">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="7519c-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
