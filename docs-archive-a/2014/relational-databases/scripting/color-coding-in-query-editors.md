---
title: Codage en couleurs dans les éditeurs de requête
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], color coding
- color coding [Query Editor]
ms.assetid: 802882dc-c997-4e3f-8a01-994bb43169ae
author: rothja
ms.author: jroth
ms.openlocfilehash: f23b37cec051b52082cdb310a134a4603423b8c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603898"
---
# <a name="color-coding-in-query-editors"></a><span data-ttu-id="c68e8-102">Codage en couleurs dans les éditeurs de requête</span><span class="sxs-lookup"><span data-stu-id="c68e8-102">Color Coding in Query Editors</span></span>
  <span data-ttu-id="c68e8-103">Une catégorie est attribuée au texte que vous entrez dans les éditeurs de code. Chaque catégorie est identifiée par une couleur.</span><span class="sxs-lookup"><span data-stu-id="c68e8-103">The text entered in the code editors is assigned a category; each category is identified by a color.</span></span> <span data-ttu-id="c68e8-104">Les couleurs vous aident rapidement à trouver un texte dans votre code.</span><span class="sxs-lookup"><span data-stu-id="c68e8-104">The colors help you quickly find text in your code.</span></span> <span data-ttu-id="c68e8-105">Par exemple, les commentaires apparaissent en vert sombre.</span><span class="sxs-lookup"><span data-stu-id="c68e8-105">For example, comments stand out in dark green.</span></span> <span data-ttu-id="c68e8-106">Le tableau suivant répertorie les couleurs les plus courantes.</span><span class="sxs-lookup"><span data-stu-id="c68e8-106">The following table lists the most common colors.</span></span> <span data-ttu-id="c68e8-107">Vous pouvez afficher la liste complète des couleurs et de leur catégorie ainsi que configurer un modèle de couleurs personnalisé à partir du menu **Outils**, **Options** .</span><span class="sxs-lookup"><span data-stu-id="c68e8-107">You can view the whole list of colors and their categories, and configure a custom color scheme by using the **Tools**, **Options** menu.</span></span> <span data-ttu-id="c68e8-108">Pour plus d’informations sur la modification des couleurs par défaut, consultez [Modifier la couleur, la taille et le style de la police](change-font-color-size-and-style.md).</span><span class="sxs-lookup"><span data-stu-id="c68e8-108">For more information about how to change the default colors, see [Change Font Color, Size, and Style](change-font-color-size-and-style.md).</span></span>  
  
## <a name="default-code-colors"></a><span data-ttu-id="c68e8-109">Couleurs du code par défaut</span><span class="sxs-lookup"><span data-stu-id="c68e8-109">Default Code Colors</span></span>  
  
|<span data-ttu-id="c68e8-110">Couleur</span><span class="sxs-lookup"><span data-stu-id="c68e8-110">Color</span></span>|<span data-ttu-id="c68e8-111">Category</span><span class="sxs-lookup"><span data-stu-id="c68e8-111">Category</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="c68e8-112">Rouge</span><span class="sxs-lookup"><span data-stu-id="c68e8-112">Red</span></span>|<span data-ttu-id="c68e8-113">Chaîne SQL</span><span class="sxs-lookup"><span data-stu-id="c68e8-113">SQL string</span></span>|  
|<span data-ttu-id="c68e8-114">Vert foncé</span><span class="sxs-lookup"><span data-stu-id="c68e8-114">Dark green</span></span>|<span data-ttu-id="c68e8-115">Commentaire</span><span class="sxs-lookup"><span data-stu-id="c68e8-115">Comment</span></span>|  
|<span data-ttu-id="c68e8-116">Noir avec un arrière-plan argenté</span><span class="sxs-lookup"><span data-stu-id="c68e8-116">Black on silver background</span></span>|<span data-ttu-id="c68e8-117">Commande SQLCMD</span><span class="sxs-lookup"><span data-stu-id="c68e8-117">SQLCMD command</span></span>|  
|<span data-ttu-id="c68e8-118">Magenta</span><span class="sxs-lookup"><span data-stu-id="c68e8-118">Magenta</span></span>|<span data-ttu-id="c68e8-119">Fonction système</span><span class="sxs-lookup"><span data-stu-id="c68e8-119">System function</span></span>|  
|<span data-ttu-id="c68e8-120">Vert</span><span class="sxs-lookup"><span data-stu-id="c68e8-120">Green</span></span>|<span data-ttu-id="c68e8-121">Table système, vue ou fonction table.</span><span class="sxs-lookup"><span data-stu-id="c68e8-121">System table, view, or table-valued function.</span></span> <span data-ttu-id="c68e8-122">Également, les schémas système et INFORMATION_SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="c68e8-122">Also, the system schemas sys and INFORMATION_SCHEMA.</span></span>|  
|<span data-ttu-id="c68e8-123">Bleu</span><span class="sxs-lookup"><span data-stu-id="c68e8-123">Blue</span></span>|<span data-ttu-id="c68e8-124">Mot clé</span><span class="sxs-lookup"><span data-stu-id="c68e8-124">Keyword</span></span>|  
|<span data-ttu-id="c68e8-125">Bleu-vert</span><span class="sxs-lookup"><span data-stu-id="c68e8-125">Teal</span></span>|<span data-ttu-id="c68e8-126">Numéros de lignes ou paramètre de modèle</span><span class="sxs-lookup"><span data-stu-id="c68e8-126">Line numbers or template parameter</span></span>|  
|<span data-ttu-id="c68e8-127">Rouge foncé</span><span class="sxs-lookup"><span data-stu-id="c68e8-127">Maroon</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c68e8-128">procédure stockée</span><span class="sxs-lookup"><span data-stu-id="c68e8-128">stored procedure</span></span>|  
|<span data-ttu-id="c68e8-129">Gris foncé</span><span class="sxs-lookup"><span data-stu-id="c68e8-129">Dark gray</span></span>|<span data-ttu-id="c68e8-130">Opérateurs</span><span class="sxs-lookup"><span data-stu-id="c68e8-130">Operators</span></span>|  
  
## <a name="status-bar"></a><span data-ttu-id="c68e8-131">Barre d’état</span><span class="sxs-lookup"><span data-stu-id="c68e8-131">Status Bar</span></span>  
 <span data-ttu-id="c68e8-132">Vous pouvez configurer les serveurs inscrits ou les serveurs du [!INCLUDE[ssDE](../../includes/ssde-md.md)] dans l'Explorateur d'objets pour avoir des couleurs différentes dans la barre d'état de l'Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c68e8-132">You can configure registered servers or [!INCLUDE[ssDE](../../includes/ssde-md.md)] servers in Object Explorer to have different colors in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor status bar.</span></span> <span data-ttu-id="c68e8-133">Cela vous permet d'identifier à quel serveur chaque fenêtre d'éditeur est connectée lorsque plusieurs fenêtres sont ouvertes en même temps.</span><span class="sxs-lookup"><span data-stu-id="c68e8-133">This helps you identify which server each editor window is connected to when you have many windows open at the same time.</span></span> <span data-ttu-id="c68e8-134">Pour plus d’informations sur la définition des couleurs de la barre d’état, consultez [Barre d’état &#40;éditeur de requête du moteur de base de données&#41;](status-bar-database-engine-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c68e8-134">For more information about setting status bar colors, see [Status Bar &#40;Database Engine Query Editor&#41;](status-bar-database-engine-query-editor.md).</span></span>  
  
 <span data-ttu-id="c68e8-135">Certains types d'éditeurs n'affichent pas la barre d'état ou ne prennent pas en charge plusieurs couleurs.</span><span class="sxs-lookup"><span data-stu-id="c68e8-135">Some types of editors do not display the status bar, or do not support multiple colors.</span></span>  
  
  
