---
title: Guide pratique pour afficher les propriétés d’une instance CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701508"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="a9a04-102">Procédure : afficher les propriétés d'une instance de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="a9a04-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="a9a04-103">Cette procédure décrit comment utiliser la console du concepteur CDC pour afficher des informations sur les instances que vous créez afin d'aider à gérer le fonctionnement des instances.</span><span class="sxs-lookup"><span data-stu-id="a9a04-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="a9a04-104">Pour afficher des informations sur une instance spécifique</span><span class="sxs-lookup"><span data-stu-id="a9a04-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="a9a04-105">Dans le menu **Démarrer** , sélectionnez **Console du concepteur de capture de données modifiées**.</span><span class="sxs-lookup"><span data-stu-id="a9a04-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="a9a04-106">Dans le volet gauche, développez **Capture de données modifiées** , puis le service qui contient l'instance que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="a9a04-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="a9a04-107">Sélectionnez le nom de l'instance à utiliser.</span><span class="sxs-lookup"><span data-stu-id="a9a04-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="a9a04-108">Les informations sur l'instance s'affichent dans la partie centrale de la console du concepteur de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a9a04-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="a9a04-109">Elles sont réparties en quatre onglets.</span><span class="sxs-lookup"><span data-stu-id="a9a04-109">It is divided into four tabs.</span></span> <span data-ttu-id="a9a04-110">Tous les onglets sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a9a04-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="a9a04-111">**État**</span><span class="sxs-lookup"><span data-stu-id="a9a04-111">**Status**</span></span>  
     <span data-ttu-id="a9a04-112">Cet onglet présente des informations sur l'état actuel de la capture de données modifiées pour l'instance.</span><span class="sxs-lookup"><span data-stu-id="a9a04-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="a9a04-113">Pour plus d'informations sur ce qui est affiché dans cet onglet, consultez la section **Onglets de la visionneuse** dans [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="a9a04-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="a9a04-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="a9a04-114">**Oracle**</span></span>  
     <span data-ttu-id="a9a04-115">Cet onglet affiche des informations générales sur l'instance de capture de données modifiées et la base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="a9a04-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="a9a04-116">Pour plus d'informations sur ce qui est affiché dans cet onglet, consultez [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a9a04-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="a9a04-117">**Tables**</span><span class="sxs-lookup"><span data-stu-id="a9a04-117">**Tables**</span></span>  
     <span data-ttu-id="a9a04-118">Cet onglet affiche des informations sur les tables incluses dans la capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="a9a04-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="a9a04-119">Il répertorie également les colonnes qui sont capturées.</span><span class="sxs-lookup"><span data-stu-id="a9a04-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="a9a04-120">Pour plus d'informations sur ce qui est affiché dans cet onglet, consultez [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a9a04-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="a9a04-121">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="a9a04-121">**Advanced**</span></span>  
     <span data-ttu-id="a9a04-122">Cet onglet contient une liste de propriétés avancées que vous définissez dans l'éditeur de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a9a04-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="a9a04-123">Pour plus d'informations sur ce qui est affiché dans cet onglet, consultez [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a9a04-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
