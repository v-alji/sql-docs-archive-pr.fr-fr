---
title: exportation de données (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- exporting data [Master Data Services]
- subscription views [Master Data Services]
- subscription views [Master Data Services], about subscription views
ms.assetid: 8b74409a-ea70-45f8-84c7-da6905e4901a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: edae5b996c25a1b6053231ed2f69ef511b9fbfa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605526"
---
# <a name="exporting-data-master-data-services"></a><span data-ttu-id="5e5c2-102">Exportation de données (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5e5c2-102">Exporting Data (Master Data Services)</span></span>
  <span data-ttu-id="5e5c2-103">Vous pouvez exporter des données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] vers des systèmes d'abonnement en créant des vues d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-103">You can export [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] data to subscribing systems by creating subscriptions views.</span></span> <span data-ttu-id="5e5c2-104">Tout système d'abonnement peut ensuite afficher les données publiées dans la base de données [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e5c2-104">Any subscribing system can then view the published data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="5e5c2-105">Pour plus d'informations sur les affichages, voir [Affichages](../relational-databases/views/views.md).</span><span class="sxs-lookup"><span data-stu-id="5e5c2-105">For more information about views, see [Views](../relational-databases/views/views.md).</span></span>  
  
## <a name="subscription-view-formats"></a><span data-ttu-id="5e5c2-106">Formats de vue d'abonnement</span><span class="sxs-lookup"><span data-stu-id="5e5c2-106">Subscription View Formats</span></span>  
 <span data-ttu-id="5e5c2-107">Lorsque vous créez une vue dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], vous devez choisir un format dans un ensemble de formats de vue standard fournis par [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e5c2-107">When you create a view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], you choose from a set of standard view formats that [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] provides.</span></span> <span data-ttu-id="5e5c2-108">Vous pouvez utiliser ces formats pour créer des vues qui affichent :</span><span class="sxs-lookup"><span data-stu-id="5e5c2-108">You can use these formats to create views that show:</span></span>  
  
-   <span data-ttu-id="5e5c2-109">Tous les membres feuille et leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-109">All leaf members and their attributes.</span></span>  
  
-   <span data-ttu-id="5e5c2-110">Tous les membres consolidés et leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-110">All consolidated members and their attributes.</span></span>  
  
-   <span data-ttu-id="5e5c2-111">Toutes les collections et leurs attributs.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-111">All collections and their attributes.</span></span>  
  
-   <span data-ttu-id="5e5c2-112">Les membres qui ont été ajoutés explicitement à une collection.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-112">The members explicitly added to a collection.</span></span>  
  
-   <span data-ttu-id="5e5c2-113">Les membres dans une hiérarchie dérivée, dans un format parent-enfant ou de niveau.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-113">The members in a derived hierarchy, in either a parent child or level format.</span></span>  
  
-   <span data-ttu-id="5e5c2-114">Les membres dans toutes les hiérarchies explicites d'une entité, dans un format parent-enfant ou de niveau.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-114">The members in all explicit hierarchies for an entity, in either a parent child or level format.</span></span>  
  
## <a name="subscription-views-can-become-out-of-date"></a><span data-ttu-id="5e5c2-115">Les vues d'abonnement peuvent devenir obsolètes</span><span class="sxs-lookup"><span data-stu-id="5e5c2-115">Subscription Views Can Become Out-of-Date</span></span>  
 <span data-ttu-id="5e5c2-116">Une fois que vous avez créé une vue d'abonnement pour une entité ou une hiérarchie, les modifications apportées aux objets de modèle associés ne sont pas automatiquement répercutées dans la vue.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-116">After you create a subscription view for an entity or hierarchy, changes to the associated model objects are not automatically reflected in the view.</span></span> <span data-ttu-id="5e5c2-117">Vous devrez peut-être régénérer une vue d'abonnement dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] pour répercuter les modifications dans les objets de modèle.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-117">You might need to regenerate a subscription view in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] to reflect changes to model objects.</span></span> <span data-ttu-id="5e5c2-118">La colonne **Modifié** dans la page **Exporter** est mise à jour avec la valeur **True** lorsque les objets modèle changent.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-118">The **Changed** column on the **Export** page is updated to **True** when model objects change.</span></span> <span data-ttu-id="5e5c2-119">**True** indique que vous devez modifier la vue d'abonnement et l'enregistrer pour régénérer la vue.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-119">**True** indicates that you should edit the subscription view and save it, which regenerates the view.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5e5c2-120">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="5e5c2-120">Related Tasks</span></span>  
  
|<span data-ttu-id="5e5c2-121">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="5e5c2-121">Task Description</span></span>|<span data-ttu-id="5e5c2-122">Rubrique</span><span class="sxs-lookup"><span data-stu-id="5e5c2-122">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="5e5c2-123">Créer une vue d'abonnement de vos données de référence.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-123">Create a subscription view of your master data.</span></span>|[<span data-ttu-id="5e5c2-124">Créer une vue d’abonnement &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5e5c2-124">Create a Subscription View &#40;Master Data Services&#41;</span></span>](create-a-subscription-view-to-export-data-master-data-services.md)|  
|<span data-ttu-id="5e5c2-125">Supprimer une vue d'abonnement existante.</span><span class="sxs-lookup"><span data-stu-id="5e5c2-125">Delete an existing subscription view.</span></span>|[<span data-ttu-id="5e5c2-126">Supprimer une vue d’abonnement &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5e5c2-126">Delete a Subscription View &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-subscription-view-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="5e5c2-127">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="5e5c2-127">Related Content</span></span>  
  
-   [<span data-ttu-id="5e5c2-128">Formats de vue d’abonnement &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5e5c2-128">Subscription View Formats &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/subscription-view-formats-master-data-services.md)  
  
-   [<span data-ttu-id="5e5c2-129">Views</span><span class="sxs-lookup"><span data-stu-id="5e5c2-129">Views</span></span>](../relational-databases/views/views.md)  
  
  
