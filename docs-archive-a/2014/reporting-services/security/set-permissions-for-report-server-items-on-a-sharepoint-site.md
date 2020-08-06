---
title: Définir des autorisations pour les éléments de serveur de rapports sur un site SharePoint (Reporting Services en mode intégré SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- permissions [Reporting Services], SharePoint integrated mode
- SharePoint integration [Reporting Services], permissions
ms.assetid: 2467c657-a3bf-4ec3-a88c-8877df19823d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f38497843ca99342f13952153d7fed957564e006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697439"
---
# <a name="set-permissions-for-report-server-items-on-a-sharepoint-site-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="b9a08-102">Définir les autorisations sur les éléments de serveur de rapports sur un site SharePoint (Reporting Services en mode intégré SharePoint)</span><span class="sxs-lookup"><span data-stu-id="b9a08-102">Set Permissions for Report Server Items on a SharePoint Site (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="b9a08-103">Si les paramètres de sécurité par défaut n'offrent pas le niveau d'accès souhaité, vous pouvez créer des niveaux d'autorisation pour fournir un accès aux opérations ou éléments spécifiques d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b9a08-103">If default security settings do not provide the level of access that you require, you can create new permission levels to provide access to specific report server items or operations.</span></span> <span data-ttu-id="b9a08-104">Les paramètres de sécurité personnalisés peuvent s'avérer utiles si vous souhaitez restreindre l'accès à un rapport particulier.</span><span class="sxs-lookup"><span data-stu-id="b9a08-104">Custom security settings can be useful if you want to restrict access to a particular report.</span></span>  
  
 <span data-ttu-id="b9a08-105">Vous devez être propriétaire d'un site pour créer des groupes et des niveaux d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="b9a08-105">You must be a site owner to create permission levels and groups.</span></span> <span data-ttu-id="b9a08-106">Les niveaux d'autorisations sont utilisés globalement dans l'ensemble d'un site.</span><span class="sxs-lookup"><span data-stu-id="b9a08-106">Permission levels are used globally throughout a site.</span></span> <span data-ttu-id="b9a08-107">Si vous créez un niveau d'autorisation, celui-ci est accessible aux autres propriétaires de site.</span><span class="sxs-lookup"><span data-stu-id="b9a08-107">If you create a new permission level, it will be available to other site owners.</span></span>  
  
 <span data-ttu-id="b9a08-108">La plupart des autorisations sont héritées d'un site parent.</span><span class="sxs-lookup"><span data-stu-id="b9a08-108">Most permissions are inherited from a parent site.</span></span> <span data-ttu-id="b9a08-109">Si vous attribuez des autorisations à un élément ou à une bibliothèque spécifique, vous rompez l'héritage des autorisations et allourdissez la charge liée à la gestion des autorisations pour cette branche de l'arborescence de votre site.</span><span class="sxs-lookup"><span data-stu-id="b9a08-109">If you assign permissions on a specific library or item, you break permission inheritance and incur additional overhead in how manage permissions for that branch of your site hierarchy.</span></span>  
  
 <span data-ttu-id="b9a08-110">Vous pouvez définir des autorisations sur les fichiers de définition de rapport (.rdl), de modèle de rapport (.smdl) et de source de données partagée (.rsds).</span><span class="sxs-lookup"><span data-stu-id="b9a08-110">You can set permissions on report definition (.rdl), model (.smdl), and shared data source (.rsds) files.</span></span> <span data-ttu-id="b9a08-111">Vous ne pouvez pas associer sur le même élément des autorisations héritées et des autorisations gérées.</span><span class="sxs-lookup"><span data-stu-id="b9a08-111">You cannot combine inherited and managed permissions on the same item.</span></span> <span data-ttu-id="b9a08-112">Si vous choisissez de gérer directement les autorisations, les autorisations héritées resteront sans effet sur l'élément actif.</span><span class="sxs-lookup"><span data-stu-id="b9a08-112">If you choose to manage permissions directly, inherited permissions will have no effect on the current item.</span></span> <span data-ttu-id="b9a08-113">Pour reprendre ultérieurement l'héritage des autorisations, vous pouvez sélectionner **Hériter les autorisations** dans le menu **Actions** .</span><span class="sxs-lookup"><span data-stu-id="b9a08-113">If you want to resume permission inheritance later, you can select **Inherit Permissions** on the **Actions** menu.</span></span>  
  
 <span data-ttu-id="b9a08-114">Pour définir des autorisations sur des entités ou des perspectives dans un modèle, vous devez disposer du niveau d'autorisation Contrôle total pour le modèle.</span><span class="sxs-lookup"><span data-stu-id="b9a08-114">To set permissions on entities and perspectives in a model, you must have Full Control level of permission for the model.</span></span> <span data-ttu-id="b9a08-115">Le Contrôle total comprend l'autorisation « Gérer les autorisations », une autorisation de niveau de site accordée à tous les propriétaires de sites et autres groupes SharePoint qui disposent du niveau Contrôle total.</span><span class="sxs-lookup"><span data-stu-id="b9a08-115">Full Control includes "Manage Permissions", which is a site level permission that is granted to site owners and other SharePoint groups who have Full Control level of permission.</span></span> <span data-ttu-id="b9a08-116">Si vous souhaitez accorder à des utilisateurs spécifiques la possibilité de définir la sécurité de l'élément de modèle, vous devez désactiver l'héritage des autorisations et accorder des autorisations de niveau plus élevé (par exemple Contrôle total) à l'utilisateur ou au groupe sur le fichier de modèle.</span><span class="sxs-lookup"><span data-stu-id="b9a08-116">If you want to offer specific users the ability to set model item security, you must break permission inheritance and grant elevated permissions (such as Full Control) to the user or group on the model file.</span></span> <span data-ttu-id="b9a08-117">Lorsque vous accordez l'autorisation Contrôle total sur un élément, un fichier dans la bibliothèque, par exemple, les autorisations sont limitées à cet élément et ne s'appliquent pas au parent ou à d'autres éléments de la même bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="b9a08-117">When you grant Full Control on an item such as a file in the library, the permissions are scoped to that item and do not extend to the parent or to other items within the same library.</span></span> <span data-ttu-id="b9a08-118">Une fois que l'utilisateur dispose de l'autorisation Gérer les autorisations sur le modèle, il peut définir la sécurité de l'élément de modèle via le site SharePoint ou le Générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="b9a08-118">After the user has Manage Permissions permission on the model, he or she can use set model item security via the SharePoint site or Model Designer.</span></span>  
  
### <a name="to-set-permissions-on-an-individual-report-model-or-data-source"></a><span data-ttu-id="b9a08-119">Pour définir des autorisations sur un rapport, un modèle ou une source de données spécifique</span><span class="sxs-lookup"><span data-stu-id="b9a08-119">To set permissions on an individual report, model, or data source</span></span>  
  
1.  <span data-ttu-id="b9a08-120">Si la bibliothèque n'est pas ouverte, cliquez sur son nom dans le menu de lancement rapide.</span><span class="sxs-lookup"><span data-stu-id="b9a08-120">If the library is not already open, click its name on the Quick Launch.</span></span> <span data-ttu-id="b9a08-121">Si le nom de la bibliothèque n'est pas visible, cliquez sur **Afficher tout le contenu du site**, puis sur le nom de la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="b9a08-121">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="b9a08-122">Pointez sur le fichier de rapport, de modèle de rapport ou de source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="b9a08-122">Point to the report, report model, or shared data source file.</span></span>  
  
3.  <span data-ttu-id="b9a08-123">Cliquez sur la flèche vers le bas et sur **Gérer les autorisations**dans le menu.</span><span class="sxs-lookup"><span data-stu-id="b9a08-123">Click the down arrow, and on the menu, click **Manage Permissions**.</span></span>  
  
4.  <span data-ttu-id="b9a08-124">Dans le menu **Actions** , cliquez sur **Modifier les autorisations**, puis sur **OK** pour confirmer l'action.</span><span class="sxs-lookup"><span data-stu-id="b9a08-124">On the **Actions** menu, click **Edit Permissions**, and then click **OK** to confirm the action.</span></span>  
  
5.  <span data-ttu-id="b9a08-125">Pour accorder des autorisations à un utilisateur ou un groupe qui ne dispose pas encore d'autorisations pour utiliser le fichier, cliquez sur **Nouveau**, puis sur **Ajouter des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-125">To give permissions to a user or group that does not yet have permissions to use the file, click **New**, and then click **Add Users**.</span></span>  
  
6.  <span data-ttu-id="b9a08-126">Pour supprimer ou modifier des autorisations pour un utilisateur ou à un groupe existant, cliquez sur **Actions**, puis sur **Supprimer les autorisations des utilisateurs** ou **Modifier les autorisations des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-126">To remove or modify permissions for an existing user or group, click the check box next to the user or group, click **Actions**, and then click **Remove User Permissions** or **Edit User Permissions**.</span></span>  
  
### <a name="to-set-permissions-that-enable-model-item-security"></a><span data-ttu-id="b9a08-127">Pour définir des autorisations qui activent la sécurité des éléments de modèle</span><span class="sxs-lookup"><span data-stu-id="b9a08-127">To set permissions that enable model item security</span></span>  
  
1.  <span data-ttu-id="b9a08-128">Connectez-vous au site SharePoint à l'aide d'un compte qui dispose de l'autorisation Gérer les autorisations sur le site.</span><span class="sxs-lookup"><span data-stu-id="b9a08-128">Log in to the SharePoint site using an account that has Manage Permissions permission on the site.</span></span>  
  
2.  <span data-ttu-id="b9a08-129">Ouvrez la bibliothèque qui contient le modèle.</span><span class="sxs-lookup"><span data-stu-id="b9a08-129">Open the library that contains the model.</span></span>  
  
3.  <span data-ttu-id="b9a08-130">Pointez sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="b9a08-130">Point to the model.</span></span>  
  
4.  <span data-ttu-id="b9a08-131">Cliquez sur la flèche orientée vers le bas en regard du modèle, puis sélectionnez **Gérer les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-131">Click the down arrow next to the model, and click **Manage Permissions**.</span></span>  
  
5.  <span data-ttu-id="b9a08-132">Cliquez sur **Actions**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-132">Click **Actions**.</span></span>  
  
6.  <span data-ttu-id="b9a08-133">Cliquez sur **Modifier les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-133">Click **Edit Permissions**.</span></span> <span data-ttu-id="b9a08-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-134">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b9a08-135">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-135">Click **New**.</span></span>  
  
8.  <span data-ttu-id="b9a08-136">Cliquez sur **Add Users**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-136">Click **Add Users**.</span></span>  
  
9. <span data-ttu-id="b9a08-137">Dans Utilisateurs/Groupes, entrez le compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b9a08-137">In Users/Groups, enter the user account.</span></span>  
  
10. <span data-ttu-id="b9a08-138">Sélectionnez **Définir directement les autorisations des utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-138">Select **Give users permission directly**.</span></span>  
  
11. <span data-ttu-id="b9a08-139">Cliquez sur **Contrôle total**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-139">Click **Full Control**.</span></span>  
  
12. <span data-ttu-id="b9a08-140">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9a08-140">Click **OK**.</span></span> <span data-ttu-id="b9a08-141">Une fois qu'un utilisateur a la possibilité de gérer des autorisations pour un modèle spécifique, celui-ci peut ouvrir le modèle pour modifier les autorisations dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="b9a08-141">Once a user has the ability to manage permissions for a specific model, he or she can open the model to edit permissions within the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a08-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9a08-142">See Also</span></span>  
 <span data-ttu-id="b9a08-143">[Utiliser la sécurité intégrée dans Windows SharePoint Services pour les éléments de serveur de rapports](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="b9a08-143">[Use Built-in Security in Windows SharePoint Services for Report Server Items](use-built-in-security-in-windows-sharepoint-services-for-report-server-items.md) </span></span>  
 <span data-ttu-id="b9a08-144">[Définir des autorisations pour des opérations de serveurs de rapports dans une application web SharePoint](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span><span class="sxs-lookup"><span data-stu-id="b9a08-144">[Set Permissions for Report Server Operations in a SharePoint Web Application](set-permissions-for-report-server-operations-in-a-sharepoint-web-application.md) </span></span>  
 <span data-ttu-id="b9a08-145">[Comparer des rôles et des tâches dans Reporting Services avec les autorisations et les groupes SharePoint](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="b9a08-145">[Compare Roles and Tasks in Reporting Services to SharePoint Groups and Permissions](../reporting-services-roles-tasks-vs-sharepoint-groups-permissions.md) </span></span>  
 <span data-ttu-id="b9a08-146">[Article de référence sur les autorisations de site SharePoint et de listes pour les éléments de serveur de rapports](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span><span class="sxs-lookup"><span data-stu-id="b9a08-146">[SharePoint Site and List Permission Reference for Report Server Items](sharepoint-site-and-list-permission-reference-for-report-server-items.md) </span></span>  
 [<span data-ttu-id="b9a08-147">Accord d'autorisations sur des éléments de serveur de rapports sur un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="b9a08-147">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
  
  
