---
title: Modifier des statistiques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613368"
---
# <a name="modify-statistics"></a><span data-ttu-id="3f6c0-102">Modifier des statistiques</span><span class="sxs-lookup"><span data-stu-id="3f6c0-102">Modify Statistics</span></span>
  <span data-ttu-id="3f6c0-103">Vous pouvez modifier des statistiques existantes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f6c0-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="3f6c0-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="3f6c0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3f6c0-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="3f6c0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3f6c0-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3f6c0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3f6c0-107">**Pour modifier des statistiques, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="3f6c0-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="3f6c0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f6c0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3f6c0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f6c0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3f6c0-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3f6c0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3f6c0-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="3f6c0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3f6c0-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="3f6c0-112">Permissions</span></span>  
 <span data-ttu-id="3f6c0-113">Exigences :</span><span class="sxs-lookup"><span data-stu-id="3f6c0-113">Requires that:</span></span>  
  
-   <span data-ttu-id="3f6c0-114">L'utilisateur doit disposer de l'autorisation ALTER sur la table ou la vue.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="3f6c0-115">L’utilisateur doit être le propriétaire de la table ou de la vue indexée ou être membre d’un des rôles suivants : rôle serveur fixe **sysadmin** , rôle de base de données fixe **db_owner** ou rôle de base de données fixe **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="3f6c0-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3f6c0-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3f6c0-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="3f6c0-117">Pour modifier des statistiques</span><span class="sxs-lookup"><span data-stu-id="3f6c0-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="3f6c0-118">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer la base de données dans laquelle vous souhaitez modifier une statistique.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="3f6c0-119">Cliquez sur le signe plus (+) pour développer le dossier **Tables** .</span><span class="sxs-lookup"><span data-stu-id="3f6c0-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="3f6c0-120">Cliquez sur le signe plus (+) pour développer la table dans laquelle vous souhaitez modifier une statistique.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="3f6c0-121">Cliquez sur le signe plus (+) pour développer le dossier **Statistiques** .</span><span class="sxs-lookup"><span data-stu-id="3f6c0-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="3f6c0-122">Cliquez avec le bouton droit sur l’objet de statistiques à modifier et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="3f6c0-123">Dans la boîte de dialogue **Propriétés des statistiques** *nom_statistiques*, dans la page **Général**, cliquez sur **Ajouter**, **Supprimer**, **Monter**, **Descendre**, ou sur une combinaison de ces commandes, pour modifier les propriétés des statistiques.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="3f6c0-124">Gardez à l’esprit que l’emplacement d’une colonne dans la grille **Colonnes de statistiques** peut avoir une incidence notable sur l’utilité des statistiques.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="3f6c0-125">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3f6c0-126">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3f6c0-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="3f6c0-127">**Pour modifier des statistiques**</span><span class="sxs-lookup"><span data-stu-id="3f6c0-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="3f6c0-128">Cette tâche ne peut pas être effectuée à l'aide d'instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="3f6c0-129">Pour modifier des statistiques à l'aide de Transact-SQL, vous devez d'abord supprimer les statistiques existantes, puis les recréer avec les nouveaux attributs.</span><span class="sxs-lookup"><span data-stu-id="3f6c0-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="3f6c0-130">Pour plus d’informations, consultez [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) et [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f6c0-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
