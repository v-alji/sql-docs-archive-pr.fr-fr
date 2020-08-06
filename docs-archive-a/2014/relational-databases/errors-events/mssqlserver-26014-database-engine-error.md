---
title: MSSQLSERVER_26014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605487"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="57e8f-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="57e8f-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="57e8f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="57e8f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57e8f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="57e8f-104">Product Name</span></span>|<span data-ttu-id="57e8f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="57e8f-105">SQL Server</span></span>|  
|<span data-ttu-id="57e8f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="57e8f-106">Event ID</span></span>|<span data-ttu-id="57e8f-107">26014</span><span class="sxs-lookup"><span data-stu-id="57e8f-107">26014</span></span>|  
|<span data-ttu-id="57e8f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="57e8f-108">Event Source</span></span>|<span data-ttu-id="57e8f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57e8f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57e8f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="57e8f-110">Component</span></span>|<span data-ttu-id="57e8f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="57e8f-111">SQLEngine</span></span>|  
|<span data-ttu-id="57e8f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="57e8f-112">Symbolic Name</span></span>|<span data-ttu-id="57e8f-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="57e8f-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="57e8f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="57e8f-114">Message Text</span></span>|<span data-ttu-id="57e8f-115">Impossible de charger un certificat spécifié par l'utilisateur [Cert Hash(sha1) "%hs"].</span><span class="sxs-lookup"><span data-stu-id="57e8f-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="57e8f-116">Le serveur n'acceptera pas de connexion.</span><span class="sxs-lookup"><span data-stu-id="57e8f-116">The server will not accept a connection.</span></span> <span data-ttu-id="57e8f-117">Vérifiez que ce certificat est installé correctement.</span><span class="sxs-lookup"><span data-stu-id="57e8f-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="57e8f-118">Consultez "Configuration du certificat en vue de son utilisation par SSL" dans la documentation en ligne.</span><span class="sxs-lookup"><span data-stu-id="57e8f-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57e8f-119">Explication</span><span class="sxs-lookup"><span data-stu-id="57e8f-119">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="57e8f-120">a essayé de charger le certificat nommé dans le message, mais l’opération a échoué.</span><span class="sxs-lookup"><span data-stu-id="57e8f-120">attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="57e8f-121">Ce problème doit être résolu pour que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puisse utiliser ce certificat.</span><span class="sxs-lookup"><span data-stu-id="57e8f-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="57e8f-122">Cette erreur peut avoir plusieurs causes :</span><span class="sxs-lookup"><span data-stu-id="57e8f-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="57e8f-123">Le certificat peut avoir été déplacé ou supprimé.</span><span class="sxs-lookup"><span data-stu-id="57e8f-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="57e8f-124">Si la connexion utilisée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a changé, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut ne pas avoir l'autorisation d'accéder au certificat.</span><span class="sxs-lookup"><span data-stu-id="57e8f-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="57e8f-125">Le certificat a peut-être expiré.</span><span class="sxs-lookup"><span data-stu-id="57e8f-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57e8f-126">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="57e8f-126">User Action</span></span>  
 <span data-ttu-id="57e8f-127">Assurez-vous que le certificat nommé dans le message existe sur le système, qu'il est accessible et qu'il est toujours valide.</span><span class="sxs-lookup"><span data-stu-id="57e8f-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
