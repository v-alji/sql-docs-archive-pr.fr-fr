---
title: Utiliser le chemin d’accès complet pour inscrire les noms de DLL de procédure stockée étendue | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700583"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="7f855-102">Utiliser le chemin d'accès complet pour inscrire les noms de DLL de procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="7f855-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="7f855-103">Les procédures stockées étendues qui étaient auparavant inscrites sans le chemin d'accès complet pour le nom de la DLL risquent de ne pas fonctionner dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f855-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="7f855-104">Composant</span><span class="sxs-lookup"><span data-stu-id="7f855-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="7f855-105">Description</span><span class="sxs-lookup"><span data-stu-id="7f855-105">Description</span></span>  
 <span data-ttu-id="7f855-106">Les procédures stockées étendues qui étaient auparavant inscrites sans le chemin d'accès complet pour le nom de la DLL risquent de ne pas fonctionner après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="7f855-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="7f855-107">Ceci est dû au fait que l'ancien répertoire BINN n'est pas ajouté au nouveau chemin durant le processus de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="7f855-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7f855-108">risque de ne pas pouvoir localiser les procédures stockées étendues.</span><span class="sxs-lookup"><span data-stu-id="7f855-108">may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="7f855-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="7f855-109">Corrective Action</span></span>  
 <span data-ttu-id="7f855-110">Avant d'effectuer la mise à niveau, exécutez la procédure suivante pour chaque procédure stockée étendue qui n'a pas été inscrite avec un nom de chemin complet :</span><span class="sxs-lookup"><span data-stu-id="7f855-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="7f855-111">Exécutez sp_dropextendedproc pour supprimer la procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="7f855-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="7f855-112">Exécutez sp_addextendedproc pour inscrire la procédure stockée étendue avec le nom de chemin complet.</span><span class="sxs-lookup"><span data-stu-id="7f855-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f855-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f855-113">See Also</span></span>  
 <span data-ttu-id="7f855-114">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="7f855-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="7f855-115">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="7f855-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
