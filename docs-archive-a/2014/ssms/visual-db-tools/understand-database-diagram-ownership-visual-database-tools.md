---
title: Comprendre la propriété du diagramme de base de données (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703672"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="a4db6-102">Comprendre la propriété du diagramme de base de données (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a4db6-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="a4db6-103">Pour utiliser le Concepteur de diagrammes de base de données, il doit d’abord être installé par un membre du rôle db_owner (rôle de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) pour contrôler l’accès aux diagrammes.</span><span class="sxs-lookup"><span data-stu-id="a4db6-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="a4db6-104">Chaque schéma a un seul propriétaire : l'utilisateur qui l'a créé.</span><span class="sxs-lookup"><span data-stu-id="a4db6-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="a4db6-105">Pour plus d’informations sur la configuration de la création de diagrammes, consultez [configurer le concepteur de schémas de base de données &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a4db6-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="a4db6-106">Voici quelques points à retenir au sujet de la propriété des schémas :</span><span class="sxs-lookup"><span data-stu-id="a4db6-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="a4db6-107">Même si tout utilisateur ayant accès à une base de données peut créer un schéma, lorsque ce dernier est créé, les seuls utilisateurs autorisés à le consulter sont son créateur et tout membre du rôle db_owner.</span><span class="sxs-lookup"><span data-stu-id="a4db6-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="a4db6-108">La propriété de schémas ne peut être transférée qu'à des membres du rôle db_owner.</span><span class="sxs-lookup"><span data-stu-id="a4db6-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="a4db6-109">Cela n'est possible que si l'ancien propriétaire du schéma a été supprimé de la base de données.</span><span class="sxs-lookup"><span data-stu-id="a4db6-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="a4db6-110">Si le propriétaire d'un schéma a été supprimé de la base de données, le schéma reste dans la base de données jusqu'à ce qu'un membre du rôle db_owner tente de l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="a4db6-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="a4db6-111">À ce stade, le membre du rôle db_owner peut choisir de prendre possession du schéma.</span><span class="sxs-lookup"><span data-stu-id="a4db6-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4db6-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4db6-112">See Also</span></span>  
 <span data-ttu-id="a4db6-113">[Utiliser des schémas de base de données &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a4db6-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a4db6-114">Configurer le Concepteur de diagrammes de base de données &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a4db6-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
