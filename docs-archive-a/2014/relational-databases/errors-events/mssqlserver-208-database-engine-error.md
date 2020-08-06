---
title: MSSQLSERVER_208 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600980"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="1cce2-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="1cce2-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="1cce2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="1cce2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cce2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="1cce2-104">Product Name</span></span>|<span data-ttu-id="1cce2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1cce2-105">SQL Server</span></span>|  
|<span data-ttu-id="1cce2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="1cce2-106">Event ID</span></span>|<span data-ttu-id="1cce2-107">208</span><span class="sxs-lookup"><span data-stu-id="1cce2-107">208</span></span>|  
|<span data-ttu-id="1cce2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="1cce2-108">Event Source</span></span>|<span data-ttu-id="1cce2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1cce2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1cce2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="1cce2-110">Component</span></span>|<span data-ttu-id="1cce2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1cce2-111">SQLEngine</span></span>|  
|<span data-ttu-id="1cce2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="1cce2-112">Symbolic Name</span></span>|<span data-ttu-id="1cce2-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="1cce2-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="1cce2-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="1cce2-114">Message Text</span></span>|<span data-ttu-id="1cce2-115">Nom d'objet '%.\*ls' non valide.</span><span class="sxs-lookup"><span data-stu-id="1cce2-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1cce2-116">Explication</span><span class="sxs-lookup"><span data-stu-id="1cce2-116">Explanation</span></span>  
 <span data-ttu-id="1cce2-117">L'objet spécifié reste introuvable.</span><span class="sxs-lookup"><span data-stu-id="1cce2-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="1cce2-118">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="1cce2-118">Possible Causes</span></span>  
 <span data-ttu-id="1cce2-119">Cette erreur peut être causée par l'un des problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="1cce2-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="1cce2-120">L'objet n'est pas correctement spécifié.</span><span class="sxs-lookup"><span data-stu-id="1cce2-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="1cce2-121">L'objet n'existe pas dans la base de données actuelle ou dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1cce2-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="1cce2-122">L'objet existe, mais n'a pas pu être exposé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1cce2-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="1cce2-123">Par exemple, l'utilisateur n'a pas d'autorisations sur l'objet ou l'objet est créé dans une instruction EXECUTE, mais l'accès à cet objet s'effectue en dehors de la portée de l'instruction EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="1cce2-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cce2-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="1cce2-124">User Action</span></span>  
 <span data-ttu-id="1cce2-125">Vérifiez les informations suivantes et corrigez l'instruction comme il convient.</span><span class="sxs-lookup"><span data-stu-id="1cce2-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="1cce2-126">Le nom de l'objet est correctement orthographié.</span><span class="sxs-lookup"><span data-stu-id="1cce2-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="1cce2-127">Le contexte de la base de données actuelle est correct.</span><span class="sxs-lookup"><span data-stu-id="1cce2-127">The current database context is correct.</span></span> <span data-ttu-id="1cce2-128">Si aucun nom de base de données n'est spécifié pour l'objet, celui-ci doit exister dans la base de données actuelle.</span><span class="sxs-lookup"><span data-stu-id="1cce2-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="1cce2-129">Pour plus d’informations sur la définition du contexte de la base de données, consultez [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cce2-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="1cce2-130">L'objet existe dans les tables système.</span><span class="sxs-lookup"><span data-stu-id="1cce2-130">The object exists in the system tables.</span></span> <span data-ttu-id="1cce2-131">Pour vérifier s’il existe une table ou un autre objet étendu aux schémas, interrogez la vue de catalogue **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="1cce2-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="1cce2-132">Si l'objet ne se trouve pas dans les tables système, cela signifie qu'il a été supprimé ou que l'utilisateur ne dispose pas d'autorisations pour afficher les métadonnées de l'objet.</span><span class="sxs-lookup"><span data-stu-id="1cce2-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="1cce2-133">Pour plus d’informations sur les autorisations d’affichage des métadonnées d’objet, consultez [Configuration de la visibilité des métadonnées](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1cce2-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="1cce2-134">L'objet est contenu dans le schéma par défaut de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1cce2-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="1cce2-135">Si ce n’est pas le cas, l’objet doit être spécifié en respectant le format en deux parties *nom_schéma.nom_objet*.</span><span class="sxs-lookup"><span data-stu-id="1cce2-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="1cce2-136">Notez que les fonctions scalaires doivent toujours être appelées à l'aide, au moins, du nom en deux parties.</span><span class="sxs-lookup"><span data-stu-id="1cce2-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="1cce2-137">Respect de la casse du classement de base de données.</span><span class="sxs-lookup"><span data-stu-id="1cce2-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="1cce2-138">Lorsqu'une base de données utilise un classement respectant la casse, la casse du nom de l'objet doit être identique à celle qui est utilisée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="1cce2-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="1cce2-139">Par exemple, quand un objet est spécifié en tant que **MyTable** dans une base de données avec un classement respectant la casse, les requêtes qui font référence à l’objet en tant que **mytable** ou **Mytable** retournent l’erreur 208, car les noms de l’objet ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="1cce2-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="1cce2-140">Vous pouvez vérifier le classement de base de données en exécutant l'instruction suivante :</span><span class="sxs-lookup"><span data-stu-id="1cce2-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="1cce2-141">L'abréviation CS dans le nom du classement indique que celui-ci respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="1cce2-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="1cce2-142">Par exemple, Latin1_General_CS_AS indique un classement qui respecte la casse et les accents.</span><span class="sxs-lookup"><span data-stu-id="1cce2-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="1cce2-143">CI indique un classement qui ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="1cce2-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="1cce2-144">L'utilisateur a l'autorisation d'accéder à l'objet.</span><span class="sxs-lookup"><span data-stu-id="1cce2-144">The user has permission to access the object.</span></span> <span data-ttu-id="1cce2-145">Pour vérifier les autorisations de l’utilisateur sur l’objet, utilisez la fonction système **Has_Perms_By_Name**.</span><span class="sxs-lookup"><span data-stu-id="1cce2-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cce2-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1cce2-146">See Also</span></span>  
 <span data-ttu-id="1cce2-147">[UTILISER &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1cce2-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="1cce2-148">[Configuration de la visibilité des métadonnées](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="1cce2-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="1cce2-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1cce2-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
