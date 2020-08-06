---
title: Précharger le cache (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700799"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="1db2f-102">préchargement du cache (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="1db2f-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="1db2f-103">Vous pouvez précharger le cache pour un dataset partagé en créant un plan d'actualisation du cache pour le dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="1db2f-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="1db2f-104">Vous pouvez précharger le cache pour un rapport de deux façons :</span><span class="sxs-lookup"><span data-stu-id="1db2f-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="1db2f-105">Créer un plan d'actualisation du cache pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="1db2f-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="1db2f-106">Ceci est la méthode privilégiée.</span><span class="sxs-lookup"><span data-stu-id="1db2f-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="1db2f-107">Utilisez l'abonnement piloté par les données pour précharger des instances de rapports paramétrables dans le cache.</span><span class="sxs-lookup"><span data-stu-id="1db2f-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="1db2f-108">Cette méthode était la seule permettant de précharger le cache dans les versions de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] antérieures à [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1db2f-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="1db2f-109">Pour plus d’informations, consultez [Mise en cache de rapports &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1db2f-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="1db2f-110">Les conditions suivantes doivent être réunies avant de pouvoir mettre en cache un rapport ou un dataset partagé :</span><span class="sxs-lookup"><span data-stu-id="1db2f-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="1db2f-111">La mise en cache doit être activée pour le dataset partagé ou le rapport.</span><span class="sxs-lookup"><span data-stu-id="1db2f-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="1db2f-112">Les sources de données partagées pour le dataset partagé ou le rapport doivent être configurées pour utiliser des informations d'identification stockées ou aucune information d'identification.</span><span class="sxs-lookup"><span data-stu-id="1db2f-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="1db2f-113">Le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit être en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="1db2f-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="1db2f-114">Pour précharger le cache en créant un plan d'actualisation du cache</span><span class="sxs-lookup"><span data-stu-id="1db2f-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="1db2f-115">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1db2f-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="1db2f-116">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis à l’élément que vous voulez mettre en cache.</span><span class="sxs-lookup"><span data-stu-id="1db2f-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="1db2f-117">Pointez sur l’élément, cliquez sur la liste déroulante, puis cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="1db2f-118">Cliquez sur l’onglet **Options d’actualisation du cache** .</span><span class="sxs-lookup"><span data-stu-id="1db2f-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="1db2f-119">Dans la barre d’outils, cliquez sur **Nouveau plan d’actualisation du cache**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1db2f-120">Si la mise en cache n'est pas activée pour l'élément, vous serez invité à l'activer.</span><span class="sxs-lookup"><span data-stu-id="1db2f-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="1db2f-121">Pour activer la mise en cache, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="1db2f-122">La page Plan d'actualisation du cache s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="1db2f-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="1db2f-123">Tapez éventuellement une description pour le plan d'actualisation.</span><span class="sxs-lookup"><span data-stu-id="1db2f-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="1db2f-124">Pour une planification partagée, cliquez sur **Planification partagée**, puis sélectionnez le nom de la planification à utiliser.</span><span class="sxs-lookup"><span data-stu-id="1db2f-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="1db2f-125">Pour une planification personnalisée, cliquez sur **Planification spécifique aux éléments**, puis cliquez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="1db2f-126">Configurer la planification</span><span class="sxs-lookup"><span data-stu-id="1db2f-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="1db2f-127">Pour précharger le cache avec un rapport spécifique à l'utilisateur en utilisant un abonnement piloté par les données</span><span class="sxs-lookup"><span data-stu-id="1db2f-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="1db2f-128">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1db2f-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="1db2f-129">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis au rapport pour lequel vous voulez créer un abonnement.</span><span class="sxs-lookup"><span data-stu-id="1db2f-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="1db2f-130">Cliquez successivement sur le rapport, sur l’onglet **Abonnements** , puis sur **Nouvel abonnement piloté par les données**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="1db2f-131">Tapez éventuellement une description pour l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="1db2f-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="1db2f-132">Dans la liste **Spécifiez le mode de notification des destinataires** , sélectionnez **Fournisseur de remise Null**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="1db2f-133">Spécifiez un type de source de données, puis cliquez sur **Suivant** pour configurer la source de données.</span><span class="sxs-lookup"><span data-stu-id="1db2f-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="1db2f-134">Spécifiez le type de connexion, la chaîne de connexion et les informations d'identification pour accéder à la source de données contenant les données des abonnés.</span><span class="sxs-lookup"><span data-stu-id="1db2f-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="1db2f-135">L'exemple suivant illustre une chaîne de connexion à la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appelée Subscribers :</span><span class="sxs-lookup"><span data-stu-id="1db2f-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="1db2f-136">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="1db2f-137">Spécifiez la requête ou la commande qui permet de récupérer les données des abonnés.</span><span class="sxs-lookup"><span data-stu-id="1db2f-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="1db2f-138">Augmentez éventuellement le délai d'attente des requêtes dont le traitement est long.</span><span class="sxs-lookup"><span data-stu-id="1db2f-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="1db2f-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1db2f-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="1db2f-140">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-140">Click **Validate**.</span></span> <span data-ttu-id="1db2f-141">La requête doit être validée pour pouvoir continuer.</span><span class="sxs-lookup"><span data-stu-id="1db2f-141">The query must be validated before you continue.</span></span> <span data-ttu-id="1db2f-142">Quand le message **Réussite de la validation de la requête** s’affiche, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="1db2f-143">Les paramètres d’extension de remise n’étant pas configurables pour le fournisseur de remise Null, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="1db2f-144">Spécifiez les valeurs des paramètres du rapport pour l’abonnement, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="1db2f-145">Précisez le moment où l'abonnement doit être traité.</span><span class="sxs-lookup"><span data-stu-id="1db2f-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="1db2f-146">Ne choisissez pas l’option **Lorsque les données du rapport sont mises à jour sur le serveur de rapports**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="1db2f-147">Elle est réservée exclusivement aux instantanés.</span><span class="sxs-lookup"><span data-stu-id="1db2f-147">That setting is for snapshots only.</span></span> <span data-ttu-id="1db2f-148">Si vous voulez utiliser une planification préexistante, sélectionnez **Suivant une planification partagée**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="1db2f-149">Ou, pour créer une planification personnalisée, cliquez sur **Suivant une planification créée pour cet abonnement** , puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="1db2f-150">Configurez la planification, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1db2f-151">Pour que les abonnés reçoivent la version du rapport la plus récente, la planification que vous configurez doit être chronologiquement cohérente par rapport à la planification de la remise du rapport que vous avez définie pour les abonnés.</span><span class="sxs-lookup"><span data-stu-id="1db2f-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="1db2f-152">Pour plus d’informations, consultez [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1db2f-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="1db2f-153">Configurez les options d'exécution du rapport comme suit.</span><span class="sxs-lookup"><span data-stu-id="1db2f-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="1db2f-154">Dans la page du rapport, cliquez sur l’onglet **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="1db2f-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="1db2f-155">Dans le cadre de gauche, cliquez sur l’onglet **Exécution** .</span><span class="sxs-lookup"><span data-stu-id="1db2f-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="1db2f-156">Dans la page qui s’affiche, sélectionnez **Effectuer le rendu de ce rapport avec les données les plus récentes**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="1db2f-157">Choisissez l'une des deux options de mise en cache suivantes et configurez l'expiration comme suit :</span><span class="sxs-lookup"><span data-stu-id="1db2f-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="1db2f-158">Pour effectuer l'expiration d'une copie mise en cache après l'écoulement d'une durée particulière, cliquez sur **Mettre en cache une copie temporaire du rapport. Faire expirer la copie du rapport après un certain nombre de minutes.**</span><span class="sxs-lookup"><span data-stu-id="1db2f-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="1db2f-159">Tapez le nombre de minutes pour l'expiration du rapport.</span><span class="sxs-lookup"><span data-stu-id="1db2f-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="1db2f-160">Pour définir l’expiration d’une copie mise en cache selon une planification, cliquez sur **Mettre en cache une copie temporaire du rapport. Faire expirer la copie du rapport selon la planification suivante.**</span><span class="sxs-lookup"><span data-stu-id="1db2f-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="1db2f-161">Cliquez sur **Configurer**ou sélectionnez une planification partagée pour définir l’expiration du rapport.</span><span class="sxs-lookup"><span data-stu-id="1db2f-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="1db2f-162">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="1db2f-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db2f-163">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1db2f-163">See Also</span></span>  
 <span data-ttu-id="1db2f-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="1db2f-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="1db2f-165">[Créer un abonnement piloté par les données &#40;didacticiel SSRS&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="1db2f-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="1db2f-166">[Performances, instantanés, mise en cache &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1db2f-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="1db2f-167">[Définir les propriétés de traitement d’un rapport](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1db2f-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="1db2f-168">Mise en cache de rapports &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1db2f-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
