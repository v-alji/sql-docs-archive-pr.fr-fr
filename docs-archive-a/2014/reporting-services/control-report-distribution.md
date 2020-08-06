---
title: Contrôler la distribution des rapports | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de8a27801ef89f10bf303cee17d1c2d0e1081c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599800"
---
# <a name="control-report-distribution"></a><span data-ttu-id="1e86f-102">Contrôler la distribution des rapports</span><span class="sxs-lookup"><span data-stu-id="1e86f-102">Control Report Distribution</span></span>
  <span data-ttu-id="1e86f-103">Vous pouvez configurer un serveur de rapports de façon à réduire les risques de sécurité associés à la remise par messagerie électronique ou dans un partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="1e86f-103">You can configure a report server to reduce the security risks associated with e-mail and file share distribution.</span></span>  
  
## <a name="securing-reports"></a><span data-ttu-id="1e86f-104">Sécurisation des rapports</span><span class="sxs-lookup"><span data-stu-id="1e86f-104">Securing Reports</span></span>  
 <span data-ttu-id="1e86f-105">La première étape du contrôle de la distribution des rapports consiste à sécuriser le rapport contre les accès non autorisés.</span><span class="sxs-lookup"><span data-stu-id="1e86f-105">The first step in controlling report distribution is to secure the report against unauthorized access.</span></span> <span data-ttu-id="1e86f-106">Pour être utilisé dans un abonnement, un rapport doit utiliser un ensemble stocké d'informations d'identification qui ne varie pas pour les remises individuelles.</span><span class="sxs-lookup"><span data-stu-id="1e86f-106">To be used in a subscription, a report must use a stored set of credentials that do not vary for individual deliveries.</span></span> <span data-ttu-id="1e86f-107">Tout utilisateur pouvant accéder à un rapport sur le serveur de rapports peut l'exécuter et éventuellement le distribuer.</span><span class="sxs-lookup"><span data-stu-id="1e86f-107">Any user who can access the report on the report server can run it and possibly distribute it.</span></span> <span data-ttu-id="1e86f-108">Pour empêcher cela, vous devez limiter l'accès au rapport aux seuls utilisateurs qui en ont besoin.</span><span class="sxs-lookup"><span data-stu-id="1e86f-108">To prevent this from occurring, you must limit report access to only those users who require it.</span></span> <span data-ttu-id="1e86f-109">Pour plus d’informations, consultez [sécuriser les rapports et les ressources](security/secure-reports-and-resources.md) et [sécuriser les dossiers](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="1e86f-109">For more information, see [Secure Reports and Resources](security/secure-reports-and-resources.md) and [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="1e86f-110">Les rapports hautement confidentiels qui utilisent la sécurité de la base de données pour autoriser l'accès ne peuvent pas être distribués par voie d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="1e86f-110">Highly confidential reports that use database security to authorize access cannot be distributed by way of subscription.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1e86f-111">Les rapports sont véhiculés comme des fichiers.</span><span class="sxs-lookup"><span data-stu-id="1e86f-111">Reports are transported as files.</span></span> <span data-ttu-id="1e86f-112">Les risques et les sécurités qui s'appliquent aux fichiers s'appliquent de la même façon aux rapports qui sont enregistrés sur disque ou envoyés comme pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="1e86f-112">The risks and safeguards that apply to files apply equally to reports that are saved to disk or sent as attachments.</span></span> <span data-ttu-id="1e86f-113">Tout utilisateur pouvant accéder à un fichier peut distribuer ou utiliser le fichier à sa guise.</span><span class="sxs-lookup"><span data-stu-id="1e86f-113">Any user who has access to a file can distribute or use the file at his or her discretion.</span></span>  
  
## <a name="controlling-e-mail-delivery"></a><span data-ttu-id="1e86f-114">Contrôle de la remise par messagerie</span><span class="sxs-lookup"><span data-stu-id="1e86f-114">Controlling E-Mail Delivery</span></span>  
 <span data-ttu-id="1e86f-115">Vous pouvez configurer un serveur de rapports de façon à limiter la distribution par messagerie à des domaines hôtes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1e86f-115">You can configure a report server to limit e-mail distribution to specific host domains.</span></span> <span data-ttu-id="1e86f-116">Par exemple, vous pouvez empêcher un serveur de rapports de remettre un rapport à tous les domaines, sauf à ceux répertoriés dans le fichier de configuration RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="1e86f-116">For example, you can prevent a report server from delivering a report to all domains except those listed in the RSReportServer configuration file.</span></span>  
  
 <span data-ttu-id="1e86f-117">Vous pouvez également définir des paramètres de configuration pour masquer le champ **À** dans un abonnement.</span><span class="sxs-lookup"><span data-stu-id="1e86f-117">You can also set configuration settings to hide the **To** field in a subscription.</span></span> <span data-ttu-id="1e86f-118">Dans ce cas, les rapports sont remis uniquement à l'utilisateur qui définit l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="1e86f-118">In this case, reports are delivered only to the user defining the subscription.</span></span> <span data-ttu-id="1e86f-119">Toutefois, une fois qu'un rapport a été envoyé à un utilisateur, vous ne pouvez pas explicitement l'empêcher d'être transféré.</span><span class="sxs-lookup"><span data-stu-id="1e86f-119">However, after a report is sent to a user, you cannot explicitly prevent it from being forwarded.</span></span>  
  
 <span data-ttu-id="1e86f-120">La façon la plus efficace de contrôler la distribution des rapports consiste à configurer un serveur de rapports de sorte qu'il n'envoie qu'une adresse URL de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1e86f-120">The most effective way to control report distribution is to configure a report server to send only a report server URL.</span></span> <span data-ttu-id="1e86f-121">Le serveur de rapports utilise l'authentification Windows et le modèle d'autorisation par rôle pour contrôler l'accès à un rapport.</span><span class="sxs-lookup"><span data-stu-id="1e86f-121">The report server uses Windows Authentication and a role-based authorization model to control access to a report.</span></span> <span data-ttu-id="1e86f-122">Si un utilisateur reçoit accidentellement par courrier électronique un rapport qu'il n'est pas autorisé à consulter, le serveur de rapports n'affiche pas le rapport.</span><span class="sxs-lookup"><span data-stu-id="1e86f-122">If a user accidentally receives through e-mail a report that he or she is not authorized to view, the report server will not display the report.</span></span>  
  
## <a name="controlling-file-share-delivery"></a><span data-ttu-id="1e86f-123">Contrôle de la remise par partage de fichiers</span><span class="sxs-lookup"><span data-stu-id="1e86f-123">Controlling File Share Delivery</span></span>  
 <span data-ttu-id="1e86f-124">La remise par partage de fichiers permet d'envoyer un rapport à un fichier sur un disque dur.</span><span class="sxs-lookup"><span data-stu-id="1e86f-124">File share delivery is used to send a report to a file on a hard disk.</span></span> <span data-ttu-id="1e86f-125">Une fois le fichier enregistré sur disque, il n'est plus soumis au modèle de sécurité basée sur les rôles que le serveur de rapports utilise pour contrôler l'accès utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1e86f-125">After the file has been saved to disk, it is no longer subject to the role-based security model that the report server uses to control user access.</span></span> <span data-ttu-id="1e86f-126">Pour protéger un rapport qui a été distribué sur un disque, placez des ACL (Access Control Lists) sur le fichier lui-même ou sur le dossier qui le contient.</span><span class="sxs-lookup"><span data-stu-id="1e86f-126">To secure a report that has been delivered to disk, you can place Access Control Lists (ACLs) on the file itself or on the folder that contains it.</span></span> <span data-ttu-id="1e86f-127">D'autres options de sécurité sont disponibles en fonction de votre système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="1e86f-127">Additional security options might be available, depending on your operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e86f-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e86f-128">See Also</span></span>  
 <span data-ttu-id="1e86f-129">[Configurer un serveur de rapports pour la remise par messagerie &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="1e86f-129">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="1e86f-130">[Abonnements et remise &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="1e86f-130">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="1e86f-131">Créer et gérer des abonnements pour les serveurs de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="1e86f-131">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  
