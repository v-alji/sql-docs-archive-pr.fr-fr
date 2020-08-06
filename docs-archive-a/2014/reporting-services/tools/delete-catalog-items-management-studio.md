---
title: Suppression des éléments du catalogue (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604384"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="0cc69-102">Suppression des éléments du catalogue (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0cc69-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="0cc69-103">Utilisez cette page pour supprimer des planifications partagées et des définitions de rôle.</span><span class="sxs-lookup"><span data-stu-id="0cc69-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="0cc69-104">Si vous supprimez une planification partagée utilisée par plusieurs rapports et abonnements, le serveur de rapports créera des planifications individuelles pour chaque rapport et abonnement qui a précédemment utilisé la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="0cc69-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="0cc69-105">Chaque nouvelle planification individuelle contiendra la date, l'heure et la périodicité spécifiée dans la planification partagée.</span><span class="sxs-lookup"><span data-stu-id="0cc69-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="0cc69-106">Notez que [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ne fournit pas de gestion centrale des planifications individuelles.</span><span class="sxs-lookup"><span data-stu-id="0cc69-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="0cc69-107">Si vous supprimez une planification partagée, vous devez désormais gérer les informations de planification pour chaque élément individuel.</span><span class="sxs-lookup"><span data-stu-id="0cc69-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="0cc69-108">Avant de supprimer une planification partagée, utilisez la [page Rapports](schedule-properties-reports-page.md) pour déterminer les rapports qui l'utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="0cc69-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="0cc69-109">Pour les définitions de rôle, vous ne pouvez supprimer que celles qui ne sont pas utilisées activement dans une attribution de rôle.</span><span class="sxs-lookup"><span data-stu-id="0cc69-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="0cc69-110">Si vous essayez de supprimer un rôle qui est actuellement en cours d'utilisation, le serveur de rapports ne supprimera pas le rôle et un message d'erreur s'affichera à cet effet.</span><span class="sxs-lookup"><span data-stu-id="0cc69-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="0cc69-111">Si cette page contient une définition de rôle unique qui n'est pas actuellement en cours d'utilisation, elle est supprimée lorsque vous cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cc69-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="0cc69-112">Si cette page contient plusieurs rôles, vous ne pouvez pas sélectionner les rôles à conserver ou supprimer.</span><span class="sxs-lookup"><span data-stu-id="0cc69-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="0cc69-113">Toutes les définitions de rôle inutilisées sont supprimées lorsque vous cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cc69-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="0cc69-114">Vous ne pouvez pas annuler une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="0cc69-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="0cc69-115">Pour récupérer un élément supprimé, vous devez le recréer ou restaurer une copie de sauvegarde de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0cc69-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0cc69-116">Options</span><span class="sxs-lookup"><span data-stu-id="0cc69-116">Options</span></span>  
 <span data-ttu-id="0cc69-117">**Nom**</span><span class="sxs-lookup"><span data-stu-id="0cc69-117">**Name**</span></span>  
 <span data-ttu-id="0cc69-118">Spécifie le nom de l'élément à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0cc69-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="0cc69-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="0cc69-119">**Type**</span></span>  
 <span data-ttu-id="0cc69-120">Affiche le type d'élément à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0cc69-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="0cc69-121">**Propriétaire**</span><span class="sxs-lookup"><span data-stu-id="0cc69-121">**Owner**</span></span>  
 <span data-ttu-id="0cc69-122">Affiche le nom du propriétaire.</span><span class="sxs-lookup"><span data-stu-id="0cc69-122">Shows the name of the owner.</span></span> <span data-ttu-id="0cc69-123">Il s'agit de Système dans la plupart des cas.</span><span class="sxs-lookup"><span data-stu-id="0cc69-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="0cc69-124">**État**</span><span class="sxs-lookup"><span data-stu-id="0cc69-124">**Status**</span></span>  
 <span data-ttu-id="0cc69-125">Affiche les informations de progression d'une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="0cc69-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="0cc69-126">**Error**</span><span class="sxs-lookup"><span data-stu-id="0cc69-126">**Error**</span></span>  
 <span data-ttu-id="0cc69-127">Affiche un code d'erreur si une erreur se produit pendant la suppression d'un élément.</span><span class="sxs-lookup"><span data-stu-id="0cc69-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc69-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cc69-128">See Also</span></span>  
 <span data-ttu-id="0cc69-129">[Supprimer un élément &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="0cc69-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="0cc69-130">[Aide du serveur de rapports dans Management Studio accessible par la touche F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0cc69-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="0cc69-131">Créer, modifier et supprimer des planifications</span><span class="sxs-lookup"><span data-stu-id="0cc69-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
