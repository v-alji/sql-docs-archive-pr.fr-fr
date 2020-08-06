---
title: Protocoles clients - Propriétés de Canaux nommés (onglet Protocole) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696359"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="90cbb-102">Protocoles clients - Propriétés de Canaux nommés (onglet Protocole)</span><span class="sxs-lookup"><span data-stu-id="90cbb-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="90cbb-103">Dans le Gestionnaire de configuration [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilisez l'onglet **Protocole** de la boîte de dialogue **Propriétés de Canaux nommés** pour visualiser ou modifier la description du canal par défaut.</span><span class="sxs-lookup"><span data-stu-id="90cbb-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="90cbb-104">Pour vous connecter à un autre canal, tapez son nom dans la zone **Canal par défaut** .</span><span class="sxs-lookup"><span data-stu-id="90cbb-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="90cbb-105">Pour plus d'informations sur les chaînes de connexion, consultez [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="90cbb-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="90cbb-106">Options</span><span class="sxs-lookup"><span data-stu-id="90cbb-106">Options</span></span>  
 <span data-ttu-id="90cbb-107">**Canal par défaut**</span><span class="sxs-lookup"><span data-stu-id="90cbb-107">**Default Pipe**</span></span>  
 <span data-ttu-id="90cbb-108">Spécifie le canal par défaut que la Net-Library des canaux nommés essaie d'utiliser pour se connecter à l'instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90cbb-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="90cbb-109">Par défaut, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est à l'écoute sur : `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="90cbb-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="90cbb-110">Pour vous connecter au canal par défaut, entrez `sql\query`</span><span class="sxs-lookup"><span data-stu-id="90cbb-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="90cbb-111">**Activé**</span><span class="sxs-lookup"><span data-stu-id="90cbb-111">**Enabled**</span></span>  
 <span data-ttu-id="90cbb-112">Les valeurs possibles sont **Yes** et **No**.</span><span class="sxs-lookup"><span data-stu-id="90cbb-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90cbb-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90cbb-113">See Also</span></span>  
 [<span data-ttu-id="90cbb-114">Choix d’un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="90cbb-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
