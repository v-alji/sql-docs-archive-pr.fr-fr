---
title: Propriétés de la base de données (page Suivi des modifications) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.changetracking.f1
ms.assetid: 9b929640-bc62-449b-9b06-b5a77b8cf372
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4107f81ef4cdf19df60d4a70d8e79007f2c9270c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702968"
---
# <a name="database-properties-changetracking-page"></a><span data-ttu-id="0ec7e-102">Propriétés de la base de données (page Suivi des modifications)</span><span class="sxs-lookup"><span data-stu-id="0ec7e-102">Database Properties (ChangeTracking Page)</span></span>
  <span data-ttu-id="0ec7e-103">Utilisez cette page pour consulter ou modifier les paramètres de suivi des modifications pour la base de données sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-103">Use this page to view or modify change tracking settings for the selected database.</span></span> <span data-ttu-id="0ec7e-104">Pour plus d’informations sur les options disponibles sur cette page, consultez [Activer et désactiver le suivi des modifications &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ec7e-104">For more information about the options available on this page, see [Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0ec7e-105">Options</span><span class="sxs-lookup"><span data-stu-id="0ec7e-105">Options</span></span>  
 <span data-ttu-id="0ec7e-106">**Suivi des modifications**</span><span class="sxs-lookup"><span data-stu-id="0ec7e-106">**Change Tracking**</span></span>  
 <span data-ttu-id="0ec7e-107">Utilisez cette option pour activer ou désactiver le suivi des modifications pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-107">Use to enable or disable change tracking for the database.</span></span>  
  
 <span data-ttu-id="0ec7e-108">Pour activer le suivi des modifications, vous devez posséder l'autorisation de modifier la base de données.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-108">To enable change tracking, you must have permission to modify the database.</span></span>  
  
 <span data-ttu-id="0ec7e-109">L’affectation de la valeur **True** définit une option de base de données qui permet d’activer le suivi des modifications sur des tables individuelles.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-109">Setting the value to **True** sets a database option that allows change tracking to be enabled on individual tables.</span></span>  
  
 <span data-ttu-id="0ec7e-110">Vous pouvez également configurer le suivi des modifications en utilisant [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0ec7e-110">You can also configure change tracking by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="0ec7e-111">**Période de rétention**</span><span class="sxs-lookup"><span data-stu-id="0ec7e-111">**Retention Period**</span></span>  
 <span data-ttu-id="0ec7e-112">Spécifie la période minimale de conservation des informations de suivi des modifications dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-112">Specifies the minimum period for keeping change track information in the database.</span></span> <span data-ttu-id="0ec7e-113">Les données sont supprimées uniquement si la valeur **Nettoyage automatique**a la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-113">Data is removed only if the **Auto Clean-Up**value is **True**.</span></span>  
  
 <span data-ttu-id="0ec7e-114">La valeur par défaut est 2.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-114">The default value is 2.</span></span>  
  
 <span data-ttu-id="0ec7e-115">**Unités de la période de rétention**</span><span class="sxs-lookup"><span data-stu-id="0ec7e-115">**Retention Period Units**</span></span>  
 <span data-ttu-id="0ec7e-116">Spécifie les unités de la valeur Période de rétention.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-116">Specifies the units for the Retention Period value.</span></span> <span data-ttu-id="0ec7e-117">Vous avez le choix entre les unités suivantes : **Jours**, **Heures**ou **Minutes**.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-117">You can select **Days**, **Hours**, or **Minutes**.</span></span> <span data-ttu-id="0ec7e-118">La valeur par défaut est **Jours**.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-118">The default value is **Days**.</span></span>  
  
 <span data-ttu-id="0ec7e-119">La période de rétention minimale est 1 minute.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-119">The minimum retention period is 1 minute.</span></span> <span data-ttu-id="0ec7e-120">Il n'existe pas de période de rétention maximale.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-120">There is no maximum retention period.</span></span>  
  
 <span data-ttu-id="0ec7e-121">**Nettoyage automatique**</span><span class="sxs-lookup"><span data-stu-id="0ec7e-121">**Auto Clean-Up**</span></span>  
 <span data-ttu-id="0ec7e-122">Indique si les informations de suivi des modifications sont supprimées automatiquement à l'issue de la période de rétention spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-122">Indicates whether change tracking information is automatically removed after the specified retention period.</span></span>  
  
 <span data-ttu-id="0ec7e-123">L’activation de l’option **Nettoyage automatique** remplace toute période de rétention personnalisée précédente par la période de rétention par défaut de 2 jours.</span><span class="sxs-lookup"><span data-stu-id="0ec7e-123">Enabling **Auto Clean-Up** resets any previous custom retention period to the default retention period of 2 days.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec7e-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ec7e-124">See Also</span></span>  
 <span data-ttu-id="0ec7e-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ec7e-125">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="0ec7e-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ec7e-126">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
