---
title: Accorder des autorisations aux utilisateurs et alerter les administrateurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613836"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="cdafa-102">Accorder des autorisations aux utilisateurs et alerter les administrateurs</span><span class="sxs-lookup"><span data-stu-id="cdafa-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="cdafa-103">Avant que les utilisateurs et les administrateurs d'alerte puissent créer, modifier, supprimer et afficher les alertes de données d'affichage, ils doivent disposer des autorisations SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cdafa-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="cdafa-104">La fonctionnalité d’alerte de données de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] ne nécessite aucune autorisation particulière. Utilisez celles qui sont intégrées à SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cdafa-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="cdafa-105">**Travailleurs de l’information** : les autorisations doivent inclure les autorisations SharePoint Créer une alerte et Afficher les éléments.</span><span class="sxs-lookup"><span data-stu-id="cdafa-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="cdafa-106">Les niveaux d'autorisation prédéfinis SharePoint nommés Concevoir, Contribuer, Lire et Vue uniquement, incluent les autorisations SharePoint Créer une alerte et Afficher les éléments.</span><span class="sxs-lookup"><span data-stu-id="cdafa-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="cdafa-107">Vous pouvez également créer un niveau d'autorisation personnalisé avec les autorisations requises pour prendre en charge les utilisateurs qui créent, modifient, exécutent, et affichent les alertes de données.</span><span class="sxs-lookup"><span data-stu-id="cdafa-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="cdafa-108">**Administrateurs d’alertes**: les autorisations doivent inclure l’autorisation gérer les alertes SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cdafa-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="cdafa-109">Par défaut, seul le niveau d'autorisation Contrôle total comprend cette autorisation pour les sites créés avec le modèle de site Team Site.</span><span class="sxs-lookup"><span data-stu-id="cdafa-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="cdafa-110">Si vous utilisez d'autres modèles de site, vous verrez des listes différentes de groupes SharePoint par défaut.</span><span class="sxs-lookup"><span data-stu-id="cdafa-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="cdafa-111">Vous pouvez ajouter des alertes de gestion à l'un des niveaux d'autorisation prédéfinis ou créer un niveau d'autorisation personnalisé avec l'autorisation requise pour prendre en charge l'alerte des administrateurs qui affichent et suppriment des alertes de données.</span><span class="sxs-lookup"><span data-stu-id="cdafa-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="cdafa-112">Pour en savoir plus sur les autorisations SharePoint, consultez [Autorisations utilisateur et niveaux d’autorisation (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="cdafa-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="cdafa-113">Pour accorder des autorisations</span><span class="sxs-lookup"><span data-stu-id="cdafa-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="cdafa-114">Accédez au site SharePoint auquel vous souhaitez accorder des autorisations.</span><span class="sxs-lookup"><span data-stu-id="cdafa-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="cdafa-115">Dans la barre d'outils, cliquez sur **Actions du site** puis cliquez sur **Autorisations du site**.</span><span class="sxs-lookup"><span data-stu-id="cdafa-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="cdafa-116">Si vous ne voyez pas cette option, vous ne disposez pas de l'autorisation suffisante pour accorder des autorisations à d'autres.</span><span class="sxs-lookup"><span data-stu-id="cdafa-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="cdafa-117">Cliquez sur **Accorder des autorisations**.</span><span class="sxs-lookup"><span data-stu-id="cdafa-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="cdafa-118">Dans **Utilisateurs/groupes**, tapez les noms d’utilisateurs, les noms de groupes ou les adresses e-mail auxquels vous souhaitez accorder l’autorisation.</span><span class="sxs-lookup"><span data-stu-id="cdafa-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="cdafa-119">Sélectionnez l'option **Ajouter des utilisateurs à un groupe SharePoint** ou **Accorder directement les autorisations aux utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="cdafa-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="cdafa-120">Selon que vous avez sélectionné **Ajouter des utilisateurs à un groupe SharePoint** ou **Accorder directement les autorisations aux utilisateurs** , effectuez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cdafa-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="cdafa-121">Si vous avez sélectionné **Ajouter des utilisateurs à un groupe SharePoint**, sélectionnez un niveau d’autorisation dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="cdafa-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="cdafa-122">Si vous avez sélectionné **Accorder directement les autorisations aux utilisateurs**, sélectionnez un niveau d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="cdafa-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cdafa-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdafa-123">See Also</span></span>  
 <span data-ttu-id="cdafa-124">[Définir des autorisations pour les éléments de serveur de rapports sur un site SharePoint &#40;Reporting Services en mode intégré SharePoint&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="cdafa-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="cdafa-125">Alertes de données Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cdafa-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
