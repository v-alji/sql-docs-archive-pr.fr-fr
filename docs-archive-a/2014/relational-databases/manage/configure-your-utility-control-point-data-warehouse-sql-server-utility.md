---
title: Configurer votre entrepôt de données de point de contrôle de l’utilitaire (utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602140"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="66981-102">Configurer votre entrepôt de données de point de contrôle de l'utilitaire (utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="66981-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="66981-103">Les données collectées par les instances gérées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont stockées dans l'entrepôt de données de gestion de l'utilitaire (UMDW). Le nom de fichier UMDW est sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="66981-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="66981-104">Vous pouvez configurer la période de rétention des données UMDW.</span><span class="sxs-lookup"><span data-stu-id="66981-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="66981-105">Pour plus d’informations, consultez [Administration de l’utilitaire &#40;utilitaire SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="66981-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="66981-106">Les paramètres de configuration suivants ne sont pas configurables dans cette version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="66981-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="66981-107">Nom UMDW : Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="66981-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="66981-108">Fréquence de téléchargement du jeu d’éléments de collecte : toutes les 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="66981-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="66981-109">Le répertoire UMDW est configurable : \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<Nom_UCP>\MSSQL\Data\\, où \<System drive> est normalement le lecteur C:\.</span><span class="sxs-lookup"><span data-stu-id="66981-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="66981-110">Le fichier journal, Sysutility_mdw_\<GUID>_LOG, se trouve dans le même répertoire.</span><span class="sxs-lookup"><span data-stu-id="66981-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66981-111">L'emplacement du fichier UMDW (sysutility_mdw) peut être modifié à l'aide des opérations de détachement et d'attachement ou d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="66981-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="66981-112">Nous recommandons l'utilisation d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="66981-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="66981-113">Pour plus d’informations, consultez [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66981-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66981-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66981-114">See Also</span></span>  
 [<span data-ttu-id="66981-115">Fonctionnalités et tâches de l’utilitaire SQL Server</span><span class="sxs-lookup"><span data-stu-id="66981-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
