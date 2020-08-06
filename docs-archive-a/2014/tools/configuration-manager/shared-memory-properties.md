---
title: Propriétés de la mémoire partagée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613720"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="f0733-102">Propriétés de Mémoire partagée</span><span class="sxs-lookup"><span data-stu-id="f0733-102">Shared Memory Properties</span></span>
  <span data-ttu-id="f0733-103">La page **Protocole**de la boîte de dialogue **Propriétés de Mémoire partagée** permet d’activer ou de désactiver le protocole de mémoire partagée.</span><span class="sxs-lookup"><span data-stu-id="f0733-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="f0733-104">Il s'agit du protocole le plus simple à utiliser et pour lequel aucun paramètre ne doit être configuré.</span><span class="sxs-lookup"><span data-stu-id="f0733-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="f0733-105">Étant donné que les clients qui utilisent le protocole de mémoire partagée peuvent se connecter uniquement à une instance [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exécutée sur le même ordinateur, ce protocole n’est généralement pas utile pour les activités de base de données.</span><span class="sxs-lookup"><span data-stu-id="f0733-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="f0733-106">Utilisez le protocole de mémoire partagée pour débloquer une situation dans laquelle vous suspectez que les autres protocoles ne sont pas configurés correctement.</span><span class="sxs-lookup"><span data-stu-id="f0733-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f0733-107">doit être redémarré pour activer ou désactiver le protocole.</span><span class="sxs-lookup"><span data-stu-id="f0733-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0733-108">Options</span><span class="sxs-lookup"><span data-stu-id="f0733-108">Options</span></span>  
 <span data-ttu-id="f0733-109">**Activé**</span><span class="sxs-lookup"><span data-stu-id="f0733-109">**Enabled**</span></span>  
 <span data-ttu-id="f0733-110">Les valeurs possibles sont **Yes** et **No**.</span><span class="sxs-lookup"><span data-stu-id="f0733-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="f0733-111">Le protocole de mémoire partagée est activé par défaut.</span><span class="sxs-lookup"><span data-stu-id="f0733-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0733-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0733-112">See Also</span></span>  
 <span data-ttu-id="f0733-113">[Choix d'un protocole réseau](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="f0733-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="f0733-114">Création d'une chaîne de connexion valide à l'aide du protocole de mémoire partagée</span><span class="sxs-lookup"><span data-stu-id="f0733-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
