---
title: Autres manières d’obtenir une connexion de données (Générateur de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601993"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="e969b-102">Autres manières d'obtenir une connexion de données (Générateur de rapports)</span><span class="sxs-lookup"><span data-stu-id="e969b-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="e969b-103">Une connexion de données contient les informations nécessaires pour se connecter à une source de données externe telle qu'une base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e969b-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="e969b-104">En règle générale, vous obtenez les informations de connexion et le type d'informations d'identification à utiliser auprès du propriétaire de la source de données.</span><span class="sxs-lookup"><span data-stu-id="e969b-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="e969b-105">Pour spécifier une connexion de données, vous pouvez utiliser une source de données partagée sur le serveur de rapports ou créer une source de données incorporée utilisée uniquement dans un rapport spécifique.</span><span class="sxs-lookup"><span data-stu-id="e969b-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="e969b-106">Dans la plupart des didacticiels, vous utilisez des sources de données incorporées, mais si vous avez accès à des sources de données partagées, vous pouvez les utiliser à la place.</span><span class="sxs-lookup"><span data-stu-id="e969b-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="e969b-107">Obtention d'une connexion de données à partir d'une source de données partagée</span><span class="sxs-lookup"><span data-stu-id="e969b-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="e969b-108">Si le serveur de rapports dispose d'une source de données partagée pour laquelle vous avez des autorisations d'accès, vous pouvez l'utiliser à la place d'une source de données incorporée.</span><span class="sxs-lookup"><span data-stu-id="e969b-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="e969b-109">Les procédures suivantes montrent comment localiser les sources de données partagées et fournir les informations d'identification nécessaires à leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="e969b-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="e969b-110">Pour utiliser une source de données partagée, vous devez accéder à un serveur de rapports afin de la sélectionner.</span><span class="sxs-lookup"><span data-stu-id="e969b-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="e969b-111">En règle générale, vous obtenez l'URL du serveur de rapports auprès de l'administrateur du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e969b-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="e969b-112">Pour spécifier une connexion de données à partir d'une liste de sources de données partagées</span><span class="sxs-lookup"><span data-stu-id="e969b-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="e969b-113">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e969b-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="e969b-114">La page **Choisir une connexion à une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="e969b-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="e969b-115">Dans la liste des sources de données, sélectionnez une source de données pour laquelle vous disposez d'autorisations d'accès.</span><span class="sxs-lookup"><span data-stu-id="e969b-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="e969b-116">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="e969b-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="e969b-117">Le message « La connexion a été correctement créée » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e969b-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="e969b-118">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e969b-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="e969b-119">Si nécessaire, entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="e969b-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="e969b-120">Pour enregistrer les informations d’identification localement, sélectionnez **Enregistrer le mot de passe avec la connexion**.</span><span class="sxs-lookup"><span data-stu-id="e969b-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="e969b-121">Si vous ne sélectionnez pas cette option, vous êtes invité à indiquer vos informations d'identification chaque fois que vous exécutez le rapport.</span><span class="sxs-lookup"><span data-stu-id="e969b-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="e969b-122">Pour spécifier une connexion de données en accédant à une source de données partagée sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="e969b-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="e969b-123">Dans la page **Choisir un dataset** , sélectionnez **Créer un dataset**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e969b-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="e969b-124">La page **Choisir une connexion à une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="e969b-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="e969b-125">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="e969b-125">Click **Browse**.</span></span> <span data-ttu-id="e969b-126">La boîte de dialogue **Sélectionner une source de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="e969b-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e969b-127">Dans la liste déroulante **Regarder dans** , sélectionnez **Sites et serveurs récents**.</span><span class="sxs-lookup"><span data-stu-id="e969b-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="e969b-128">Dans le volet de source de données, cliquez sur l’URL de votre serveur, puis sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e969b-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="e969b-129">La liste des sources de données ou modèles s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e969b-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="e969b-130">Vous pouvez aussi taper l’URL du serveur de rapports dans la zone **Nom**.</span><span class="sxs-lookup"><span data-stu-id="e969b-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="e969b-131">Cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e969b-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="e969b-132">Le Générateur de rapports se connecte au serveur de rapports, puis charge les sources de données disponibles au niveau du dossier racine.</span><span class="sxs-lookup"><span data-stu-id="e969b-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="e969b-133">Naviguez jusqu’à un dossier qui contient une source de données pour laquelle vous disposez d’autorisations suffisantes pour vous y connecter, sélectionnez la source de données, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="e969b-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="e969b-134">Vous revenez à la page **Choisir une connexion à une source de données** .</span><span class="sxs-lookup"><span data-stu-id="e969b-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="e969b-135">Pour vous assurer que vous pouvez vous connecter à la source de données, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="e969b-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="e969b-136">Le message « La connexion a été correctement créée » s'affiche.</span><span class="sxs-lookup"><span data-stu-id="e969b-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="e969b-137">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e969b-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="e969b-138">Si vous êtes invité à entrer un nom d'utilisateur et un mot de passe, entrez vos informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="e969b-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="e969b-139">Pour enregistrer les informations d’identification localement, sélectionnez **Enregistrer le mot de passe avec la connexion**.</span><span class="sxs-lookup"><span data-stu-id="e969b-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e969b-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e969b-140">See Also</span></span>  
 <span data-ttu-id="e969b-141">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e969b-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="e969b-142">Didacticiels &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="e969b-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
