---
title: Propriétés de l’alerte-nouvelle alerte (page général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705908"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="01603-102">Propriétés de l’alerte-nouvelle alerte (page général)</span><span class="sxs-lookup"><span data-stu-id="01603-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="01603-103">Utilisez cette page pour afficher et modifier les propriétés générales des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertes de l’agent.</span><span class="sxs-lookup"><span data-stu-id="01603-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01603-104">Options</span><span class="sxs-lookup"><span data-stu-id="01603-104">Options</span></span>  
 <span data-ttu-id="01603-105">**Nom**</span><span class="sxs-lookup"><span data-stu-id="01603-105">**Name**</span></span>  
 <span data-ttu-id="01603-106">Modifiez le nom de l'alerte.</span><span class="sxs-lookup"><span data-stu-id="01603-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="01603-107">**Activer**</span><span class="sxs-lookup"><span data-stu-id="01603-107">**Enable**</span></span>  
 <span data-ttu-id="01603-108">Active l'alerte.</span><span class="sxs-lookup"><span data-stu-id="01603-108">Enable the alert.</span></span> <span data-ttu-id="01603-109">Si l'alerte n'est pas activée, les actions spécifiées dans celle-ci n'ont pas lieu.</span><span class="sxs-lookup"><span data-stu-id="01603-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="01603-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="01603-110">**Type**</span></span>  
 <span data-ttu-id="01603-111">Sélectionnez le type d'alerte :</span><span class="sxs-lookup"><span data-stu-id="01603-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="01603-112">Une**alerte d'événement SQL Server** répond aux messages dans le journal des événements de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="01603-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="01603-113">Une**alerte de condition de performances SQL Server** répond à une condition spécifique liée à un compteur de performance.</span><span class="sxs-lookup"><span data-stu-id="01603-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="01603-114">Une**alerte d’événement WMI** répond à un événement WMI (Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="01603-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="01603-115">Options des alertes d'événement SQL Server</span><span class="sxs-lookup"><span data-stu-id="01603-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="01603-116">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="01603-116">**Database name**</span></span>  
 <span data-ttu-id="01603-117">Indiquez une base de données pour l’événement, ou sélectionnez **Toutes les bases de données** pour répondre à un message quelle que soit la base de données dans laquelle l’événement a lieu.</span><span class="sxs-lookup"><span data-stu-id="01603-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="01603-118">**Numéro d'erreur**</span><span class="sxs-lookup"><span data-stu-id="01603-118">**Error number**</span></span>  
 <span data-ttu-id="01603-119">Indique que cet événement répond à une erreur. Précisez le numéro de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="01603-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="01603-120">**Niveau de gravité**</span><span class="sxs-lookup"><span data-stu-id="01603-120">**Severity**</span></span>  
 <span data-ttu-id="01603-121">Indique que cet événement répond à un message quelconque d'un niveau de gravité spécifique. Précisez le niveau de gravité.</span><span class="sxs-lookup"><span data-stu-id="01603-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="01603-122">**Déclencher une alerte quand le message contient**</span><span class="sxs-lookup"><span data-stu-id="01603-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="01603-123">Filtre les événements d'après une chaîne spécifique.</span><span class="sxs-lookup"><span data-stu-id="01603-123">Filter events by a specific string.</span></span> <span data-ttu-id="01603-124">Si cette option est sélectionnée, l'alerte répond uniquement aux événements contenant cette chaîne.</span><span class="sxs-lookup"><span data-stu-id="01603-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="01603-125">**Texte du message**</span><span class="sxs-lookup"><span data-stu-id="01603-125">**Message text**</span></span>  
 <span data-ttu-id="01603-126">Spécifiez la chaîne à utiliser pour filtrer les événements.</span><span class="sxs-lookup"><span data-stu-id="01603-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="01603-127">Alertes de condition de performances de SQL Server</span><span class="sxs-lookup"><span data-stu-id="01603-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="01603-128">**Object**</span><span class="sxs-lookup"><span data-stu-id="01603-128">**Object**</span></span>  
 <span data-ttu-id="01603-129">Précisez l'objet de performance à surveiller.</span><span class="sxs-lookup"><span data-stu-id="01603-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="01603-130">**Compteur**</span><span class="sxs-lookup"><span data-stu-id="01603-130">**Counter**</span></span>  
 <span data-ttu-id="01603-131">Précisez le compteur à surveiller au sein de l'objet de performance.</span><span class="sxs-lookup"><span data-stu-id="01603-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="01603-132">**Instance**</span><span class="sxs-lookup"><span data-stu-id="01603-132">**Instance**</span></span>  
 <span data-ttu-id="01603-133">Indiquez l'instance du compteur à surveiller.</span><span class="sxs-lookup"><span data-stu-id="01603-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="01603-134">**Alerte si compteur**</span><span class="sxs-lookup"><span data-stu-id="01603-134">**Alert if counter**</span></span>  
 <span data-ttu-id="01603-135">Spécifiez le comportement du compteur auquel l'alerte répond.</span><span class="sxs-lookup"><span data-stu-id="01603-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="01603-136">Par exemple, vous pouvez faire en sorte que l’alerte réponde à une baisse de la valeur du compteur **Espace disponible dans tempdb (Ko)** en deçà d’une valeur spécifiée, ou à un dépassement d’une valeur spécifiée par la valeur du compteur **Compilations SQL/s** .</span><span class="sxs-lookup"><span data-stu-id="01603-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="01603-137">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="01603-137">**Value**</span></span>  
 <span data-ttu-id="01603-138">Spécifiez une valeur pour le compteur.</span><span class="sxs-lookup"><span data-stu-id="01603-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="01603-139">Options des alertes d'événement WMI</span><span class="sxs-lookup"><span data-stu-id="01603-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="01603-140">**Espace de noms**</span><span class="sxs-lookup"><span data-stu-id="01603-140">**Namespace**</span></span>  
 <span data-ttu-id="01603-141">Spécifiez l'espace de noms à utiliser pour l'instruction WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="01603-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="01603-142">Seuls les espaces de noms résidant sur l'ordinateur qui exécute [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="01603-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="01603-143">**Requête**</span><span class="sxs-lookup"><span data-stu-id="01603-143">**Query**</span></span>  
 <span data-ttu-id="01603-144">Spécifiez l'instruction WQL identifiant l'événement auquel l'alerte répond.</span><span class="sxs-lookup"><span data-stu-id="01603-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01603-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01603-145">See Also</span></span>  
 <span data-ttu-id="01603-146">[Alerts](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="01603-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="01603-147">[Utilisation de WQL avec le fournisseur WMI pour les événements de serveur](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="01603-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="01603-148">[Créer une alerte en utilisant un numéro d’erreur](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="01603-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="01603-149">Créer une alerte à l'aide d'un niveau de gravité</span><span class="sxs-lookup"><span data-stu-id="01603-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
