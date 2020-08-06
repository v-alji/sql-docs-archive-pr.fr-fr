---
title: Gérer mes alertes de données dans le Gestionnaire des alertes de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- managing, alerts
- managing, data alerts
ms.assetid: e0e4ffdf-bd4c-4ebd-872b-07486cbb47c2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 371c62c2f97334e20280a659c8039ab20852ccfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704956"
---
# <a name="manage-my-data-alerts-in-data-alert-manager"></a><span data-ttu-id="8366f-102">Gérer mes alertes de données dans le Gestionnaire des alertes de données</span><span class="sxs-lookup"><span data-stu-id="8366f-102">Manage My Data Alerts in Data Alert Manager</span></span>
  <span data-ttu-id="8366f-103">Les utilisateurs SharePoint peuvent consulter la liste des alertes de données qu'ils ont créées et les informations sur les alertes.</span><span class="sxs-lookup"><span data-stu-id="8366f-103">SharePoint users can view a list of the data alerts that they created and information about the alerts.</span></span> <span data-ttu-id="8366f-104">Ils peuvent également supprimer leurs alertes, ouvrir les définitions d'alerte pour les modifier dans le Concepteur d'alertes de données et les exécuter.</span><span class="sxs-lookup"><span data-stu-id="8366f-104">Users can also delete their alerts, open alert definitions for edit in Data Alert Designer, and run their alerts.</span></span> <span data-ttu-id="8366f-105">L'image suivante affiche les fonctionnalités disponibles aux utilisateurs dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="8366f-105">The following picture shows the features available to users in Data Alert Manager.</span></span>  
  
 <span data-ttu-id="8366f-106">![Fonctionnalités du Gestionnaire d'alertes pour les utilisateurs SharePoint](media/rs-alertmanageriw.gif "Fonctionnalités du Gestionnaire d'alertes pour les utilisateurs SharePoint")</span><span class="sxs-lookup"><span data-stu-id="8366f-106">![Alert Manager features for SharePoint users](media/rs-alertmanageriw.gif "Alert Manager features for SharePoint users")</span></span>  
  
### <a name="to-view-a-list-of-your-alerts"></a><span data-ttu-id="8366f-107">Pour consulter la liste de vos alertes</span><span class="sxs-lookup"><span data-stu-id="8366f-107">To view a list of your alerts</span></span>  
  
1.  <span data-ttu-id="8366f-108">Accédez à la bibliothèque SharePoint où vous avez enregistré les rapports sur lesquels vous avez créé des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="8366f-108">Go to the SharePoint library where you saved the reports on which you created data alerts.</span></span>  
  
2.  <span data-ttu-id="8366f-109">Cliquez sur l’icône pour développer le menu déroulant sur un rapport et cliquez sur **Gérer les alertes de données**.</span><span class="sxs-lookup"><span data-stu-id="8366f-109">Click the icon for the expand drop-down menu on a report and click **Manage Data Alerts**.</span></span> <span data-ttu-id="8366f-110">L'image suivante montre le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="8366f-110">The following picture shows the drop-down menu.</span></span>  
  
     <span data-ttu-id="8366f-111">![Ouvrir le Gestionnaire d'alertes à partir du menu contextuel du rapport](media/rs-openalertmanager.gif "Ouvrir le Gestionnaire d'alertes à partir du menu contextuel du rapport")</span><span class="sxs-lookup"><span data-stu-id="8366f-111">![Open Alert Manager from report context menu](media/rs-openalertmanager.gif "Open Alert Manager from report context menu")</span></span>  
  
     <span data-ttu-id="8366f-112">Le Gestionnaire des alertes de données s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="8366f-112">Data Alert Manager opens.</span></span> <span data-ttu-id="8366f-113">Par défaut, il répertorie les alertes du rapport que vous avez sélectionné dans la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="8366f-113">By default, it lists the alerts for the report that you selected in the library.</span></span>  
  
3.  <span data-ttu-id="8366f-114">Cliquez sur la flèche vers le bas en regard de la liste **Afficher les alertes pour le rapport** et sélectionnez un rapport pour consulter ses alertes, ou cliquez sur **Afficher tout** pour répertorier toutes les alertes.</span><span class="sxs-lookup"><span data-stu-id="8366f-114">Click the down arrow next to the **View alerts for report** list and select a report to view its alerts, or click **Show All** to list all alerts.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8366f-115">Si le rapport que vous avez sélectionné n'a aucune alerte, il n'est pas nécessaire de revenir à la bibliothèque SharePoint pour rechercher et sélectionner un rapport contenant des alertes.</span><span class="sxs-lookup"><span data-stu-id="8366f-115">If the report that you selected does not have any alerts, you do not have to return to the SharePoint library to locate and select a report that hasalerts.</span></span> <span data-ttu-id="8366f-116">Au lieu de cela, cliquez sur **Afficher tout** pour afficher la liste de toutes les alertes.</span><span class="sxs-lookup"><span data-stu-id="8366f-116">Instead, click **Show All** to see a list of all your alerts.</span></span>  
  
     <span data-ttu-id="8366f-117">Une table répertorie le nom de l'alerte, le nom du rapport, votre nom en tant que créateur de l'alerte, le nombre d'instances d'alerte envoyées, la dernière fois que la définition d'alerte a été modifiée et l'état de l'alerte.</span><span class="sxs-lookup"><span data-stu-id="8366f-117">A table lists the alert name, report name, your name as the creator of the alert, the number the alert was sent, the last time the alert definition was modified, and the status of the alert.</span></span> <span data-ttu-id="8366f-118">Si l'alerte ne peut pas être générée ou envoyée, la colonne d'état contient des informations sur l'erreur et vous aide à dépanner le problème.</span><span class="sxs-lookup"><span data-stu-id="8366f-118">If the alert cannot be generated or sent, the status column contains information about the error and helps you troubleshoot the problem.</span></span>  
  
### <a name="to-edit-an-alert-definition"></a><span data-ttu-id="8366f-119">Pour modifier une définition d'alerte</span><span class="sxs-lookup"><span data-stu-id="8366f-119">To edit an alert definition</span></span>  
  
-   <span data-ttu-id="8366f-120">Cliquez avec le bouton droit sur l’alerte de données que vous souhaitez modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="8366f-120">Right-click the data alert for which you want to edit the alert definition and click **Edit**.</span></span>  
  
     <span data-ttu-id="8366f-121">La définition de l'alerte s'ouvre dans le Concepteur d'alertes de données.</span><span class="sxs-lookup"><span data-stu-id="8366f-121">The alert definition opens in Data Alert Designer.</span></span> <span data-ttu-id="8366f-122">Pour plus d’informations, consultez [Modifier une alerte de données dans le Concepteur d’alertes](edit-a-data-alert-in-alert-designer.md) et [Concepteur d’alertes de données](../../2014/reporting-services/data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8366f-122">For more information, see [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md) and [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8366f-123">Uniquement l'utilisateur qui a créé la définition d'alerte de données peut la modifier.</span><span class="sxs-lookup"><span data-stu-id="8366f-123">Only the user that created the data alert definition can edit it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8366f-124">Si le rapport a changé et les flux de données générés à partir du rapport ont changé, la définition d'alerte peut ne plus être valide.</span><span class="sxs-lookup"><span data-stu-id="8366f-124">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="8366f-125">Cela se produit lorsqu'une colonne référencée par l'alerte dans ses règles est supprimée du rapport, change de type de données ou est incluse dans un flux de données différent, ou lorsque le rapport est supprimé ou déplacé.</span><span class="sxs-lookup"><span data-stu-id="8366f-125">This occurs when a column that the alert references in its rules is deleted from the report, changes data type, or is included in a different data feed or the report is deleted or moved.</span></span> <span data-ttu-id="8366f-126">Vous pouvez ouvrir une définition d'alerte non valide, mais vous ne pouvez pas l'enregistrer tant qu'elle n'est pas compatible avec la version actuelle du flux de données du rapport sur lequel elle repose.</span><span class="sxs-lookup"><span data-stu-id="8366f-126">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="8366f-127">Pour en savoir plus sur la façon dont les flux de données sont générés à partir des rapports, consultez [Génération de flux de données à partir de rapports &#40;Générateur de rapports et SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8366f-127">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-delete-an-alert-definition"></a><span data-ttu-id="8366f-128">Pour supprimer une définition d'alerte</span><span class="sxs-lookup"><span data-stu-id="8366f-128">To delete an alert definition</span></span>  
  
-   <span data-ttu-id="8366f-129">Cliquez avec le bouton droit sur l’alerte de données à supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8366f-129">Right-click the data alert that you want to delete and click **Delete**.</span></span>  
  
     <span data-ttu-id="8366f-130">Lorsque vous supprimez l'alerte, aucun message d'alerte n'est envoyé par la suite.</span><span class="sxs-lookup"><span data-stu-id="8366f-130">When you delete the alert, no further alert messages are sent.</span></span>  
  
### <a name="to-run-an-alert"></a><span data-ttu-id="8366f-131">Pour exécuter une alerte</span><span class="sxs-lookup"><span data-stu-id="8366f-131">To run an alert</span></span>  
  
-   <span data-ttu-id="8366f-132">Cliquez avec le bouton droit sur l’alerte de données à exécuter, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8366f-132">Right-click the data alert that you want to run and click **Run**.</span></span>  
  
     <span data-ttu-id="8366f-133">L'instance d'alerte est créée et le message d'alerte de données est immédiatement envoyé, quelles que soient les options de planification spécifiées dans le concepteur d'alertes de données.</span><span class="sxs-lookup"><span data-stu-id="8366f-133">The alert instance is created and the data alert message is immediately sent, regardless of the schedule options you specified in Data Alert Designer.</span></span> <span data-ttu-id="8366f-134">Par exemple, une alerte configurée pour s'exécuter toutes les semaines est envoyée par la suite uniquement si les résultats changent.</span><span class="sxs-lookup"><span data-stu-id="8366f-134">For example, an alert configured to be sent weekly and then only if the results change is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8366f-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8366f-135">See Also</span></span>  
 <span data-ttu-id="8366f-136">[Gestionnaire des alertes de données pour les administrateurs d’alertes](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span><span class="sxs-lookup"><span data-stu-id="8366f-136">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) </span></span>  
 [<span data-ttu-id="8366f-137">Alertes de données Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8366f-137">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
