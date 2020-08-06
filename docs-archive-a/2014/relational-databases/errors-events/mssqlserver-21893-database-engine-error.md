---
title: MSSQLSERVER_21893 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612391"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="e69ab-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="e69ab-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="e69ab-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e69ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e69ab-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e69ab-104">Product Name</span></span>|<span data-ttu-id="e69ab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e69ab-105">SQL Server</span></span>|  
|<span data-ttu-id="e69ab-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e69ab-106">Event ID</span></span>|<span data-ttu-id="e69ab-107">21893</span><span class="sxs-lookup"><span data-stu-id="e69ab-107">21893</span></span>|  
|<span data-ttu-id="e69ab-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e69ab-108">Event Source</span></span>|<span data-ttu-id="e69ab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e69ab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e69ab-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e69ab-110">Component</span></span>|<span data-ttu-id="e69ab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e69ab-111">SQLEngine</span></span>|  
|<span data-ttu-id="e69ab-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e69ab-112">Symbolic Name</span></span>|<span data-ttu-id="e69ab-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="e69ab-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="e69ab-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e69ab-114">Message Text</span></span>|<span data-ttu-id="e69ab-115">Les abonnés (%s) du serveur de publication d'origine '%s' n'apparaissent pas en tant que serveurs distants sur le serveur de publication redirigé '%s'.</span><span class="sxs-lookup"><span data-stu-id="e69ab-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="e69ab-116">Exécutez `sp_addlinkedserver` sur le serveur de publication Redirigé pour ajouter ces abonnés en tant que serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="e69ab-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e69ab-117">Explication</span><span class="sxs-lookup"><span data-stu-id="e69ab-117">Explanation</span></span>  
 <span data-ttu-id="e69ab-118">`sp_validate_redirected_publisher` utilise les tables de métadonnées d'abonnement de la base de données du serveur de publication sur le serveur distant pour identifier ses abonnés associés et vérifie qu'il existe des entrées associées dans master.dbo.sysservers pour les abonnés.</span><span class="sxs-lookup"><span data-stu-id="e69ab-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="e69ab-119">Cette erreur est retournée si des abonnés identifiés ne sont pas présents.</span><span class="sxs-lookup"><span data-stu-id="e69ab-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="e69ab-120">Elle n'est pas considérée comme une erreur fatale.</span><span class="sxs-lookup"><span data-stu-id="e69ab-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="e69ab-121">Les agents qui reçoivent cette erreur vont la consigner dans le journal à titre d'information mais ne vont pas s'arrêter, car l'absence d'entrées d'abonnés appropriées sur le nouveau serveur de publication a un impact limité sur la réplication.</span><span class="sxs-lookup"><span data-stu-id="e69ab-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="e69ab-122">Sans une entrée appropriée pour un abonné dans sysservers, certaines activités de gestion d’abonnement peuvent échouer quand elles sont exécutées par [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e69ab-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e69ab-123">Toutefois, ces mêmes opérations peuvent être effectuées avec succès en exécutant les procédures stockées de gestion explicitement.</span><span class="sxs-lookup"><span data-stu-id="e69ab-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e69ab-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e69ab-124">User Action</span></span>  
 <span data-ttu-id="e69ab-125">Exécutez `sp_addlinkedserver` sur le serveur de publication redirigé pour chaque abonné identifié afin de l'ajouter en tant que serveur distant.</span><span class="sxs-lookup"><span data-stu-id="e69ab-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="e69ab-126">Puis, exécutez `sp_serveroption` pour définir le bit d'abonné pour le serveur.</span><span class="sxs-lookup"><span data-stu-id="e69ab-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
