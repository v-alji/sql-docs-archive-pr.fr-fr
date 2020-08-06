---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699702"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="73d75-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="73d75-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="73d75-103">Détails</span><span class="sxs-lookup"><span data-stu-id="73d75-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73d75-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="73d75-104">Product Name</span></span>|<span data-ttu-id="73d75-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="73d75-105">SQL Server</span></span>|  
|<span data-ttu-id="73d75-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="73d75-106">Event ID</span></span>|<span data-ttu-id="73d75-107">17130</span><span class="sxs-lookup"><span data-stu-id="73d75-107">17130</span></span>|  
|<span data-ttu-id="73d75-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="73d75-108">Event Source</span></span>|<span data-ttu-id="73d75-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="73d75-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="73d75-110">Composant</span><span class="sxs-lookup"><span data-stu-id="73d75-110">Component</span></span>|<span data-ttu-id="73d75-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="73d75-111">SQLEngine</span></span>|  
|<span data-ttu-id="73d75-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="73d75-112">Symbolic Name</span></span>|<span data-ttu-id="73d75-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="73d75-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="73d75-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="73d75-114">Message Text</span></span>|<span data-ttu-id="73d75-115">Mémoire insuffisante pour le nombre de verrous configuré.</span><span class="sxs-lookup"><span data-stu-id="73d75-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="73d75-116">Tentative de démarrage avec une table de hachage de verrou moins importante en cours, ce qui risque d'influer sur les performances.</span><span class="sxs-lookup"><span data-stu-id="73d75-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="73d75-117">Contactez l'administrateur de base de données pour configurer une quantité de mémoire plus importante pour cette instance du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="73d75-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="73d75-118">Explication</span><span class="sxs-lookup"><span data-stu-id="73d75-118">Explanation</span></span>  
 <span data-ttu-id="73d75-119">Mémoire insuffisante pour la taille souhaitée de la table de hachage du gestionnaire de verrous.</span><span class="sxs-lookup"><span data-stu-id="73d75-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="73d75-120">Une tentative d'allocation d'une table de hachage plus petite va être effectuée.</span><span class="sxs-lookup"><span data-stu-id="73d75-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73d75-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="73d75-121">User Action</span></span>  
 <span data-ttu-id="73d75-122">Vérifiez les paramètres de configuration de la mémoire du serveur (min server memory et max server memory), ainsi que la sollicitation de la mémoire :</span><span class="sxs-lookup"><span data-stu-id="73d75-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="73d75-123">Allouez davantage de mémoire à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73d75-123">Provide SQL Server more memory.</span></span>  
  
  
