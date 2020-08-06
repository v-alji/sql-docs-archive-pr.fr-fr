---
title: Propriétés TCP-IP (onglet Protocoles) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601244"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="5136d-102">Propriétés TCP-IP (onglet Protocoles)</span><span class="sxs-lookup"><span data-stu-id="5136d-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="5136d-103">La boîte de dialogue **Propriétés de TCP/IP** permet de configurer les options du protocole TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="5136d-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="5136d-104">Cliquez sur **TCP/IP** dans le volet gauche pour afficher les configurations de chaque adresse IP dans le volet d’informations.</span><span class="sxs-lookup"><span data-stu-id="5136d-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="5136d-105">Pour appliquer les modifications, redémarrez Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5136d-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5136d-106">Options</span><span class="sxs-lookup"><span data-stu-id="5136d-106">Options</span></span>  
 <span data-ttu-id="5136d-107">**Activé**</span><span class="sxs-lookup"><span data-stu-id="5136d-107">**Enabled**</span></span>  
 <span data-ttu-id="5136d-108">Les valeurs possibles sont **Yes** et **No**.</span><span class="sxs-lookup"><span data-stu-id="5136d-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="5136d-109">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="5136d-109">**Keep Alive**</span></span>  
 <span data-ttu-id="5136d-110">Spécifiez la fréquence (millisecondes) à laquelle les paquets de maintien d'activité sont transmis pour vérifier si l'ordinateur situé à l'extrémité distante d'une connexion est toujours disponible.</span><span class="sxs-lookup"><span data-stu-id="5136d-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="5136d-111">**Écouter tout**</span><span class="sxs-lookup"><span data-stu-id="5136d-111">**Listen All**</span></span>  
 <span data-ttu-id="5136d-112">Spécifiez si SQL Server doit écouter sur toutes les adresses IP liées aux cartes réseau de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5136d-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="5136d-113">Si vous choisissez la valeur **No**, configurez chaque adresse IP séparément en utilisant la boîte de dialogue des propriétés de chaque adresse IP.</span><span class="sxs-lookup"><span data-stu-id="5136d-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="5136d-114">Si vous choisissez la valeur **Yes**, les paramètres de la zone des propriétés de **IPAll** s’appliquent à toutes les adresses IP.</span><span class="sxs-lookup"><span data-stu-id="5136d-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="5136d-115">La valeur par défaut est **Yes**.</span><span class="sxs-lookup"><span data-stu-id="5136d-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="5136d-116">**Aucun délai**</span><span class="sxs-lookup"><span data-stu-id="5136d-116">**No Delay**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5136d-117">n'implémente pas les modifications apportées à cette propriété.</span><span class="sxs-lookup"><span data-stu-id="5136d-117">does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5136d-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5136d-118">See Also</span></span>  
 <span data-ttu-id="5136d-119">[Choix d'un protocole réseau](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="5136d-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="5136d-120">Création d’une chaîne de connexion valide à l’aide du protocole TCP/IP</span><span class="sxs-lookup"><span data-stu-id="5136d-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
