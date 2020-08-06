---
title: Configuration réseau du cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604949"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="c457f-102">Configuration du réseau du cluster</span><span class="sxs-lookup"><span data-stu-id="c457f-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="c457f-103">Utilisez la page **Sélection du réseau du cluster** pour spécifier les ressources réseau de votre instance de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="c457f-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c457f-104">Options</span><span class="sxs-lookup"><span data-stu-id="c457f-104">Options</span></span>  
 <span data-ttu-id="c457f-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Nom réseau du cluster de basculement\*\* : il s’agit du nom utilisé pour identifier votre instance de cluster de basculement sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c457f-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="c457f-106">**Paramètres réseau** : spécifiez le type IP et l’adresse IP de votre instance de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="c457f-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="c457f-107">Lors des opérations Ajouter un nœud et Supprimer un nœud, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affiche une liste en lecture seule des adresses IP existantes pour le cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c457f-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="c457f-108">Installation intégrée :</span><span class="sxs-lookup"><span data-stu-id="c457f-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="c457f-109">Si vous ajoutez un nœud qui prend en charge un ensemble identique des sous-réseaux de réseau pris en charge par les nœuds existants du cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , aucune adresse IP supplémentaire ne peut être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="c457f-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="c457f-110">Le paramètre de dépendance reste inchangé.</span><span class="sxs-lookup"><span data-stu-id="c457f-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="c457f-111">Si vous ajoutez un nœud qui prend en charge un sous-ensemble des sous-réseaux pris en charge par les nœuds existants du cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , aucune ressource d'adresse IP supplémentaire ne peut être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="c457f-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="c457f-112">La dépendance de ressource d'adresse IP est définie sur OR pour prendre en compte le fait que toutes les adresses IP spécifiées ne sont pas valides sur l'ensemble des nœuds de cluster.</span><span class="sxs-lookup"><span data-stu-id="c457f-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="c457f-113">Si vous ajoutez un nœud qui prend en charge des sous-réseaux en plus de ceux déjà pris en charge par les nœuds existants sur le cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous avez la possibilité d'ajouter de nouvelles adresses IP valides.</span><span class="sxs-lookup"><span data-stu-id="c457f-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="c457f-114">Si de nouvelles adresses IP sont spécifiées, la dépendance de ressource d'adresse IP est définie sur OR pour prendre en compte le fait que toutes les adresses IP spécifiées ne sont pas valides sur l'ensemble des nœuds de cluster.</span><span class="sxs-lookup"><span data-stu-id="c457f-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="c457f-115">Si vous ajoutez un nœud qui prend en charge des sous-réseaux de réseau supplémentaires, mais aucun des sous-réseaux pris en charge par les nœuds existants sur le cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez ajouter des adresses IP supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c457f-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="c457f-116">La dépendance de ressource d'adresse IP est définie sur OR pour prendre en compte le fait que toutes les adresses IP spécifiées ne sont pas valides sur l'ensemble des nœuds de cluster.</span><span class="sxs-lookup"><span data-stu-id="c457f-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="c457f-117">Installation avancée : lors de l'étape de fin de l'installation, spécifiez l'adresse IP de tous les nœuds et sous-réseaux pour votre instance de cluster de basculement.</span><span class="sxs-lookup"><span data-stu-id="c457f-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="c457f-118">Vous pouvez spécifier plusieurs adresses IP pour un cluster de basculement de sous-réseaux multiples, mais une seule adresse IP par sous-réseau est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c457f-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="c457f-119">Chaque nœud préparé doit être le propriétaire d'au moins une adresse IP.</span><span class="sxs-lookup"><span data-stu-id="c457f-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="c457f-120">Si vous avez plusieurs sous-réseaux dans votre cluster de basculement [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous êtes invité à définir la dépendance de ressource d'adresse IP sur OR. Supprimer un nœud :</span><span class="sxs-lookup"><span data-stu-id="c457f-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="c457f-121">Si les adresses IP restantes sont prises en charge sur tous les nœuds restants, vous êtes invité à définir la dépendance de ressource d'adresse IP sur AND.</span><span class="sxs-lookup"><span data-stu-id="c457f-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="c457f-122">Si les adresses IP restantes ne sont pas prises en charge sur tous les nœuds restants, la dépendance de ressource d'adresse IP reste sur OR.</span><span class="sxs-lookup"><span data-stu-id="c457f-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
