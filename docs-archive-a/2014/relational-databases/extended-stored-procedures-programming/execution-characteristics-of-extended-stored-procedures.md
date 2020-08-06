---
title: Caractéristiques d’exécution des procédures stockées étendues | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601473"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="1b308-102">Caractéristiques d'exécution des procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="1b308-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1b308-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="1b308-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="1b308-104">L'exécution d'une procédure stockée étendue présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1b308-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="1b308-105">La fonction de procédure stockée étendue est exécutée dans le contexte de sécurité de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1b308-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1b308-106">La fonction de procédure stockée étendue s'exécute dans l'espace de processus de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b308-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="1b308-107">Le thread associé à l'exécution de la procédure stockée étendue est le même que celui utilisé pour la connexion cliente.</span><span class="sxs-lookup"><span data-stu-id="1b308-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1b308-108">Avant d'ajouter des procédures stockées étendues au serveur et d'octroyer à d'autres utilisateurs l'autorisation de les exécuter, il est conseillé à l'administrateur système de revoir chaque procédure stockée étendue afin de s'assurer qu'elle n'intègre aucun code nuisible ou malveillant.</span><span class="sxs-lookup"><span data-stu-id="1b308-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="1b308-109">Une fois la DLL de procédure stockée étendue chargée, la DLL reste chargée dans l’espace d’adressage du serveur jusqu’à ce qu' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elle soit arrêtée ou l’administrateur décharge explicitement la dll à l’aide de DBCC *DLL_name* (Free).</span><span class="sxs-lookup"><span data-stu-id="1b308-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="1b308-110">La procédure stockée étendue peut être exécutée à partir de [!INCLUDE[tsql](../../includes/tsql-md.md)] comme procédure stockée à l'aide de l'instruction EXECUTE :</span><span class="sxs-lookup"><span data-stu-id="1b308-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b308-111">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1b308-111">Parameters</span></span>  
 <span data-ttu-id="1b308-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="1b308-112">\@ *retval*</span></span>  
 <span data-ttu-id="1b308-113">Valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="1b308-113">Is a return value.</span></span>  
  
 <span data-ttu-id="1b308-114">\@*param1*</span><span class="sxs-lookup"><span data-stu-id="1b308-114">\@ *param1*</span></span>  
 <span data-ttu-id="1b308-115">Paramètre d'entrée.</span><span class="sxs-lookup"><span data-stu-id="1b308-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="1b308-116">\@*param2*</span><span class="sxs-lookup"><span data-stu-id="1b308-116">\@ *param2*</span></span>  
 <span data-ttu-id="1b308-117">Paramètre d'entrée/sortie.</span><span class="sxs-lookup"><span data-stu-id="1b308-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="1b308-118">Les procédures stockées étendues offrent une amélioration des performances et étendent les fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b308-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="1b308-119">Toutefois, comme la DLL de procédure stockée étendue et [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] partagent le même espace d'adressage, une procédure problématique peut affecter le fonctionnement de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de façon défavorable.</span><span class="sxs-lookup"><span data-stu-id="1b308-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="1b308-120">Bien que les exceptions levées par la DLL de procédure stockée étendue soient gérées par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il est possible d'endommager les zones de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b308-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="1b308-121">À titre de mesure de sécurité, seuls les administrateurs systèmes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peuvent ajouter des procédures stockées étendues à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b308-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1b308-122">Ces procédures doivent être testées entièrement avant d'être installées.</span><span class="sxs-lookup"><span data-stu-id="1b308-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b308-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b308-123">See Also</span></span>  
 <span data-ttu-id="1b308-124">[Programmation de procédures stockées étendues](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="1b308-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="1b308-125">Interrogation des procédures stockées étendues installées dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b308-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
