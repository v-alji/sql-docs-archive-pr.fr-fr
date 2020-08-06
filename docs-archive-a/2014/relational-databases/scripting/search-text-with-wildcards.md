---
title: Rechercher du texte avec des caractères génériques
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614475"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="5f564-102">Rechercher du texte avec des caractères génériques</span><span class="sxs-lookup"><span data-stu-id="5f564-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="5f564-103">Les expressions ci-après peuvent remplacer des caractères ou des chiffres dans le champ **Rechercher** de la boîte de dialogue [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Rechercher et remplacer**de**.</span><span class="sxs-lookup"><span data-stu-id="5f564-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="5f564-104">Pour effectuer une recherche avec des caractères génériques</span><span class="sxs-lookup"><span data-stu-id="5f564-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="5f564-105">Pour pouvoir utiliser des caractères génériques dans le champ **Rechercher** pendant des opérations Recherche rapide, **Rechercher dans les fichiers**, **Remplacement rapide**ou **Remplacer dans les fichiers** , sélectionnez l’option **Utiliser** sous **Options de recherche** , puis choisissez **Caractères génériques**.</span><span class="sxs-lookup"><span data-stu-id="5f564-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="5f564-106">Le bouton triangulaire **Générateur d'expressions** situé en regard du champ **Rechercher** devient alors disponible.</span><span class="sxs-lookup"><span data-stu-id="5f564-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="5f564-107">Cliquez sur ce bouton pour afficher la liste des caractères génériques disponibles.</span><span class="sxs-lookup"><span data-stu-id="5f564-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="5f564-108">Quand vous choisissez un élément dans le **Générateur d’expressions**, il est inséré dans la chaîne **Rechercher** .</span><span class="sxs-lookup"><span data-stu-id="5f564-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="5f564-109">Le tableau ci-dessous décrit les caractères génériques disponibles dans le **Générateur d’expressions**.</span><span class="sxs-lookup"><span data-stu-id="5f564-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="5f564-110">Expression</span><span class="sxs-lookup"><span data-stu-id="5f564-110">Expression</span></span>|<span data-ttu-id="5f564-111">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5f564-111">Syntax</span></span>|<span data-ttu-id="5f564-112">Description</span><span class="sxs-lookup"><span data-stu-id="5f564-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="5f564-113">Tout caractère unique</span><span class="sxs-lookup"><span data-stu-id="5f564-113">Any single character</span></span>|<span data-ttu-id="5f564-114">?</span><span class="sxs-lookup"><span data-stu-id="5f564-114">?</span></span>|<span data-ttu-id="5f564-115">Représente n'importe quel caractère unique.</span><span class="sxs-lookup"><span data-stu-id="5f564-115">Matches any single character.</span></span>|  
|<span data-ttu-id="5f564-116">Tout chiffre</span><span class="sxs-lookup"><span data-stu-id="5f564-116">Any single digit</span></span>|#|<span data-ttu-id="5f564-117">Représente n'importe quel chiffre unique.</span><span class="sxs-lookup"><span data-stu-id="5f564-117">Matches any single digit.</span></span> <span data-ttu-id="5f564-118">Par exemple, 7# représente les nombres incluant 7 suivi d'un autre nombre, tels que 71, mais pas 17.</span><span class="sxs-lookup"><span data-stu-id="5f564-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="5f564-119">Caractères hors jeu</span><span class="sxs-lookup"><span data-stu-id="5f564-119">Characters not in set</span></span>|<span data-ttu-id="5f564-120">[!</span><span class="sxs-lookup"><span data-stu-id="5f564-120">[!</span></span> <span data-ttu-id="5f564-121">]</span><span class="sxs-lookup"><span data-stu-id="5f564-121">]</span></span>|<span data-ttu-id="5f564-122">Représente tout caractère ne figurant pas dans le jeu spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f564-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="5f564-123">Un ou plusieurs caractères</span><span class="sxs-lookup"><span data-stu-id="5f564-123">One or more characters</span></span>|*|<span data-ttu-id="5f564-124">Représente n'importe quel caractère.</span><span class="sxs-lookup"><span data-stu-id="5f564-124">Matches any one or more characters.</span></span> <span data-ttu-id="5f564-125">Par exemple, nou\* représente tout texte incluant « nou », tel que nouveaufichier.txt.</span><span class="sxs-lookup"><span data-stu-id="5f564-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="5f564-126">Jeu de caractères</span><span class="sxs-lookup"><span data-stu-id="5f564-126">Set of characters</span></span>|<span data-ttu-id="5f564-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="5f564-127">[ ]</span></span>|<span data-ttu-id="5f564-128">Représente tout caractère du jeu de caractères spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f564-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f564-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f564-129">See Also</span></span>  
 <span data-ttu-id="5f564-130">[Recherche et remplacement](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="5f564-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="5f564-131">Rechercher du texte avec des expressions régulières</span><span class="sxs-lookup"><span data-stu-id="5f564-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
