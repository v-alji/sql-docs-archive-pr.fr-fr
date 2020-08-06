---
title: MSSQLSERVER_21898 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699654"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="173b4-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="173b4-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="173b4-103">Détails</span><span class="sxs-lookup"><span data-stu-id="173b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="173b4-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="173b4-104">Product Name</span></span>|<span data-ttu-id="173b4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="173b4-105">SQL Server</span></span>|  
|<span data-ttu-id="173b4-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="173b4-106">Event ID</span></span>|<span data-ttu-id="173b4-107">21898</span><span class="sxs-lookup"><span data-stu-id="173b4-107">21898</span></span>|  
|<span data-ttu-id="173b4-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="173b4-108">Event Source</span></span>|<span data-ttu-id="173b4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="173b4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="173b4-110">Composant</span><span class="sxs-lookup"><span data-stu-id="173b4-110">Component</span></span>|<span data-ttu-id="173b4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="173b4-111">SQLEngine</span></span>|  
|<span data-ttu-id="173b4-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="173b4-112">Symbolic Name</span></span>|<span data-ttu-id="173b4-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="173b4-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="173b4-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="173b4-114">Message Text</span></span>|<span data-ttu-id="173b4-115">Le serveur de publication '%s' utilise la base de données de distribution '%s' et non '%s', requise pour héberger la base de données de publication '%s'.</span><span class="sxs-lookup"><span data-stu-id="173b4-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="173b4-116">Exécutez `sp_changedistpublisher` sur le serveur de distribution '%s' pour modifier la base de données de distribution utilisée par le serveur de publication sur '%s'.</span><span class="sxs-lookup"><span data-stu-id="173b4-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="173b4-117">Explication</span><span class="sxs-lookup"><span data-stu-id="173b4-117">Explanation</span></span>  
 <span data-ttu-id="173b4-118">`sp_validate_redirected_publisher` interroge msdb.dbo.MSdistpublishers sur le serveur de distribution local pour vérifier que la base de données de distribution utilisée par le nouveau serveur de publication est la même que la base de données de distribution utilisée par le serveur de publication d'origine.</span><span class="sxs-lookup"><span data-stu-id="173b4-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="173b4-119">Cette erreur est retournée lorsque ces bases de données diffèrent, faisant du serveur de publication un hôte incorrect pour la base de données du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="173b4-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="173b4-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="173b4-120">User Action</span></span>  
 <span data-ttu-id="173b4-121">Exécutez la procédure stockée `sp_changedistpublisher` pour modifier la base de données de distribution du nouveau serveur de publication et utiliser celle utilisée par le serveur de publication d'origine.</span><span class="sxs-lookup"><span data-stu-id="173b4-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="173b4-122">L'exécution de `sp_changedistpublisher` résout le problème si la base de données de distribution incorrecte a été configurée lorsque `sp_adddistpublisher` a été exécuté sur le serveur de distribution pour le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="173b4-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="173b4-123">Toutefois, si le serveur de publication distant possède des publications existantes provenant d'une autre base de données de publication qui utilisent la base de données de distribution identifiée, cette modification n'est pas appropriée.</span><span class="sxs-lookup"><span data-stu-id="173b4-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="173b4-124">La réplication utilisant la base de données de distribution nommée doit être systématiquement supprimée puis rétablie à l’aide de la base de données de distribution d’origine du serveur de publication pour que le nouveau serveur de publication fonctionne comme un hôte approprié.</span><span class="sxs-lookup"><span data-stu-id="173b4-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
