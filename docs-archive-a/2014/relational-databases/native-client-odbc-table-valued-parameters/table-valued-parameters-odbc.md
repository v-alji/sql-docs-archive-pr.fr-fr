---
title: Paramètres table (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC)
- ODBC, table-valued parameters
ms.assetid: ef06cd13-18e2-4c65-8ede-c3955d820e54
author: rothja
ms.author: jroth
ms.openlocfilehash: fedfd63f7cbafd68d39aeb62dd29c046df8ab100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600844"
---
# <a name="table-valued-parameters-odbc"></a><span data-ttu-id="eb5ce-102">Paramètres table (ODBC)</span><span class="sxs-lookup"><span data-stu-id="eb5ce-102">Table-Valued Parameters (ODBC)</span></span>
  <span data-ttu-id="eb5ce-103">La prise en charge des paramètres table par ODBC permet à une application cliente d'envoyer plus efficacement des données paramétrables au serveur par l'envoi de plusieurs lignes au serveur en un seul appel.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-103">ODBC support for table-valued parameters lets a client application send parameterized data to the server more efficiently, by sending multiple rows to the server with one call.</span></span>  
  
 <span data-ttu-id="eb5ce-104">Pour plus d’informations sur les paramètres table sur le serveur, consultez [utiliser des paramètres table &#40;Moteur de base de données&#41;](../tables/use-table-valued-parameters-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="eb5ce-104">For information about table-valued parameters on the server, see [Use Table-Valued Parameters &#40;Database Engine&#41;](../tables/use-table-valued-parameters-database-engine.md).</span></span>  
  
 <span data-ttu-id="eb5ce-105">Dans ODBC, vous pouvez envoyer des paramètres table au serveur de deux manières :</span><span class="sxs-lookup"><span data-stu-id="eb5ce-105">In ODBC, there are two ways that you can send table-valued parameters to the server:</span></span>  
  
-   <span data-ttu-id="eb5ce-106">Toutes les données de paramètre table peuvent être en mémoire au moment de l’appel de SQLExecDirect ou SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-106">All the table-valued parameter data can be in memory at the time SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="eb5ce-107">Ces données sont stockées dans des tableaux si la valeur de table contient plusieurs lignes.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-107">This data is stored in arrays if there are multiple rows in the table-value.</span></span>  
  
-   <span data-ttu-id="eb5ce-108">Une application peut spécifier des données en cours d’exécution pour un paramètre table lorsque SQLExecDirect ou SQLExecute est appelé.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-108">An application can specify data-at-execution for a table-valued parameter when SQLExecDirect or SQLExecute is called.</span></span> <span data-ttu-id="eb5ce-109">Dans ce cas, les lignes de données de la valeur de table peuvent être fournies par lots, ou une par une pour réduire la mémoire requise.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-109">In this case, rows of data for the table-value can be provided in batches, or one at a time to reduce memory requirements.</span></span>  
  
 <span data-ttu-id="eb5ce-110">La première option permet aux procédures stockées de renfermer une logique métier plus importante.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-110">The first option enables stored procedures to encapsulate more business logic.</span></span> <span data-ttu-id="eb5ce-111">Par exemple, une même procédure stockée peut encapsuler une transaction d'enregistrement de commande entière lorsque les éléments de la commande sont passés sous la forme de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-111">For example, a single stored procedure could encapsulate a whole order entry transaction when the order items are passed as a table-valued parameter.</span></span> <span data-ttu-id="eb5ce-112">Cette option est très efficace, car un seul aller-retour sur le serveur est requis.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-112">This option is very efficient, because only a single round trip to the server is required.</span></span> <span data-ttu-id="eb5ce-113">Vous pouvez également utiliser différentes procédures pour gérer séparément l'en-tête de commande et les éléments de commande, ce qui nécessiterait davantage de code et un contrat plus complexe entre le client et le serveur.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-113">Alternatively, you could use different procedures to handle the order header and order items separately, which would require more code and a more complex contract between the client and server.</span></span>  
  
 <span data-ttu-id="eb5ce-114">La seconde méthode propose un mécanisme efficace pour les opérations en bloc portant sur de grandes quantités de données.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-114">The second method provides an efficient mechanism for bulk operations with very large amounts of data.</span></span> <span data-ttu-id="eb5ce-115">Une application peut en effet transmettre en continu des lignes de données au serveur sans devoir commencer par toutes les mettre en mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-115">This enables an application to stream rows of data to the server without having to buffer them all in memory first.</span></span>  
  
 <span data-ttu-id="eb5ce-116">Vous pouvez créer des contraintes et des clés primaires lorsque vous créez la variable de table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-116">You can create constraints and primary keys when you create the table variable.</span></span> <span data-ttu-id="eb5ce-117">Les contraintes sont un bon moyen de veiller à ce que les données d'une table répondent à des spécifications particulières.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-117">Constraints are a good way to ensure that the data in a table meets specific requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb5ce-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="eb5ce-118">In This Section</span></span>  
 [<span data-ttu-id="eb5ce-119">Scénarios d'utilisation des paramètres table ODBC</span><span class="sxs-lookup"><span data-stu-id="eb5ce-119">Uses of ODBC Table-Valued Parameters</span></span>](uses-of-odbc-table-valued-parameters.md)  
 <span data-ttu-id="eb5ce-120">Décrit les principaux scénarios utilisateur pour les paramètres table et ODBC.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-120">Describes the primary user scenarios for table-valued parameters and ODBC.</span></span>  
  
 [<span data-ttu-id="eb5ce-121">Type ODBC SQL pour les paramètres table</span><span class="sxs-lookup"><span data-stu-id="eb5ce-121">ODBC SQL Type for Table-Valued Parameters</span></span>](odbc-sql-type-for-table-valued-parameters.md)  
 <span data-ttu-id="eb5ce-122">Décrit le type SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-122">Describes the SQL_SS_TABLE type.</span></span> <span data-ttu-id="eb5ce-123">ll s'agit d'un nouveau type SQL ODBC qui prend en charge les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-123">This is a new ODBC SQL type that supports table-valued parameters.</span></span>  
  
 [<span data-ttu-id="eb5ce-124">Champs de descripteur de paramètres table</span><span class="sxs-lookup"><span data-stu-id="eb5ce-124">Table-Valued Parameter Descriptor Fields</span></span>](table-valued-parameter-descriptor-fields.md)  
 <span data-ttu-id="eb5ce-125">Décrit les champs de descripteur qui prennent en charge les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-125">Describes descriptor fields that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="eb5ce-126">Champs de descripteur pour les colonnes constituantes des paramètres table</span><span class="sxs-lookup"><span data-stu-id="eb5ce-126">Descriptor Fields for Table-Valued Parameter Constituent Columns</span></span>](descriptor-fields-for-table-valued-parameter-constituent-columns.md)  
 <span data-ttu-id="eb5ce-127">Décrit des champs de descripteur qui ont une signification pour les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-127">Describes descriptor fields that have meaning for table-valued parameters.</span></span>  
  
 [<span data-ttu-id="eb5ce-128">Champs d’enregistrement de diagnostic de paramètres table</span><span class="sxs-lookup"><span data-stu-id="eb5ce-128">Table-Valued Parameter Diagnostic Record Fields</span></span>](table-valued-parameter-diagnostic-record-fields.md)  
 <span data-ttu-id="eb5ce-129">Décrit deux champs de diagnostic qui ont été ajoutés aux enregistrements de diagnostic pour prendre en charge les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-129">Describes two diagnostic fields that have been added to diagnostic records to support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="eb5ce-130">Attributs d'instruction qui affectent des paramètres table</span><span class="sxs-lookup"><span data-stu-id="eb5ce-130">Statement Attributes that Affect Table-Valued Parameters</span></span>](statement-attributes-that-affect-table-valued-parameters.md)  
 <span data-ttu-id="eb5ce-131">Décrit un nouveau champ d'en-tête de descripteur qui permet aux colonnes de paramètres table d'être adressés.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-131">Describes a new descriptor header field that enables table-valued parameters columns to be addressed.</span></span>  
  
 [<span data-ttu-id="eb5ce-132">Liaison et transfert de données de paramètres table et de valeurs de colonnes</span><span class="sxs-lookup"><span data-stu-id="eb5ce-132">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>](binding-and-data-transfer-of-table-valued-parameters-and-column-values.md)  
 <span data-ttu-id="eb5ce-133">Décrit la liaison de paramètre et comment passer un paramètre table au serveur.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-133">Describes parameter binding and how to pass a table-valued parameter to the server.</span></span>  
  
 [<span data-ttu-id="eb5ce-134">Métadonnées de paramètres table pour les instructions préparées</span><span class="sxs-lookup"><span data-stu-id="eb5ce-134">Table-Valued Parameter Metadata for Prepared Statements</span></span>](table-valued-parameter-metadata-for-prepared-statements.md)  
 <span data-ttu-id="eb5ce-135">Décrit comment une application peut obtenir des métadonnées pour un appel de procédure préparé.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-135">Describes how an application can obtain metadata for a prepared procedure call.</span></span>  
  
 [<span data-ttu-id="eb5ce-136">Métadonnées de paramètres table supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb5ce-136">Additional Table-Valued Parameter Metadata</span></span>](additional-table-valued-parameter-metadata.md)  
 <span data-ttu-id="eb5ce-137">Décrit comment utiliser SQLProcedureColumns, SQLTables et SQLColumns pour récupérer les métadonnées d’un paramètre table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-137">Describes how to use SQLProcedureColumns, SQLTables, and SQLColumns to retrieve metadata for a table-valued parameter.</span></span>  
  
 [<span data-ttu-id="eb5ce-138">Conversion des données des paramètres table, et autres erreurs et avertissements</span><span class="sxs-lookup"><span data-stu-id="eb5ce-138">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>](table-valued-parameter-data-conversion-and-other-errors-and-warnings.md)  
 <span data-ttu-id="eb5ce-139">Décrit comment traiter les erreurs sur les valeurs de colonne de paramètre table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-139">Describes how to process errors on table-valued parameter column values.</span></span>  
  
 [<span data-ttu-id="eb5ce-140">Compatibilité des versions</span><span class="sxs-lookup"><span data-stu-id="eb5ce-140">Cross-Version Compatibility</span></span>](cross-version-compatibility.md)  
 <span data-ttu-id="eb5ce-141">Décrit les conflits qui peuvent se produire lorsque des paramètres table sont utilisés par un client ou un serveur utilisant une version antérieure de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb5ce-141">Describes conflicts that can occur when table-valued parameters are used by a client or server of a version earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 [<span data-ttu-id="eb5ce-142">Récapitulatif des API de paramètre table ODBC</span><span class="sxs-lookup"><span data-stu-id="eb5ce-142">ODBC Table-Valued Parameter API Summary</span></span>](odbc-table-valued-parameter-api-summary.md)  
 <span data-ttu-id="eb5ce-143">Répertorie les fonctions ODBC qui prennent en charge les paramètres table.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-143">Lists the ODBC functions that support table-valued parameters.</span></span>  
  
 [<span data-ttu-id="eb5ce-144">Exemples de programmation de paramètres table ODBC</span><span class="sxs-lookup"><span data-stu-id="eb5ce-144">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
 <span data-ttu-id="eb5ce-145">Décrit comment réaliser des tâches courantes.</span><span class="sxs-lookup"><span data-stu-id="eb5ce-145">Describes how to perform common tasks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5ce-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb5ce-146">See Also</span></span>  
 <span data-ttu-id="eb5ce-147">[SQL Server Native Client &#40;&#41;ODBC](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="eb5ce-147">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="eb5ce-148">Paramètres table &#40;SQL Server Native Client&#41;</span><span class="sxs-lookup"><span data-stu-id="eb5ce-148">Table-Valued Parameters &#40;SQL Server Native Client&#41;</span></span>](../native-client/features/table-valued-parameters-sql-server-native-client.md)  
  
  
