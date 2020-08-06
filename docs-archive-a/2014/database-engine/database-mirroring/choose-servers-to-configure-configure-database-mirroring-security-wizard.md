---
title: Choisir les serveurs à configurer (Configurer l’Assistant Sécurité de mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603031"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="0e630-102">Choisir les serveurs à configurer (Configurer l'Assistant Sécurité de mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="0e630-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="0e630-103">Cette page vous permet de spécifier les instances de serveurs que vous voulez configurer.</span><span class="sxs-lookup"><span data-stu-id="0e630-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="0e630-104">Vous devez sélectionner au moins une instance de serveur avant de poursuivre l'exécution de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="0e630-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="0e630-105">Si vous désactivez la case à cocher pour une instance de serveur, l'Assistant ne lui apportera aucune modification.</span><span class="sxs-lookup"><span data-stu-id="0e630-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="0e630-106">Toutefois, l'Assistant vous demandera d'entrer des informations sur cette instance et d'enregistrer ces informations au sein de la configuration des autres instances de serveurs.</span><span class="sxs-lookup"><span data-stu-id="0e630-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="0e630-107">Par exemple, si vous désactivez la case à cocher pour l'instance de serveur témoin, l'Assistant vous demandera d'entrer le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] du témoin car une connexion doit être créée pour ce compte dans le cadre de la configuration de sécurité enregistrée au niveau des instances du principal et du serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="0e630-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="0e630-108">**Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="0e630-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="0e630-109">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e630-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="0e630-110">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0e630-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="0e630-111">Options</span><span class="sxs-lookup"><span data-stu-id="0e630-111">Options</span></span>  
 <span data-ttu-id="0e630-112">**Instance de serveur principal**</span><span class="sxs-lookup"><span data-stu-id="0e630-112">**Principal server instance**</span></span>  
 <span data-ttu-id="0e630-113">Sélectionnez cette option pour configurer la sécurité pour le serveur principal.</span><span class="sxs-lookup"><span data-stu-id="0e630-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="0e630-114">**Instance de serveur miroir**</span><span class="sxs-lookup"><span data-stu-id="0e630-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="0e630-115">Sélectionnez cette option pour configurer la sécurité pour le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="0e630-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="0e630-116">**Instance de serveur témoin**</span><span class="sxs-lookup"><span data-stu-id="0e630-116">**Witness server instance**</span></span>  
 <span data-ttu-id="0e630-117">Sélectionnez cette option pour configurer la sécurité pour le serveur témoin (s'il est présent).</span><span class="sxs-lookup"><span data-stu-id="0e630-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e630-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e630-118">See Also</span></span>  
 <span data-ttu-id="0e630-119">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="0e630-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="0e630-120">Mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0e630-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
