---
title: MSSQLSERVER_4064 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613467"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="7c16b-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="7c16b-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="7c16b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="7c16b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c16b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="7c16b-104">Product Name</span></span>|<span data-ttu-id="7c16b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7c16b-105">SQL Server</span></span>|  
|<span data-ttu-id="7c16b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="7c16b-106">Event ID</span></span>|<span data-ttu-id="7c16b-107">4064</span><span class="sxs-lookup"><span data-stu-id="7c16b-107">4064</span></span>|  
|<span data-ttu-id="7c16b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="7c16b-108">Event Source</span></span>|<span data-ttu-id="7c16b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7c16b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7c16b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="7c16b-110">Component</span></span>|<span data-ttu-id="7c16b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7c16b-111">SQLEngine</span></span>|  
|<span data-ttu-id="7c16b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="7c16b-112">Symbolic Name</span></span>|<span data-ttu-id="7c16b-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="7c16b-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="7c16b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="7c16b-114">Message Text</span></span>|<span data-ttu-id="7c16b-115">La base de données utilisateur par défaut ne peut pas être ouverte.</span><span class="sxs-lookup"><span data-stu-id="7c16b-115">Cannot open user default database.</span></span> <span data-ttu-id="7c16b-116">Échec de la connexion.</span><span class="sxs-lookup"><span data-stu-id="7c16b-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7c16b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="7c16b-117">Explanation</span></span>  
 <span data-ttu-id="7c16b-118">La connexion SQL Server n'a pas pu se connecter en raison d'un problème avec sa base de données par défaut.</span><span class="sxs-lookup"><span data-stu-id="7c16b-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="7c16b-119">Soit la base de données n'est pas valide, soit la connexion ne dispose pas de l'autorisation CONNECT sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="7c16b-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c16b-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="7c16b-120">User Action</span></span>  
 <span data-ttu-id="7c16b-121">Utilisez ALTER LOGIN pour modifier la base de données par défaut de la connexion.</span><span class="sxs-lookup"><span data-stu-id="7c16b-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="7c16b-122">Accordez l'autorisation CONNECT à la connexion.</span><span class="sxs-lookup"><span data-stu-id="7c16b-122">Grant CONNECT permission to the login.</span></span>  
  
  
