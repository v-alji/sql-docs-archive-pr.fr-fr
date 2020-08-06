---
title: Objets pris en charge par l'Assistant Génération de scripts
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613416"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="9268e-102">Objets pris en charge par l'Assistant Génération de scripts</span><span class="sxs-lookup"><span data-stu-id="9268e-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="9268e-103">L'Assistant Générer et publier des scripts prend en charge un sous-ensemble des objets pris en charge par le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9268e-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="9268e-104">Objets pris en charge</span><span class="sxs-lookup"><span data-stu-id="9268e-104">Supported Objects</span></span>  
 <span data-ttu-id="9268e-105">Le tableau suivant répertorie les objets qui peuvent être publiés et pris en charge par l'Assistant Générer et publier des scripts.</span><span class="sxs-lookup"><span data-stu-id="9268e-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="9268e-106">Rôle d'application</span><span class="sxs-lookup"><span data-stu-id="9268e-106">Application role</span></span>|<span data-ttu-id="9268e-107">Rôle de base de données</span><span class="sxs-lookup"><span data-stu-id="9268e-107">Database role</span></span>|<span data-ttu-id="9268e-108">schéma</span><span class="sxs-lookup"><span data-stu-id="9268e-108">Schema</span></span>|<span data-ttu-id="9268e-109">Agrégat défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-109">User-defined aggregate</span></span>|<span data-ttu-id="9268e-110">Vue<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9268e-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="9268e-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="9268e-111">Assembly</span></span>|<span data-ttu-id="9268e-112">Contrainte DEFAULT</span><span class="sxs-lookup"><span data-stu-id="9268e-112">DEFAULT constraint</span></span>|<span data-ttu-id="9268e-113">Procédure stockée<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9268e-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="9268e-114">Type de données défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-114">User-defined data type</span></span>|<span data-ttu-id="9268e-115">Collection de schémas XML</span><span class="sxs-lookup"><span data-stu-id="9268e-115">XML schema collection</span></span>|  
|<span data-ttu-id="9268e-116">Contrainte CHECK</span><span class="sxs-lookup"><span data-stu-id="9268e-116">CHECK constraint</span></span>|<span data-ttu-id="9268e-117">Catalogue de texte intégral</span><span class="sxs-lookup"><span data-stu-id="9268e-117">Full-text catalog</span></span>|<span data-ttu-id="9268e-118">Synonyme</span><span class="sxs-lookup"><span data-stu-id="9268e-118">Synonym</span></span>|<span data-ttu-id="9268e-119">Fonction définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-119">User-defined function</span></span>||  
|<span data-ttu-id="9268e-120">Procédure stockée CLR (common language runtime)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9268e-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="9268e-121">Index</span><span class="sxs-lookup"><span data-stu-id="9268e-121">Index</span></span>|<span data-ttu-id="9268e-122">Table de charge de travail</span><span class="sxs-lookup"><span data-stu-id="9268e-122">Table</span></span>|<span data-ttu-id="9268e-123">Table définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-123">User-defined table</span></span>||  
|<span data-ttu-id="9268e-124">Fonction CLR définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-124">CLR user-defined function</span></span>|<span data-ttu-id="9268e-125">Règle</span><span class="sxs-lookup"><span data-stu-id="9268e-125">Rule</span></span>|<span data-ttu-id="9268e-126">Utilisateur<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9268e-126">User<sup>2</sup></span></span>|<span data-ttu-id="9268e-127">Type défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9268e-127">User-defined type</span></span>||  
  
 <span data-ttu-id="9268e-128"><sup>1</sup> publié sans chiffrement.</span><span class="sxs-lookup"><span data-stu-id="9268e-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="9268e-129"><sup>2</sup> les utilisateurs non-système qui existent dans la base de données sont publiés en tant que rôles.</span><span class="sxs-lookup"><span data-stu-id="9268e-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
