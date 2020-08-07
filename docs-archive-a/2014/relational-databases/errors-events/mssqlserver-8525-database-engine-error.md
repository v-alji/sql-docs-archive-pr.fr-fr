---
title: MSSQLSERVER_8525 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611816"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="9bbc5-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="9bbc5-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="9bbc5-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9bbc5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9bbc5-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9bbc5-104">Product Name</span></span>|<span data-ttu-id="9bbc5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9bbc5-105">SQL Server</span></span>|  
|<span data-ttu-id="9bbc5-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9bbc5-106">Event ID</span></span>|<span data-ttu-id="9bbc5-107">8525</span><span class="sxs-lookup"><span data-stu-id="9bbc5-107">8525</span></span>|  
|<span data-ttu-id="9bbc5-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9bbc5-108">Event Source</span></span>|<span data-ttu-id="9bbc5-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9bbc5-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9bbc5-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9bbc5-110">Component</span></span>|<span data-ttu-id="9bbc5-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9bbc5-111">SQLEngine</span></span>|  
|<span data-ttu-id="9bbc5-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9bbc5-112">Symbolic Name</span></span>||  
|<span data-ttu-id="9bbc5-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9bbc5-113">Message Text</span></span>|<span data-ttu-id="9bbc5-114">La transaction distribuée est terminée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-114">Distributed transaction completed.</span></span> <span data-ttu-id="9bbc5-115">Inscrivez cette session, soit dans une nouvelle transaction, soit dans une transaction NULL.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9bbc5-116">Explication</span><span class="sxs-lookup"><span data-stu-id="9bbc5-116">Explanation</span></span>  
 <span data-ttu-id="9bbc5-117">Le modèle de programmation permettant d’utiliser Distributed Transaction Coordinator avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requiert des applications à inscrire explicitement dans une transaction distribuée et à désinscrire explicitement d’une transaction distribuée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="9bbc5-118">Cette erreur se produit lorsque les quatre conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="9bbc5-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="9bbc5-119">L'application est inscrite dans une transaction distribuée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="9bbc5-120">La transaction est terminée, validée ou restaurée, pour une raison quelconque.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="9bbc5-121">L'application utilisateur n'est pas explicitement désinscrite d'une transaction distribuée ni explicitement inscrite dans une nouvelle transaction distribuée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="9bbc5-122">L'application tente d'effectuer une opération transactionnelle qui n'est ni la désinscription d'une transaction distribuée existante ni l'inscription dans une nouvelle transaction distribuée. Il peut s'agir par exemple de l'émission d'une requête ou du démarrage d'une transaction locale.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="9bbc5-123">L'état d'erreur 1 est utilisé lorsque l'application effectue une opération qui permet de créer des transactions locales et l'état 2 est utilisé lorsque l'application tente une inscription dans une session associée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9bbc5-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9bbc5-124">User Action</span></span>  
 <span data-ttu-id="9bbc5-125">Une fois qu'une application est inscrite dans une transaction distribuée, l'application doit être explicitement désinscrite de la transaction distribuée ou inscrite dans une autre transaction distribuée.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="9bbc5-126">Cela entraînera la désinscription implicite d'une transaction inscrite antérieure.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="9bbc5-127">Pour obtenir la syntaxe exacte relative à la désinscription ou à l'inscription dans une transaction distribuée, consultez le manuel de l'interface de programmation de l'application.</span><span class="sxs-lookup"><span data-stu-id="9bbc5-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
