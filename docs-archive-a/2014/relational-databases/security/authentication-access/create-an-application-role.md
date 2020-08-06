---
title: Créer un rôle d’application | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.approle.general.f1
helpviewer_keywords:
- application roles [SQL Server], creating
ms.assetid: 6b8da1f5-3d8e-4f88-b111-b915788b06f1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 51272dad57558cdb771f9b98a2f5e5b3da7609cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612737"
---
# <a name="create-an-application-role"></a><span data-ttu-id="7c128-102">Créer un rôle d'application</span><span class="sxs-lookup"><span data-stu-id="7c128-102">Create an Application Role</span></span>
  <span data-ttu-id="7c128-103">Cette rubrique explique comment créer un rôle d'application dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c128-103">This topic describes how to create an application role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7c128-104">Les rôles d'application limitent l'accès utilisateur à une base de données sauf via des applications spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7c128-104">Application roles restrict user access to a database except through specific applications.</span></span> <span data-ttu-id="7c128-105">Les rôles d'application ne possèdent pas d'utilisateurs, de sorte que la liste **Membres du rôle** n'est pas affichée lorsque l'option **Rôle d'application** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7c128-105">Application roles have no users, so the **Role Members** list is not displayed when **Application role** is selected.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7c128-106">La complexité des mots de passe est vérifiée lors de la définition des mots de passe des rôles d'application.</span><span class="sxs-lookup"><span data-stu-id="7c128-106">Password complexity is checked when application role passwords are set.</span></span> <span data-ttu-id="7c128-107">Les applications qui appellent des rôles d'application doivent stocker leurs mots de passe.</span><span class="sxs-lookup"><span data-stu-id="7c128-107">Applications that invoke application roles must store their passwords.</span></span> <span data-ttu-id="7c128-108">Les mots de passe des rôles d'application doivent toujours être stockés sous forme chiffrée.</span><span class="sxs-lookup"><span data-stu-id="7c128-108">Application role passwords should always be stored encrypted.</span></span>  
  
 <span data-ttu-id="7c128-109">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="7c128-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7c128-110">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="7c128-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7c128-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7c128-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7c128-112">**Pour créer un rôle d'application, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="7c128-112">**To create an application role, using:**</span></span>  
  
     [<span data-ttu-id="7c128-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c128-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7c128-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c128-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7c128-115">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7c128-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7c128-116">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7c128-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7c128-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7c128-117">Permissions</span></span>  
 <span data-ttu-id="7c128-118">Nécessite l'autorisation ALTER ANY APPLICATION ROLE sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="7c128-118">Requires ALTER ANY APPLICATION ROLE permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7c128-119">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7c128-119">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-an-application-role"></a><span data-ttu-id="7c128-120">Pour créer un rôle d'application</span><span class="sxs-lookup"><span data-stu-id="7c128-120">To create an application role</span></span>  
  
1.  <span data-ttu-id="7c128-121">Dans l'Explorateur d'objets, développez la base de données dans laquelle vous souhaitez créer un rôle d'application.</span><span class="sxs-lookup"><span data-stu-id="7c128-121">In Object Explorer, expand the database where you want to create an application role.</span></span>  
  
2.  <span data-ttu-id="7c128-122">Développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="7c128-122">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="7c128-123">Développez le dossier **Rôles** .</span><span class="sxs-lookup"><span data-stu-id="7c128-123">Expand the **Roles** folder.</span></span>  
  
4.  <span data-ttu-id="7c128-124">Cliquez avec le bouton droit sur le dossier **Rôles d’application** et sélectionnez **Nouveau rôle d’application...** .</span><span class="sxs-lookup"><span data-stu-id="7c128-124">Right-click the **Application Roles** folder and select **New Application Role...**.</span></span>  
  
5.  <span data-ttu-id="7c128-125">Dans la boîte de dialogue **Rôle d’application - Nouveau**, dans la **page Général**, entrez le nouveau nom du nouveau rôle d’application dans la zone **Nom du rôle**.</span><span class="sxs-lookup"><span data-stu-id="7c128-125">In the **Application Role - New** dialog box, on the **General Page**, enter the new name of the new application role in the **Role name** box.</span></span>  
  
6.  <span data-ttu-id="7c128-126">Dans la zone **Schéma par défaut** , spécifiez le schéma qui possédera les objets créés par ce rôle en entrant les noms d'objet.</span><span class="sxs-lookup"><span data-stu-id="7c128-126">In the **Default Schema** box, specify the schema that will own objects created by this role by entering the object names.</span></span> <span data-ttu-id="7c128-127">Vous pouvez également cliquer sur les points de suspension **(…)** pour ouvrir la boîte de dialogue **Localiser le schéma**.</span><span class="sxs-lookup"><span data-stu-id="7c128-127">Alternately, click the ellipsis **(...)** to open the **Locate Schema** dialog box.</span></span>  
  
7.  <span data-ttu-id="7c128-128">Dans la zone **Mot de passe** , entrez un mot de passe pour le nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="7c128-128">In the **Password** box, enter a password for the new role.</span></span> <span data-ttu-id="7c128-129">Entrez de nouveau ce mot de passe dans la zone **Confirmer le mot de passe** .</span><span class="sxs-lookup"><span data-stu-id="7c128-129">Enter that password again into the **Confirm Password** box.</span></span>  
  
8.  <span data-ttu-id="7c128-130">Sous **Schémas appartenant à ce rôle**, sélectionnez ou affichez les schémas qui appartiendront à ce rôle.</span><span class="sxs-lookup"><span data-stu-id="7c128-130">Under **Schemas owned by this role**, select or view schemas that will be owned by this role.</span></span> <span data-ttu-id="7c128-131">Un schéma ne peut appartenir qu'à un seul schéma ou rôle.</span><span class="sxs-lookup"><span data-stu-id="7c128-131">A schema can be owned by only one schema or role.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="7c128-132">Options supplémentaires</span><span class="sxs-lookup"><span data-stu-id="7c128-132">Additional Options</span></span>  
 <span data-ttu-id="7c128-133">La boîte de dialogue **Rôle d'application - Nouveau** offre également des options sur deux pages supplémentaires : **Sécurisables** et **Propriétés étendues**.</span><span class="sxs-lookup"><span data-stu-id="7c128-133">The **Application Role - New** dialog box also offers options on two additional pages: **Securables** and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="7c128-134">La page **Éléments sécurisables** répertorie tous les éléments sécurisables possibles et les autorisations sur ces éléments sécurisables qui peuvent être accordées à la connexion.</span><span class="sxs-lookup"><span data-stu-id="7c128-134">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="7c128-135">La page **Propriétés étendues** vous permet d'ajouter des propriétés personnalisées aux utilisateurs de base de données.</span><span class="sxs-lookup"><span data-stu-id="7c128-135">The **Extended properties** page allows you to add custom properties to database users.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7c128-136">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7c128-136">Using Transact-SQL</span></span>  
  
#### <a name="to-create-an-application-role"></a><span data-ttu-id="7c128-137">Pour créer un rôle d'application</span><span class="sxs-lookup"><span data-stu-id="7c128-137">To create an application role</span></span>  
  
1.  <span data-ttu-id="7c128-138">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c128-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7c128-139">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="7c128-139">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7c128-140">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="7c128-140">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates an application role called "weekly_receipts" that has the password "987Gbv876sPYY5m23" and "Sales" as its default schema.  
  
    CREATE APPLICATION ROLE weekly_receipts   
        WITH PASSWORD = '987G^bv876sPY)Y5m23'   
        , DEFAULT_SCHEMA = Sales;  
    GO  
    ```  
  
 <span data-ttu-id="7c128-141">Pour plus d’informations, consultez [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7c128-141">For more information, see [CREATE APPLICATION ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-application-role-transact-sql).</span></span>  
  
  
