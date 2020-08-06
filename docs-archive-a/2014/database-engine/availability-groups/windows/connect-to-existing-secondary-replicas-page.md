---
title: Page se connecter à des réplicas secondaires existants (Assistant Ajout de réplica et Assistant Ajout de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697188"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="df98e-102">Page Se connecter à la page à des réplicas secondaires existants (Assistant Ajout de réplica et Assistant Ajout de bases de données)</span><span class="sxs-lookup"><span data-stu-id="df98e-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="df98e-103"> Cette rubrique d’aide décrit les options de la page **Se connecter à des réplicas secondaires existants**.</span><span class="sxs-lookup"><span data-stu-id="df98e-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="df98e-104">Cette rubrique est utilisée par l' [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] et par l' [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df98e-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="df98e-105">**Colonnes de la grille :**</span><span class="sxs-lookup"><span data-stu-id="df98e-105">**Grid columns:**</span></span>  
 <span data-ttu-id="df98e-106">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="df98e-106">**Server Instance**</span></span>  
 <span data-ttu-id="df98e-107">Affiche le nom de l'instance du serveur qui hébergera le réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="df98e-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="df98e-108">**Connecté en tant que**</span><span class="sxs-lookup"><span data-stu-id="df98e-108">**Connected As**</span></span>  
 <span data-ttu-id="df98e-109">Affiche le compte qui est connecté à l'instance de serveur, une fois que la connexion a été établie.</span><span class="sxs-lookup"><span data-stu-id="df98e-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="df98e-110">Si cette colonne affiche «**Non connecté**» pour une instance de serveur donnée, vous devez cliquer sur le bouton **Se connecter** ou **Se connecter à tous** .</span><span class="sxs-lookup"><span data-stu-id="df98e-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="df98e-111">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="df98e-111">**Connect**</span></span>  
 <span data-ttu-id="df98e-112">Cliquez sur ce bouton si cette instance de serveur s'exécute sous un compte différent de celui des autres instances de serveur auxquelles vous devez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="df98e-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="df98e-113">**Se connecter à tous**</span><span class="sxs-lookup"><span data-stu-id="df98e-113">**Connect All**</span></span>  
 <span data-ttu-id="df98e-114">Cliquez sur ce bouton uniquement si chaque instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à laquelle vous devez vous connecter s'exécute en tant que service dans le même compte d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df98e-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="df98e-115">**Annuler**</span><span class="sxs-lookup"><span data-stu-id="df98e-115">**Cancel**</span></span>  
 <span data-ttu-id="df98e-116">Cliquez pour annuler l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="df98e-116">Click to cancel the wizard.</span></span> <span data-ttu-id="df98e-117">Dans la page **Se connecter à des réplicas secondaires existants** , l’annulation de l’Assistant provoque sa fermeture sans effectuer aucune action.</span><span class="sxs-lookup"><span data-stu-id="df98e-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="df98e-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="df98e-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="df98e-119">Utiliser l’Assistant Ajouter un réplica au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="df98e-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="df98e-120">Utiliser l’Assistant Ajouter une base de données au groupe de disponibilité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="df98e-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="df98e-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df98e-121">See Also</span></span>  
 [<span data-ttu-id="df98e-122">Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="df98e-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
