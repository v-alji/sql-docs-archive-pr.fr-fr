---
title: Informations de référence sur l’interface utilisateur de la boîte de dialogue rôles de package | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703179"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="e16b3-102">Référence de l'interface utilisateur de la boîte de dialogue Rôles de package</span><span class="sxs-lookup"><span data-stu-id="e16b3-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="e16b3-103">Utilisez la boîte de dialogue **Rôles de package** , disponible dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], pour spécifier les rôles au niveau de la base de données qui possèdent un accès en lecture au package et les rôles au niveau de la base de données qui possèdent un accès en écriture au package.</span><span class="sxs-lookup"><span data-stu-id="e16b3-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="e16b3-104">Les rôles au niveau de la base de données s’appliquent uniquement aux packages stockés dans la base de données [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb**.</span><span class="sxs-lookup"><span data-stu-id="e16b3-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="e16b3-105">Pour en savoir plus sur les rôles au niveau de la base de données [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] et leurs autorisations, consultez [Rôles Integration Services &#40;Service SSIS&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="e16b3-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="e16b3-106">Les rôles répertoriés dans la boîte de dialogue sont les rôles actuels de la base de données système **msdb** .</span><span class="sxs-lookup"><span data-stu-id="e16b3-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="e16b3-107">Si aucun rôle n'est sélectionné, les rôles [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] par défaut s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="e16b3-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="e16b3-108">Par défaut, le rôle de lecteur inclut **db_ssisadmin**, **db_ssisoperator**et l’utilisateur qui a créé le package.</span><span class="sxs-lookup"><span data-stu-id="e16b3-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="e16b3-109">Un utilisateur membre de l'un de ces rôles ou qui a créé les packages peut énumérer, consulter, exporter et exécuter des packages.</span><span class="sxs-lookup"><span data-stu-id="e16b3-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="e16b3-110">Par défaut, le rôle de rédacteur inclut **db_ssisadmin** et l’utilisateur qui a créé le package.</span><span class="sxs-lookup"><span data-stu-id="e16b3-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="e16b3-111">Un utilisateur membre de ce rôle et l'utilisateur qui a créé les packages peuvent importer, supprimer et modifier des packages.</span><span class="sxs-lookup"><span data-stu-id="e16b3-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="e16b3-112">La colonne **ownersid** de la table **sysssispackages** contient l'identificateur de sécurité unique de l'utilisateur qui a créé le package.</span><span class="sxs-lookup"><span data-stu-id="e16b3-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e16b3-113">Options</span><span class="sxs-lookup"><span data-stu-id="e16b3-113">Options</span></span>  
 <span data-ttu-id="e16b3-114">**Nom du package**</span><span class="sxs-lookup"><span data-stu-id="e16b3-114">**Package Name**</span></span>  
 <span data-ttu-id="e16b3-115">Spécifiez le nom du package.</span><span class="sxs-lookup"><span data-stu-id="e16b3-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="e16b3-116">**Rôle de lecteur**</span><span class="sxs-lookup"><span data-stu-id="e16b3-116">**Reader Role**</span></span>  
 <span data-ttu-id="e16b3-117">Sélectionnez un rôle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e16b3-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="e16b3-118">**Rôle Rédacteur**</span><span class="sxs-lookup"><span data-stu-id="e16b3-118">**Writer Role**</span></span>  
 <span data-ttu-id="e16b3-119">Sélectionnez un rôle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e16b3-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16b3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e16b3-120">See Also</span></span>  
 <span data-ttu-id="e16b3-121">[Rôles au niveau de la base de données](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="e16b3-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="e16b3-122">Vue d’ensemble de la sécurité &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e16b3-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
