---
title: Conditions préalables pour le conseiller de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- requirements [Upgrade Advisor]
- software [Upgrade Advisor]
- system requirements [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, prerequisites
- prerequisites [Upgrade Advisor]
- Upgrade Advisor [SQL Server], prerequisites
ms.assetid: d21a39e5-5f81-4096-a7dd-f244e4779992
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 41c97cf585d1768c7aebeec2613ee8744cb220da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604863"
---
# <a name="upgrade-advisor-prerequisites"></a><span data-ttu-id="4798c-102">Configuration requise par le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="4798c-102">Upgrade Advisor Prerequisites</span></span>
  <span data-ttu-id="4798c-103">Cette rubrique décrit la configuration logicielle requise par le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4798c-103">This topic describes the software requirements for Upgrade Advisor.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4798c-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="4798c-104">Prerequisites</span></span>  
 <span data-ttu-id="4798c-105">La configuration requise pour l'installation et l'exécution du Conseiller de mise à niveau est la suivante :</span><span class="sxs-lookup"><span data-stu-id="4798c-105">The prerequisites for installing and running Upgrade Advisor are as follows:</span></span>  
  
-   [!INCLUDE[wiprlhext](../../includes/wiprlhext-md.md)] <span data-ttu-id="4798c-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] depuis SP2, Windows 7 ou [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span><span class="sxs-lookup"><span data-stu-id="4798c-106">SP1, [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] beginning with SP2, Windows 7, or [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] R2.</span></span>  
  
-   <span data-ttu-id="4798c-107">Windows Installer 4.5.</span><span class="sxs-lookup"><span data-stu-id="4798c-107">Windows Installer 4.5.</span></span> <span data-ttu-id="4798c-108">Vous pouvez installer Windows Installer à partir du [site Web Windows Installer](https://www.microsoft.com/download/details.aspx?id=8483).</span><span class="sxs-lookup"><span data-stu-id="4798c-108">You can install Windows Installer from the [Windows Installer Web site](https://www.microsoft.com/download/details.aspx?id=8483).</span></span>  
  
-   <span data-ttu-id="4798c-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], depuis .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4798c-109">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], beginning with .NET Framework 4.</span></span> <span data-ttu-id="4798c-110">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]Est disponible sur le [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support du produit, et à partir du [Kit de développement logiciel (SDK), redistribuable et Service Pack site Web de téléchargement](https://go.microsoft.com/fwlink/?LinkId=48882).</span><span class="sxs-lookup"><span data-stu-id="4798c-110">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] is available on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] product media, and from the [SDK, redistributable, and service pack download Web site](https://go.microsoft.com/fwlink/?LinkId=48882).</span></span>  
  
    -   <span data-ttu-id="4798c-111">Pour installer .NET Framework 4 à partir du support de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], localisez la racine du lecteur de disque.</span><span class="sxs-lookup"><span data-stu-id="4798c-111">To install the .NET Framework 4 from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] media, locate the root of the disk drive.</span></span> <span data-ttu-id="4798c-112">Ensuite, double-cliquez sur le dossier \redist, sur le dossier DotNetFrameworks et exécutez dotNetFx40_Full_x86_x64.exe (pour les systèmes d'exploitation 32 bits et 64 bits).</span><span class="sxs-lookup"><span data-stu-id="4798c-112">Then double-click the \redist folder, double-click the DotNetFrameworks folder, and run dotNetFx40_Full_x86_x64.exe (for both 32-bit and 64-bit operating systems).</span></span>  
  
-   <span data-ttu-id="4798c-113">Le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom est un composant requis pour l’installation du [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] conseiller de mise à niveau et n’est pas installé par le programme d’installation du conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="4798c-113">The [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom is a prerequisite for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor, and is not installed by Upgrade Advisor Setup.</span></span> <span data-ttu-id="4798c-114">Le programme d’installation vous demande de télécharger et d’installer le [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom à partir du [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span><span class="sxs-lookup"><span data-stu-id="4798c-114">The Setup requires you to download and install the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4798c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4798c-115">See Also</span></span>  
 [<span data-ttu-id="4798c-116">Procédure : installer le Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="4798c-116">How to: Install Upgrade Advisor</span></span>](../../../2014/sql-server/install/how-to-install-upgrade-advisor.md)  
  
  
