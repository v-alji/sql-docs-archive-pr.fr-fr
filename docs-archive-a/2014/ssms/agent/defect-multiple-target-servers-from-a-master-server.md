---
title: Annuler l’inscription de plusieurs serveurs cibles dans un serveur maître | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699222"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="7ade6-102">Annuler l'inscription de plusieurs serveurs cibles dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="7ade6-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="7ade6-103">Cette rubrique explique comment annuler l'inscription de plusieurs serveurs cibles sur une configuration d'administration multiserveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ade6-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7ade6-104">Exécutez la procédure suivante à partir du serveur maître :</span><span class="sxs-lookup"><span data-stu-id="7ade6-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7ade6-105">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7ade6-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="7ade6-106">Pour annuler l'inscription de plusieurs serveurs cibles dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="7ade6-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="7ade6-107">Dans l' **Explorateur d'objets**, développez un serveur configuré en tant que serveur maître.</span><span class="sxs-lookup"><span data-stu-id="7ade6-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="7ade6-108">Cliquez avec le bouton droit sur **Agent SQL Server**, pointez sur **Administration multiserveur**, puis cliquez sur **Gérer les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="7ade6-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="7ade6-109">Cliquez sur **Publier les instructions**puis, dans la liste **Type d'instruction** , sélectionnez **Désinscrire**.</span><span class="sxs-lookup"><span data-stu-id="7ade6-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="7ade6-110">Sous **Destinataires**, activez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7ade6-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="7ade6-111">**Tous les serveurs cibles** pour annuler l'inscription de tous les serveurs cibles de ce serveur principal.</span><span class="sxs-lookup"><span data-stu-id="7ade6-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="7ade6-112">Utilisez cette option si vous souhaitez désinstaller complètement la configuration de l'administration multiserveur active.</span><span class="sxs-lookup"><span data-stu-id="7ade6-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="7ade6-113">**Serveurs cibles sélectionnés**, puis cliquez sur la zone **Sélectionner** correspondante afin d'annuler l'inscription de certains serveurs cibles (mais pas tous) de ce serveur maître.</span><span class="sxs-lookup"><span data-stu-id="7ade6-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ade6-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7ade6-114">See Also</span></span>  
 <span data-ttu-id="7ade6-115">[Créer un environnement multiserveur](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="7ade6-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="7ade6-116">[Administration automatisée à l'échelle d'une entreprise](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="7ade6-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="7ade6-117">Annuler l’inscription d’un serveur cible dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="7ade6-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
