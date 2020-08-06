---
title: Inscrire un serveur cible dans un serveur maître | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- enlisting target servers [SQL Server]
- SQL Server Agent jobs, target servers
- master servers [SQL Server], enlisting target servers
- SQL Server Agent jobs, master servers
- target servers [SQL Server], enlisting
ms.assetid: 7633adb5-d140-4e58-a8f2-5b4b50c2f95b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 256f1a78d298d89a36412ee5689695f3ab3fde8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600467"
---
# <a name="enlist-a-target-server-to-a-master-server"></a><span data-ttu-id="96079-102">Inscrire un serveur cible dans un serveur maître</span><span class="sxs-lookup"><span data-stu-id="96079-102">Enlist a Target Server to a Master Server</span></span>
  <span data-ttu-id="96079-103">Cette rubrique explique comment ajouter des serveurs cibles à une configuration d'administration multiserveur.</span><span class="sxs-lookup"><span data-stu-id="96079-103">This topic describes how to add target servers to a multiserver administration configuration.</span></span> <span data-ttu-id="96079-104">Exécutez la procédure suivante à partir du serveur maître :</span><span class="sxs-lookup"><span data-stu-id="96079-104">Run this procedure from the master server.</span></span> <span data-ttu-id="96079-105">dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../includes/tsql-md.md)], ou d'objets SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="96079-105">in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span>  
  
 <span data-ttu-id="96079-106">Pour plus d’informations sur la manière dont le compte Windows utilisé pour le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent affecte un environnement multiserveur, consultez [Créer un environnement multi-serveur](create-a-multiserver-environment.md).</span><span class="sxs-lookup"><span data-stu-id="96079-106">For information about how the Windows account used for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service affects a multiserver environment, see [Create a Multiserver Environment](create-a-multiserver-environment.md).</span></span>  
  
 <span data-ttu-id="96079-107">Le chiffrement SSL (Secure Sockets Layer) complet et la validation de certificats sont activés pour les connexions entre les serveurs maîtres et les serveurs cible par défaut.</span><span class="sxs-lookup"><span data-stu-id="96079-107">Full Secure Sockets Layer (SSL) encryption and certificate validation is enabled for connections between master servers and target servers by default.</span></span> <span data-ttu-id="96079-108">Pour plus d’informations, consultez [Définir des options de chiffrement sur des serveurs cibles](set-encryption-options-on-target-servers.md).</span><span class="sxs-lookup"><span data-stu-id="96079-108">For more information, see [Set Encryption Options on Target Servers](set-encryption-options-on-target-servers.md).</span></span>  
  
 <span data-ttu-id="96079-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="96079-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96079-110">**Pour inscrire un serveur cible à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="96079-110">**To enlist a target server, using:**</span></span>  
  
     [<span data-ttu-id="96079-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96079-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="96079-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96079-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="96079-113">SMO</span><span class="sxs-lookup"><span data-stu-id="96079-113">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96079-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96079-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="96079-115">Pour inscrire un serveur cible</span><span class="sxs-lookup"><span data-stu-id="96079-115">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="96079-116">Dans l' **Explorateur d'objets**, développez un serveur configuré en tant que serveur maître.</span><span class="sxs-lookup"><span data-stu-id="96079-116">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="96079-117">Cliquez avec le bouton droit sur **SQL Server Agent**, pointez sur **Administration multiserveur**, puis cliquez sur **Ajouter des serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="96079-117">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Add Target Servers**.</span></span>  
  
3.  <span data-ttu-id="96079-118">Exécutez l'Assistant Création d'un serveur cible, qui vous guide tout au long du processus.</span><span class="sxs-lookup"><span data-stu-id="96079-118">Complete the Target Server Wizard, which guides you through the process.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="96079-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="96079-119">Using Transact-SQL</span></span>  
  
#### <a name="to-enlist-a-target-server"></a><span data-ttu-id="96079-120">Pour inscrire un serveur cible</span><span class="sxs-lookup"><span data-stu-id="96079-120">To enlist a target server</span></span>  
  
1.  <span data-ttu-id="96079-121">Utilisez la procédure stockée `sp_msx_enlist`.</span><span class="sxs-lookup"><span data-stu-id="96079-121">Use the `sp_msx_enlist` stored procedure.</span></span>  <span data-ttu-id="96079-122">Pour plus d’informations, consultez [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="96079-122">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql)</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="96079-123">Utilisation de SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="96079-123">Using SQL Server Management Objects (SMO)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96079-124"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96079-124">See Also</span></span>  
 [<span data-ttu-id="96079-125">Administration automatisée à l'échelle d'une entreprise</span><span class="sxs-lookup"><span data-stu-id="96079-125">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
