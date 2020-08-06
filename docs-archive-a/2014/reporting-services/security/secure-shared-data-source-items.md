---
title: Sécuriser les éléments de source de données partagée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610427"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="1f198-102">Sécuriser les éléments de source de données partagée</span><span class="sxs-lookup"><span data-stu-id="1f198-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="1f198-103">Vous pouvez définir la sécurité sur un élément de source de données partagée afin d'en activer ou d'en désactiver l'accès.</span><span class="sxs-lookup"><span data-stu-id="1f198-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="1f198-104">Un utilisateur qui dispose d’un accès minimal à une source de données partagée (par exemple, l’accès accordé par le rôle **Explorateur** ) peut visualiser la liste des rapports qui utilisent l’élément, à condition qu’il soit autorisé à afficher les rapports eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="1f198-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="1f198-105">Un utilisateur qui dispose d’un accès supplémentaire (tel que celui conféré par le rôle **Gestionnaire de contenu** ) peut consulter et définir les propriétés de la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="1f198-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="1f198-106">Pour définir la sécurité, vous créez une attribution de rôle qui spécifie quel compte d'utilisateur ou de groupe dispose de l'accès à la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="1f198-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="1f198-107">Les utilisateurs qui ont accès à un élément de source de données partagée peuvent changer son nom, sa description, sa chaîne de connexion ou ses informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="1f198-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="1f198-108">Tâches et accès aux éléments</span><span class="sxs-lookup"><span data-stu-id="1f198-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="1f198-109">Lorsque vous créez des attributions de rôles, utilisez un rôle qui possède ces tâches pour affecter des autorisations appropriées aux utilisateurs et aux groupes.</span><span class="sxs-lookup"><span data-stu-id="1f198-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="1f198-110">Sélectionnez cette tâche</span><span class="sxs-lookup"><span data-stu-id="1f198-110">Select this task</span></span>|<span data-ttu-id="1f198-111">Pour autoriser les utilisateurs à effectuer les opérations suivantes</span><span class="sxs-lookup"><span data-stu-id="1f198-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="1f198-112">Afficher les sources de données</span><span class="sxs-lookup"><span data-stu-id="1f198-112">View data sources</span></span>|<span data-ttu-id="1f198-113">Afficher les éléments de source de données dans l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="1f198-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="1f198-114">Sans cette tâche, l'élément n'est pas visible pour les utilisateurs et ils peuvent ignorer que la source de données est disponible.</span><span class="sxs-lookup"><span data-stu-id="1f198-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="1f198-115">Gérer les sources de données</span><span class="sxs-lookup"><span data-stu-id="1f198-115">Manage data sources</span></span>|<span data-ttu-id="1f198-116">Afficher les propriétés qui spécifient le nom, la description et les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="1f198-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="1f198-117">Cette tâche est également utilisée pour afficher un élément de source de données partagée dans la hiérarchie de dossiers.</span><span class="sxs-lookup"><span data-stu-id="1f198-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="1f198-118">Si vous choisissez cette tâche, vous pouvez omettre la tâche « Afficher les sources de données ».</span><span class="sxs-lookup"><span data-stu-id="1f198-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="1f198-119">Définir la sécurité au niveau des éléments</span><span class="sxs-lookup"><span data-stu-id="1f198-119">Set security on items</span></span>|<span data-ttu-id="1f198-120">Créer et modifier des attributions de rôles qui contrôlent l'accès à la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="1f198-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="1f198-121">Cette tâche doit être utilisée avec la tâche « Afficher les sources de données » ou avec la tâche « Gérer les sources de données ».</span><span class="sxs-lookup"><span data-stu-id="1f198-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="1f198-122">Si tel n'est pas le cas, elle est sans effet puisque l'utilisateur ne peut pas sélectionner l'élément.</span><span class="sxs-lookup"><span data-stu-id="1f198-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f198-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f198-123">See Also</span></span>  
 <span data-ttu-id="1f198-124">[Gérer des sources de données de rapports](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="1f198-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="1f198-125">[Dossiers sécurisés](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="1f198-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="1f198-126">[Sécuriser des rapports et des ressources](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="1f198-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="1f198-127">[Octroi d'autorisations sur un serveur de rapports en mode natif](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="1f198-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="1f198-128">Stocker des informations d’identification dans une source de données Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1f198-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
