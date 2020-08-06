---
title: Ajouter des solutions et des projets au contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], source controls
- solutions [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], solutions
- source controls [SQL Server Management Studio], projects
ms.assetid: 3eaed80e-6f55-42ea-a964-aca31c09d055
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5256795677f4e8ce4249737d25d3ded1c4cd69c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698555"
---
# <a name="add-solutions-and-projects-to-source-control"></a><span data-ttu-id="e2f68-102">Ajouter des solutions et des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="e2f68-102">Add Solutions and Projects to Source Control</span></span>
  <span data-ttu-id="e2f68-103">Lorsque vous ajoutez une solution au contrôle de code source, la solution est intégrée à une archive de contrôle de version dynamique créée et gérée par le fournisseur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="e2f68-103">When you add a solution to source control, the solution becomes part of a dynamic versioning archive created and maintained by the source control provider.</span></span> <span data-ttu-id="e2f68-104">Chaque fois qu'un utilisateur archive une nouvelle version de la solution, cette version est intégrée à l'archive et devient disponible auprès des autres utilisateurs du contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="e2f68-104">Each time someone checks in a new version of the solution, that version becomes part of the archive and is available to other source control users.</span></span>  
  
 <span data-ttu-id="e2f68-105">Lorsque vous ajoutez une solution au contrôle de code source, un système de gestion centralisée de fichiers se lance.</span><span class="sxs-lookup"><span data-stu-id="e2f68-105">Adding a solution to source control also starts a system of centralized file management.</span></span> <span data-ttu-id="e2f68-106">Les fournisseurs de contrôle de code source, tels que [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, contrôlent l'accès aux éléments sous contrôle de code source. Les clients du contrôle de code source ne peuvent pas modifier des copies locales de fichiers sous contrôle de code source sans les avoir préalablement extraits.</span><span class="sxs-lookup"><span data-stu-id="e2f68-106">Source control providers, such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, control access to source-controlled items; source control clients cannot write to local copies of source-controlled files without checking them out.</span></span>  
  
 <span data-ttu-id="e2f68-107">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="e2f68-107">The following table describes the topics in this section.</span></span>  
  
|<span data-ttu-id="e2f68-108">Rubrique</span><span class="sxs-lookup"><span data-stu-id="e2f68-108">Topic</span></span>|<span data-ttu-id="e2f68-109">Description</span><span class="sxs-lookup"><span data-stu-id="e2f68-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e2f68-110">Ajouter des solutions au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="e2f68-110">Add Solutions to Source Control</span></span>](../../2014/database-engine/add-solutions-to-source-control.md)|<span data-ttu-id="e2f68-111">Décrit les types de projets que vous pouvez ajouter et explique comment ajouter une solution au contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="e2f68-111">Describes the project types you can add, and provides instructions on how to add a solution to source control.</span></span>|  
|[<span data-ttu-id="e2f68-112">Ajouter des projets au contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="e2f68-112">Add Projects to Source Control</span></span>](../../2014/database-engine/add-projects-to-source-control.md)|<span data-ttu-id="e2f68-113">Fournit des instructions sur l'ajout d'un projet à une solution.</span><span class="sxs-lookup"><span data-stu-id="e2f68-113">Provides instructions on how to add a project to a solution.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2f68-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2f68-114">See Also</span></span>  
 [<span data-ttu-id="e2f68-115">Ouvrir des solutions et des projets à partir du contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="e2f68-115">Open Solutions and Projects from Source Control</span></span>](../../2014/database-engine/open-solutions-and-projects-from-source-control.md)  
  
  
