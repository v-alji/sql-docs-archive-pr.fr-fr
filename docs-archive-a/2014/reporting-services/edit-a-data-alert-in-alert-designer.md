---
title: Modifier une alerte de données dans le Concepteur d’alertes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- editing, data alerts
- updating, data alerts
- editing, alerts
- updating, alerts
ms.assetid: dde3664d-90b5-4b12-969e-39152c86e58a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9906b33ae50d51733eaec1bf5c201c9f5b5d120e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703903"
---
# <a name="edit-a-data-alert-in-alert-designer"></a><span data-ttu-id="461db-102">Modifier une alerte de données dans le Concepteur d'alertes</span><span class="sxs-lookup"><span data-stu-id="461db-102">Edit a Data Alert in Alert Designer</span></span>
  <span data-ttu-id="461db-103">Vous ouvrez la définition d'alerte de données que vous souhaitez modifier dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="461db-103">You open the data alert definition that you want to edit from Data Alert Manager.</span></span> <span data-ttu-id="461db-104">Uniquement l'utilisateur qui a créé la définition d'alerte peut la modifier.</span><span class="sxs-lookup"><span data-stu-id="461db-104">Only the user that created the alert definition can edit it.</span></span> <span data-ttu-id="461db-105">Pour plus d’informations sur l’ouverture du Gestionnaire des alertes de données, consultez [Gérer mes alertes de données dans le Gestionnaire des alertes de données](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="461db-105">For more information about opening Data Alert Manager, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

 <span data-ttu-id="461db-106">L'image suivante montre le menu contextuel d'une alerte de données dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="461db-106">The following picture shows you the context menu on a data alert in Data Alert Manager.</span></span>

 <span data-ttu-id="461db-107">![Ouvrir le Concepteur d'alertes de données en cliquant sur Modifier](media/rs-alertmanageriwopendesigner.gif "Ouvrir le Concepteur d'alertes de données en cliquant sur Modifier")</span><span class="sxs-lookup"><span data-stu-id="461db-107">![Open Data Alert Designer by clicking Edit](media/rs-alertmanageriwopendesigner.gif "Open Data Alert Designer by clicking Edit")</span></span>

 <span data-ttu-id="461db-108">La procédure suivante décrit les étapes pour ouvrir la définition d'alerte et la modifier dans le Concepteur d'alertes de données du Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="461db-108">The following procedure includes the steps to open the alert definition for editing in Data Alert Designer from Data Alert Manager.</span></span>

### <a name="to-edit-a-data-alert-definition-in-data-alert-designer"></a><span data-ttu-id="461db-109">Pour modifier une définition d'alerte de données dans le Concepteur d'alertes de données</span><span class="sxs-lookup"><span data-stu-id="461db-109">To edit a data alert definition in Data Alert Designer</span></span>

1.  <span data-ttu-id="461db-110">Dans le Gestionnaire des alertes de données, cliquez avec le bouton droit sur la définition d’alerte de données à modifier, puis cliquez sur l’option **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="461db-110">In Data Alert Manager, right-click the data alert definition that you want to edit and click **Edit**.</span></span>

     <span data-ttu-id="461db-111">La définition de l'alerte s'ouvre dans le Concepteur d'alertes de données.</span><span class="sxs-lookup"><span data-stu-id="461db-111">The alert definition opens in Data Alert Designer.</span></span>

2.  <span data-ttu-id="461db-112">Mettez à jour les règles, les paramètres de planification et les paramètres de courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="461db-112">Update the rules, schedule settings, and email settings.</span></span> <span data-ttu-id="461db-113">Pour plus d’informations, consultez [Concepteur d’alertes de données](../../2014/reporting-services/data-alert-designer.md) et [Créer une alerte de données dans le Concepteur d’alertes](create-a-data-alert-in-data-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="461db-113">For more information, see [Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) and [Create a Data Alert in Data Alert Designer](create-a-data-alert-in-data-alert-designer.md).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="461db-114">Vous ne pouvez pas choisir un flux de données différent.</span><span class="sxs-lookup"><span data-stu-id="461db-114">You cannot choose a different data feed.</span></span> <span data-ttu-id="461db-115">Si vous souhaitez utiliser un flux de données différent, vous devez créer une nouvelle définition d'alerte de données.</span><span class="sxs-lookup"><span data-stu-id="461db-115">To use a different data feed, you must create a new data alert definition.</span></span>

3.  <span data-ttu-id="461db-116">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="461db-116">Click **Save**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="461db-117">Si le rapport a changé et les flux de données générés à partir du rapport ont changé, la définition d'alerte peut ne plus être valide.</span><span class="sxs-lookup"><span data-stu-id="461db-117">If the report has changed and the data feeds generated from the report have changed the alert definition might no longer be valid.</span></span> <span data-ttu-id="461db-118">Ceci se produit lorsqu'une colonne référencée par la définition d'alerte dans ses règles est supprimée du rapport, si le type de ses données change, ou encore, si le rapport est supprimé ou déplacé.</span><span class="sxs-lookup"><span data-stu-id="461db-118">This occurs when a column that the alert definition references in its rules is deleted from the report or changes data type or the report is deleted or moved.</span></span> <span data-ttu-id="461db-119">Vous pouvez ouvrir une définition d'alerte non valide, mais vous ne pouvez pas l'enregistrer tant qu'elle n'est pas compatible avec la version actuelle du flux de données du rapport sur lequel elle repose.</span><span class="sxs-lookup"><span data-stu-id="461db-119">You can open an alert definition that is not valid, but you cannot resave it until it is valid based on the current version of the report data feed that it is built upon.</span></span> <span data-ttu-id="461db-120">Pour en savoir plus sur la façon dont les flux de données sont générés à partir des rapports, consultez [Génération de flux de données à partir de rapports &#40;Générateur de rapports et SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="461db-120">To learn more about how data feeds are generated from reports, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="461db-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="461db-121">See Also</span></span>
 <span data-ttu-id="461db-122">[Gestionnaire des alertes de données pour les administrateurs d’alertes Reporting Services les alertes de](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [données](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="461db-122">[Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


