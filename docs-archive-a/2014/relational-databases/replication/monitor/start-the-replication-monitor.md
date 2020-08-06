---
title: Démarrer le Moniteur de réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709187"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="1ffce-102">Démarrer le Moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="1ffce-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="1ffce-103">Vous pouvez démarrer le moniteur de réplication depuis [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] dans n'importe quelle instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]ou à partir de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="1ffce-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="1ffce-104">Après avoir démarré le Moniteur de réplication, ajoutez un ou plusieurs serveurs de publication à surveiller.</span><span class="sxs-lookup"><span data-stu-id="1ffce-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="1ffce-105">Pour plus d’informations, consultez [Ajouter et supprimer des serveurs de publication à partir du moniteur de réplication](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="1ffce-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="1ffce-106">Pour démarrer le moniteur de réplication à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ffce-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1ffce-107">Connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="1ffce-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="1ffce-108">Cliquez avec le bouton droit sur le dossier **Réplication** ou sur l'un de ses sous-dossiers, puis cliquez sur **Lancer le Moniteur de réplication**.</span><span class="sxs-lookup"><span data-stu-id="1ffce-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="1ffce-109">Pour démarrer le moniteur de réplication à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="1ffce-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="1ffce-110">À partir de l'invite de commandes, accédez au répertoire d'installation des outils.</span><span class="sxs-lookup"><span data-stu-id="1ffce-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="1ffce-111">Le chemin d'accès par défaut est [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\.</span><span class="sxs-lookup"><span data-stu-id="1ffce-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="1ffce-112">Exécutez sqlmonitor.exe.</span><span class="sxs-lookup"><span data-stu-id="1ffce-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ffce-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ffce-113">See Also</span></span>  
 [<span data-ttu-id="1ffce-114">Surveillance de la réplication</span><span class="sxs-lookup"><span data-stu-id="1ffce-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
