---
title: Désactiver des contraintes de clé étrangère pour la réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604415"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="98c34-102">Désactiver des contraintes de clé étrangère pour la réplication</span><span class="sxs-lookup"><span data-stu-id="98c34-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="98c34-103">Vous pouvez désactiver les contraintes de clé étrangère lors de la réplication dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98c34-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="98c34-104">Cela peut être utile si vous publiez des données issues d'une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98c34-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98c34-105">Si une table est publiée à l'aide du processus de réplication, les contraintes de clé étrangère sont automatiquement désactivées lors des opérations effectuées par les Agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="98c34-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="98c34-106">Lorsqu'un Agent de réplication effectue une requête Insert, Update ou Delete vers un abonné, la contrainte n'est pas vérifiée ; si c'est un utilisateur qui effectue la requête Insert, Update ou Delete, la contrainte est vérifiée.</span><span class="sxs-lookup"><span data-stu-id="98c34-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="98c34-107">La contrainte est désactivée pour l'Agent de réplication, car elle était déjà vérifiée au niveau de l'éditeur lorsque les données ont été insérées, mises à jour ou supprimées à l'origine.</span><span class="sxs-lookup"><span data-stu-id="98c34-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="98c34-108">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="98c34-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="98c34-109">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="98c34-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="98c34-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="98c34-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="98c34-111">**Pour désactiver une contrainte de clé étrangère lors de la réplication, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="98c34-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="98c34-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98c34-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="98c34-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98c34-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="98c34-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="98c34-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="98c34-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="98c34-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="98c34-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="98c34-116">Permissions</span></span>  
 <span data-ttu-id="98c34-117">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="98c34-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="98c34-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="98c34-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="98c34-119">Pour désactiver une contrainte de clé étrangère lors de la réplication</span><span class="sxs-lookup"><span data-stu-id="98c34-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="98c34-120">Dans l' **Explorateur d'objets**, développez la table avec la contrainte de clé étrangère que vous souhaitez modifier, puis développez le dossier **Clés** .</span><span class="sxs-lookup"><span data-stu-id="98c34-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="98c34-121">Cliquez avec le bouton droit sur la contrainte de clé étrangère et cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="98c34-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="98c34-122">Dans la boîte de dialogue **Relations de clé étrangère** , sélectionnez la valeur **Non** pour **Appliquer la réplication**.</span><span class="sxs-lookup"><span data-stu-id="98c34-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="98c34-123">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="98c34-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="98c34-124">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="98c34-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="98c34-125">Pour désactiver une contrainte de clé étrangère lors de la réplication</span><span class="sxs-lookup"><span data-stu-id="98c34-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="98c34-126">Pour effectuer cette tâche dans [!INCLUDE[tsql](../../includes/tsql-md.md)], supprimez la contrainte de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="98c34-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="98c34-127">Ensuite, ajoutez une nouvelle contrainte de clé étrangère et spécifiez l'option NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="98c34-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="98c34-128">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="98c34-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
