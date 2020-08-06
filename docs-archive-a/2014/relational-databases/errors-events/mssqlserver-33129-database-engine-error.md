---
title: MSSQLSERVER_33129 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604506"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="e9ec9-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="e9ec9-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="e9ec9-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e9ec9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9ec9-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e9ec9-104">Product Name</span></span>|<span data-ttu-id="e9ec9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9ec9-105">SQL Server</span></span>|  
|<span data-ttu-id="e9ec9-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e9ec9-106">Event ID</span></span>|<span data-ttu-id="e9ec9-107">33129</span><span class="sxs-lookup"><span data-stu-id="e9ec9-107">33129</span></span>|  
|<span data-ttu-id="e9ec9-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e9ec9-108">Event Source</span></span>|<span data-ttu-id="e9ec9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9ec9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9ec9-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e9ec9-110">Component</span></span>|<span data-ttu-id="e9ec9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e9ec9-111">SQLEngine</span></span>|  
|<span data-ttu-id="e9ec9-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e9ec9-112">Symbolic Name</span></span>|<span data-ttu-id="e9ec9-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="e9ec9-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="e9ec9-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e9ec9-114">Message Text</span></span>|<span data-ttu-id="e9ec9-115">Impossible d'utiliser ALTER_LOGIN avec l'argument DISABLE pour refuser l'accès à un groupe Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9ec9-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e9ec9-116">Explanation</span></span>  
 <span data-ttu-id="e9ec9-117">Ce message est généré lors d'une tentative de désactivation de la connexion d'un groupe Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9ec9-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e9ec9-118">User Action</span></span>  
 <span data-ttu-id="e9ec9-119">La connexion d'un groupe Windows ne peut pas être désactivée.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="e9ec9-120">Pour supprimer temporairement l'autorisation d'accès accordée à un groupe Windows, révoquez avec REVOKE l'autorisation CONNECT de la connexion du groupe Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="e9ec9-121">Les utilisateurs Windows peuvent encore bénéficier d'un accès par leur connexion individuelle ou via un autre groupe Windows.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="e9ec9-122">L'exemple suivant révoque l'autorisation de connexion au groupe de comptabilité Accounting du domaine WESTCOAST.</span><span class="sxs-lookup"><span data-stu-id="e9ec9-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
