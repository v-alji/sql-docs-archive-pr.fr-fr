---
title: Dépendances d’objet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708899"
---
# <a name="object-dependencies"></a><span data-ttu-id="9ca23-102">Dépendances d'objet</span><span class="sxs-lookup"><span data-stu-id="9ca23-102">Object Dependencies</span></span>
  <span data-ttu-id="9ca23-103">Certains objets de base de données possèdent des dépendances sur d'autres objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="9ca23-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="9ca23-104">Par exemple, les vues et les procédures stockées dépendent de l'existence de tables qui contiennent les données retournées par la vue ou la procédure.</span><span class="sxs-lookup"><span data-stu-id="9ca23-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="9ca23-105">Les **Dépendances d'objets (page Général)** de l'objet actuel répertorient à la fois les objets de base de données indispensables au bon fonctionnement de l'objet et les objets qui dépendent de l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="9ca23-106">Un objet qui référence un autre objet dans sa définition et dont la définition est stockée dans le catalogue système est appelé une *entité de référence*.</span><span class="sxs-lookup"><span data-stu-id="9ca23-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="9ca23-107">Un objet référencé par un autre objet est appelé *entité référencée*.</span><span class="sxs-lookup"><span data-stu-id="9ca23-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="9ca23-108">Les **Dépendances d'objet (page Avancé)** de l'objet actuel répertorient les objets de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ainsi que les objets [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui dépendent de l'objet.</span><span class="sxs-lookup"><span data-stu-id="9ca23-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="9ca23-109">Les objets peuvent être stockés sur des serveurs différents.</span><span class="sxs-lookup"><span data-stu-id="9ca23-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="9ca23-110">Utilisez cette boîte de dialogue pour comprendre les dépendances avant de modifier ou de supprimer l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="9ca23-111">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="9ca23-111">UI element list</span></span>  
 <span data-ttu-id="9ca23-112">**Objets qui dépendent de**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="9ca23-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="9ca23-113">Cliquez sur ce bouton pour afficher la liste des objets dont les dépendances sont suivies et qui dépendent de l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="9ca23-114">**Objets sur lesquels** _\<selected object>_ **dépend** de    </span><span class="sxs-lookup"><span data-stu-id="9ca23-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="9ca23-115">Cliquez sur ce bouton pour afficher la liste des objets dont les dépendances sont suivies et dont dépend l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="9ca23-116">**Dépendances**</span><span class="sxs-lookup"><span data-stu-id="9ca23-116">**Dependencies**</span></span>  
 <span data-ttu-id="9ca23-117">Cliquez sur **Objets qui dépendent de** _\<selected object>_ pour afficher une vue hiérarchique des objets qui dépendent de l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="9ca23-118">Cliquez sur **Objets desquels** _\<selected object>_ **dépend** pour afficher une vue hiérarchique des objets dont dépend l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9ca23-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="9ca23-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="9ca23-119">**Name**</span></span>  
 <span data-ttu-id="9ca23-120">Affiche le nom de l'objet sélectionné dans l'arborescence **Dépendances** affichée plus haut.</span><span class="sxs-lookup"><span data-stu-id="9ca23-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="9ca23-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="9ca23-121">**Type**</span></span>  
 <span data-ttu-id="9ca23-122">Affiche le type de l'objet sélectionné dans l'arborescence **Dépendances** affichée plus haut.</span><span class="sxs-lookup"><span data-stu-id="9ca23-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="9ca23-123">**Dernière heure de synchronisation**</span><span class="sxs-lookup"><span data-stu-id="9ca23-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="9ca23-124">Cette option est disponible uniquement dans la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="9ca23-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="9ca23-125">Spécifie l'heure et date de la dernière mise à jour des informations de dépendance.</span><span class="sxs-lookup"><span data-stu-id="9ca23-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="9ca23-126">**Type de dépendance**</span><span class="sxs-lookup"><span data-stu-id="9ca23-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="9ca23-127">Cette option est disponible uniquement dans la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="9ca23-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="9ca23-128">Affiche le type de dépendance entre deux objets.</span><span class="sxs-lookup"><span data-stu-id="9ca23-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="9ca23-129">Il peut s'agir d'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ca23-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="9ca23-130">Dépendance liée au schéma</span><span class="sxs-lookup"><span data-stu-id="9ca23-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="9ca23-131">Relation entre deux objets qui empêche l'objet référencé d'être supprimé ou modifié tant que l'objet de référence existe.</span><span class="sxs-lookup"><span data-stu-id="9ca23-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="9ca23-132">Une dépendance liée au schéma est créée lorsqu'une vue ou une fonction définie par l'utilisateur est créée à l'aide de la clause WITH SCHEMABINDING, lorsqu'une table référence un autre objet via une contrainte CHECK ou DEFAULT ou dans la définition d'une colonne calculée.</span><span class="sxs-lookup"><span data-stu-id="9ca23-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="9ca23-133">Dépendance non liée au schéma</span><span class="sxs-lookup"><span data-stu-id="9ca23-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="9ca23-134">Relation entre deux objets qui n'empêche pas l'objet référencé d'être supprimé ou modifié.</span><span class="sxs-lookup"><span data-stu-id="9ca23-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="9ca23-135">Entité non disponible ou non résolue</span><span class="sxs-lookup"><span data-stu-id="9ca23-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="9ca23-136">Indique le type de dépendance qui ne peut pas être déterminé.</span><span class="sxs-lookup"><span data-stu-id="9ca23-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="9ca23-137">Cela se produit uniquement lorsque l'objet sélectionné est situé sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieure à [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ca23-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
