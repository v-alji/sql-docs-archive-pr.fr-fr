---
title: Copier des tables d’un schéma de base de données vers un autre (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695131"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="0d0ee-102">Copier des tables d’un diagramme de base de données vers un autre (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0d0ee-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="0d0ee-103">Vous pouvez copier une table d’un diagramme de base de données à l’autre dans la même base de données.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="0d0ee-104">Cette opération ajoute une référence à la table dans le deuxième diagramme.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="0d0ee-105">La table n'est pas dupliquée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="0d0ee-106">Par exemple, si vous copiez la table `authors` d’un diagramme de base de données à un autre, les deux diagrammes font référence à la même table `authors` de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="0d0ee-107">Pour copier une table à partir d’un autre diagramme de base de données</span><span class="sxs-lookup"><span data-stu-id="0d0ee-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="0d0ee-108">Vérifiez que vous êtes connecté à la base de données dont vous voulez copier une table.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="0d0ee-109">Ouvrez les diagrammes de base de données source et cible, puis, dans le diagramme source, sélectionnez la table que vous voulez copier vers le diagramme cible.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="0d0ee-110">Dans la barre d’outils, cliquez sur le bouton **Copier** .</span><span class="sxs-lookup"><span data-stu-id="0d0ee-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="0d0ee-111">Cette action place la définition de la table sélectionnée dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="0d0ee-112">Basculez vers le schéma cible.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-112">Switch to the target diagram.</span></span> <span data-ttu-id="0d0ee-113">Ce schéma doit se trouver dans la même base de données que le schéma source.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="0d0ee-114">Dans la barre d’outils, cliquez sur le bouton **Coller** .</span><span class="sxs-lookup"><span data-stu-id="0d0ee-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="0d0ee-115">Le contenu du Presse-papiers apparaît au nouvel emplacement et reste affiché en surbrillance jusqu'à ce que vous cliquiez ailleurs.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="0d0ee-116">S'il existe des relations entre les tables sélectionnées et d'autres tables du schéma cible, les lignes de relation correspondantes sont dessinées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="0d0ee-117">Lorsque vous modifiez la table dans un des schémas, les deux schémas reflètent ces changements.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="0d0ee-118">De même, une fois que vous avez enregistré la table dans l'un des schémas, elle cesse d'être considérée comme « modifiée » dans les deux schémas.</span><span class="sxs-lookup"><span data-stu-id="0d0ee-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d0ee-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d0ee-119">See Also</span></span>  
 <span data-ttu-id="0d0ee-120">[Utiliser des schémas de base de données &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0d0ee-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0d0ee-121">Ajouter des tables à des schémas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0d0ee-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
