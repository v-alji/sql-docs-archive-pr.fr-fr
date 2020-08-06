---
title: remote admin connections (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613129"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="0ffca-102">remote admin connections (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="0ffca-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0ffca-103">fournit une connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="0ffca-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="0ffca-104">Celle-ci permet à un administrateur d’accéder à un serveur actif pour exécuter des fonctions de diagnostic ou des instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] ou pour résoudre des problèmes sur ce serveur, même s’il est verrouillé, que son état est anormal ou qu’il ne répond pas à une connexion du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ffca-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="0ffca-105">Par défaut, cette connexion n'est disponible qu'à partir d'un client sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="0ffca-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="0ffca-106">Pour autoriser des applications clientes sur des ordinateurs distants à utiliser la connexion administrateur dédiée, utilisez l'option remote admin connections de sp_configure.</span><span class="sxs-lookup"><span data-stu-id="0ffca-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="0ffca-107">Par défaut, la connexion administrateur dédiée n'écoute que sur l'adresse IP (127.0.0.1), port 1434.</span><span class="sxs-lookup"><span data-stu-id="0ffca-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="0ffca-108">Si le port TCP 1434 n’est pas disponible, un port TCP est affecté dynamiquement lors du démarrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ffca-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="0ffca-109">Lorsque plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont installées sur un ordinateur, consultez le journal des erreurs afin de connaître le numéro de port TCP.</span><span class="sxs-lookup"><span data-stu-id="0ffca-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="0ffca-110">Le tableau suivant répertorie les valeurs possibles de l'option remote admin connections.</span><span class="sxs-lookup"><span data-stu-id="0ffca-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="0ffca-111">Valeur</span><span class="sxs-lookup"><span data-stu-id="0ffca-111">Value</span></span>|<span data-ttu-id="0ffca-112">Description</span><span class="sxs-lookup"><span data-stu-id="0ffca-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ffca-113">0</span><span class="sxs-lookup"><span data-stu-id="0ffca-113">0</span></span>|<span data-ttu-id="0ffca-114">Indique que seules les connexions locales sont autorisées à utiliser la connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="0ffca-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="0ffca-115">1</span><span class="sxs-lookup"><span data-stu-id="0ffca-115">1</span></span>|<span data-ttu-id="0ffca-116">Indique que les connexions à distance sont autorisées à utiliser la connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="0ffca-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0ffca-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="0ffca-117">Example</span></span>  
 <span data-ttu-id="0ffca-118">L'exemple suivant active la connexion administrateur dédiée à partir d'un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="0ffca-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ffca-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ffca-119">See Also</span></span>  
 [<span data-ttu-id="0ffca-120">Connexion de diagnostic pour les administrateurs de base de données</span><span class="sxs-lookup"><span data-stu-id="0ffca-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
