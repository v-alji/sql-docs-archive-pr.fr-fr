---
title: Stockage de Gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699456"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="4dc22-102">Stockage de Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="4dc22-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="4dc22-103">Les stratégies sont stockées dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="4dc22-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="4dc22-104">Après la modification d'une stratégie ou d'une condition, vous devez sauvegarder msdb.</span><span class="sxs-lookup"><span data-stu-id="4dc22-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="4dc22-105">Pour plus d’informations, consultez [Sauvegarder et restaurer des bases de données système &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4dc22-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="4dc22-106">Stockage des stratégies</span><span class="sxs-lookup"><span data-stu-id="4dc22-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="4dc22-107">est fourni avec des stratégies qui peuvent être utilisées pour contrôler une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc22-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4dc22-108">Par défaut, ces stratégies ne sont pas installées sur le [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; Toutefois, elles peuvent être importées à partir de l’emplacement d’installation par défaut C:\Program Files (x86) \Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="4dc22-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="4dc22-109">Vous pouvez créer directement des stratégies à l’aide du menu **Fichier/Nouveau** , puis les enregistrer dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="4dc22-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="4dc22-110">Cela vous permet de créer des stratégies quand vous n’êtes pas connecté à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dc22-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4dc22-111">L’historique de stratégie pour les stratégies évaluées dans l’instance actuelle du [!INCLUDE[ssDE](../../includes/ssde-md.md)] est conservé dans les tables système msdb.</span><span class="sxs-lookup"><span data-stu-id="4dc22-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="4dc22-112">L'historique de stratégie pour les stratégies appliquées à d'autres instances du [!INCLUDE[ssDE](../../includes/ssde-md.md)] ou appliquées à [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ou à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] n'est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="4dc22-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
