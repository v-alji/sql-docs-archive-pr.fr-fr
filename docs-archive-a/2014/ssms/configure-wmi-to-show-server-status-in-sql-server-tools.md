---
title: Configurer WMI pour afficher l’état du serveur dans les outils SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705856"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="7a43e-102">Configurer WMI pour afficher l'état du serveur dans les outils SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a43e-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="7a43e-103">Cette rubrique explique comment configurer WMI pour afficher l'état du serveur dans les outils SQL Server dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a43e-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7a43e-104">Lors de la connexion aux serveurs, les composants Serveurs inscrits et Explorateur d'objets de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], ainsi que le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , utilisent WMI (Windows Management Instrumentation) pour obtenir l'état des services [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) et [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="7a43e-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="7a43e-105">Pour afficher l'état du service, l'utilisateur doit disposer des droits d'accéder à distance à l'objet WMI.</span><span class="sxs-lookup"><span data-stu-id="7a43e-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="7a43e-106">Cette autorisation peut être configurée seulement si WMI a été installé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7a43e-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="7a43e-107">Pour configurer l’autorisation WMI</span><span class="sxs-lookup"><span data-stu-id="7a43e-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="7a43e-108">Sur le serveur distant, dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7a43e-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="7a43e-109">Dans la zone **ouvrir** `wmimgmt.msc` , tapez, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a43e-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="7a43e-110">Dans le programme **Windows Management Infrastructure** , cliquez avec le bouton droit sur **Contrôle WMI (local)** , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7a43e-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="7a43e-111">Dans la boîte de dialogue **Propriétés de WMI Control (Local)** , sous l’onglet **Sécurité** , développez **Root**, puis cliquez sur **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="7a43e-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="7a43e-112">Cliquez sur **Sécurité** pour ouvrir la boîte de dialogue **Sécurité pour ROOT\CIMV2** .</span><span class="sxs-lookup"><span data-stu-id="7a43e-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="7a43e-113">Ajoutez un groupe ou un utilisateur à la zone **Noms de groupes ou d’utilisateurs** et sélectionnez-le.</span><span class="sxs-lookup"><span data-stu-id="7a43e-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="7a43e-114">Dans la zone **Autorisations pour** _\<group or user>_ , sélectionnez la colonne **Autoriser** correspondant à l’autorisation **Appel à distance autorisé** , pour les utilisateurs dont vous souhaitez détecter à distance l’état de service.</span><span class="sxs-lookup"><span data-stu-id="7a43e-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a43e-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7a43e-115">See Also</span></span>  
 [<span data-ttu-id="7a43e-116">Démarrer, arrêter ou suspendre le service SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="7a43e-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
