---
title: Classement du serveur de Moteur de base de données incompatible (conseiller de mise à niveau) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613784"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="c7113-102">Classement du serveur du moteur de base de données incompatible (Conseiller de mise à niveau)</span><span class="sxs-lookup"><span data-stu-id="c7113-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="c7113-103">Le conseiller de mise à niveau détecté utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configuré pour utiliser un classement de serveur incompatible.</span><span class="sxs-lookup"><span data-stu-id="c7113-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c7113-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c7113-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c7113-105">Composant</span><span class="sxs-lookup"><span data-stu-id="c7113-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c7113-106">Description</span><span class="sxs-lookup"><span data-stu-id="c7113-106">Description</span></span>  
 <span data-ttu-id="c7113-107">Le conseiller de mise à niveau détecté utilise [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configuré pour utiliser un classement de serveur incompatible.</span><span class="sxs-lookup"><span data-stu-id="c7113-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="c7113-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Le mode SharePoint utilise l’architecture des services partagés SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c7113-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="c7113-109">SharePoint ne prend pas en charge le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configuré pour respecter la casse ou des classements du serveur ou des classements du serveur binaires.</span><span class="sxs-lookup"><span data-stu-id="c7113-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="c7113-110">Les classements incompatibles incluent les classements qui respectent la casse par défaut ou binaires et un classement de base qui est par défaut compatible, a ont été configuré avec l'un des indicateurs de classement suivants :</span><span class="sxs-lookup"><span data-stu-id="c7113-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="c7113-111">**Binaire**</span><span class="sxs-lookup"><span data-stu-id="c7113-111">**Binary**</span></span>  
  
-   <span data-ttu-id="c7113-112">**Respect de la casse**</span><span class="sxs-lookup"><span data-stu-id="c7113-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="c7113-113">**Point de code binaire**</span><span class="sxs-lookup"><span data-stu-id="c7113-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="c7113-114">Étant donné que le classement du serveur du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] actuel est incompatible, la mise à niveau est bloquée.</span><span class="sxs-lookup"><span data-stu-id="c7113-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c7113-115">Action corrective</span><span class="sxs-lookup"><span data-stu-id="c7113-115">Corrective Action</span></span>  
 <span data-ttu-id="c7113-116">La propriété de classement du serveur du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ne peut pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="c7113-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="c7113-117">Vous ne pouvez pas effectuer une mise à niveau de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7113-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="c7113-118">Vous devez migrer votre installation de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sur un nouveau serveur qui utilise un classement du serveur compatible.</span><span class="sxs-lookup"><span data-stu-id="c7113-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="c7113-119">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7113-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="c7113-120">Mettre à niveau et migrer Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c7113-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="c7113-121">Choix d'un classement SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7113-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
