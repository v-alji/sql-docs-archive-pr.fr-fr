---
title: MSSQLSERVER_2501 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702931"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="99dd7-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="99dd7-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="99dd7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="99dd7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99dd7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="99dd7-104">Product Name</span></span>|<span data-ttu-id="99dd7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="99dd7-105">SQL Server</span></span>|  
|<span data-ttu-id="99dd7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="99dd7-106">Event ID</span></span>|<span data-ttu-id="99dd7-107">2501</span><span class="sxs-lookup"><span data-stu-id="99dd7-107">2501</span></span>|  
|<span data-ttu-id="99dd7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="99dd7-108">Event Source</span></span>|<span data-ttu-id="99dd7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="99dd7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="99dd7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="99dd7-110">Component</span></span>|<span data-ttu-id="99dd7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="99dd7-111">SQLEngine</span></span>|  
|<span data-ttu-id="99dd7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="99dd7-112">Symbolic Name</span></span>|<span data-ttu-id="99dd7-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="99dd7-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="99dd7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="99dd7-114">Message Text</span></span>|<span data-ttu-id="99dd7-115">Table ou objet avec le nom 'NAME' introuvable.</span><span class="sxs-lookup"><span data-stu-id="99dd7-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="99dd7-116">Vérifiez le catalogue système.</span><span class="sxs-lookup"><span data-stu-id="99dd7-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99dd7-117">Explication</span><span class="sxs-lookup"><span data-stu-id="99dd7-117">Explanation</span></span>  
 <span data-ttu-id="99dd7-118">L'objet spécifié reste introuvable.</span><span class="sxs-lookup"><span data-stu-id="99dd7-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="99dd7-119">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="99dd7-119">Possible Causes</span></span>  
 <span data-ttu-id="99dd7-120">Cette erreur peut être causée par l'un des problèmes suivants :</span><span class="sxs-lookup"><span data-stu-id="99dd7-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="99dd7-121">L'objet n'est pas correctement spécifié.</span><span class="sxs-lookup"><span data-stu-id="99dd7-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="99dd7-122">L'objet n'existe pas ou il a été supprimé avant qu'une instruction n'essaie de l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="99dd7-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="99dd7-123">L'objet existe probablement mais n'a pas pu être exposé à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99dd7-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="99dd7-124">Il se peut par exemple que l'utilisateur ne dispose pas d'autorisations sur l'objet ou que l'objet soit une table interne qui ne peut pas être vue par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99dd7-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99dd7-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="99dd7-125">User Action</span></span>  
  
-   <span data-ttu-id="99dd7-126">Vérifiez que le contexte de base de données est correct.</span><span class="sxs-lookup"><span data-stu-id="99dd7-126">Verify the current database context is correct.</span></span> <span data-ttu-id="99dd7-127">Pour plus d’informations, consultez [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99dd7-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="99dd7-128">Vérifiez que le nom de la table ou de l'objet est correctement orthographié.</span><span class="sxs-lookup"><span data-stu-id="99dd7-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="99dd7-129">Vérifiez le nom de schéma que contient l'objet.</span><span class="sxs-lookup"><span data-stu-id="99dd7-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="99dd7-130">Si l’objet appartient à un schéma autre que le schéma par défaut (**dbo**), vous devez spécifier le nom de la table ou de l’objet à l’aide du format en deux parties *nom_schéma.nom_objet*.</span><span class="sxs-lookup"><span data-stu-id="99dd7-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="99dd7-131">Vérifiez que l'objet existe dans les tables système.</span><span class="sxs-lookup"><span data-stu-id="99dd7-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="99dd7-132">Pour vérifier s’il existe une table ou un autre objet étendu aux schémas, interrogez la vue de catalogue [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99dd7-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="99dd7-133">Si l'objet ne se trouve pas dans les tables système, cela signifie qu'il a été supprimé ou que l'utilisateur ne dispose pas d'autorisations pour afficher les métadonnées de l'objet.</span><span class="sxs-lookup"><span data-stu-id="99dd7-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="99dd7-134">Pour plus d’informations sur l’affichage des métadonnées d’objet, consultez [Configuration de la visibilité des métadonnées](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="99dd7-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dd7-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99dd7-135">See Also</span></span>  
 [<span data-ttu-id="99dd7-136">Affichages catalogue &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="99dd7-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
