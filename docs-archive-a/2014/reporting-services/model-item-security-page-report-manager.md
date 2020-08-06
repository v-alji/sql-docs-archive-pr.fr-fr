---
title: Page sécurité de l’élément de modèle (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600631"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="a478a-102">Page Sécurité de l'élément de modèle (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="a478a-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="a478a-103">Utilisez cette page pour sécuriser des parties d'un modèle en accordant ou en refusant des autorisations en lecture seule sur des éléments particuliers.</span><span class="sxs-lookup"><span data-stu-id="a478a-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="a478a-104">La sécurité de l'élément de modèle affecte l'exploration de données appropriée au moment de l'exécution et la possibilité d'utiliser des parties d'un modèle publié lors de la création de rapports dans le Générateur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a478a-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="a478a-105">Pour utiliser cette fonctionnalité, vous devez disposer des autorisations de gestionnaire de contenu.</span><span class="sxs-lookup"><span data-stu-id="a478a-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="a478a-106">La sécurité de l'élément de modèle est appliquée à un modèle qui est traité sur le serveur de rapports et n'affecte pas les fichiers .smdl que vous modifiez dans le Générateur de modèles ou utilisez dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="a478a-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="a478a-107">En outre, celui-ci n'a aucun effet sur les utilisateurs autorisés à modifier une définition de modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="a478a-108">Un utilisateur qui possède les autorisations de Gestionnaire Contenu ou de Serveur de publication sur un modèle peut consulter toutes les parties de celui-ci, que la sécurité de l'élément de modèle soit appliquée ou non.</span><span class="sxs-lookup"><span data-stu-id="a478a-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a478a-109">La sécurité des éléments de modèle peut être renforcée à l'aide de filtres de sécurité.</span><span class="sxs-lookup"><span data-stu-id="a478a-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="a478a-110">Vous pouvez définir la sécurité de l'élément de modèle sur les entités, dossiers et champs individuels d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="a478a-111">Dans la mesure où un modèle présente une telle grande surface d'éléments sécurisables, l'héritage des autorisations est intégré au modèle afin que vous puissiez sécuriser un grand nombre d'éléments par le biais d'un nombre relativement restreint d'attributions de rôles.</span><span class="sxs-lookup"><span data-stu-id="a478a-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="a478a-112">L'héritage des autorisations est basé sur les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a478a-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="a478a-113">Modèle</span><span class="sxs-lookup"><span data-stu-id="a478a-113">Model</span></span>  
  
-   <span data-ttu-id="a478a-114">Nœud racine</span><span class="sxs-lookup"><span data-stu-id="a478a-114">Root node</span></span>  
  
-   <span data-ttu-id="a478a-115">Dossiers ou entités</span><span class="sxs-lookup"><span data-stu-id="a478a-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="a478a-116">Champs</span><span class="sxs-lookup"><span data-stu-id="a478a-116">Fields</span></span>  
  
 <span data-ttu-id="a478a-117">Initialement, l'autorisation d'accéder aux éléments de modèle est héritée par le biais des attributions de rôles définies sur le modèle lui-même.</span><span class="sxs-lookup"><span data-stu-id="a478a-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="a478a-118">Un utilisateur qui a l'autorisation de consulter un modèle dans un dossier dans le Gestionnaire de rapports peut consulter tous les éléments du modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="a478a-119">Si vous appliquez la sécurité de l'élément de modèle, vous devez créer au moins une attribution de rôle au niveau du nœud racine.</span><span class="sxs-lookup"><span data-stu-id="a478a-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="a478a-120">Cette attribution de rôle initiale au niveau du nœud racine devient la nouvelle source d'autorisations héritées.</span><span class="sxs-lookup"><span data-stu-id="a478a-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="a478a-121">L'attribution de rôle au niveau du nœud racine est héritée automatiquement par tous les éléments dans la hiérarchie du modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="a478a-122">Pour personnaliser davantage les autorisations sur l'exploration de données, vous pouvez changer les autorisations sur les dossiers et les entités.</span><span class="sxs-lookup"><span data-stu-id="a478a-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="a478a-123">Enfin, vous pouvez définir des autorisations sur les champs individuels.</span><span class="sxs-lookup"><span data-stu-id="a478a-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="a478a-124">Pour faciliter la gestion des attributions de rôles, définissez des autorisations uniquement sur les dossiers ou entités plutôt que sur les champs individuels.</span><span class="sxs-lookup"><span data-stu-id="a478a-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="a478a-125">Vous ne pouvez pas effectuer de recherche sur les attributions de rôles que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="a478a-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="a478a-126">Si vous définissez la sécurité sur des champs spécifiques et souhaitez ultérieurement mettre à jour les paramètres de sécurité, vous devez parcourir l'espace de noms du modèle pour rechercher les champs que vous avez sécurisés.</span><span class="sxs-lookup"><span data-stu-id="a478a-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="a478a-127">Pour commencer, créez une attribution de rôle au niveau du nœud racine, puis des attributions de rôles supplémentaires sur les entités et les dossiers.</span><span class="sxs-lookup"><span data-stu-id="a478a-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="a478a-128">Pour supprimer la sécurité de l'élément de modèle, désactivez la case à cocher **Sécuriser les éléments de modèles de manière indépendante pour ce modèle**.</span><span class="sxs-lookup"><span data-stu-id="a478a-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="a478a-129">La désactivation de la case à cocher rétablit les autorisations initiales héritées du modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="a478a-130">Navigation</span><span class="sxs-lookup"><span data-stu-id="a478a-130">Navigation</span></span>  
 <span data-ttu-id="a478a-131">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a478a-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="a478a-132">Pour ouvrir la page Propriétés générales pour un rapport</span><span class="sxs-lookup"><span data-stu-id="a478a-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="a478a-133">Ouvrez le Gestionnaire de rapports et recherchez le modèle pour lequel vous souhaitez configurer la sécurité pour les éléments de modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="a478a-134">Pointez sur le modèle et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="a478a-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="a478a-135">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="a478a-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="a478a-136">La page Propriétés générales pour le modèle s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="a478a-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="a478a-137">Sélectionnez l'onglet **Sécurité de l'élément de modèle** .</span><span class="sxs-lookup"><span data-stu-id="a478a-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a478a-138">Options</span><span class="sxs-lookup"><span data-stu-id="a478a-138">Options</span></span>  
 <span data-ttu-id="a478a-139">**Sécuriser les éléments de modèles de manière indépendante pour ce modèle**</span><span class="sxs-lookup"><span data-stu-id="a478a-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="a478a-140">Activez cette case à cocher pour activer la sécurité des éléments de modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="a478a-141">**Spécifiez la sécurité pour chaque élément du modèle**</span><span class="sxs-lookup"><span data-stu-id="a478a-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="a478a-142">Affiche tous les éléments d'un modèle.</span><span class="sxs-lookup"><span data-stu-id="a478a-142">Shows all of the items in a model.</span></span> <span data-ttu-id="a478a-143">Vous pouvez parcourir l'espace de noms du modèle pour sélectionner l'élément à sécuriser.</span><span class="sxs-lookup"><span data-stu-id="a478a-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="a478a-144">Vous ne pouvez sélectionner qu'un seul élément à la fois.</span><span class="sxs-lookup"><span data-stu-id="a478a-144">You can only select one item at a time.</span></span> <span data-ttu-id="a478a-145">Veillez à créer la première attribution de rôle au niveau du nœud racine avant de passer aux autres entités et dossiers.</span><span class="sxs-lookup"><span data-stu-id="a478a-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="a478a-146">**Hériter les autorisations de l'élément parent**</span><span class="sxs-lookup"><span data-stu-id="a478a-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="a478a-147">Sélectionnez cette option pour hériter des paramètres de sécurité de l'élément parent.</span><span class="sxs-lookup"><span data-stu-id="a478a-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="a478a-148">**Affecter l'autorisation d'accès en lecture aux utilisateurs et groupes suivants (séparés par des points-virgules)**</span><span class="sxs-lookup"><span data-stu-id="a478a-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="a478a-149">Sélectionnez cette option pour spécifier le compte d'utilisateur ou de groupe pour lequel vous définissez l'accès.</span><span class="sxs-lookup"><span data-stu-id="a478a-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="a478a-150">Si vous utilisez la sécurité par défaut, les comptes d'utilisateur et de groupe sont des comptes de domaine Windows.</span><span class="sxs-lookup"><span data-stu-id="a478a-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="a478a-151">Spécifiez les comptes au format suivant : \* \<domain> \\<\> compte\*.</span><span class="sxs-lookup"><span data-stu-id="a478a-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a478a-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a478a-152">See Also</span></span>  
 [<span data-ttu-id="a478a-153">Aide du serveur de rapports dans Management Studio accessible par la touche F1</span><span class="sxs-lookup"><span data-stu-id="a478a-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
