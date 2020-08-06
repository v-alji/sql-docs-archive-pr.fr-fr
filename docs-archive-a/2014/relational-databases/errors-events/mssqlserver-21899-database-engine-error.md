---
title: MSSQLSERVER_21899 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699648"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="01bb7-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="01bb7-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="01bb7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="01bb7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01bb7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="01bb7-104">Product Name</span></span>|<span data-ttu-id="01bb7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="01bb7-105">SQL Server</span></span>|  
|<span data-ttu-id="01bb7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="01bb7-106">Event ID</span></span>|<span data-ttu-id="01bb7-107">21899</span><span class="sxs-lookup"><span data-stu-id="01bb7-107">21899</span></span>|  
|<span data-ttu-id="01bb7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="01bb7-108">Event Source</span></span>|<span data-ttu-id="01bb7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="01bb7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="01bb7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="01bb7-110">Component</span></span>|<span data-ttu-id="01bb7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="01bb7-111">SQLEngine</span></span>|  
|<span data-ttu-id="01bb7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="01bb7-112">Symbolic Name</span></span>|<span data-ttu-id="01bb7-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="01bb7-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="01bb7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="01bb7-114">Message Text</span></span>|<span data-ttu-id="01bb7-115">Échec de la requête effectuée sur le serveur de publication redirigé '%s' afin de déterminer s’il existe des entrées sysserver pour les abonnés du serveur de publication d’origine '%s'. Erreur '%d', message d’erreur '%s'.</span><span class="sxs-lookup"><span data-stu-id="01bb7-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01bb7-116">Explication</span><span class="sxs-lookup"><span data-stu-id="01bb7-116">Explanation</span></span>  
 <span data-ttu-id="01bb7-117">`sp_validate_redirected_publisher` interroge les tables de métadonnées d'abonnement de la base de données du serveur de publication sur le serveur distant pour déterminer ses abonnés associés.</span><span class="sxs-lookup"><span data-stu-id="01bb7-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="01bb7-118">L'erreur 21899 est retournée si cette requête échoue.</span><span class="sxs-lookup"><span data-stu-id="01bb7-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="01bb7-119">La requête de validation requiert l'accès à la base de données publiée sur le serveur de publication redirigé.</span><span class="sxs-lookup"><span data-stu-id="01bb7-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="01bb7-120">Si la connexion spécifiée lorsque `sp_adddistpublisher` est appelé pour le serveur de publication d'origine n'est pas autorisée pour accéder à la base de données publiée sur le serveur de publication redirigé, l'erreur 21899 est retournée.</span><span class="sxs-lookup"><span data-stu-id="01bb7-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01bb7-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="01bb7-121">User Action</span></span>  
 <span data-ttu-id="01bb7-122">Consultez le message d'erreur cité pour déterminer la cause de l'échec et prendre l'action corrective appropriée</span><span class="sxs-lookup"><span data-stu-id="01bb7-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
