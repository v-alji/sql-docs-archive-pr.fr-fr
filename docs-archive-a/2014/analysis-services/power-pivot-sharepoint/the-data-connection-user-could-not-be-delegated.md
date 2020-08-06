---
title: "La connexion de données utilise l'authentification Windows, et les informations d'identification utilisateur n'ont pas pu être déléguées. Échec de l’actualisation des connexions suivantes : données PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603698"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="5918c-103">La connexion de données utilise l'authentification Windows, et les informations d'identification utilisateur n'ont pas pu être déléguées.</span><span class="sxs-lookup"><span data-stu-id="5918c-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="5918c-104">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="5918c-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="5918c-105">Pour les classeurs Excel contenant des données PowerPivot, Excel Services retourne cette erreur s'il ne peut pas se connecter à une instance de serveur PowerPivot dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5918c-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5918c-106">Détails</span><span class="sxs-lookup"><span data-stu-id="5918c-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5918c-107">S’applique à</span><span class="sxs-lookup"><span data-stu-id="5918c-107">Applies to</span></span>|<span data-ttu-id="5918c-108">PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="5918c-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="5918c-109">Version du produit</span><span class="sxs-lookup"><span data-stu-id="5918c-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="5918c-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5918c-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="5918c-111">Cause</span><span class="sxs-lookup"><span data-stu-id="5918c-111">Cause</span></span>|<span data-ttu-id="5918c-112">Échec de connexion lors d'une tentative d'utilisation d'un fournisseur de données PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="5918c-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="5918c-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5918c-113">Message Text</span></span>|<span data-ttu-id="5918c-114">La connexion de données utilise l'authentification Windows, et les informations d'identification utilisateur n'ont pas pu être déléguées.</span><span class="sxs-lookup"><span data-stu-id="5918c-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="5918c-115">Échec de l'actualisation des connexions suivantes : Données PowerPivot</span><span class="sxs-lookup"><span data-stu-id="5918c-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5918c-116">Explication</span><span class="sxs-lookup"><span data-stu-id="5918c-116">Explanation</span></span>  
 <span data-ttu-id="5918c-117">Ce message d'erreur peut s'afficher pour plusieurs raisons.</span><span class="sxs-lookup"><span data-stu-id="5918c-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="5918c-118">Le facteur qu'ils ont en commun est qu'Excel Services ne peut pas obtenir une identité de l'utilisateur Windows valide à partir d'un jeton de revendications dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5918c-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="5918c-119">Dans le cas des classeurs Excel contenant des données PowerPivot, cette erreur se produit lorsque l'une des conditions suivantes est respectée :</span><span class="sxs-lookup"><span data-stu-id="5918c-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="5918c-120">Le service d'émission de jetons Revendications vers Windows n'est pas en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5918c-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="5918c-121">Vous pouvez vérifier la cause de cette erreur en consultant le fichier journal SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5918c-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="5918c-122">Si les journaux SharePoint incluent le message « Le point de terminaison du canal 'net.pipe://localhost/s 4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' est introuvable sur la machine locale », le service d'émission de jetons Revendications vers Windows n'est pas en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5918c-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="5918c-123">Pour le démarrer, utilisez l'Administration centrale, puis vérifiez que le service est en cours d'exécution dans l'application console Services.</span><span class="sxs-lookup"><span data-stu-id="5918c-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="5918c-124">Aucun contrôleur de domaine n'est disponible pour valider l'identité de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5918c-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="5918c-125">Le service d'émission de jetons Revendications vers Windows n'utilise pas des informations d'identification mises en cache.</span><span class="sxs-lookup"><span data-stu-id="5918c-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="5918c-126">Il valide l'identité de l'utilisateur pour chaque connexion.</span><span class="sxs-lookup"><span data-stu-id="5918c-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="5918c-127">Vous pouvez vérifier la cause de cette erreur en consultant le fichier journal SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5918c-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="5918c-128">Si les journaux SharePoint incluent le message « Échec de l'obtention de WindowsIdentity à partir de IClaimsIdentity », l'identité de l'utilisateur n'a pas pu être authentifiée.</span><span class="sxs-lookup"><span data-stu-id="5918c-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="5918c-129">Les ordinateurs doivent être membres du même domaine ou se trouver dans des domaines qui bénéficient dune relation d'approbation bidirectionnelle.</span><span class="sxs-lookup"><span data-stu-id="5918c-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="5918c-130">Vous devez utiliser des comptes d'utilisateur de domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="5918c-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="5918c-131">Les comptes doivent avoir un nom d'utilisateur principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="5918c-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="5918c-132">Le compte de service Excel Services doit disposer d'autorisations Active Directory pour interroger l'objet.</span><span class="sxs-lookup"><span data-stu-id="5918c-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5918c-133">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5918c-133">User Action</span></span>  
 <span data-ttu-id="5918c-134">Utilisez les instructions suivantes pour vérifier l'état du service d'émission de jetons Revendications vers Windows.</span><span class="sxs-lookup"><span data-stu-id="5918c-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="5918c-135">Pour tous les autres scénarios, contactez votre administrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="5918c-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="5918c-136">Activer le service d'émission de jetons Revendications vers Windows</span><span class="sxs-lookup"><span data-stu-id="5918c-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="5918c-137">Dans l’administration centrale, sous paramètres système, cliquez sur **gérer les services sur le serveur**.</span><span class="sxs-lookup"><span data-stu-id="5918c-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="5918c-138">Sélectionnez **Service d'émission de jetons Revendications vers Windows**, puis cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="5918c-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="5918c-139">Vérifiez que le service est également en cours d'exécution dans la console Services :</span><span class="sxs-lookup"><span data-stu-id="5918c-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="5918c-140">Dans Outils d'administration, cliquez sur Services.</span><span class="sxs-lookup"><span data-stu-id="5918c-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="5918c-141">Démarrez le service d'émission de jetons Revendications vers Windows s'il n'est pas en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="5918c-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5918c-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5918c-142">See Also</span></span>  
 [<span data-ttu-id="5918c-143">Configurer des comptes de service PowerPivot</span><span class="sxs-lookup"><span data-stu-id="5918c-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
