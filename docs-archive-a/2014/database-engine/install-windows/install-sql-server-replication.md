---
title: Installer la réplication SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- components [SQL Server replication]
- command line installations [SQL Server replication]
- installing replication
- replication [SQL Server], installing
- command prompt [SQL Server replication]
ms.assetid: c50ad078-060b-4a8d-ad45-9e31a8d85729
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ba941fda1d463e7bb4a26bd2fbb45d2a82ca27b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697120"
---
# <a name="install-sql-server-replication"></a><span data-ttu-id="896f1-102">Installer la réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="896f1-102">Install SQL Server Replication</span></span>
  <span data-ttu-id="896f1-103">Les composants de réplication peuvent être installés à l'aide de l'Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou à l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="896f1-103">Replication components can be installed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard or at a command prompt.</span></span> <span data-ttu-id="896f1-104">Installez la réplication lors de l'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou lors de la modification d'une instance existante.</span><span class="sxs-lookup"><span data-stu-id="896f1-104">Install replication when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or when you modify an existing instance.</span></span>  
  
 <span data-ttu-id="896f1-105">Une fois que les composants de réplication sont installés, vous devez configurer le serveur avant de pouvoir utiliser la réplication.</span><span class="sxs-lookup"><span data-stu-id="896f1-105">After replication components are installed, you must configure the server before you can use replication.</span></span> <span data-ttu-id="896f1-106">Pour plus d’informations, consultez [Configurer la distribution](../../relational-databases/replication/configure-distribution.md) dans la documentation en ligne [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="896f1-106">For more information, see [Configure Distribution](../../relational-databases/replication/configure-distribution.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="896f1-107">Si vous installez des composants de réplication lorsque vous modifiez une instance existante de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous devez arrêter et redémarrer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] une fois l'installation terminée.</span><span class="sxs-lookup"><span data-stu-id="896f1-107">If you install replication components when you modify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent after the installation is completed.</span></span> <span data-ttu-id="896f1-108">Cette action garantit que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reconnaît les sous-systèmes de l'agent de réplication et peut appeler les agents de réplication à partir des étapes de travail.</span><span class="sxs-lookup"><span data-stu-id="896f1-108">This action helps ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent recognizes the replication agent subsystems and can call replication agents from job steps.</span></span>  
  
## <a name="installing-replication-by-using-setup"></a><span data-ttu-id="896f1-109">Installation de la réplication à l'aide du programme d'installation</span><span class="sxs-lookup"><span data-stu-id="896f1-109">Installing Replication by Using Setup</span></span>  
 <span data-ttu-id="896f1-110">**Pour installer la réplication en même temps qu’une nouvelle instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="896f1-110">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="896f1-111">Pour installer les composants de réplication, notamment des objets RMO (Replication Management Objects), sélectionnez **Réplication SQL Server** dans la page **Sélection de composant** de l’Assistant Installation.</span><span class="sxs-lookup"><span data-stu-id="896f1-111">To install replication components, including Replication Management Objects (RMO), select **SQL Server Replication** on the **Feature Selection** page of the Installation Wizard.</span></span>  
  
## <a name="installing-replication-from-the-command-prompt"></a><span data-ttu-id="896f1-112">Installation de la réplication à partir de l'invite de commandes</span><span class="sxs-lookup"><span data-stu-id="896f1-112">Installing Replication from the Command Prompt</span></span>  
 <span data-ttu-id="896f1-113">**Pour installer la réplication en même temps qu’une nouvelle instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="896f1-113">**To install replication when installing a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**</span></span>  
  
-   <span data-ttu-id="896f1-114">Consultez [installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="896f1-114">See [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896f1-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="896f1-115">See Also</span></span>  
 <span data-ttu-id="896f1-116">[Installer SQL Server 2014](install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="896f1-116">[Install SQL Server 2014](install-sql-server.md) </span></span>  
 <span data-ttu-id="896f1-117">[Installer SQL Server 2014 à partir de l’invite de commandes](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="896f1-117">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 [<span data-ttu-id="896f1-118">Fonctionnalités prises en charge par les éditions de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="896f1-118">Features Supported by the Editions of SQL Server 2014</span></span>](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
