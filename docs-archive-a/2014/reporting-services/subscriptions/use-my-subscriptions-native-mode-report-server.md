---
title: Utiliser mes abonnements | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], My Subscriptions page
- My Subscriptions page [Reporting Services]
ms.assetid: e96623ba-677e-4748-8787-f32bed3b5c12
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3378a65637ad04151cc517fd9047363af954c31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706972"
---
# <a name="use-my-subscriptions"></a><span data-ttu-id="0dc91-102">Utiliser Mes abonnements</span><span class="sxs-lookup"><span data-stu-id="0dc91-102">Use My Subscriptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]<span data-ttu-id="0dc91-103">Gestionnaire de rapports comprend une page **mes abonnements** qui réorganise tous vos abonnements dans un même emplacement.</span><span class="sxs-lookup"><span data-stu-id="0dc91-103">Report Manager includes a **My Subscriptions** page that organizes all of your subscriptions into one place.</span></span> <span data-ttu-id="0dc91-104">Vous pouvez utiliser cette page pour afficher, modifier et supprimer des abonnements existants.</span><span class="sxs-lookup"><span data-stu-id="0dc91-104">You can use My Subscriptions to view, modify, and delete existing subscriptions.</span></span> <span data-ttu-id="0dc91-105">En revanche, vous ne pouvez pas l'utiliser pour créer des abonnements.</span><span class="sxs-lookup"><span data-stu-id="0dc91-105">However, you cannot use it to create subscriptions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="0dc91-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en mode natif</span><span class="sxs-lookup"><span data-stu-id="0dc91-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode</span></span>|  
  
 <span data-ttu-id="0dc91-107">La page Mes abonnements vous permet de trier les abonnements par dossier, rapport, description, déclencheur, date d'exécution ou état.</span><span class="sxs-lookup"><span data-stu-id="0dc91-107">Within My Subscriptions, you can sort subscriptions by folder, report, description, trigger, last run, or status.</span></span> <span data-ttu-id="0dc91-108">Toutes les valeurs sont triées par ordre alphabétique, à l'exception de Dernière exécution, qui est trié par ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="0dc91-108">All values are sorted alphabetically except for Last Run, which is in chronological order.</span></span>  
  
 <span data-ttu-id="0dc91-109">La page Mes abonnements contient uniquement les abonnements que vous créez.</span><span class="sxs-lookup"><span data-stu-id="0dc91-109">My Subscriptions shows only the subscriptions that you create.</span></span> <span data-ttu-id="0dc91-110">Elle ne répertorie ni les abonnements pilotés par les données ni les abonnements appartenant à d'autres utilisateurs, même si vous figurez parmi les abonnés.</span><span class="sxs-lookup"><span data-stu-id="0dc91-110">It does not list subscriptions that are owned by other users, even if you are added as a subscriber to those subscriptions, nor does it show data-driven subscriptions.</span></span>  
  
 <span data-ttu-id="0dc91-111">Vous ne pouvez pas rechercher directement les abonnements par nom, pas plus que vous ne pouvez rechercher un abonnement par informations de déclencheur, informations d'état, etc.</span><span class="sxs-lookup"><span data-stu-id="0dc91-111">You cannot search for subscriptions by name, nor can you search for subscriptions based on trigger information, status information, and so forth.</span></span> <span data-ttu-id="0dc91-112">Pour plus d’informations, consultez [créer, modifier et supprimer des abonnements Standard &#40;Reporting Services en mode natif&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="0dc91-112">For more information, see [Create, Modify, and Delete Standard Subscriptions &#40;Reporting Services in Native Mode&#41;](create-and-manage-subscriptions-for-native-mode-report-servers.md).</span></span>  
  
## <a name="how-to-use-my-subscriptions"></a><span data-ttu-id="0dc91-113">Utilisation de la page Mes abonnements</span><span class="sxs-lookup"><span data-stu-id="0dc91-113">How to Use My Subscriptions</span></span>  
 <span data-ttu-id="0dc91-114">Vous affichez la page Mes abonnements via le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="0dc91-114">My Subscriptions is available through Report Manager.</span></span> <span data-ttu-id="0dc91-115">Pour ce faire, dans la barre d'outils globale du Gestionnaire de rapports, cliquez sur **Mes abonnements** .</span><span class="sxs-lookup"><span data-stu-id="0dc91-115">To access My Subscriptions, click **My Subscriptions** on the Report Manager global toolbar.</span></span>  
  
## <a name="use-windows-powershell-to-list-mysubscriptions"></a><span data-ttu-id="0dc91-116">Utiliser Windows PowerShell pour répertorier les abonnements MySubscriptions</span><span class="sxs-lookup"><span data-stu-id="0dc91-116">Use Windows PowerShell to list MySubscriptions</span></span>  
 <span data-ttu-id="0dc91-117">![Contenu relatif à PowerShell](../media/rs-powershellicon.jpg "Contenu relatif à PowerShell")</span><span class="sxs-lookup"><span data-stu-id="0dc91-117">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>  
  
 <span data-ttu-id="0dc91-118">Le script PowerShell suivant renvoie la liste des abonnements et des propriétés d'abonnement pour l'utilisateur actuel.</span><span class="sxs-lookup"><span data-stu-id="0dc91-118">The following PowerShell script will return the list of subscriptions and subscription properties for the current user.</span></span> <span data-ttu-id="0dc91-119">Pour plus d'informations, consultez [Méthode ReportingService2010.ListMySubscriptions](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span><span class="sxs-lookup"><span data-stu-id="0dc91-119">For more information, see [ReportingService2010.ListMySubscriptions Method](https://technet.microsoft.com/library/reportservice2010.reportingservice2010.listmysubscriptions.aspx).</span></span>  
  
```powershell
#server -  all subscriptions of the current user at the given server or site  
$server="[server name]/reportserver"  
$rs2010 = New-WebServiceProxy -Uri "http://$server/ReportService2010.asmx" -Namespace SSRS.ReportingService2010 -UseDefaultCredential ;  
  
$subscriptions=ListMySubscriptions(ItemPathOrSiteURL)  
$subscriptions | select Path, report, Description, Owner, SubscriptionID, lastexecuted,Status  
#uncomment the following to list all the subscription properties  
#$subscriptions
```  
  
## <a name="see-also"></a><span data-ttu-id="0dc91-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0dc91-120">See Also</span></span>  
 <span data-ttu-id="0dc91-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="0dc91-121">[Data-Driven Subscriptions](data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="0dc91-122">[Abonnements et remise &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="0dc91-122">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="0dc91-123">Créer et gérer des abonnements pour les serveurs de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="0dc91-123">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../create-manage-subscriptions-native-mode-report-servers.md)  
