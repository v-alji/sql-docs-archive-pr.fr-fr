---
title: Mapper les ports TCP/IP aux nœuds NUMA (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696052"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="38c8b-102">Mapper les ports TCP/IP aux nœuds NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="38c8b-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="38c8b-103">Cette rubrique explique comment mapper des ports TCP/IP à des nœuds NUMA (Non-Uniform Memory Access) à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38c8b-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="38c8b-104">Au démarrage, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] écrit les informations relatives aux nœuds dans le journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="38c8b-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="38c8b-105">Pour déterminer quel numéro de nœud utiliser, consultez les informations sur les nœuds dans le journal des erreurs ou dans la vue **sys.dm_os_schedulers** .</span><span class="sxs-lookup"><span data-stu-id="38c8b-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="38c8b-106">Pour définir l'adresse et le port TCP/IP d'un ou de plusieurs nœuds, ajoutez une bitmap d'identification de nœud (masque d'affinité) entre crochets après le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="38c8b-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="38c8b-107">Les nœuds peuvent être spécifiés au format décimal ou hexadécimal.</span><span class="sxs-lookup"><span data-stu-id="38c8b-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="38c8b-108">Pour créer la bitmap, numérotez d'abord les nœuds de droite à gauche en commençant par zéro (par exemple, 76543210).</span><span class="sxs-lookup"><span data-stu-id="38c8b-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="38c8b-109">Créez une représentation binaire de la liste des nœuds en attribuant la valeur 1 aux nœuds que vous souhaitez utiliser et la valeur 0 aux nœuds que vous ne souhaitez pas utiliser.</span><span class="sxs-lookup"><span data-stu-id="38c8b-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="38c8b-110">Par exemple, pour utiliser les nœuds NUMA 0, 2 et 5, spécifiez 00100101.</span><span class="sxs-lookup"><span data-stu-id="38c8b-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38c8b-111">Numéro de nœud NUMA</span><span class="sxs-lookup"><span data-stu-id="38c8b-111">NUMA node number</span></span>|<span data-ttu-id="38c8b-112">76543210</span><span class="sxs-lookup"><span data-stu-id="38c8b-112">76543210</span></span>|  
|<span data-ttu-id="38c8b-113">Masque pour 0, 2 et 5 en comptant à partir de la droite</span><span class="sxs-lookup"><span data-stu-id="38c8b-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="38c8b-114">00100101</span><span class="sxs-lookup"><span data-stu-id="38c8b-114">00100101</span></span>|  
  
 <span data-ttu-id="38c8b-115">Convertissez la représentation binaire (00100101) au format décimal `[37]`ou hexadécimal `[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="38c8b-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="38c8b-116">Pour écouter tous les nœuds, n'indiquez aucun identificateur de nœud.</span><span class="sxs-lookup"><span data-stu-id="38c8b-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="38c8b-117">Si un port est mappé à plusieurs nœuds NUMA, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attribue les connexions aux nœuds les unes après les autres sans chercher à équilibrer la charge entre les nœuds.</span><span class="sxs-lookup"><span data-stu-id="38c8b-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38c8b-118">Pour activer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour écouter sur plusieurs ports TCP pour chaque adresse IP, consultez [Configurer le moteur de base de données de manière à écouter sur plusieurs ports TCP](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span><span class="sxs-lookup"><span data-stu-id="38c8b-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="38c8b-119">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="38c8b-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="38c8b-120">Pour mapper un port TCP/IP à un nœud NUMA</span><span class="sxs-lookup"><span data-stu-id="38c8b-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="38c8b-121">Dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Gestionnaire de configuration **, développez Configuration du réseau SQL Server**, puis cliquez sur**Protocoles pour** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="38c8b-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="38c8b-122">Dans le volet de détails, double-cliquez sur **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="38c8b-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="38c8b-123">Sous l'onglet **Adresses IP** , dans la zone **Port TCP** de la section correspondant à l'adresse IP à configurer, ajoutez l'identificateur du nœud NUMA entre crochets, après le numéro de port.</span><span class="sxs-lookup"><span data-stu-id="38c8b-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="38c8b-124">Par exemple, pour le port TCP 1500 et les nœuds 0, 2 et 5, utilisez `1500[37]` ou `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="38c8b-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c8b-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="38c8b-125">See Also</span></span>  
 [<span data-ttu-id="38c8b-126">Configurez SQL Server pour utiliser le &#40;soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="38c8b-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
