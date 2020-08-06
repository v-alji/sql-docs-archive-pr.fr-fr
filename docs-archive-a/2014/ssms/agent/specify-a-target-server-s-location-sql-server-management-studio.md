---
title: Spécifier un serveur cible&#39;emplacement s (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612060"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="430e5-102">Spécifier l’emplacement d’un serveur cible (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="430e5-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="430e5-103">Cette rubrique explique comment spécifier l'emplacement d'un serveur cible dans une configuration d'administration multiserveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="430e5-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="430e5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="430e5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="430e5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="430e5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="430e5-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="430e5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="430e5-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="430e5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="430e5-108">**Pour spécifier l'emplacement d'un serveur cible, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="430e5-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="430e5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="430e5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="430e5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="430e5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="430e5-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="430e5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="430e5-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="430e5-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="430e5-113">Cette action modifie le Registre.</span><span class="sxs-lookup"><span data-stu-id="430e5-113">Performing this action edits the registry.</span></span> <span data-ttu-id="430e5-114">La modification manuelle du Registre n'est pas recommandée parce que des modifications inadaptées ou incorrectes peuvent provoquer de graves problèmes de configuration à votre système.</span><span class="sxs-lookup"><span data-stu-id="430e5-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="430e5-115">Seuls des utilisateurs expérimentés peuvent utiliser regedit.exe pour modifier le Registre.</span><span class="sxs-lookup"><span data-stu-id="430e5-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="430e5-116">Pour plus d'informations, consultez la documentation de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="430e5-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="430e5-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="430e5-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="430e5-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="430e5-118">Permissions</span></span>  
 <span data-ttu-id="430e5-119">Nécessite l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="430e5-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="430e5-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="430e5-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="430e5-121">Pour spécifier l'emplacement d'un serveur cible</span><span class="sxs-lookup"><span data-stu-id="430e5-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="430e5-122">Dans **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur maître sur lequel vous souhaitez spécifier l'emplacement du serveur cible.</span><span class="sxs-lookup"><span data-stu-id="430e5-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="430e5-123">Cliquez avec le bouton droit sur **SQL Server Agent**, pointez sur **Administration multiserveur**, puis sélectionnez **Gérer les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="430e5-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="430e5-124">Cliquez avec le bouton droit sur un serveur cible et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="430e5-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="430e5-125">Dans la zone **Emplacement** , entrez l'emplacement du serveur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="430e5-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="430e5-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="430e5-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="430e5-127">Pour spécifier l'emplacement d'un serveur cible</span><span class="sxs-lookup"><span data-stu-id="430e5-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="430e5-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="430e5-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="430e5-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="430e5-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="430e5-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="430e5-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="430e5-131">Pour plus d’informations, consultez [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="430e5-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  
