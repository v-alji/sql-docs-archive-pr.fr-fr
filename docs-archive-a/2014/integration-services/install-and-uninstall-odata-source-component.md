---
title: Installer et désinstaller le composant source OData | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0a3ae788-e8c8-4a4d-bb15-34c673abcd17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad0a86c6226f408b0495569d0a853dd7340aeca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605640"
---
# <a name="install-and-uninstall-odata-source-component"></a><span data-ttu-id="17120-102">Installer et désinstaller le composant source OData</span><span class="sxs-lookup"><span data-stu-id="17120-102">Install and Uninstall OData Source Component</span></span>
  <span data-ttu-id="17120-103">Cette rubrique fournit des instructions pour installer ou supprimer le composant source OData sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="17120-103">This topic provides instructions for installing or removing OData Source Component on your computer.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="17120-104">Installation</span><span class="sxs-lookup"><span data-stu-id="17120-104">Installation</span></span>  
 <span data-ttu-id="17120-105">Le composant source OData requiert les composants suivants et sera installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="17120-105">The OData Source Component requires following prerequisite components to be installed on your computer.</span></span>  
  
-   <span data-ttu-id="17120-106">SQL Server Data Tools (pour concevoir des packages)</span><span class="sxs-lookup"><span data-stu-id="17120-106">SQL Server Data Tools (to design packages)</span></span>  
  
-   <span data-ttu-id="17120-107">SQL Server Integration Services (pour exécuter des packages hors de Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="17120-107">SQL Server Integration Services (to run packages outside Visual Studio)</span></span>  
  
 <span data-ttu-id="17120-108">Pour installer le composant source OData, téléchargez [SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/p/?LinkId=391999) et exécutez l'un des fichiers MSI suivants.</span><span class="sxs-lookup"><span data-stu-id="17120-108">To install the OData Source Component, download [SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/p/?LinkId=391999) and run one of the following MSI files.</span></span>  
  
-   <span data-ttu-id="17120-109">ODataSourceForSQLServer2014-amd64.msi pour les plateformes 64 bits</span><span class="sxs-lookup"><span data-stu-id="17120-109">ODataSourceForSQLServer2014-amd64.msi for 64bit platforms</span></span>  
  
-   <span data-ttu-id="17120-110">ODataSourceForSQLServer2014-x86.msi pour les plateformes 32 bits</span><span class="sxs-lookup"><span data-stu-id="17120-110">ODataSourceForSQLServer2014-x86.msi for 32bit platforms</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="17120-111">Le programme d'installation 64 bits installera les versions 32 bits et 64 bits du composant source OData.</span><span class="sxs-lookup"><span data-stu-id="17120-111">The 64bit installer will install both 32bit and 64bit versions of the OData Source Component.</span></span> <span data-ttu-id="17120-112">Exécutez uniquement le programme d'installation 32 bits si vous utilisez un système d'exploitation 32 bits.</span><span class="sxs-lookup"><span data-stu-id="17120-112">You only need to run the 32bit installer if you are using a 32bit OS.</span></span>  
  
## <a name="uninstallation"></a><span data-ttu-id="17120-113">Désinstallation</span><span class="sxs-lookup"><span data-stu-id="17120-113">Uninstallation</span></span>  
 <span data-ttu-id="17120-114">Le composant source OData peut être désinstallé à partir du menu **Programmes et fonctionnalités** .</span><span class="sxs-lookup"><span data-stu-id="17120-114">The OData Source component can be uninstalled from the **Programs and Features** menu.</span></span> <span data-ttu-id="17120-115">Recherchez l'entrée **Composant source OData Microsoft SQL Server SSIS (x64)** et cliquez sur **Désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="17120-115">Find the **Microsoft SQL Server SSIS OData Source Component (x64)** entry and click **Uninstall**.</span></span>  
  
  
