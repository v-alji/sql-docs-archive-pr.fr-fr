---
title: Activer l’intégration des fonctionnalités PowerPivot pour les collections de sites dans l’administration centrale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
author: minewiskan
ms.author: owend
ms.openlocfilehash: b565434cba197d04327e833d4ac6eab3caf96646
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698579"
---
# <a name="activate-powerpivot-feature-integration-for-site-collections-in-central-administration"></a><span data-ttu-id="b0efb-102">Activer la fonctionnalité d'intégration PowerPivot pour des collections de sites dans l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="b0efb-102">Activate PowerPivot Feature Integration for Site Collections in Central Administration</span></span>
  <span data-ttu-id="b0efb-103">Activer la fonctionnalité d'intégration PowerPivot pour des collections de sites spécifiques est indispensable si vous avez utilisé l'option d'installation Batterie de serveurs existante lors de l'installation de SQL Server PowerPivot pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b0efb-103">Activating PowerPivot feature integration for specific site collections is required if you used the Existing Farm installation option to install SQL Server PowerPivot for SharePoint.</span></span> <span data-ttu-id="b0efb-104">Si vous avez installé PowerPivot pour SharePoint à l'aide de l'option Nouveau serveur, vous pouvez ignorer cette tâche, car le programme d'installation de SQL Server a déjà activé la fonctionnalité d'intégration PowerPivot pour la collection de sites racine lorsqu'il a configuré votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="b0efb-104">If you installed PowerPivot for SharePoint using the New Server option, you can skip this task because SQL Server Setup already activated PowerPivot feature integration for the root site collection when it configured your deployment.</span></span>  
  
 <span data-ttu-id="b0efb-105">L'activation de fonctionnalités au niveau de la collection de sites est nécessaire pour mettre à disposition de vos sites des pages et des modèles d'application, notamment des pages de configuration pour l'actualisation des données planifiée et des pages d'application pour la bibliothèque Galerie PowerPivot et les bibliothèques de flux.</span><span class="sxs-lookup"><span data-stu-id="b0efb-105">Feature activation at the site collection level is necessary to make application pages and templates available to your sites, including configuration pages for scheduled data refresh and application pages for PowerPivot Gallery and Data Feed libraries.</span></span>  
  
 <span data-ttu-id="b0efb-106">Vous devez activer l'intégration de PowerPivot pour chaque collection de sites qui prend en charge le traitement des requêtes PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="b0efb-106">You must activate PowerPivot integration for each site collection that supports PowerPivot query processing.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0efb-107">Prérequis</span><span class="sxs-lookup"><span data-stu-id="b0efb-107">Prerequisites</span></span>  
 <span data-ttu-id="b0efb-108">Vous devez être administrateur de collection de sites.</span><span class="sxs-lookup"><span data-stu-id="b0efb-108">You must be a site collection administrator.</span></span>  
  
## <a name="activate-powerpivot-features"></a><span data-ttu-id="b0efb-109">Activer les fonctionnalités PowerPivot</span><span class="sxs-lookup"><span data-stu-id="b0efb-109">Activate PowerPivot Features</span></span>  
  
1.  <span data-ttu-id="b0efb-110">Sur un site SharePoint, cliquez sur **Actions du site**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-110">On a SharePoint site, click **Site Actions**.</span></span>  
  
     <span data-ttu-id="b0efb-111">Par défaut, les applications Web SharePoint sont accessibles via le port 80.</span><span class="sxs-lookup"><span data-stu-id="b0efb-111">By default, SharePoint web applications are accessed through port 80.</span></span> <span data-ttu-id="b0efb-112">Cela signifie que vous pouvez souvent accéder à un site SharePoint en entrant http://\<computer name> pour ouvrir la collection de sites racine.</span><span class="sxs-lookup"><span data-stu-id="b0efb-112">This means that you can often access a SharePoint site by entering http://\<computer name> to open the root site collection.</span></span>  
  
2.  <span data-ttu-id="b0efb-113">Cliquez sur **Paramètres du site**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-113">Click **Site Settings**.</span></span>  
  
3.  <span data-ttu-id="b0efb-114">Dans Administration de la collection de sites, cliquez sur **Fonctionnalités de la collection de sites**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-114">In Site Collection Administration, click **Site collection features**.</span></span>  
  
4.  <span data-ttu-id="b0efb-115">Faites défiler la page jusqu’à ce que vous trouviez la **fonctionnalité de collection de sites d’intégration PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-115">Scroll down the page until you find **PowerPivot Integration Site Collection Feature**.</span></span>  
  
5.  <span data-ttu-id="b0efb-116">Cliquez sur **Activer**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-116">Click **Activate**.</span></span>  
  
6.  <span data-ttu-id="b0efb-117">Répétez ces étapes pour les collections de sites supplémentaires en ouvrant chaque site et en cliquant sur **Actions du site**.</span><span class="sxs-lookup"><span data-stu-id="b0efb-117">Repeat for additional site collections by opening each site and clicking **Site Actions**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0efb-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0efb-118">See Also</span></span>  
 <span data-ttu-id="b0efb-119">[Administration et configuration du serveur PowerPivot dans l’administration centrale](power-pivot-server-administration-and-configuration-in-central-administration.md) </span><span class="sxs-lookup"><span data-stu-id="b0efb-119">[PowerPivot Server Administration and Configuration in Central Administration](power-pivot-server-administration-and-configuration-in-central-administration.md) </span></span>  
 <span data-ttu-id="b0efb-120">[Configuration initiale &#40;PowerPivot pour SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="b0efb-120">[Initial Configuration &#40;PowerPivot for SharePoint&#41;](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="b0efb-121">PowerPivot for SharePoint 2010 Installation</span><span class="sxs-lookup"><span data-stu-id="b0efb-121">PowerPivot for SharePoint 2010 Installation</span></span>](../../sql-server/install/powerpivot-for-sharepoint-2010-installation.md)  
  
  
