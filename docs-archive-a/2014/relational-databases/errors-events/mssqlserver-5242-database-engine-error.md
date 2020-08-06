---
title: MSSQLSERVER_5242 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5242 (Database Engine error)
ms.assetid: 712b1a10-2f87-41df-a111-1ed9f14102d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c979d0a788e80cf5c7e1ab9b9a1ca8eccc0eea19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604504"
---
# <a name="mssqlserver_5242"></a><span data-ttu-id="e66b2-102">MSSQLSERVER_5242</span><span class="sxs-lookup"><span data-stu-id="e66b2-102">MSSQLSERVER_5242</span></span>
    
## <a name="details"></a><span data-ttu-id="e66b2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e66b2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e66b2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e66b2-104">Product Name</span></span>|<span data-ttu-id="e66b2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e66b2-105">SQL Server</span></span>|  
|<span data-ttu-id="e66b2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e66b2-106">Event ID</span></span>|<span data-ttu-id="e66b2-107">5242</span><span class="sxs-lookup"><span data-stu-id="e66b2-107">5242</span></span>|  
|<span data-ttu-id="e66b2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e66b2-108">Event Source</span></span>|<span data-ttu-id="e66b2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e66b2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e66b2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e66b2-110">Component</span></span>|<span data-ttu-id="e66b2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e66b2-111">SQLEngine</span></span>|  
|<span data-ttu-id="e66b2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e66b2-112">Symbolic Name</span></span>||  
|<span data-ttu-id="e66b2-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e66b2-113">Message Text</span></span>|<span data-ttu-id="e66b2-114">Une incohérence a été détectée durant une opération interne dans la base de données '%.\*ls'(ID : %d), dans la page %S_PGID.</span><span class="sxs-lookup"><span data-stu-id="e66b2-114">An inconsistency was detected during an internal operation in database '%.\*ls'(ID:%d) on page %S_PGID.</span></span> <span data-ttu-id="e66b2-115">Contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="e66b2-115">Please contact technical support.</span></span> <span data-ttu-id="e66b2-116">Numéro de référence %ld.</span><span class="sxs-lookup"><span data-stu-id="e66b2-116">Reference number %ld.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e66b2-117">Explication</span><span class="sxs-lookup"><span data-stu-id="e66b2-117">Explanation</span></span>  
 <span data-ttu-id="e66b2-118">Une incohérence structurelle s'est produite dans la page de base de données qui est référencée dans le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="e66b2-118">A structural inconsistency occurred on the database page that is referenced in the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66b2-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e66b2-119">See Also</span></span>  
 <span data-ttu-id="e66b2-120">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e66b2-120">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 [<span data-ttu-id="e66b2-121">Groupes de fichiers et fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="e66b2-121">Database Files and Filegroups</span></span>](../databases/database-files-and-filegroups.md)  
  
  
