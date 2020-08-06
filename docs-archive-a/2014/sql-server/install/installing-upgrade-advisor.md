---
title: Installation du conseiller de mise à niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- Upgrade Advisor [SQL Server], installing
ms.assetid: 1b7d6eca-1df1-47df-bbba-0fc485706a95
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 40f214b01f3e2066708a060c5f3ad1e8aa4a0a23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697407"
---
# <a name="installing-upgrade-advisor"></a><span data-ttu-id="5490f-102">Installation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="5490f-102">Installing Upgrade Advisor</span></span>
  <span data-ttu-id="5490f-103">L'emplacement d'installation du Conseiller de mise à niveau SQL Server 2014 dépend des éléments que vous allez analyser.</span><span class="sxs-lookup"><span data-stu-id="5490f-103">Where you install SQL Server 2014 Upgrade Advisor depends on what you will be analyzing.</span></span> <span data-ttu-id="5490f-104">Le Conseiller de mise à niveau prend en charge l'analyse à distance de tous les composants [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l'exception de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5490f-104">Upgrade Advisor supports remote analysis of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components except [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5490f-105">Si vous n'analysez pas d'instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez installer le Conseiller de mise à niveau sur n'importe quel ordinateur pouvant se connecter à vos instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]et répondant à la [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5490f-105">If you are not scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can install Upgrade Advisor on any computer that can connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and that meets the [Upgrade Advisor Prerequisites](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md).</span></span> <span data-ttu-id="5490f-106">Si vous analysez des instances de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous devez installer le Conseiller de mise à niveau sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5490f-106">If you are scanning instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must install Upgrade Advisor on the report server.</span></span>  
  
 <span data-ttu-id="5490f-107">Exécutez le fichier **SQLUA.msi** pour installer le Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="5490f-107">Run the **SQLUA.msi** file to install Upgrade Advisor.</span></span> <span data-ttu-id="5490f-108">L’invite de commandes vous permet d’effectuer des installations automatisées et sans assistance.</span><span class="sxs-lookup"><span data-stu-id="5490f-108">You can install from the command prompt for unattended and automated installations.</span></span> <span data-ttu-id="5490f-109">Consultez [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) pour la syntaxe et des exemples.</span><span class="sxs-lookup"><span data-stu-id="5490f-109">See [Installing Upgrade Advisor from the Command Prompt](../../../2014/sql-server/install/installing-upgrade-advisor-from-the-command-prompt.md) for syntax and examples.</span></span>  
  
 <span data-ttu-id="5490f-110">Obtenir SQLUA.msi :</span><span class="sxs-lookup"><span data-stu-id="5490f-110">Get SQLUA.msi:</span></span>  
  
-   <span data-ttu-id="5490f-111">Dans le dossier **redist** du support du produit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5490f-111">In the **redist** folder of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] product media.</span></span>  
  
-   <span data-ttu-id="5490f-112">Dans le cadre du [téléchargement de SQL 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=42295).</span><span class="sxs-lookup"><span data-stu-id="5490f-112">As part of the [SQL 2014 Feature Pack download](https://www.microsoft.com/download/details.aspx?id=42295).</span></span>  
  
## <a name="uninstalling-upgrade-advisor"></a><span data-ttu-id="5490f-113">Désinstallation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="5490f-113">Uninstalling Upgrade Advisor</span></span>  
 <span data-ttu-id="5490f-114">Vous pouvez désinstaller le Conseiller de mise à niveau à l'aide de la fonction **Ajout/Suppression de programmes**.</span><span class="sxs-lookup"><span data-stu-id="5490f-114">You can uninstall Upgrade Advisor by using **Add or Remove Programs**.</span></span> <span data-ttu-id="5490f-115">La syntaxe de l’invite de commandes prend également en charge la suppression/désinstallation.</span><span class="sxs-lookup"><span data-stu-id="5490f-115">The command prompt syntax also supports removal/uninstall.</span></span>  
  
  
