---
title: Gérer toutes les alertes de données sur un site SharePoint dans le Gestionnaire des alertes de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: 9c70b0f4-2db8-4c2e-acbf-96e2a55ddc48
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b41fdbd18a0b1b4a7a69a3ca202de1c555c070de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704955"
---
# <a name="manage-all-data-alerts-on-a-sharepoint-site-in-data-alert-manager"></a><span data-ttu-id="7866c-102">Gérer toutes les alertes de données sur un site SharePoint dans le Gestionnaire des alertes de données</span><span class="sxs-lookup"><span data-stu-id="7866c-102">Manage All Data Alerts on a SharePoint Site in Data Alert Manager</span></span>
  <span data-ttu-id="7866c-103">Les administrateurs d'alertes SharePoint peuvent consulter la liste des alertes de données que tous les utilisateurs du site ont créées et les informations sur les alertes.</span><span class="sxs-lookup"><span data-stu-id="7866c-103">SharePoint alerting administrators can view a list of the data alerts that were created by any site user and information about the alerts.</span></span> <span data-ttu-id="7866c-104">Ils peuvent également supprimer des alertes.</span><span class="sxs-lookup"><span data-stu-id="7866c-104">Alerting administrators can also delete alerts.</span></span> <span data-ttu-id="7866c-105">L'illustration suivante montre les fonctionnalités disponibles aux administrateurs d'alertes dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="7866c-105">The following picture shows the features available to alerting administrators in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="7866c-106">![Gestionnaire d'alertes pour les administrateurs du site SharePoint](media/rs-alertmanagersite.gif "Gestionnaire d'alertes pour les administrateurs du site SharePoint")</span><span class="sxs-lookup"><span data-stu-id="7866c-106">![Alert Manager for SharePoin tsite administrators](media/rs-alertmanagersite.gif "Alert Manager for SharePoin tsite administrators")</span></span>  
  
### <a name="to-view-a-list-of-alerts-created-by-a-site-user"></a><span data-ttu-id="7866c-107">Pour consulter la liste des alertes créées par un utilisateur du site</span><span class="sxs-lookup"><span data-stu-id="7866c-107">To view a list of alerts created by a site user</span></span>  
  
1.  <span data-ttu-id="7866c-108">Accédez au site SharePoint où les définitions d'alertes de données sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="7866c-108">Go to the SharePoint site where data alerts definitions are saved.</span></span>  
  
2.  <span data-ttu-id="7866c-109">Dans la page d’accueil, cliquez sur **Actions de site**.</span><span class="sxs-lookup"><span data-stu-id="7866c-109">On the Home page, click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="7866c-110">Faites défiler jusqu’au fond de la liste et cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="7866c-110">Scroll to the bottom of the list and click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="7866c-111">Sous **Reporting Services**cliquez sur **Gérer les alertes de données**.</span><span class="sxs-lookup"><span data-stu-id="7866c-111">Under **Reporting Services**, click **Manage Data Alerts**.</span></span>  
  
5.  <span data-ttu-id="7866c-112">Cliquez sur la flèche vers le bas dans la liste **Afficher les alertes pour l’utilisateur** et sélectionnez l’utilisateur dont vous souhaitez afficher les alertes.</span><span class="sxs-lookup"><span data-stu-id="7866c-112">Click the down arrow by the **View alerts for user** list and select the user whose alerts you want to view.</span></span>  
  
6.  <span data-ttu-id="7866c-113">Cliquez sur la flèche vers le bas en regard de la liste **Afficher les alertes pour le rapport** et sélectionnez une alerte spécifique ou cliquez sur **Afficher tout** pour répertorier toutes les alertes créées par l’utilisateur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="7866c-113">Click the down arrow next to the **View alerts for report** list and select a specific alert to view, or click **Show All** to list all alerts created by the selected user.</span></span>  
  
     <span data-ttu-id="7866c-114">Une table répertorie le nom de l'alerte, le nom du rapport, le nom de la personne qui a créé l'alerte de données, le nombre de fois que l'alerte de données a été envoyée, la dernière fois que la définition d'alerte de données a été modifiée et l'état de l'alerte de données.</span><span class="sxs-lookup"><span data-stu-id="7866c-114">A table lists the name, report name, name of the person who created the data alert, the number times the data alert was sent, the last time the data alert definition was modified, and the status of the data alert.</span></span> <span data-ttu-id="7866c-115">Si l'alerte de données ne peut pas être générée ou envoyée, la colonne d'état contient des informations sur l'erreur et vous aide à dépanner le problème.</span><span class="sxs-lookup"><span data-stu-id="7866c-115">If the data alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="7866c-116">Pour supprimer une définition d'alerte</span><span class="sxs-lookup"><span data-stu-id="7866c-116">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="7866c-117">Cliquez avec le bouton droit sur l’alerte de données à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="7866c-117">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7866c-118">Une fois que vous avez supprimé l’alerte, aucun message d’alerte n’est envoyé.</span><span class="sxs-lookup"><span data-stu-id="7866c-118">After you delete the alert, no further alert messages are sent.</span></span> <span data-ttu-id="7866c-119">Toutefois, si vous interrogez la base de données des alertes, vous constaterez que la définition d'alerte existe encore.</span><span class="sxs-lookup"><span data-stu-id="7866c-119">However, if you query the alerting database you might find that the alert definition still exists.</span></span> <span data-ttu-id="7866c-120">Le service d'alertes effectue un nettoyage planifié qui supprimera définitivement la définition d'alerte lors du nettoyage suivant.</span><span class="sxs-lookup"><span data-stu-id="7866c-120">The alerting service performs clean up on a schedule and the alert definition is deleted permanently in the next cleanup.</span></span> <span data-ttu-id="7866c-121">L'intervalle de nettoyage par défaut est de 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="7866c-121">The default cleanup interval is 20 minutes.</span></span> <span data-ttu-id="7866c-122">Cet intervalle, ainsi que d'autres paramètres de nettoyage, sont configurables.</span><span class="sxs-lookup"><span data-stu-id="7866c-122">This and other cleanup intervals are configurable.</span></span> <span data-ttu-id="7866c-123">Pour plus d’informations, consultez [Alertes de données Reporting Services](../ssms/agent/alerts.md).</span><span class="sxs-lookup"><span data-stu-id="7866c-123">For more information, see [Reporting Services Data Alerts](../ssms/agent/alerts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7866c-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7866c-124">See Also</span></span>  
 <span data-ttu-id="7866c-125">[Gestionnaire des alertes de données pour les administrateurs d’alertes](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="7866c-125">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="7866c-126">Alertes de données Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7866c-126">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
