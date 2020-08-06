---
title: Autorisations ou Éléments sécurisables, page | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.permissions.f1
- sql12.swb.SecurableAndEffectPermissions.f1
- sql12.swb.availabilitygroupproperties.permission.f1
- sql12.swb.common.columnperm.f1
- sql12.swb.SecurableAndEffectivePermission.f1
ms.assetid: b3bf077a-bec2-4161-ac0c-460586199906
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 80417c720258833850f07eb67f83f5c47f487ad2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697715"
---
# <a name="permissions-or-securables-page"></a><span data-ttu-id="18cf5-102">Page Autorisations ou Éléments sécurisables</span><span class="sxs-lookup"><span data-stu-id="18cf5-102">Permissions or Securables Page</span></span>
  <span data-ttu-id="18cf5-103">Utilisez la page **Autorisations** ou **Éléments sécurisables** pour afficher ou définir les autorisations pour les éléments sécurisables.</span><span class="sxs-lookup"><span data-stu-id="18cf5-103">Use the **Permissions** page or the **Securables** page to view or set the permissions for securables.</span></span> <span data-ttu-id="18cf5-104">Cette page peut être ouverte à partir de plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="18cf5-104">This page can be opened from many locations.</span></span> <span data-ttu-id="18cf5-105">Le contenu de la page peut varier légèrement, selon la façon dont la page est ouverte et ce qu'elle contient.</span><span class="sxs-lookup"><span data-stu-id="18cf5-105">The contents of the page can change slightly, depending on how the page is opened and what it contains.</span></span> <span data-ttu-id="18cf5-106">La grille supérieure de la page peut être remplie lorsque la page s'ouvre, ou elle peut être vide.</span><span class="sxs-lookup"><span data-stu-id="18cf5-106">The top grid of the page might be populated when the page opens, or it might be empty.</span></span> <span data-ttu-id="18cf5-107">Pour ajouter des éléments à la grille supérieure, cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="18cf5-107">To add items to the upper grid, click **Search**.</span></span> <span data-ttu-id="18cf5-108">Dans la grille supérieure, sélectionnez un élément, puis définissez les autorisations appropriées sous l'onglet **Autorisations explicites** . Pour afficher les autorisations agrégées, utilisez l'onglet **Autorisations effectives** .</span><span class="sxs-lookup"><span data-stu-id="18cf5-108">In the upper grid, select an item, and then set the appropriate permissions on the **Explicit** tab. To view aggregated permissions, use the **Effective** tab.</span></span>  
  
 <span data-ttu-id="18cf5-109">Pour comprendre les combinaisons possibles d’éléments sécurisables et de principaux, consultez les liens relatifs à la syntaxe spécifique des éléments sécurisables dans la rubrique [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="18cf5-109">To understand the possible combinations of securables and principals, see the securable-specific syntax links in the topic [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="18cf5-110">Pour plus d'informations, consultez [Securables](securables.md).</span><span class="sxs-lookup"><span data-stu-id="18cf5-110">For more information, see [Securables](securables.md).</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="18cf5-111">En-tête de page</span><span class="sxs-lookup"><span data-stu-id="18cf5-111">Page Header</span></span>  
 <span data-ttu-id="18cf5-112">L'en-tête de la page **Autorisations** ou **Éléments sécurisables** varie en fonction de l'élément sécurisable ou du principal.</span><span class="sxs-lookup"><span data-stu-id="18cf5-112">The header of the **Permissions** or **Securables** page varies depending on the securable or principal.</span></span> <span data-ttu-id="18cf5-113">Il affiche des informations pertinentes sur l'élément, telles que son nom.</span><span class="sxs-lookup"><span data-stu-id="18cf5-113">It displays information relevant to the item, such as its name.</span></span>  
  
## <a name="upper-grid"></a><span data-ttu-id="18cf5-114">Grille supérieure</span><span class="sxs-lookup"><span data-stu-id="18cf5-114">Upper Grid</span></span>  
 <span data-ttu-id="18cf5-115">La grille supérieure contient un ou plusieurs éléments pour lesquels des autorisations peuvent être définies.</span><span class="sxs-lookup"><span data-stu-id="18cf5-115">The upper grid contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="18cf5-116">Cette boîte de dialogue contient le bouton **Rechercher** , qui permet de sélectionner des objets ou des principaux à ajouter à la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="18cf5-116">This dialog box provides the **Search** button for selecting objects or principals to add to the upper grid.</span></span> <span data-ttu-id="18cf5-117">Le nom de la grille peut afficher **Éléments sécurisables** ou un ou plusieurs types d'éléments sécurisables ou de principaux.</span><span class="sxs-lookup"><span data-stu-id="18cf5-117">The name of the grid might display **Securables** or one or more types of securables or principals.</span></span> <span data-ttu-id="18cf5-118">Les colonnes affichées dans la grille supérieure varient selon le principal ou l'élément sécurisable.</span><span class="sxs-lookup"><span data-stu-id="18cf5-118">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="18cf5-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="18cf5-119">**Name**</span></span>  
 <span data-ttu-id="18cf5-120">Nom de chaque principal ou élément sécurisable ajouté à la grille.</span><span class="sxs-lookup"><span data-stu-id="18cf5-120">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="18cf5-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="18cf5-121">**Type**</span></span>  
 <span data-ttu-id="18cf5-122">Décrit le type de chaque élément.</span><span class="sxs-lookup"><span data-stu-id="18cf5-122">Describes the type of each item.</span></span>  
  
## <a name="explicit-tab"></a><span data-ttu-id="18cf5-123">Onglet Autorisations explicites</span><span class="sxs-lookup"><span data-stu-id="18cf5-123">Explicit Tab</span></span>  
 <span data-ttu-id="18cf5-124">L'onglet **Autorisations explicites** énumère les autorisations possibles pour les éléments sécurisables sélectionnés dans la grille supérieure.</span><span class="sxs-lookup"><span data-stu-id="18cf5-124">The **Explicit** tab lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="18cf5-125">Pour configurer les autorisations, cochez ou décochez les cases **Accorder** (ou **Autoriser**), **Avec autorisation**et **Refuser** .</span><span class="sxs-lookup"><span data-stu-id="18cf5-125">To configure the permissions, select or clear the **Grant** (or **Allow**), **With Grant**, and **Deny** check boxes.</span></span> <span data-ttu-id="18cf5-126">Toutes les options ne sont pas disponibles pour toutes les autorisations explicites.</span><span class="sxs-lookup"><span data-stu-id="18cf5-126">All options are not available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="18cf5-127">**autorisations**</span><span class="sxs-lookup"><span data-stu-id="18cf5-127">**Permissions**</span></span>  
 <span data-ttu-id="18cf5-128">Nom de l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-128">The name of the permission.</span></span>  
  
 <span data-ttu-id="18cf5-129">**Fournisseur d'autorisations**</span><span class="sxs-lookup"><span data-stu-id="18cf5-129">**Grantor**</span></span>  
 <span data-ttu-id="18cf5-130">Principal ayant accordé l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-130">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="18cf5-131">**Octroyer**</span><span class="sxs-lookup"><span data-stu-id="18cf5-131">**Grant**</span></span>  
 <span data-ttu-id="18cf5-132">Sélectionnez cette option pour octroyer cette autorisation à la connexion.</span><span class="sxs-lookup"><span data-stu-id="18cf5-132">Select to grant this permission to the login.</span></span> <span data-ttu-id="18cf5-133">Désactivez-la pour révoquer cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-133">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="18cf5-134">**Avec autorisation**</span><span class="sxs-lookup"><span data-stu-id="18cf5-134">**With Grant**</span></span>  
 <span data-ttu-id="18cf5-135">Reflète l'état de l'option WITH GRANT pour l'autorisation indiquée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="18cf5-135">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="18cf5-136">Cette zone est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="18cf5-136">This box is read-only.</span></span> <span data-ttu-id="18cf5-137">Pour appliquer cette autorisation, utilisez l'instruction [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="18cf5-137">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="18cf5-138">**Deny**</span><span class="sxs-lookup"><span data-stu-id="18cf5-138">**Deny**</span></span>  
 <span data-ttu-id="18cf5-139">Sélectionnez cette option pour refuser cette autorisation à la connexion.</span><span class="sxs-lookup"><span data-stu-id="18cf5-139">Select to deny this permission to the login.</span></span> <span data-ttu-id="18cf5-140">Désactivez-la pour révoquer cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-140">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="18cf5-141">**Autorisations au niveau des colonnes**</span><span class="sxs-lookup"><span data-stu-id="18cf5-141">**Column Permissions**</span></span>  
 <span data-ttu-id="18cf5-142">Pour les objets qui contiennent des colonnes (tels que les tables, les vues ou les fonctions table), le bouton **Autorisations au niveau des colonnes** ouvre la boîte de dialogue du **même nom** .</span><span class="sxs-lookup"><span data-stu-id="18cf5-142">For objects that contain columns (such as tables, views, or table-valued functions), the **Column Permissions** button opens the **Column Permissions** dialog box.</span></span> <span data-ttu-id="18cf5-143">Dans cette boîte de dialogue, vous pouvez définir les autorisations **Octroyer**, **Autoriser**ou **Refuser** sur des colonnes individuelles d'une table ou d'une vue.</span><span class="sxs-lookup"><span data-stu-id="18cf5-143">In this dialog box, you can set **Grant**, **Allow**, or **Deny** permissions on individual columns of a table or view.</span></span> <span data-ttu-id="18cf5-144">Cette option n'est pas disponible pour tous les types d'objets ou autorisations.</span><span class="sxs-lookup"><span data-stu-id="18cf5-144">This option is not available for all object types or permissions.</span></span>  
  
## <a name="effective-tab"></a><span data-ttu-id="18cf5-145">Onglet Autorisations effectives</span><span class="sxs-lookup"><span data-stu-id="18cf5-145">Effective Tab</span></span>  
 <span data-ttu-id="18cf5-146">Les autorisations qu'un principal a mises en rapport avec un élément sécurisable peuvent provenir des autorisations définies pour plusieurs principaux différents.</span><span class="sxs-lookup"><span data-stu-id="18cf5-146">The permissions that a principal has related to a securable may come from permissions that are set for several different principals.</span></span> <span data-ttu-id="18cf5-147">Par exemple, une connexion peut recevoir des autorisations individuellement, et également comme membre d'un groupe.</span><span class="sxs-lookup"><span data-stu-id="18cf5-147">For example, a login might be granted permissions individually and also as a member of a group.</span></span> <span data-ttu-id="18cf5-148">L'onglet **Autorisations effectives** affiche le résultat de la combinaison d'autorisations explicites et des autorisations provenant d'appartenances de groupe ou de rôle.</span><span class="sxs-lookup"><span data-stu-id="18cf5-148">The **Effective** tab shows the result of combining explicit permissions and the permissions that are received from group or role memberships.</span></span> <span data-ttu-id="18cf5-149">Les autorisations Octroyer sont agrégées.</span><span class="sxs-lookup"><span data-stu-id="18cf5-149">Grant permissions are aggregated.</span></span> <span data-ttu-id="18cf5-150">Une autorisation Refuser remplace toutes les autorisations Octroyer.</span><span class="sxs-lookup"><span data-stu-id="18cf5-150">A deny permission overrides all grant permissions.</span></span>  
  
 <span data-ttu-id="18cf5-151">**autorisations**</span><span class="sxs-lookup"><span data-stu-id="18cf5-151">**Permissions**</span></span>  
 <span data-ttu-id="18cf5-152">Nom de l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-152">The name of the permission.</span></span>  
  
 <span data-ttu-id="18cf5-153">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="18cf5-153">**Column**</span></span>  
 <span data-ttu-id="18cf5-154">Noms des colonnes affectées par l'autorisation.</span><span class="sxs-lookup"><span data-stu-id="18cf5-154">The names of columns that are affected by the permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cf5-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18cf5-155">See Also</span></span>  
 <span data-ttu-id="18cf5-156">[Rôles au niveau de la base de données](authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="18cf5-156">[Database-Level Roles](authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="18cf5-157">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="18cf5-157">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
