---
title: Configurer le Concepteur de diagrammes de base de données (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.InstallSqlDiagramSupport
helpviewer_keywords:
- Database Diagram Designer
- database diagrams [SQL Server], Database Diagram Designer
- diagrams [SQL Server], Database Diagram Designer
ms.assetid: 927321ee-b459-4f5b-9719-4a7a95639143
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d59fa2ed197a410de6b68e388e76d2bf21c334d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703679"
---
# <a name="set-up-database-diagram-designer-visual-database-tools"></a><span data-ttu-id="1f03e-102">Configurer le Concepteur de diagrammes de base de données (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="1f03e-102">Set Up Database Diagram Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="1f03e-103">Pour pouvoir utiliser le Concepteur de diagrammes de base de données, il doit d’abord être configuré par un membre du rôle **db_owner** afin de contrôler l’accès aux diagrammes.</span><span class="sxs-lookup"><span data-stu-id="1f03e-103">To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.</span></span>  
  
### <a name="to-set-up-database-diagramming"></a><span data-ttu-id="1f03e-104">Pour configurer la fonctionnalité de diagrammes de base de données</span><span class="sxs-lookup"><span data-stu-id="1f03e-104">To set up database diagramming</span></span>  
  
1.  <span data-ttu-id="1f03e-105">Dans l'Explorateur d'objets, développez un nœud de base de données.</span><span class="sxs-lookup"><span data-stu-id="1f03e-105">From Object Explorer, expand a database node.</span></span>  
  
2.  <span data-ttu-id="1f03e-106">Développez le nœud Diagrammes de base de données sous la connexion de base de données.</span><span class="sxs-lookup"><span data-stu-id="1f03e-106">Expand the Database Diagrams node under the database connection.</span></span>  
  
3.  <span data-ttu-id="1f03e-107">Sélectionnez **Oui** quand vous êtes invité à spécifier si vous souhaitez installer le diagramme de base de données.</span><span class="sxs-lookup"><span data-stu-id="1f03e-107">Select **Yes** when prompted if you want to set up database diagramming.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1f03e-108">Cela entraîne la création de la table de diagramme de base de données, de procédures stockées système et d’une fonction système dans la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f03e-108">This will create the database diagram table, system stored procedures, and a system function on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="1f03e-109">Visual Studio créera les objets suivants sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1f03e-109">Visual Studio will create the following objects on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="1f03e-110">Table sysdiagrams</span><span class="sxs-lookup"><span data-stu-id="1f03e-110">sysdiagrams table</span></span>  
  
    2.  <span data-ttu-id="1f03e-111">Procédure stockée sp_alterdiagram</span><span class="sxs-lookup"><span data-stu-id="1f03e-111">sp_alterdiagram stored procedure</span></span>  
  
    3.  <span data-ttu-id="1f03e-112">Procédure stockée sp_creatediagram</span><span class="sxs-lookup"><span data-stu-id="1f03e-112">sp_creatediagram stored procedure</span></span>  
  
    4.  <span data-ttu-id="1f03e-113">Procédure stockée sp_dropdiagram</span><span class="sxs-lookup"><span data-stu-id="1f03e-113">sp_dropdiagram stored procedure</span></span>  
  
    5.  <span data-ttu-id="1f03e-114">Procédure stockée sp_renamediagram</span><span class="sxs-lookup"><span data-stu-id="1f03e-114">sp_renamediagram stored procedure</span></span>  
  
    6.  <span data-ttu-id="1f03e-115">Fonction fn_diagramobjects</span><span class="sxs-lookup"><span data-stu-id="1f03e-115">fn_diagramobjects function</span></span>  
  
    7.  <span data-ttu-id="1f03e-116">Procédure stockée sp_helpdiagrams</span><span class="sxs-lookup"><span data-stu-id="1f03e-116">sp_helpdiagrams stored procedure</span></span>  
  
    8.  <span data-ttu-id="1f03e-117">Procédure stockée sp_helpdiagramsdefinition</span><span class="sxs-lookup"><span data-stu-id="1f03e-117">sp_helpdiagramsdefinition stored procedure</span></span>  
  
    9. <span data-ttu-id="1f03e-118">Procédure stockée sp_upgraddiagrams</span><span class="sxs-lookup"><span data-stu-id="1f03e-118">sp_upgraddiagrams stored procedure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f03e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f03e-119">See Also</span></span>  
 <span data-ttu-id="1f03e-120">[Comprendre la propriété du schéma de base de données &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1f03e-120">[Understand Database Diagram Ownership &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="1f03e-121">[Mettre à niveau les schémas de base de données des éditions précédentes &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="1f03e-121">[Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="1f03e-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f03e-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  
