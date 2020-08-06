---
title: Définir le seuil et la durée d’inactivité de l’UC (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710096"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="5d020-102">Définir le seuil et la durée d'inactivité de l'UC (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5d020-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5d020-103">Cette rubrique indique comment définir la condition d'inactivité de l'UC pour votre serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] au moyen de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d020-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5d020-104">La définition de l’inactivité de l’UC influence la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] réponse de l’agent aux événements.</span><span class="sxs-lookup"><span data-stu-id="5d020-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="5d020-105">Par exemple, supposons que vous définissez la condition d'inactivité de l'UC comme une utilisation UC moyenne tombant sous 10 % et restant à ce niveau pendant 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="5d020-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="5d020-106">Ensuite, si vous avez défini des travaux à exécuter lorsque l'UC du serveur atteint une condition d'inactivité, le travail démarre lorsque l'utilisation de l'UC tombe sous 10 % et reste à ce niveau pendant 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="5d020-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="5d020-107">S'il s'agit d'un travail qui a un impact significatif sur les performances de votre serveur, la définition de la condition d'inactivité de l'UC est importante.</span><span class="sxs-lookup"><span data-stu-id="5d020-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5d020-108">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5d020-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="5d020-109">Pour définir le seuil et la durée d'inactivité de l'UC</span><span class="sxs-lookup"><span data-stu-id="5d020-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="5d020-110">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="5d020-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5d020-111">Cliquez avec le bouton droit sur **Agent SQL Server**, cliquez sur **Propriétés**, puis sélectionnez la page **Avancé** .</span><span class="sxs-lookup"><span data-stu-id="5d020-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="5d020-112">Sous **Condition d'inactivité de l'UC**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5d020-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="5d020-113">Activez la case à cocher **Définir la condition d'inactivité de l'UC**.</span><span class="sxs-lookup"><span data-stu-id="5d020-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="5d020-114">Spécifiez un pourcentage pour la zone **La moyenne d’utilisation de l’UC tombe en dessous de** (tous les UC).</span><span class="sxs-lookup"><span data-stu-id="5d020-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="5d020-115">Cette intervention définit le niveau d'utilisation sous lequel l'UC doit tomber avant d'être considérée inactive.</span><span class="sxs-lookup"><span data-stu-id="5d020-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="5d020-116">Spécifiez un nombre de secondes pour la zone **Et reste sous ce niveau pendant** .</span><span class="sxs-lookup"><span data-stu-id="5d020-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="5d020-117">Cette intervention définit la durée d'utilisation d'UC minimale au terme de laquelle l'UC est considérée inactive.</span><span class="sxs-lookup"><span data-stu-id="5d020-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  
