---
title: Sécuriser une application web Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706575"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="7d757-102">Sécuriser une application Web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="7d757-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="7d757-103">Vous pouvez sécuriser l'application Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] avec HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7d757-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d757-104">L'application Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] peut utiliser HTTP ou HTTPS, mais pas les deux.</span><span class="sxs-lookup"><span data-stu-id="7d757-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7d757-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="7d757-105">Prerequisites</span></span>  
 <span data-ttu-id="7d757-106">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="7d757-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="7d757-107">Vous devez être administrateur du serveur Web sur lequel [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="7d757-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="7d757-108">MDS doivent être installé sur le serveur Web, et une application Web doit exister.</span><span class="sxs-lookup"><span data-stu-id="7d757-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="7d757-109">Pour plus d’informations, consultez [Installer Master Data Services](install-master-data-services.md) et [Créer une application Web Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="7d757-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="7d757-110">Pour sécuriser l'application Web Master Data Manager avec HTTPS</span><span class="sxs-lookup"><span data-stu-id="7d757-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="7d757-111">Après avoir vérifié que l'application Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] est configurée correctement avec HTTP, créez un certificat dans IIS.</span><span class="sxs-lookup"><span data-stu-id="7d757-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="7d757-112">Pour plus d'informations, consultez [Configuration des certificats de serveur dans IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d757-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="7d757-113">Dans le volet **Connexions** , sous **Sites**, cliquez sur le site qui héberge l'application Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d757-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="7d757-114">Dans le volet **Actions**, cliquez sur **Liaisons**.</span><span class="sxs-lookup"><span data-stu-id="7d757-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="7d757-115">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="7d757-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="7d757-116">Dans la liste, sélectionnez **https**.</span><span class="sxs-lookup"><span data-stu-id="7d757-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="7d757-117">Sélectionnez le certificat SSL.</span><span class="sxs-lookup"><span data-stu-id="7d757-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="7d757-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d757-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="7d757-119">facultatif.</span><span class="sxs-lookup"><span data-stu-id="7d757-119">Optional.</span></span> <span data-ttu-id="7d757-120">Pour supprimer HTTP afin que les utilisateurs puissent accéder au site avec HTTPS uniquement, dans la liste, cliquez sur la ligne avec **http**.</span><span class="sxs-lookup"><span data-stu-id="7d757-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="7d757-121">Cliquez sur **Supprimer** et dans la boîte de dialogue de confirmation, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="7d757-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7d757-122">Vous devez changer les configurations basicHttp et wsHttpBinding après avoir supprimé HTTP.</span><span class="sxs-lookup"><span data-stu-id="7d757-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="7d757-123">Pour fermer la boîte de dialogue **Liaisons de sites** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="7d757-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="7d757-124">Ouvrez maintenant le fichier web.config sous *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span><span class="sxs-lookup"><span data-stu-id="7d757-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="7d757-125">Recherchez la chaîne `<security mode="Message">` et modifiez-la en `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="7d757-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="7d757-126">Enregistrez et fermez le fichier.</span><span class="sxs-lookup"><span data-stu-id="7d757-126">Save and close the file.</span></span> <span data-ttu-id="7d757-127">Si vous obtenez une erreur, cela peut être dû au fait que vous avez activé le contrôle de compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7d757-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="7d757-128">Pour plus d'informations, consultez le [Guide pas à pas du contrôle de compte d'utilisateur Windows](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="7d757-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="7d757-129">Les utilisateurs doivent maintenant être en mesure d'utiliser HTTPS pour accéder au site.</span><span class="sxs-lookup"><span data-stu-id="7d757-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d757-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d757-130">See Also</span></span>  
 [<span data-ttu-id="7d757-131">Créer une application web Master Data Manager &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7d757-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
