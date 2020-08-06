---
title: Créer des synonymes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599852"
---
# <a name="create-synonyms"></a><span data-ttu-id="a0bfa-102">Créer des synonymes</span><span class="sxs-lookup"><span data-stu-id="a0bfa-102">Create Synonyms</span></span>
  <span data-ttu-id="a0bfa-103">Cette rubrique explique comment créer un synonyme dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0bfa-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a0bfa-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a0bfa-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0bfa-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a0bfa-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0bfa-107">**Pour créer un synonyme à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="a0bfa-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bfa-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a0bfa-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bfa-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0bfa-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a0bfa-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0bfa-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a0bfa-111">Security</span></span>  
 <span data-ttu-id="a0bfa-112">Pour créer un synonyme dans un schéma donné, un utilisateur doit disposer de l'autorisation CREATE SYNONYM, et il doit posséder le schéma ou bénéficier de l'autorisation ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="a0bfa-113">L'autorisation CREATE SYNONYM est octroyable.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0bfa-114">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a0bfa-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0bfa-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0bfa-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="a0bfa-116">Pour créer un synonyme</span><span class="sxs-lookup"><span data-stu-id="a0bfa-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="a0bfa-117">Dans l' **Explorateur d'objets**, développez la base de données dans laquelle vous souhaitez créer votre nouvelle vue.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="a0bfa-118">Cliquez avec le bouton droit sur le dossier **Synonymes**, puis cliquez sur **Nouveau synonyme...** .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="a0bfa-119">Dans la boîte de dialogue **Ajouter un synonyme** , entrez les informations suivantes.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="a0bfa-120">**Nom du synonyme**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-120">**Synonym name**</span></span>  
     <span data-ttu-id="a0bfa-121">Tapez le nouveau nom à utiliser pour cet objet.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="a0bfa-122">**Schéma du synonyme**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-122">**Synonym schema**</span></span>  
     <span data-ttu-id="a0bfa-123">Tapez le schéma du nouveau nom à utiliser pour cet objet.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="a0bfa-124">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-124">**Server name**</span></span>  
     <span data-ttu-id="a0bfa-125">Tapez l'instance de serveur à laquelle vous connecter.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="a0bfa-126">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-126">**Database name**</span></span>  
     <span data-ttu-id="a0bfa-127">Tapez ou sélectionnez la base de données contenant l'objet.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="a0bfa-128">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-128">**Schema**</span></span>  
     <span data-ttu-id="a0bfa-129">Tapez ou sélectionnez le schéma propriétaire de l'objet.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="a0bfa-130">**Type d'objet**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-130">**Object type**</span></span>  
     <span data-ttu-id="a0bfa-131">Permet de sélectionner le type d'objet.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="a0bfa-132">**Nom de l'objet**</span><span class="sxs-lookup"><span data-stu-id="a0bfa-132">**Object name**</span></span>  
     <span data-ttu-id="a0bfa-133">Tapez le nom de l'objet auquel le synonyme fait référence.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a0bfa-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0bfa-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="a0bfa-135">Pour créer un synonyme</span><span class="sxs-lookup"><span data-stu-id="a0bfa-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="a0bfa-136">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0bfa-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a0bfa-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a0bfa-138">Copiez et collez les exemples suivants dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="a0bfa-139">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a0bfa-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="a0bfa-140">L'exemple suivant crée un synonyme pour une table existante dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="a0bfa-141">Le synonyme est ensuite utilisé dans les exemples suivants.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="a0bfa-142">L'exemple suivant insère une ligne dans la table de base référencée par le synonyme `MyAddressType` .</span><span class="sxs-lookup"><span data-stu-id="a0bfa-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="a0bfa-143">L'exemple suivant montre comment un synonyme peut être référencé en SQL dynamique.</span><span class="sxs-lookup"><span data-stu-id="a0bfa-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
