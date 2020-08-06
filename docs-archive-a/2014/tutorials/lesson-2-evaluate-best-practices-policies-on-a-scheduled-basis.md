---
title: 'Leçon 2 : évaluer les stratégies des meilleures pratiques sur une base planifiée | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603173"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="c6baa-102">Leçon 2 : évaluer les stratégies des bonnes pratiques de façon planifiée</span><span class="sxs-lookup"><span data-stu-id="c6baa-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="c6baa-103">Vous pouvez configurer des évaluations planifiées des stratégies des meilleures pratiques sur une ou plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6baa-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c6baa-104">Pour configurer l'exécution des stratégies des meilleures pratiques de façon planifiée, vous devez importer les stratégies dans l'instance cible.</span><span class="sxs-lookup"><span data-stu-id="c6baa-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="c6baa-105">Pour déployer les stratégies planifiées vers plusieurs serveurs, vous pouvez importer les stratégies vers une instance, configurer les planifications pour chaque stratégie, exporter les stratégies planifiées vers un dossier, puis les déployer vers des instances cibles via des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="c6baa-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6baa-106">Les instances cibles doivent exécuter [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c6baa-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="c6baa-107">L'automation requiert que les stratégies soient stockées localement sur l'instance, ce qui n'est pas pris en charge par les versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui sont antérieures à [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6baa-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="c6baa-108">Dans cette leçon, vous effectuerez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6baa-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="c6baa-109">Importer les stratégies des meilleures pratiques dans une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6baa-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="c6baa-110">Configurer l'exécution des stratégies selon une planification.</span><span class="sxs-lookup"><span data-stu-id="c6baa-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="c6baa-111">Déployer les stratégies des meilleures pratiques planifiées sur plusieurs instances via des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="c6baa-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="c6baa-112">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6baa-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="c6baa-113">Importer les stratégies vers une instance unique</span><span class="sxs-lookup"><span data-stu-id="c6baa-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="c6baa-114">Planifier les stratégies</span><span class="sxs-lookup"><span data-stu-id="c6baa-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="c6baa-115">Déployer des stratégies planifiées sur plusieurs instances</span><span class="sxs-lookup"><span data-stu-id="c6baa-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6baa-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6baa-116">See Also</span></span>  
 [<span data-ttu-id="c6baa-117">Administrer plusieurs serveurs à l’aide de serveurs de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="c6baa-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
