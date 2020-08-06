---
title: 'Leçon 3 : définition d’un abonnement piloté par les données | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710260"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="ab2f4-102">Leçon 3 : Définition d'un abonnement piloté par les données</span><span class="sxs-lookup"><span data-stu-id="ab2f4-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="ab2f4-103">Au cours de cette leçon, vous allez utiliser les pages d'abonnement piloté par les données pour vous connecter à une source de données d'abonnement, créer une requête qui extrait des données d'abonnement et mapper le jeu de résultats aux options de remise et de rapport.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab2f4-104">Avant de commencer, assurez-vous que le service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="ab2f4-105">Sans ce service, vous ne pouvez pas enregistrer l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="ab2f4-106">Cette leçon suppose que vous avez terminé les leçons 1 et 2, et que la source de données du rapport utilise des informations d'identification stockées.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="ab2f4-107">Pour plus d’informations, consultez [Leçon 2 : Modification des propriétés d’une source de données de rapport](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span><span class="sxs-lookup"><span data-stu-id="ab2f4-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="ab2f4-108">Dans cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="ab2f4-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="ab2f4-109">Démarrer l’Assistant abonnement piloté par les données</span><span class="sxs-lookup"><span data-stu-id="ab2f4-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="ab2f4-110">Étape 1 - Définir une description</span><span class="sxs-lookup"><span data-stu-id="ab2f4-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="ab2f4-111">Étape 2 - Définir une connexion à la source de données d'abonnement</span><span class="sxs-lookup"><span data-stu-id="ab2f4-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="ab2f4-112">Étape 3 - Définir une requête qui extrait les données des abonnés</span><span class="sxs-lookup"><span data-stu-id="ab2f4-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="ab2f4-113">Étape 4 - Définir des options de remise</span><span class="sxs-lookup"><span data-stu-id="ab2f4-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="ab2f4-114">Étape 5 - Configurer une valeur de paramètre pour modifier le résultat du rapport</span><span class="sxs-lookup"><span data-stu-id="ab2f4-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="ab2f4-115">Étape 6 - Pour planifier un abonnement</span><span class="sxs-lookup"><span data-stu-id="ab2f4-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="ab2f4-116">Démarrer l’Assistant abonnement piloté par les données</span><span class="sxs-lookup"><span data-stu-id="ab2f4-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="ab2f4-117">Dans le Gestionnaire de rapports, cliquez sur **Accueil**, puis naviguez jusqu'au dossier contenant le rapport **Sales Orders** .</span><span class="sxs-lookup"><span data-stu-id="ab2f4-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="ab2f4-118">Dans le menu contextuel du rapport, cliquez sur **Gérer**, puis sur l'onglet **Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="ab2f4-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="ab2f4-119">Cliquez sur **Nouvel abonnement piloté par les données**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="ab2f4-120">Si ce bouton n'apparaît pas, il se peut que vous n'ayez pas les autorisations relatives au Gestionnaire de contenu.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="ab2f4-121">Étape 1-définir une description</span><span class="sxs-lookup"><span data-stu-id="ab2f4-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="ab2f4-122">Tapez **Sales Order delivery** comme description.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="ab2f4-123">Sélectionnez **Partage de fichiers Windows** pour **Spécifiez le mode de notification des destinataires**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="ab2f4-124">Sélectionnez **Spécifier pour cet abonnement uniquement**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="ab2f4-125">Étape 2-définir une connexion à la source de données de l’abonné</span><span class="sxs-lookup"><span data-stu-id="ab2f4-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="ab2f4-126">Sélectionnez **Microsoft SQL Server** comme type de source de données.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="ab2f4-127">Dans Chaîne de connexion, tapez la chaîne de connexion suivante :</span><span class="sxs-lookup"><span data-stu-id="ab2f4-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab2f4-128">Les abonnés correspondent à la base de données que vous avez créée au cours de la leçon 1.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="ab2f4-129">Cliquez sur **Informations d'identification stockées en sécurité dans le serveur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="ab2f4-130">Dans les zones **Nom d'utilisateur** et **Mot de passe**, tapez le nom d'utilisateur et le mot de passe de votre domaine.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="ab2f4-131">Prenez en compte à la fois le domaine et le compte d'utilisateur au moment de définir le **Nom d'utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab2f4-132">Les informations d'identification utilisées pour la connexion à la source de données d'un abonné ne sont pas renvoyées à [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab2f4-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="ab2f4-133">Si vous modifiez l'abonnement ultérieurement, vous devrez retaper le mot de passe utilisé pour la connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="ab2f4-134">Sélectionnez l'option **Utiliser comme informations d'identification Windows lors de la connexion à la source de données**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="ab2f4-135">Étape 3-définir une requête pour récupérer les données de l’abonné</span><span class="sxs-lookup"><span data-stu-id="ab2f4-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="ab2f4-136">Dans la zone de requête, tapez la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="ab2f4-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="ab2f4-137">Spécifiez un délai d'expiration de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="ab2f4-138">Cliquez sur **Valider**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="ab2f4-139">Étape 4 : définir les options de remise</span><span class="sxs-lookup"><span data-stu-id="ab2f4-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="ab2f4-140">Pour **Nom de fichier**, sélectionnez **Obtenir la valeur de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="ab2f4-141">Sélectionnez le champ **Order**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="ab2f4-142">Pour **Chemin d'accès**, sélectionnez **Spécifier une valeur statique**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="ab2f4-143">Dans Valeur de paramètre, tapez le nom d'un partage de fichiers public pour lequel vous disposez d'autorisations en écriture (par exemple, `\\mycomputer\public\myreports`).</span><span class="sxs-lookup"><span data-stu-id="ab2f4-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="ab2f4-144">Pour **Format du rendu**, sélectionnez **Obtenir la valeur de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="ab2f4-145">Sélectionnez **format**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="ab2f4-146">Pour **Mode écriture**, sélectionnez **Spécifier une valeur statique** , puis **Autoincrément**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="ab2f4-147">Pour **Extension de fichier**, sélectionnez **Spécifier une valeur statique** , puis **True**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="ab2f4-148">Pour **Nom d'utilisateur**, sélectionnez **Spécifier une valeur statique**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="ab2f4-149">Tapez votre compte d'utilisateur de domaine</span><span class="sxs-lookup"><span data-stu-id="ab2f4-149">Type your domain user account.</span></span> <span data-ttu-id="ab2f4-150">Entrez-le au format suivant : `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="ab2f4-151">Le compte d'utilisateur a besoin d'autorisations sur le chemin d'accès que vous avez configuré dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="ab2f4-152">Pour **Mot de passe**, sélectionnez **Spécifier une valeur statique**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="ab2f4-153">Tapez votre mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-153">Type your password.</span></span> <span data-ttu-id="ab2f4-154">Tapez le mot de passe avec prudence.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="ab2f4-155">L'Assistant ne valide pas le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="ab2f4-156">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="ab2f4-157">Étape 5-configurer une valeur de paramètre pour une sortie de rapport très importante</span><span class="sxs-lookup"><span data-stu-id="ab2f4-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="ab2f4-158">Pour **OrderNumber**, sélectionnez **Obtenir la valeur de la base de données**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="ab2f4-159">Dans Valeur, sélectionnez **Ordre**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-159">In Value, select **Order**.</span></span> <span data-ttu-id="ab2f4-160">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="ab2f4-161">Étape 6-pour planifier un abonnement</span><span class="sxs-lookup"><span data-stu-id="ab2f4-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="ab2f4-162">Cliquez sur **Suivant une planification créée pour cet abonnement**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="ab2f4-163">Dans **Détails de la planification**, cliquez sur **Une fois**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="ab2f4-164">Spécifiez une heure de début quelques minutes avant l'heure actuelle.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="ab2f4-165">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ab2f4-166">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ab2f4-166">Next Steps</span></span>  
 <span data-ttu-id="ab2f4-167">Lors de l'exécution de l'abonnement, quatre fichiers de rapport sont remis au partage de fichiers que vous avez défini, un pour chaque commande dans la source de données *Abonnés* .</span><span class="sxs-lookup"><span data-stu-id="ab2f4-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="ab2f4-168">Chaque remise doit être unique en termes de données (les données doivent être propres à chaque commande), de format de rendu et de format de fichier.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="ab2f4-169">Vous pouvez ouvrir chaque rapport à partir du dossier partagé pour vérifier que chaque version est personnalisée en fonction des options d'abonnement que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="ab2f4-170">![Liste de fichiers créés par l'abonnement](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Liste de fichiers créés par l'abonnement")</span><span class="sxs-lookup"><span data-stu-id="ab2f4-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="ab2f4-171">La page des abonnements dans le Gestionnaire de rapports contiendra la date **Dernière exécution** et l' **État** de l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab2f4-172">Actualisez la page après l'exécution de l'abonnement pour consulter les informations mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ab2f4-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="ab2f4-173">![Résultats d'abonnement dans le Gestionnaire de rapports](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Résultats d'abonnement dans le Gestionnaire de rapports")</span><span class="sxs-lookup"><span data-stu-id="ab2f4-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="ab2f4-174">Cette étape est la dernière du didacticiel « Définition d'un abonnement piloté par les données ».</span><span class="sxs-lookup"><span data-stu-id="ab2f4-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="ab2f4-175">Pour en savoir plus sur les autres [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] didacticiels, consultez [didacticiels de Reporting Services &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ab2f4-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab2f4-176">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab2f4-176">See Also</span></span>  
 <span data-ttu-id="ab2f4-177">[Créer un abonnement piloté par les données &#40;didacticiel SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="ab2f4-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="ab2f4-178">[Abonnements et remise &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="ab2f4-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="ab2f4-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="ab2f4-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="ab2f4-180">[Créer, modifier et supprimer un abonnement piloté par les données](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="ab2f4-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="ab2f4-181">Utiliser une source de données externe pour les données des abonnés &#40;abonnements pilotés par les données&#41;</span><span class="sxs-lookup"><span data-stu-id="ab2f4-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
