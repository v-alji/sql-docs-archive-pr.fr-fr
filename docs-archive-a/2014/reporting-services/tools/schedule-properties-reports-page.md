---
title: Propriétés de planification (page Rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603812"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="01a79-102">Propriétés de planification (page Rapports)</span><span class="sxs-lookup"><span data-stu-id="01a79-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="01a79-103">Utilisez cette page pour afficher la liste de tous les rapports qui utilisent cette planification partagée.</span><span class="sxs-lookup"><span data-stu-id="01a79-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="01a79-104">Les planifications peuvent être utilisées pour actualiser les instantanés de rapport, générer un historique de rapport, déclencher un abonnement ou faire expirer une copie mise en cache du rapport.</span><span class="sxs-lookup"><span data-stu-id="01a79-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="01a79-105">Pour savoir comment la planification est utilisée, consultez les informations sur les propriétés et les abonnements du rapport.</span><span class="sxs-lookup"><span data-stu-id="01a79-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="01a79-106">Bien que cette page affiche chaque rapport qui utilise la planification partagée, elle n'indique pas le nombre de fois où la planification partagée est utilisée dans cet unique rapport.</span><span class="sxs-lookup"><span data-stu-id="01a79-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="01a79-107">Par exemple, supposons que 20 abonnés différents au rapport des ventes de l'entreprise utilisent tous la même planification partagée pour déclencher le traitement des abonnements.</span><span class="sxs-lookup"><span data-stu-id="01a79-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="01a79-108">Dans ce cas, le rapport des ventes de l'entreprise apparaîtra seulement une fois dans cette liste, même s'il contient 20 références à la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="01a79-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="01a79-109">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à un serveur de rapports, ouvrez le dossier **Planifications partagées** , cliquez avec le bouton droit sur une planification partagée, sélectionnez **Propriétés**, puis cliquez sur **Rapports**.</span><span class="sxs-lookup"><span data-stu-id="01a79-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01a79-110">Cette fonctionnalité n'est pas disponible dans toutes les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="01a79-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="01a79-111">Pour obtenir la liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [fonctionnalités prises en charge par les éditions de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="01a79-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="01a79-112">Options</span><span class="sxs-lookup"><span data-stu-id="01a79-112">Options</span></span>  
 <span data-ttu-id="01a79-113">**Folder**</span><span class="sxs-lookup"><span data-stu-id="01a79-113">**Folder**</span></span>  
 <span data-ttu-id="01a79-114">Spécifie le chemin d'accès au rapport.</span><span class="sxs-lookup"><span data-stu-id="01a79-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="01a79-115">**Report**</span><span class="sxs-lookup"><span data-stu-id="01a79-115">**Report**</span></span>  
 <span data-ttu-id="01a79-116">Définit le nom du rapport qui utilise la planification.</span><span class="sxs-lookup"><span data-stu-id="01a79-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a79-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01a79-117">See Also</span></span>  
 <span data-ttu-id="01a79-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="01a79-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="01a79-119">[Planifications](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="01a79-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="01a79-120">[Serveur de rapports dans Management Studio aide (F1)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="01a79-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="01a79-121">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="01a79-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="01a79-122">Configurer les propriétés générales d’un rapport &#40;Gestionnaire de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="01a79-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
