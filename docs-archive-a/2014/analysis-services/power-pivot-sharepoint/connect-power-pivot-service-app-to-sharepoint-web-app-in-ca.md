---
title: Connecter une application de service PowerPivot à une application Web SharePoint dans l’administration centrale | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612541"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="6548f-102">Connecter une application de service PowerPivot à une application Web SharePoint dans l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="6548f-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="6548f-103">Une application de service PowerPivot peut être utilisée par les applications Web SharePoint de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="6548f-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="6548f-104">Pour rendre une application de service PowerPivot disponible, vous devez l'ajouter à une liste d'association de services.</span><span class="sxs-lookup"><span data-stu-id="6548f-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6548f-105">Vous devez disposer d'une application de service PowerPivot dans le groupe par défaut pour garantir que le tableau de bord de gestion PowerPivot fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="6548f-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="6548f-106">N'ajoutez pas plusieurs applications de service PowerPivot au groupe par défaut.</span><span class="sxs-lookup"><span data-stu-id="6548f-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="6548f-107">L'ajout de plusieurs entrées du même type d'application de service n'est pas une configuration prise en charge et risque de provoquer des erreurs.</span><span class="sxs-lookup"><span data-stu-id="6548f-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="6548f-108">Si vous créez des applications de service supplémentaires, ajoutez-les aux listes personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6548f-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="6548f-109">Cette rubrique contient les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="6548f-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="6548f-110">Ajouter une application de service PowerPivot au groupe par défaut</span><span class="sxs-lookup"><span data-stu-id="6548f-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="6548f-111">Ajouter une application de service PowerPivot à une liste d'association de services personnalisée</span><span class="sxs-lookup"><span data-stu-id="6548f-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="6548f-112">Ajouter une application de services PowerPivot au groupe par défaut</span><span class="sxs-lookup"><span data-stu-id="6548f-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="6548f-113">Une liste d'association de services est une liste de services partagés qui fournissent des ressources à d'autres applications Web SharePoint de la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="6548f-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="6548f-114">Il existe un groupe par défaut d'association de services pour la batterie de serveurs.</span><span class="sxs-lookup"><span data-stu-id="6548f-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="6548f-115">Pour faire figurer une application de service PowerPivot dans la liste, vous pouvez l'ajouter, soit lorsque vous créez l'application, soit ultérieurement en effectuant la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="6548f-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="6548f-116">Dans Administration centrale, dans **Gestion des applications**, cliquez sur **Configurer les paramètres d'application de service**.</span><span class="sxs-lookup"><span data-stu-id="6548f-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="6548f-117">Dans Groupe de proxy d'application, cliquez sur **valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="6548f-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="6548f-118">Activez la case à cocher en regard de l'application de service PowerPivot (signalée par la valeur `PowerPivot Service Application Proxy` pour le nom de type).</span><span class="sxs-lookup"><span data-stu-id="6548f-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="6548f-119">Si vous disposez de plusieurs applications de service PowerPivot, choisissez-en une seule.</span><span class="sxs-lookup"><span data-stu-id="6548f-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="6548f-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6548f-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="6548f-121">Ajouter une application de services PowerPivot à une liste d’association de services personnalisée</span><span class="sxs-lookup"><span data-stu-id="6548f-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="6548f-122">Le groupe par défaut peut être remplacé par une liste personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6548f-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="6548f-123">Une liste personnalisée est créée spécifiquement pour une application Web SharePoint précise.</span><span class="sxs-lookup"><span data-stu-id="6548f-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="6548f-124">Elle remplace le groupe par défaut par les associations de services spécifiées par un administrateur de batterie de serveurs ou de service.</span><span class="sxs-lookup"><span data-stu-id="6548f-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="6548f-125">Si vous avez créé plusieurs applications de service PowerPivot, vous devez utiliser une liste personnalisée pour spécifier l'application à utiliser.</span><span class="sxs-lookup"><span data-stu-id="6548f-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="6548f-126">Une liste personnalisée ne peut pas être réutilisée par d'autres applications Web.</span><span class="sxs-lookup"><span data-stu-id="6548f-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="6548f-127">Elle s'applique uniquement à l'application Web pour laquelle elle a été créée.</span><span class="sxs-lookup"><span data-stu-id="6548f-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="6548f-128">Dans Administration Centrale, sous **Gestion des applications**, cliquez sur **Gérer les applications Web**.</span><span class="sxs-lookup"><span data-stu-id="6548f-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="6548f-129">Sélectionnez l'application (par exemple, SharePoint -80).</span><span class="sxs-lookup"><span data-stu-id="6548f-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="6548f-130">Dans Applications Web, dans Gérer, cliquez sur **Connexions aux services**.</span><span class="sxs-lookup"><span data-stu-id="6548f-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="6548f-131">Dans **Modifier le groupe suivant de connexions**, sélectionnez **[personnalisé]**.</span><span class="sxs-lookup"><span data-stu-id="6548f-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="6548f-132">Activez la case à cocher en regard de chaque connexion d'application de service que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="6548f-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="6548f-133">Si vous disposez de plusieurs applications de service PowerPivot (signalées par la valeur `PowerPivot Service Application Proxy` pour Type), veillez à n'en choisir qu'une seule.</span><span class="sxs-lookup"><span data-stu-id="6548f-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="6548f-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6548f-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6548f-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6548f-135">See Also</span></span>  
 <span data-ttu-id="6548f-136">[Créer et configurer une application de service PowerPivot dans l’administration centrale](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="6548f-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="6548f-137">Configuration initiale &#40;PowerPivot pour SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="6548f-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
