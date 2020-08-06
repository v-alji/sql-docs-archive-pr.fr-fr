---
title: Problèmes liés à l’évolution d’une base de données (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708016"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="9ca78-102">Problèmes liés à l'évolution d'une base de données (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9ca78-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="9ca78-103">Si vous modifiez la structure d'une base de données déployée, assurez-vous que les changements sont compatibles avec les données existantes et la structure de la base de données.</span><span class="sxs-lookup"><span data-stu-id="9ca78-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="9ca78-104">Il est quelquefois nécessaire de prendre des mesures spéciales si les modifications appartiennent à une des catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ca78-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="9ca78-105">**Ajout d’une contrainte** Quand vous ajoutez une contrainte, la base de données contient peut-être déjà des données qui ne la respectent pas.</span><span class="sxs-lookup"><span data-stu-id="9ca78-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="9ca78-106">Quand vous essayez d’enregistrer la nouvelle contrainte, la [boîte de dialogue Notifications post-enregistrement &#40;Visual Database Tools&#41;](visual-database-tools.md) vous informe que le serveur de base de données n’a pas pu la créer.</span><span class="sxs-lookup"><span data-stu-id="9ca78-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="9ca78-107">Pour obliger la base de données à accepter la nouvelle contrainte, vous pouvez décocher la case **Vérifier les données existantes à la création**.</span><span class="sxs-lookup"><span data-stu-id="9ca78-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="9ca78-108">**Ajout d’une relation** Quand vous ajoutez une relation, la base de données contient peut-être déjà dans la table de clés étrangères des lignes sans correspondance dans la table de clés primaires.</span><span class="sxs-lookup"><span data-stu-id="9ca78-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="9ca78-109">Ce qui signifie que les données existantes ne respectent peut-être pas l'intégrité référentielle.</span><span class="sxs-lookup"><span data-stu-id="9ca78-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="9ca78-110">Quand vous essayez d’enregistrer la nouvelle relation, la [boîte de dialogue Notifications post-enregistrement &#40;Visual Database Tools&#41;](visual-database-tools.md) vous informe que le serveur de base de données n’a pas pu enregistrer la table de clé étrangère révisée.</span><span class="sxs-lookup"><span data-stu-id="9ca78-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="9ca78-111">Pour obliger la base de données à accepter la modification, vous pouvez décocher la case **Vérifier les données existantes à la création**.</span><span class="sxs-lookup"><span data-stu-id="9ca78-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="9ca78-112">**Modification d’une table contribuant à une vue indexée** Si vous modifiez une table contribuant à une vue Microsoft SQL Server indexée, vous perdez les index de la vue.</span><span class="sxs-lookup"><span data-stu-id="9ca78-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="9ca78-113">Pour plus d'informations sur la reconstitution d'index, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9ca78-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="9ca78-114">**Suppression d’un objet** Si vous supprimez un objet, tel qu’une colonne, une table ou une vue, vérifiez d’abord qu’il n’est pas référencé par un autre objet dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="9ca78-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="9ca78-115">Quelle que soit la façon dont vous modifiez le design de la base de données, gardez un historique de ces modifications.</span><span class="sxs-lookup"><span data-stu-id="9ca78-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="9ca78-116">Une méthode consiste à conserver des scripts SQL de toutes les modifications que vous avez apportées à la base de données de production.</span><span class="sxs-lookup"><span data-stu-id="9ca78-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca78-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ca78-117">See Also</span></span>  
 <span data-ttu-id="9ca78-118">[Contraintes uniques et contraintes de validation](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="9ca78-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="9ca78-119">Environnements multi-utilisateurs &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9ca78-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
