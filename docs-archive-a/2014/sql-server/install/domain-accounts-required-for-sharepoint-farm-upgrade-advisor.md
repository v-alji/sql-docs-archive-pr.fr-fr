---
title: Comptes de domaine requis pour la batterie de serveurs SharePoint (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614358"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="60583-102">Comptes de domaine requis pour la batterie de serveurs SharePoint (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="60583-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="60583-103">Les produits SharePoint configurés pour un environnement de batterie requièrent l'utilisation de comptes de domaine.</span><span class="sxs-lookup"><span data-stu-id="60583-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="60583-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60583-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="60583-105">Composant</span><span class="sxs-lookup"><span data-stu-id="60583-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="60583-106">Description</span><span class="sxs-lookup"><span data-stu-id="60583-106">Description</span></span>  
 <span data-ttu-id="60583-107">Les produits SharePoint configurés pour un environnement de batterie requièrent l'utilisation de comptes de domaine pour les services et les connexions de base de données.</span><span class="sxs-lookup"><span data-stu-id="60583-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="60583-108">Cette exigence concerne notamment le compte spécifié pour le compte de service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="60583-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="60583-109">Si vous n'utilisez pas de compte d'utilisateur de domaine pour Reporting Services, vous rencontrez des problèmes notamment en consultant les pages Administration centrale de SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="60583-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="60583-110">Lorsque vous essayez de configurer l'intégration de Reporting Services, un message d'erreur semblable au suivant s'affiche :</span><span class="sxs-lookup"><span data-stu-id="60583-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="60583-111">« Le serveur de rapports s'exécute sous le compte NT AUTHORITY\NETWORK SERVICE intégré, qui n'est pas pris en charge par les batteries de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60583-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="60583-112">Reconfigurez le serveur de rapports pour qu’il s’exécute sous un compte de domaine.»</span><span class="sxs-lookup"><span data-stu-id="60583-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="60583-113">Action corrective</span><span class="sxs-lookup"><span data-stu-id="60583-113">Corrective Action</span></span>  
 <span data-ttu-id="60583-114">Pour [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et les versions précédentes, utilisez la gestionnaire de configuration de Reporting Services pour modifier le compte qui est affecté en tant que compte de service Report Server.</span><span class="sxs-lookup"><span data-stu-id="60583-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="60583-115">Pour modifier le compte de service à partir du Gestionnaire de configuration</span><span class="sxs-lookup"><span data-stu-id="60583-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="60583-116">Dans le menu **Démarrer** , sélectionnez **tous les programmes**, puis cliquez sur **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="60583-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="60583-117">Sélectionnez **outils de configuration**, puis cliquez sur **Gestionnaire de configuration de Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="60583-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="60583-118">Dans Configuration Manager, sélectionnez l’onglet **compte de service** .</span><span class="sxs-lookup"><span data-stu-id="60583-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="60583-119">Sélectionnez **utiliser un autre compte** et entrez les informations d’identification d’un compte de domaine.</span><span class="sxs-lookup"><span data-stu-id="60583-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="60583-120">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="60583-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60583-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60583-121">See Also</span></span>  
 [<span data-ttu-id="60583-122">Configurer le compte de service Report Server &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="60583-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
