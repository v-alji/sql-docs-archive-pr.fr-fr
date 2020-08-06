---
title: Supprimer les appels à la commande DBCC CONCURRENCYVIOLATION déconseillée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705939"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a><span data-ttu-id="eec4f-102">Supprimer les appels à la commande DBCC CONCURRENCYVIOLATION déconseillée</span><span class="sxs-lookup"><span data-stu-id="eec4f-102">Remove calls to the deprecated DBCC CONCURRENCYVIOLATION command</span></span>
  <span data-ttu-id="eec4f-103">Le Conseiller de mise à niveau a détecté l'utilisation de la commande DBCC CONCURRENCYVIOLATION.</span><span class="sxs-lookup"><span data-stu-id="eec4f-103">Upgrade Advisor detected the use of the DBCC CONCURRENCYVIOLATION command.</span></span> <span data-ttu-id="eec4f-104">Cette commande n'est plus disponible.</span><span class="sxs-lookup"><span data-stu-id="eec4f-104">This command is no longer available.</span></span> <span data-ttu-id="eec4f-105">L'exécution de cette commande retourne l'erreur 2526.</span><span class="sxs-lookup"><span data-stu-id="eec4f-105">Executing this command returns error 2526.</span></span>  
  
## <a name="component"></a><span data-ttu-id="eec4f-106">Composant</span><span class="sxs-lookup"><span data-stu-id="eec4f-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="eec4f-107">Description</span><span class="sxs-lookup"><span data-stu-id="eec4f-107">Description</span></span>  
 <span data-ttu-id="eec4f-108">Aucune version récente ou édition de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'inclut un administrateur de charge de travail ; par conséquent, la commande a été supprimée.</span><span class="sxs-lookup"><span data-stu-id="eec4f-108">No recent version of edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes a workload governor; therefore the command has been removed.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="eec4f-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="eec4f-109">Corrective Action</span></span>  
 <span data-ttu-id="eec4f-110">Mettez à jour les applications et les scripts pour supprimer les références à cette commande déconseillée.</span><span class="sxs-lookup"><span data-stu-id="eec4f-110">Update applications and scripts to remove references to this deprecated command.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="eec4f-111">Ressources externes</span><span class="sxs-lookup"><span data-stu-id="eec4f-111">External Resources</span></span>  
  
