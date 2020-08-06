---
title: MSSQLSERVER_1461 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612905"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="90891-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="90891-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="90891-103">Détails</span><span class="sxs-lookup"><span data-stu-id="90891-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90891-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="90891-104">Product Name</span></span>|<span data-ttu-id="90891-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="90891-105">SQL Server</span></span>|  
|<span data-ttu-id="90891-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="90891-106">Event ID</span></span>|<span data-ttu-id="90891-107">1461</span><span class="sxs-lookup"><span data-stu-id="90891-107">1461</span></span>|  
|<span data-ttu-id="90891-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="90891-108">Event Source</span></span>|<span data-ttu-id="90891-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="90891-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="90891-110">Composant</span><span class="sxs-lookup"><span data-stu-id="90891-110">Component</span></span>|<span data-ttu-id="90891-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="90891-111">SQLEngine</span></span>|  
|<span data-ttu-id="90891-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="90891-112">Symbolic Name</span></span>|<span data-ttu-id="90891-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="90891-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="90891-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="90891-114">Message Text</span></span>|<span data-ttu-id="90891-115">Plusieurs niveaux de sécurité de mise en miroir de bases de données ont été détectés pour la base de données « %.\*ls ».</span><span class="sxs-lookup"><span data-stu-id="90891-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="90891-116">Le niveau de sécurité FULL sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="90891-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="90891-117">Explication</span><span class="sxs-lookup"><span data-stu-id="90891-117">Explanation</span></span>  
 <span data-ttu-id="90891-118">Les connexions de mise en miroir ont été interrompues lorsque le niveau de sécurité des transactions a été modifié car les paramètres de sécurité des transactions étaient incohérents entre la base de données principale et la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="90891-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="90891-119">Le paramètre de sécurité par défaut, à savoir la sécurité totale des transactions, sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="90891-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="90891-120">La session sera exécutée en mode haute sécurité.</span><span class="sxs-lookup"><span data-stu-id="90891-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="90891-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="90891-121">User Action</span></span>  
 <span data-ttu-id="90891-122">Pour désactiver la sécurité des transactions, réexécutez l’instruction ALTER DATABASE *nom_base_de_données* SET PARTNER SAFETY OFF sur la base de données principale.</span><span class="sxs-lookup"><span data-stu-id="90891-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
