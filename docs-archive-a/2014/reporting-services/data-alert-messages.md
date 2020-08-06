---
title: Messages d’alerte de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611604"
---
# <a name="data-alert-messages"></a><span data-ttu-id="cb1da-102">Messages d'alerte de données</span><span class="sxs-lookup"><span data-stu-id="cb1da-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="cb1da-103">Les alertes de données autorisent l’envoi de deux types de messages d’alerte de données par courrier électronique : les messages contenant les résultats de l’alerte de données et les messages sans description d’erreur.</span><span class="sxs-lookup"><span data-stu-id="cb1da-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="cb1da-104">Les messages contenant des résultats avisent tous les destinataires des modifications apportées aux données d'un rapport dignes d'intérêt et importantes pour les décisions économiques.</span><span class="sxs-lookup"><span data-stu-id="cb1da-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="cb1da-105">Si pour une raison quelconque une erreur se produit et les résultats ne sont pas disponibles, un message d'erreur est envoyé à la place.</span><span class="sxs-lookup"><span data-stu-id="cb1da-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="cb1da-106">Le propriétaire de la définition d'alerte de données peut également afficher des informations sur l'instance de l'alerte de données dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="cb1da-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="cb1da-107">Pour plus d’informations, consultez [Gestionnaire des alertes de données pour les utilisateurs SharePoint](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="cb1da-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="cb1da-108">Messages d’alerte de données</span><span class="sxs-lookup"><span data-stu-id="cb1da-108">Data Alert Messages</span></span>
 <span data-ttu-id="cb1da-109">Les images suivantes montrent un message d'alerte de données avec des résultats et un message d'alerte avec la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="cb1da-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="cb1da-110">**Message contenant les résultats**</span><span class="sxs-lookup"><span data-stu-id="cb1da-110">**Results message**</span></span>

 <span data-ttu-id="cb1da-111">![E-mail d’alerte de données avec les résultats](media/rs-alertmessageresults.gif "E-mail d’alerte de données avec les résultats")</span><span class="sxs-lookup"><span data-stu-id="cb1da-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="cb1da-112">**Message d’erreur**</span><span class="sxs-lookup"><span data-stu-id="cb1da-112">**Error message**</span></span>

 <span data-ttu-id="cb1da-113">![E-mail d’alerte de données avec un message d’erreur](media/rs-alertmessageerrror.gif "E-mail d’alerte de données avec un message d’erreur")</span><span class="sxs-lookup"><span data-stu-id="cb1da-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="cb1da-114">Les messages incluent les mêmes types d'informations.</span><span class="sxs-lookup"><span data-stu-id="cb1da-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="cb1da-115">**De la part de** indique le nom de la personne qui a créé la définition d’alerte de données.</span><span class="sxs-lookup"><span data-stu-id="cb1da-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="cb1da-116">Si vous avez fourni une description dans la définition d’alerte, elle s’affiche sous **De la part de**.</span><span class="sxs-lookup"><span data-stu-id="cb1da-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="cb1da-117">Les**Résultats d’alerte** affichent les lignes dans le flux de données du rapport qui correspondent aux règles spécifiées dans la définition de l’alerte, organisées dans un format tabulaire ; en cas d’erreur, une description est affichée.</span><span class="sxs-lookup"><span data-stu-id="cb1da-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="cb1da-118">Il n'existe aucune limite quant au nombre de lignes qui s'affiche.</span><span class="sxs-lookup"><span data-stu-id="cb1da-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="cb1da-119">**Atteindre le rapport** est un lien vers le rapport concerné par la définition de l’alerte.</span><span class="sxs-lookup"><span data-stu-id="cb1da-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="cb1da-120">Si le lien n'est pas valide car le rapport a été déplacé ou supprimé, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="cb1da-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="cb1da-121">Les informations sous**Règle(s)** répertorient les règles et les clauses dans la définition de l’alerte.</span><span class="sxs-lookup"><span data-stu-id="cb1da-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="cb1da-122">Ces informations vous permettent de vérifier et comprendre les résultats de l'alerte et d'identifier les règles dans la définition de l'alerte de données que vous pouvez modifier pour limiter ou élargir les résultats.</span><span class="sxs-lookup"><span data-stu-id="cb1da-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="cb1da-123">Les**Paramètres de rapport** présentent les paramètres et les valeurs de paramètres utilisés lors de l’exécution du rapport.</span><span class="sxs-lookup"><span data-stu-id="cb1da-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="cb1da-124">Les paramètres et les valeurs de paramètre vous aident à comprendre les résultats des alertes.</span><span class="sxs-lookup"><span data-stu-id="cb1da-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="cb1da-125">Les**Valeurs contextuelles** répertorient les noms et les valeurs des éléments du rapport qui sont en dehors des régions de données de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="cb1da-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="cb1da-126">Les éléments sont généralement des zones de texte.</span><span class="sxs-lookup"><span data-stu-id="cb1da-126">The items are typically text boxes.</span></span> <span data-ttu-id="cb1da-127">Par exemple, il peut s'agir d'une zone de texte avec une valeur constante telle que l'objet ou la description d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="cb1da-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="cb1da-128">La seule différence entre les deux types de messages est l’élément 5, **Résultats d’alerte**.</span><span class="sxs-lookup"><span data-stu-id="cb1da-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="cb1da-129">Si une erreur se produit quand une instance d’alerte de données ou un message d’alerte de données est créé, l’élément **Résultats d’alerte** affiche un message d’erreur qui décrit le problème.</span><span class="sxs-lookup"><span data-stu-id="cb1da-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="cb1da-130">Le message d'erreur, envoyé à tous les destinataires, les informe que les résultats de l'alerte qu'ils attendent et sur lesquels ils s'appuient pour prendre des décisions ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="cb1da-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="cb1da-131">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="cb1da-131">Related Tasks</span></span>
 <span data-ttu-id="cb1da-132">Cette section répertorie les procédures de création et de modification des définitions d'alerte de données qui fournissent la plupart des informations sur les éléments affichés dans les messages d'alerte de données.</span><span class="sxs-lookup"><span data-stu-id="cb1da-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="cb1da-133">Créer une alerte de données dans le concepteur d’alertes de données</span><span class="sxs-lookup"><span data-stu-id="cb1da-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="cb1da-134">Modifier une alerte de données dans le concepteur d'alertes</span><span class="sxs-lookup"><span data-stu-id="cb1da-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="cb1da-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb1da-135">See Also</span></span>
 <span data-ttu-id="cb1da-136">[Concepteur](../../2014/reporting-services/data-alert-designer.md) d’alertes de données [Reporting Services des alertes de données](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cb1da-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


