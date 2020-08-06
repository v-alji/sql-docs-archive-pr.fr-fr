---
title: Spécifier des valeurs par défaut pour les colonnes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612711"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="b5629-102">Spécifier des valeurs par défaut pour les colonnes</span><span class="sxs-lookup"><span data-stu-id="b5629-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="b5629-103">Vous pouvez spécifier une valeur par défaut qui sera écrite dans la colonne dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5629-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b5629-104">Si vous n'assignez aucune valeur par défaut et que l'utilisateur laisse la colonne vide, alors :</span><span class="sxs-lookup"><span data-stu-id="b5629-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="b5629-105">Si vous choisissez Oui pour Nul autorisé, la valeur NULL sera insérée dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="b5629-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="b5629-106">Si vous n'avez pas choisi Oui pour Nul autorisé, la colonne restera vide, mais l'utilisateur ne pourra pas enregistrer la ligne avant d'avoir fourni une valeur pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="b5629-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="b5629-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b5629-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5629-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b5629-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5629-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b5629-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b5629-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5629-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5629-111">**Pour spécifier une valeur à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="b5629-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="b5629-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5629-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5629-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5629-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5629-114">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b5629-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b5629-115">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b5629-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b5629-116">Si votre entrée dans le champ **Valeur par défaut** remplace une valeur par défaut liée (qui est affichée sans parenthèses), vous êtes invité à annuler la liaison de la valeur par défaut et à la remplacer par la nouvelle valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5629-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="b5629-117">Pour entrer une chaîne de texte, placez la valeur entre des guillemets simples (') ; n'utilisez pas de guillemets doubles ("), car ils sont réservés pour les identificateurs entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="b5629-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="b5629-118">Pour entrer une valeur numérique par défaut, entrez le nombre sans guillemets autour.</span><span class="sxs-lookup"><span data-stu-id="b5629-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="b5629-119">Pour entrer un objet/une fonction, entrez le nom de l'objet/fonction sans guillemets autour.</span><span class="sxs-lookup"><span data-stu-id="b5629-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5629-120">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5629-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5629-121">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b5629-121">Permissions</span></span>  
 <span data-ttu-id="b5629-122">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="b5629-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5629-123">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5629-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="b5629-124">Pour spécifier une valeur par défaut pour une colonne</span><span class="sxs-lookup"><span data-stu-id="b5629-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="b5629-125">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table contenant les colonnes dont vous souhaitez modifier l’échelle et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="b5629-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="b5629-126">Sélectionnez la colonne pour laquelle vous souhaitez spécifier une valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5629-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="b5629-127">Sous l'onglet **Propriétés des colonnes** , entrez la nouvelle valeur par défaut dans la propriété **Valeur ou liaison par défaut** .</span><span class="sxs-lookup"><span data-stu-id="b5629-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b5629-128">Pour entrer une valeur par défaut numérique, entrez le nombre.</span><span class="sxs-lookup"><span data-stu-id="b5629-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="b5629-129">Pour un objet ou une fonction, entrez son nom.</span><span class="sxs-lookup"><span data-stu-id="b5629-129">For an object or function enter its name.</span></span> <span data-ttu-id="b5629-130">Pour une valeur par défaut alphanumérique, entrez la valeur dans des guillemets simples.</span><span class="sxs-lookup"><span data-stu-id="b5629-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="b5629-131">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="b5629-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5629-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5629-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="b5629-133">Pour spécifier une valeur par défaut pour une colonne</span><span class="sxs-lookup"><span data-stu-id="b5629-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="b5629-134">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5629-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b5629-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="b5629-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b5629-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b5629-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="b5629-137">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b5629-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
