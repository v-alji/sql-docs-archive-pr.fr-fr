---
title: Afficher ou modifier les emplacements par défaut des fichiers de données et des fichiers journaux (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- log files [SQL Server], changing default location
- data files [SQL Server], changing default location
ms.assetid: 70a57fda-fcfe-490f-9cf6-5df620e32b2a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: def6be137aecbab7f2730fa4c2bf210b374a3a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697148"
---
# <a name="view-or-change-the-default-locations-for-data-and-log-files-sql-server-management-studio"></a><span data-ttu-id="c666f-102">Afficher ou modifier les emplacements par défaut des fichiers de données et des fichiers journaux (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c666f-102">View or Change the Default Locations for Data and Log Files (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c666f-103">Cette rubrique explique comment afficher et modifier les emplacements par défaut des nouveaux fichiers de données et fichiers journaux dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c666f-103">This topic describes how to view and change the default locations of new data and log files in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c666f-104">Le chemin d'accès par défaut est obtenu à partir du Registre.</span><span class="sxs-lookup"><span data-stu-id="c666f-104">The default path is obtained from the registry.</span></span> <span data-ttu-id="c666f-105">Une fois l'emplacement modifié, toutes les nouvelles bases de données créées dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliseront cet emplacement si aucun autre emplacement n'est spécifié.</span><span class="sxs-lookup"><span data-stu-id="c666f-105">After you change the location all new databases created in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will use that location if a different location is not specified.</span></span>  
  
 <span data-ttu-id="c666f-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c666f-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c666f-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c666f-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c666f-108">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c666f-108">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="c666f-109">**Pour afficher ou modifier les emplacements par défaut des fichiers de données et des fichiers journaux, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c666f-109">**To view or change the data and log file default locations, using:**</span></span>  
  
     [<span data-ttu-id="c666f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c666f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   <span data-ttu-id="c666f-111">**Suivi :**  [Modification des emplacements par défaut](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c666f-111">**Follow Up:**  [Changing the Default Locations](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c666f-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c666f-112">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c666f-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c666f-113">Recommendations</span></span>  
 <span data-ttu-id="c666f-114">La bonne pratique pour protéger vos fichiers de données et fichiers journaux consiste à vous assurer qu'ils sont protégés par des listes de contrôle d'accès (ACL).</span><span class="sxs-lookup"><span data-stu-id="c666f-114">The best practice for protecting your data files and log files is to ensure that they are protected by access control lists (ACLs).</span></span> <span data-ttu-id="c666f-115">Les listes de contrôle d'accès doivent être définies sur la racine du répertoire où sont créés les fichiers.</span><span class="sxs-lookup"><span data-stu-id="c666f-115">The ACLs should be set on the directory root under which the files are created.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c666f-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c666f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c666f-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c666f-117">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c666f-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c666f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-default-locations-for-database-files"></a><span data-ttu-id="c666f-119">Pour afficher ou modifier les emplacements par défaut des fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="c666f-119">To view or change the default locations for database files</span></span>  
  
1.  <span data-ttu-id="c666f-120">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c666f-120">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c666f-121">Dans le volet gauche, cliquez sur la page **Paramètres de base de données** .</span><span class="sxs-lookup"><span data-stu-id="c666f-121">In the left panel, click the **Database settings** page.</span></span>  
  
3.  <span data-ttu-id="c666f-122">Dans **Emplacements de la base de données par défaut**, consultez les emplacements par défaut actuels pour les nouveaux fichiers de données et les nouveaux fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="c666f-122">In **Database default locations**, view the current default locations for new data files and new log files.</span></span> <span data-ttu-id="c666f-123">Pour modifier un emplacement par défaut, entrez un nouveau chemin d'accès par défaut dans le champ **Données** ou **Journal** , ou cliquez sur le bouton Parcourir pour rechercher et sélectionner un chemin d'accès.</span><span class="sxs-lookup"><span data-stu-id="c666f-123">To change a default location, enter a new default pathname in the **Data** or **Log** field, or click the browse button to find and select a pathname.</span></span>  
  
##  <a name="follow-up-after-changing-the-default-locations"></a><a name="FollowUp"></a><span data-ttu-id="c666f-124">Suivi : après avoir modifié les emplacements par défaut</span><span class="sxs-lookup"><span data-stu-id="c666f-124">Follow Up: After Changing the Default Locations</span></span>  
 <span data-ttu-id="c666f-125">Vous devez arrêter et démarrer le service SQL Server pour valider la modification.</span><span class="sxs-lookup"><span data-stu-id="c666f-125">You must stop and start the SQL Server service to complete the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c666f-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c666f-126">See Also</span></span>  
 <span data-ttu-id="c666f-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c666f-127">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="c666f-128">Créer une base de données</span><span class="sxs-lookup"><span data-stu-id="c666f-128">Create a Database</span></span>](../../relational-databases/databases/create-a-database.md)  
  
  
