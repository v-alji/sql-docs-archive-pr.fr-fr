---
title: Boîte de dialogue Ajouter une adresse IP (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601708"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="d602e-102">Boîte de dialogue Ajouter une adresse IP (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="d602e-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="d602e-103"> Cette rubrique d’aide F1 décrit les options de la boîte de dialogue **Ajouter une adresse IP**.</span><span class="sxs-lookup"><span data-stu-id="d602e-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="d602e-104">Cette boîte de dialogue accessible depuis la boîte de dialogue **Nouvel écouteur du groupe de disponibilité** et l'onglet **Écouteur** de la page **Spécifier les réplicas** de l' [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] ou l' [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d602e-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d602e-105">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d602e-105">Prerequisites</span></span>  
 <span data-ttu-id="d602e-106">Avant de commencer à ajouter des sous-réseaux à un écouteur de groupe de disponibilité, vérifiez que vous connaissez l'adresse IP de chaque sous-réseau et, pour une adresse IPv4, le masque de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d602e-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a><span data-ttu-id="d602e-107">Options ajouter une adresse IP</span><span class="sxs-lookup"><span data-stu-id="d602e-107">Add IP Address Options</span></span>  
 <span data-ttu-id="d602e-108">**Sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="d602e-108">**Subnet**</span></span>  
 <span data-ttu-id="d602e-109">Utilisez la liste déroulante pour sélectionner une adresse pour le sous-réseau que vous ajoutez à l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d602e-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="d602e-110">Par défaut, un sous-réseau possède une adresse IPv4 et une adresse IPv6.</span><span class="sxs-lookup"><span data-stu-id="d602e-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="d602e-111">La première fois que vous utilisez la boîte de dialogue **Ajouter une adresse IP** , la liste déroulante **Sous-réseau** affiche les deux adresses de sous-réseau pour chaque sous-réseau qui héberge un réplica pour le groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d602e-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="d602e-112">Pour ajouter un sous-réseau donné à l'écouteur, sélectionnez l'une de ses adresses de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d602e-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="d602e-113">Après avoir complété la boîte de dialogue **Ajouter une adresse IP** et cliqué sur **OK** pour ajouter une adresse de sous-réseau sélectionnée à l'écouteur, la liste déroulante **Sous-réseau** filtre cette adresse de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d602e-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="d602e-114">Toutes les adresses de sous-réseau non sélectionnées demeurent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="d602e-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="d602e-115">Assurez-vous que vous ajoutez une et une seule adresse de sous-réseau par sous-réseau à l'écouteur, sinon la création de l'écouteur échoue.</span><span class="sxs-lookup"><span data-stu-id="d602e-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="d602e-116">**Adresses**</span><span class="sxs-lookup"><span data-stu-id="d602e-116">**Addresses**</span></span>  
 <span data-ttu-id="d602e-117">Utilisez ce champ pour entrer une adresse IP statique pour l'adresse de sous-réseau sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d602e-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="d602e-118">Contactez l'administrateur réseau pour connaître cette adresse IP.</span><span class="sxs-lookup"><span data-stu-id="d602e-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="d602e-119">Assurez-vous que vous entrez une adresse valide pour l'adresse de sous-réseau sélectionnée, sinon la création de l'écouteur échoue.</span><span class="sxs-lookup"><span data-stu-id="d602e-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="d602e-120">**Adresse IPv4**</span><span class="sxs-lookup"><span data-stu-id="d602e-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="d602e-121">Si vous avez sélectionné l'adresse de sous-réseau IPv4 d'un sous-réseau, entrez une adresse IPv4 statique valide ici.</span><span class="sxs-lookup"><span data-stu-id="d602e-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="d602e-122">**Masque de sous-réseau**</span><span class="sxs-lookup"><span data-stu-id="d602e-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="d602e-123">Pour une adresse IPv4, ce champ en lecture seule affiche le masque de sous-réseau du sous-réseau sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d602e-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="d602e-124">**Adresse IPv6**</span><span class="sxs-lookup"><span data-stu-id="d602e-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="d602e-125">Si vous avez sélectionné l'adresse de sous-réseau IPv6 d'un sous-réseau, entrez une adresse IPv6 statique valide ici.</span><span class="sxs-lookup"><span data-stu-id="d602e-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="d602e-126">**OK**</span><span class="sxs-lookup"><span data-stu-id="d602e-126">**OK**</span></span>  
 <span data-ttu-id="d602e-127">Cliquez pour créer et ajouter le sous-réseau dont vous avez sélectionné l'adresse, avec l'adresse IP statique que vous avez spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d602e-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="d602e-128">Une ligne contenant ces valeurs sera ajoutée à la grille de sous-réseau de la boîte de dialogue **Nouvel écouteur du groupe de disponibilité** ou **Spécifier les réplicas** .</span><span class="sxs-lookup"><span data-stu-id="d602e-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d602e-129">La boîte de dialogue **Ajouter une adresse IP** ne vérifie pas l'adresse IP.</span><span class="sxs-lookup"><span data-stu-id="d602e-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="d602e-130">De plus, la boîte de dialogue ne vous empêche pas d'ajouter la deuxième adresse de sous-réseau pour un sous-réseau que vous avez déjà ajouté à l'écouteur du groupe de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d602e-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="d602e-131">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="d602e-131">**Cancel**</span></span>  
 <span data-ttu-id="d602e-132">Cliquez pour annuler vos sélections et revenir à la boîte de dialogue **Nouvel écouteur du groupe de disponibilité** ou à l’onglet **Écouteur** sans ajouter une adresse IP statique pour un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="d602e-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d602e-133">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="d602e-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d602e-134">Créer ou configurer un écouteur de groupe de disponibilité &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d602e-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="d602e-135">Utiliser la boîte de dialogue Nouveau groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d602e-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="d602e-136">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d602e-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="d602e-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d602e-137">See Also</span></span>  
 <span data-ttu-id="d602e-138">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d602e-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="d602e-139">[Écouteurs de groupe de disponibilité, connectivité client et basculement d’application &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="d602e-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="d602e-140">Connectivité client AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d602e-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
