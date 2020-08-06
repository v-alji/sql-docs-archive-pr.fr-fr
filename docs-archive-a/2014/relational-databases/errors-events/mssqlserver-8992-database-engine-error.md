---
title: MSSQLSERVER_8992 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615150"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="f3315-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="f3315-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="f3315-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f3315-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3315-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f3315-104">Product Name</span></span>|<span data-ttu-id="f3315-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3315-105">SQL Server</span></span>|  
|<span data-ttu-id="f3315-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f3315-106">Event ID</span></span>|<span data-ttu-id="f3315-107">8992</span><span class="sxs-lookup"><span data-stu-id="f3315-107">8992</span></span>|  
|<span data-ttu-id="f3315-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f3315-108">Event Source</span></span>|<span data-ttu-id="f3315-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3315-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3315-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f3315-110">Component</span></span>|<span data-ttu-id="f3315-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3315-111">SQLEngine</span></span>|  
|<span data-ttu-id="f3315-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f3315-112">Symbolic Name</span></span>|<span data-ttu-id="f3315-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="f3315-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="f3315-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f3315-114">Message Text</span></span>|<span data-ttu-id="f3315-115">Contrôle du message du catalogue ERROR, niveau LEVEL, état STATE : MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="f3315-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3315-116">Explication</span><span class="sxs-lookup"><span data-stu-id="f3315-116">Explanation</span></span>  
 <span data-ttu-id="f3315-117">DBCC CHECKCATALOG ou DBCC CHECKDB a trouvé une incohérence dans les tables de métadonnées système pour l'objet spécifié.</span><span class="sxs-lookup"><span data-stu-id="f3315-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="f3315-118">En d'autres termes, il y a une incohérence entre l'ID d'objet enregistré et l'objet spécifié dans le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="f3315-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="f3315-119">Cette erreur peut se produire lorsqu'une ou plusieurs tables système ont été mises à jour manuellement de telle sorte qu'il existe une incohérence dans les métadonnées système.</span><span class="sxs-lookup"><span data-stu-id="f3315-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="f3315-120">Par exemple, un utilisateur a pu supprimer manuellement un objet de la table **sysobjects** sans supprimer les lignes associées dans d’autres tables telles que **sysindexes** et **syscolumns**.</span><span class="sxs-lookup"><span data-stu-id="f3315-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="f3315-121">Cette erreur peut se produire lors de l'exécution de DBCC CHECKDB sur une base de données mise à niveau de SQL Server 2000 vers SQL Server 2005 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f3315-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="f3315-122">Dans SQL Server 2000, DBCC CHECKDB n'incluait pas la fonctionnalité DBCC CHECKCATALOG ; par conséquent, l'erreur ne peut pas être interceptée avant la mise à niveau à moins que DBCC CHECKCATALOG n'ait été spécifiquement exécuté sur la base de données dans SQL Server 2000.</span><span class="sxs-lookup"><span data-stu-id="f3315-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="f3315-123">Vous pouvez voir s'afficher les erreurs suivantes conjointement avec l'erreur 8992 :</span><span class="sxs-lookup"><span data-stu-id="f3315-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="f3315-124">Msg 3851 - Une ligne non valide (%ls) a été détectée dans la table système sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-125">Msg 3852 - La ligne (%ls) de sys.%ls%ls ne correspond à aucune ligne (%ls) dans sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-126">3853 - L'attribut (%ls) de la ligne (%ls) dans sys.%ls%ls ne correspond à aucune ligne (%ls) dans sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-127">3854 - L'attribut (%ls) de la ligne (%ls) dans sys.%ls%ls correspond à une ligne (%ls) dans sys.%ls%ls qui est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="f3315-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="f3315-128">3855 - L'attribut (%ls) figure sans ligne (%ls) dans sys.%3ls%ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-129">3856 - L'attribut (%ls) existe alors qu'il ne le devrait pas pour la ligne (%ls) dans sys.%ls%4ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-130">3857 - L'attribut (%ls) est obligatoire mais il n'existe pas pour la ligne (%ls) dans sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="f3315-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="f3315-131">3858 - L'attribut (%ls) de la ligne (%ls) dans sys.%ls%ls a une valeur non valide.</span><span class="sxs-lookup"><span data-stu-id="f3315-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3315-132">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f3315-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="f3315-133">Supprimer et recréer l'objet spécifié</span><span class="sxs-lookup"><span data-stu-id="f3315-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="f3315-134">Si possible, supprimez et recréez l'objet spécifié.</span><span class="sxs-lookup"><span data-stu-id="f3315-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="f3315-135">Par exemple, si l'objet est une procédure stockée ou un type défini par l'utilisateur, le fait de recréer l'objet peut résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="f3315-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="f3315-136">Restaurer à partir de la sauvegarde</span><span class="sxs-lookup"><span data-stu-id="f3315-136">Restore from Backup</span></span>  
 <span data-ttu-id="f3315-137">Si le problème n'est pas matériel et si une restauration réputée en bon état est disponible, restaurez la base de données à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f3315-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="f3315-138">Cette action est applicable uniquement si la sauvegarde ne contient pas l'erreur de métadonnées.</span><span class="sxs-lookup"><span data-stu-id="f3315-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="f3315-139">Exporter les données vers une nouvelle base de données</span><span class="sxs-lookup"><span data-stu-id="f3315-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="f3315-140">Si la sauvegarde contient également une incohérence des métadonnées, vous devez créer une base de données et exporter le contenu de la base de données existante vers la nouvelle base de données.</span><span class="sxs-lookup"><span data-stu-id="f3315-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="f3315-141">DBCC CHECKDB ne peut pas résoudre cette erreur.</span><span class="sxs-lookup"><span data-stu-id="f3315-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="f3315-142">Cette erreur ne peut pas être corrigée.</span><span class="sxs-lookup"><span data-stu-id="f3315-142">This error cannot be repaired.</span></span>  <span data-ttu-id="f3315-143">Si vous ne pouvez pas restaurer la base de données à partir d'une sauvegarde, contactez le service clientèle et le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3315-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="f3315-144">Ne pas mettre à jour manuellement les tables système</span><span class="sxs-lookup"><span data-stu-id="f3315-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="f3315-145">N'apportez pas de mises à jour manuelles aux tables système.</span><span class="sxs-lookup"><span data-stu-id="f3315-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="f3315-146">SQL Server ne prend pas en charge les modifications manuelles apportées aux bases de données système.</span><span class="sxs-lookup"><span data-stu-id="f3315-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="f3315-147">Si vous mettez à jour une table système dans une base de données SQL Server, deux événements (ID 17659 et ID 3859) sont consignés.</span><span class="sxs-lookup"><span data-stu-id="f3315-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="f3315-148">Pour plus d'informations, consultez l'article 2688307 de la Base de connaissances « L'ID d'événement 17659 et l'ID d'événement 3859 sont consignés lorsque vous mettez à jour des tables système dans une base de données SQL Server ».</span><span class="sxs-lookup"><span data-stu-id="f3315-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3315-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3315-149">See Also</span></span>  
 [<span data-ttu-id="f3315-150">L’ID d’événement 17659 et l’ID d’événement 3859 sont consignés lorsque vous mettez à jour des tables système dans une base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3315-150">Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database</span></span>](https://support.microsoft.com/kb/2688307/EN-US)  
  
  
