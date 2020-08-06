---
title: Désactiver des contraintes de validation pour la réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599856"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="f58fe-102">Désactiver des contraintes de validation lors de la réplication</span><span class="sxs-lookup"><span data-stu-id="f58fe-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="f58fe-103">Vous pouvez désactiver des contrainte de validation dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f58fe-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f58fe-104">Vous pouvez également choisir expressément de désactiver les contraintes de validation pour la réplication, ce qui est parfois très utile si vous publiez des données issues d'une version précédente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f58fe-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f58fe-105">Si une table est publiée à l'aide du processus de réplication, les contraintes de validation sont automatiquement désactivées lors des opérations effectuées par les agents de réplication.</span><span class="sxs-lookup"><span data-stu-id="f58fe-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="f58fe-106">Lorsqu'un Agent de réplication effectue une requête Insert, Update ou Delete vers un abonné, la contrainte n'est pas vérifiée ; si c'est un utilisateur qui effectue la requête Insert, Update ou Delete, la contrainte est vérifiée.</span><span class="sxs-lookup"><span data-stu-id="f58fe-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="f58fe-107">La contrainte est désactivée pour l'Agent de réplication, car elle était déjà vérifiée au niveau de l'éditeur lorsque les données ont été insérées, mises à jour ou supprimées à l'origine.</span><span class="sxs-lookup"><span data-stu-id="f58fe-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="f58fe-108">Pour plus d’informations, consultez [Spécifier des options de schéma](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="f58fe-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f58fe-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f58fe-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f58fe-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f58fe-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f58fe-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f58fe-111">Permissions</span></span>  
 <span data-ttu-id="f58fe-112">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="f58fe-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f58fe-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f58fe-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="f58fe-114">Pour désactiver une contrainte de validation lors de la réplication</span><span class="sxs-lookup"><span data-stu-id="f58fe-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="f58fe-115">Dans l' **Explorateur d'objets**, développez la table avec la contrainte que vous souhaitez modifier, puis développez le dossier **Contraintes** .</span><span class="sxs-lookup"><span data-stu-id="f58fe-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="f58fe-116">Cliquez avec le bouton droit sur la contrainte de validation à modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f58fe-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="f58fe-117">Dans la boîte de dialogue **Contraintes de validation** , sous **Concepteur de tables**, sélectionnez la valeur **Non** pour **Appliquer la réplication**.</span><span class="sxs-lookup"><span data-stu-id="f58fe-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="f58fe-118">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="f58fe-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f58fe-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f58fe-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="f58fe-120">Pour désactiver une contrainte de validation lors de la réplication</span><span class="sxs-lookup"><span data-stu-id="f58fe-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="f58fe-121">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f58fe-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f58fe-122">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f58fe-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f58fe-123">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f58fe-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f58fe-124">L'exemple crée une table avec une colonne IDENTITY et une contrainte CHECK sur la table.</span><span class="sxs-lookup"><span data-stu-id="f58fe-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="f58fe-125">Il supprime ensuite la contrainte et la recrée en spécifiant la clause NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="f58fe-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="f58fe-126">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f58fe-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="f58fe-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f58fe-127">See Also</span></span>  
 [<span data-ttu-id="f58fe-128">Spécifier des options de schéma</span><span class="sxs-lookup"><span data-stu-id="f58fe-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
