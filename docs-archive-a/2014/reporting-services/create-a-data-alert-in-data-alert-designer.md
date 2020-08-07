---
title: Créer une alerte de données dans le Concepteur d’alertes de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703955"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="576d7-102">Créer une alerte de données dans le Concepteur d’alertes</span><span class="sxs-lookup"><span data-stu-id="576d7-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="576d7-103">Vous pouvez créer les définitions d'alerte de données dans le Concepteur d'alertes de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="576d7-104">Après les avoir enregistrées, vous pouvez les rouvrir, les modifier, puis les enregistrer de nouveau dans le Concepteur d'alertes de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="576d7-105">Pour plus d’informations sur la modification des définitions d’alerte, consultez [Gérer mes alertes de données dans le Gestionnaire des alertes de données](manage-my-data-alerts-in-data-alert-manager.md) et [Modifier une alerte de données dans le Concepteur d’alertes](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="576d7-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="576d7-106">Pour créer une définition d'alerte de données</span><span class="sxs-lookup"><span data-stu-id="576d7-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="576d7-107">Localisez la bibliothèque SharePoint qui contient le rapport pour lequel vous souhaitez créer une définition d'alerte de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="576d7-108">Cliquez sur le rapport.</span><span class="sxs-lookup"><span data-stu-id="576d7-108">Click the report.</span></span>

     <span data-ttu-id="576d7-109">Le rapport est exécuté.</span><span class="sxs-lookup"><span data-stu-id="576d7-109">The report runs.</span></span> <span data-ttu-id="576d7-110">Si le rapport est paramétré, vérifiez qu'il affiche les données au sujet desquelles vous souhaitez recevoir des messages d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="576d7-111">Si vous ne voyez pas les colonnes ou les valeurs qui vous intéressent, vous pouvez exécuter de nouveau le rapport en utilisant des valeurs de paramètre différentes.</span><span class="sxs-lookup"><span data-stu-id="576d7-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="576d7-112">Les valeurs de paramètre choisies pour exécuter le rapport sont enregistrées dans la définition d'alerte et seront utilisées lorsque le rapport sera exécuté une nouvelle fois dans le cadre d'une étape de traitement de la définition d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="576d7-113">Pour utiliser des valeurs de paramètre différentes, vous devez créer une nouvelle définition d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="576d7-114">Dans le menu **Actions** , cliquez sur **Nouvelle alerte de données**.</span><span class="sxs-lookup"><span data-stu-id="576d7-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="576d7-115">L’image suivante affiche le menu **Actions** .</span><span class="sxs-lookup"><span data-stu-id="576d7-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="576d7-116">![Ouvrir le Concepteur d'alertes à partir de la bibliothèque SharePoint](media/rs-openalertdesigneriw.gif "Ouvrir le Concepteur d'alertes à partir de la bibliothèque SharePoint")</span><span class="sxs-lookup"><span data-stu-id="576d7-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="576d7-117">Le Concepteur d'alertes de données s'ouvre et affiche les 100 premières lignes du premier flux de données que le rapport génère dans une table.</span><span class="sxs-lookup"><span data-stu-id="576d7-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="576d7-118">Si vous ne voyez pas l’option **Nouvelle alerte de données** , le service d’alerte n’est pas configuré sur le site SharePoint ou l’édition d’ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] n’inclut pas les alertes de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="576d7-119">Pour plus d’informations, consultez [Services Reporting Services SharePoint et applications de service](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="576d7-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="576d7-120">Si l’option **Nouvelle alerte de données** est grisée, la source de données du rapport est configurée pour utiliser les informations d’identification de sécurité intégrée ou pour demander les informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="576d7-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="576d7-121">Pour rendre l’option **Nouvelle alerte de données** disponible, vous devez mettre à jour la source de données afin d’utiliser les informations d’identification stockées ou aucune information d’identification.</span><span class="sxs-lookup"><span data-stu-id="576d7-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="576d7-122">Le nom du flux de données s’affiche dans la liste déroulante **Nom des données du rapport** .</span><span class="sxs-lookup"><span data-stu-id="576d7-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="576d7-123">Éventuellement, sélectionnez un flux de données différent dans la liste déroulante **Nom des données du rapport** .</span><span class="sxs-lookup"><span data-stu-id="576d7-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="576d7-124">Si aucun flux de données n'est généré à partir du rapport, vous ne pouvez pas créer de définition d'alerte pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="576d7-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="576d7-125">La mise en page du rapport détermine le contenu de chaque flux de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="576d7-126">Pour plus d’informations, consultez [Génération de flux de données à partir de rapports &#40;Générateur de rapports et SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="576d7-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="576d7-127">Éventuellement, dans la zone de texte **Nom de l’alerte** , modifiez le nom par défaut pour qu’il soit plus explicite.</span><span class="sxs-lookup"><span data-stu-id="576d7-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="576d7-128">Le nom par défaut de la définition d'alerte est le nom du rapport.</span><span class="sxs-lookup"><span data-stu-id="576d7-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="576d7-129">Les noms des définitions d'alerte ne sont pas nécessairement uniques ; par conséquent, ils peuvent être difficiles à distinguer lorsque vous consulterez ultérieurement la liste de vos alertes dans le Gestionnaire des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="576d7-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="576d7-130">Il est recommandé d'utiliser des noms explicites et uniques pour vos définitions d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="576d7-131">Éventuellement, modifiez l’option des données par défaut en remplaçant l’option **toutes les données dans le flux de données ont** par l’option **aucune donnée dans le flux de données n’a**.</span><span class="sxs-lookup"><span data-stu-id="576d7-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="576d7-132">Cliquez sur **Ajouter une règle**.</span><span class="sxs-lookup"><span data-stu-id="576d7-132">Click **Add rule**.</span></span>

     <span data-ttu-id="576d7-133">La liste des colonnes dans le flux de données s'affiche.</span><span class="sxs-lookup"><span data-stu-id="576d7-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="576d7-134">Dans la liste, sélectionnez la colonne que vous souhaitez utiliser dans la règle, puis sélectionnez un opérateur de comparaison et entrez la valeur de seuil.</span><span class="sxs-lookup"><span data-stu-id="576d7-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="576d7-135">Selon le type de données de la colonne sélectionnée, des opérateurs de comparaison différents apparaissent.</span><span class="sxs-lookup"><span data-stu-id="576d7-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="576d7-136">Si la colonne a un type de données « date », l'icône du calendrier s'affiche en regard de la valeur de seuil pour la règle.</span><span class="sxs-lookup"><span data-stu-id="576d7-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="576d7-137">Vous pouvez entrer des données en cliquant sur une date dans le calendrier ou en tapant la date.</span><span class="sxs-lookup"><span data-stu-id="576d7-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="576d7-138">Le Concepteur d’alertes de données fournit deux modes de comparaison : **Mode de saisie de valeur** et **Mode de sélection de champ**.</span><span class="sxs-lookup"><span data-stu-id="576d7-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="576d7-139">Le mode par défaut est **Mode de saisie de valeur**.</span><span class="sxs-lookup"><span data-stu-id="576d7-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="576d7-140">Vous pouvez ajouter des clauses OR uniquement quand vous travaillez en **Mode de saisie de valeur** et vous utilisez la comparaison **is** .</span><span class="sxs-lookup"><span data-stu-id="576d7-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="576d7-141">Pour ajouter une clause OR, cliquez sur la flèche vers le bas, puis sur **Mode de saisie de valeur**.</span><span class="sxs-lookup"><span data-stu-id="576d7-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="576d7-142">Tapez la valeur de comparaison.</span><span class="sxs-lookup"><span data-stu-id="576d7-142">Type the comparison value.</span></span>

11. <span data-ttu-id="576d7-143">Vous pouvez éventuellement cliquer à nouveau sur le bouton de sélection **(...)**.</span><span class="sxs-lookup"><span data-stu-id="576d7-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="576d7-144">Les points de suspension **(...)** apparaissent sur la ligne qui contient la première clause.</span><span class="sxs-lookup"><span data-stu-id="576d7-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="576d7-145">La clause OR est ajoutée au-dessous et dans la règle AND.</span><span class="sxs-lookup"><span data-stu-id="576d7-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="576d7-146">Éventuellement, cliquez sur la flèche vers le bas, sélectionnez **Mode de sélection de champ**, puis sélectionnez une colonne dans la liste.</span><span class="sxs-lookup"><span data-stu-id="576d7-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="576d7-147">Vous remarquerez que les points de suspension **(...)** qui vous permettent d’ajouter des clauses OR ont disparu.</span><span class="sxs-lookup"><span data-stu-id="576d7-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="576d7-148">Éventuellement, recliquez sur **Ajouter une règle** pour ajouter des règles supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="576d7-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="576d7-149">Les règles sont combinées par l'opérateur logique AND.</span><span class="sxs-lookup"><span data-stu-id="576d7-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="576d7-150">Sélectionnez une option dans la liste de périodicité.</span><span class="sxs-lookup"><span data-stu-id="576d7-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="576d7-151">Selon le type de périodicité, entrez un intervalle.</span><span class="sxs-lookup"><span data-stu-id="576d7-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="576d7-152">Éventuellement, cliquez sur **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="576d7-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="576d7-153">Éventuellement, modifiez la date de début du message d'alerte en tapant une date différente ou en ouvrant le calendrier et en cliquant sur une date.</span><span class="sxs-lookup"><span data-stu-id="576d7-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="576d7-154">La date de début par défaut est la date courante.</span><span class="sxs-lookup"><span data-stu-id="576d7-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="576d7-155">Éventuellement, cochez la case située en regard de **Arrêter l’alerte le**, puis choisissez une date pour arrêter le message d’alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="576d7-156">Par défaut, un message d'alerte n'a pas de date d'arrêt.</span><span class="sxs-lookup"><span data-stu-id="576d7-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="576d7-157">L'arrêt d'un message d'alerte ne supprime pas la définition d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="576d7-158">Une fois que vous avez arrêté un message d'alerte, vous pouvez le redémarrer en mettant à jour les dates de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="576d7-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="576d7-159">Pour plus d’informations sur la suppression des définitions d’alerte, consultez [Gérer mes alertes de données dans le Gestionnaire des alertes de données](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="576d7-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="576d7-160">Éventuellement, décochez la case **Envoyer un message seulement si les résultats changent** .</span><span class="sxs-lookup"><span data-stu-id="576d7-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="576d7-161">Si vous paramétrez fréquemment des messages d'alerte, les informations redondantes peuvent être agaçantes ; dans ce cas, ne désactivez pas cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="576d7-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="576d7-162">Entrez les adresses de messagerie des destinataires du message d'alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="576d7-163">Séparez les adresses par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="576d7-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="576d7-164">Si l’adresse e-mail de la personne qui a créé la définition d’alerte est disponible, elle est ajouté à la zone **Destinataire** .</span><span class="sxs-lookup"><span data-stu-id="576d7-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="576d7-165">Éventuellement, dans la zone de texte **Objet** , mettez à jour la ligne Objet du message d’alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="576d7-166">L’objet par défaut est \*\*alerte de \<data alert name> données pour \*\*.</span><span class="sxs-lookup"><span data-stu-id="576d7-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="576d7-167">Éventuellement, dans la zone de texte **Description** , tapez une description pour le message d’alerte.</span><span class="sxs-lookup"><span data-stu-id="576d7-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="576d7-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="576d7-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="576d7-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="576d7-169">See Also</span></span>
 <span data-ttu-id="576d7-170">[Concepteur](../../2014/reporting-services/data-alert-designer.md) [d’alertes de données Gestionnaire des alertes de données pour les administrateurs d’alertes Reporting Services les alertes de](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [données](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="576d7-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


