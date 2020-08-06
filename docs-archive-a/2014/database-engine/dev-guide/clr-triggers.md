---
title: Déclencheurs CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602987"
---
# <a name="clr-triggers"></a><span data-ttu-id="c322b-102">Déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="c322b-102">CLR Triggers</span></span>
  <span data-ttu-id="c322b-103">En raison de l'intégration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] au CLR (Common Language Runtime) [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vous pouvez utiliser n'importe quel langage [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] pour créer des déclencheurs CLR.</span><span class="sxs-lookup"><span data-stu-id="c322b-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="c322b-104">Cette section couvre des informations spécifiques aux déclencheurs implémentés avec l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="c322b-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="c322b-105">Pour une description complète des déclencheurs, consultez [déclencheurs DDL](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="c322b-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="c322b-106">Que sont les déclencheurs ?</span><span class="sxs-lookup"><span data-stu-id="c322b-106">What Are Triggers?</span></span>  
 <span data-ttu-id="c322b-107">Un déclencheur est un type spécial de procédure stockée qui s'exécute automatiquement lorsqu'un événement de langage s'exécute.</span><span class="sxs-lookup"><span data-stu-id="c322b-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c322b-108">intègre deux types généraux de déclencheurs : les déclencheurs du langage de manipulation de données (DML) et les déclencheurs du langage de définition de données (DDL).</span><span class="sxs-lookup"><span data-stu-id="c322b-108">includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="c322b-109">Les déclencheurs DML peuvent être utilisés lorsque des instructions `INSERT`, `UPDATE` ou `DELETE` modifient des données dans une table ou une vue spécifiée.</span><span class="sxs-lookup"><span data-stu-id="c322b-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="c322b-110">Les déclencheurs DDL activent des procédures stockées en réponse à diverses instructions DDL, qui sont essentiellement des instructions qui commencent par `CREATE`, `ALTER` et `DROP`.</span><span class="sxs-lookup"><span data-stu-id="c322b-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="c322b-111">Les déclencheurs DDL peuvent être utilisés dans des tâches d'administration telles que l'audit et la régulation d'opérations de base de données.</span><span class="sxs-lookup"><span data-stu-id="c322b-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="c322b-112">Fonctionnalités uniques des déclencheurs CLR</span><span class="sxs-lookup"><span data-stu-id="c322b-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="c322b-113">Les déclencheurs écrits en [!INCLUDE[tsql](../../includes/tsql-md.md)] peuvent déterminer les colonnes de la vue ou de la table d'activation qui ont été mises à jour à l'aide des fonctions `UPDATE(column)` et `COLUMNS_UPDATED()`.</span><span class="sxs-lookup"><span data-stu-id="c322b-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="c322b-114">Les déclencheurs écrits dans un langage CLR diffèrent des autres objets d'intégration du CLR par bien des aspects.</span><span class="sxs-lookup"><span data-stu-id="c322b-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="c322b-115">Les déclencheurs CLR peuvent effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="c322b-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="c322b-116">référencer des données dans les tables `INSERTED` et `DELETED` ;</span><span class="sxs-lookup"><span data-stu-id="c322b-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="c322b-117">déterminer les colonnes qui ont été modifiées suite à une opération `UPDATE` ;</span><span class="sxs-lookup"><span data-stu-id="c322b-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="c322b-118">accéder aux informations sur les objets de base de données affectés par l'exécution d'instructions DDL.</span><span class="sxs-lookup"><span data-stu-id="c322b-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="c322b-119">Ces fonctionnalités sont fournies intrinsèquement dans le langage de requête, ou par la classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="c322b-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="c322b-120">Pour plus d’informations sur les avantages de l’intégration du CLR et le choix entre le code managé et [!INCLUDE[tsql](../../includes/tsql-md.md)] , consultez [vue d’ensemble de l’intégration du CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c322b-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="c322b-121">Utilisation de la classe SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="c322b-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="c322b-122">La classe `SqlTriggerContext` ne peut pas être construite publiquement et peut uniquement être obtenue en accédant à la propriété `SqlContext.TriggerContext` dans le corps d'un déclencheur CLR.</span><span class="sxs-lookup"><span data-stu-id="c322b-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="c322b-123">La classe `SqlTriggerContext` peut être obtenue à partir du `SqlContext` actif en appelant la propriété `SqlContext.TriggerContext` :</span><span class="sxs-lookup"><span data-stu-id="c322b-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="c322b-124">La classe `SqlTriggerContext` fournit des informations de contexte sur le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="c322b-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="c322b-125">Ces informations contextuelles comprennent le type d'action ayant provoqué l'activation du déclencheur, les colonnes qui ont été modifiées dans une opération UPDATE et, dans le cas d'un déclencheur DDL, une structure `EventData` XML qui décrit l'opération de déclenchement.</span><span class="sxs-lookup"><span data-stu-id="c322b-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="c322b-126">Pour plus d’informations, consultez [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c322b-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="c322b-127">Détermination de l'action du déclencheur</span><span class="sxs-lookup"><span data-stu-id="c322b-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="c322b-128">Une fois que vous avez obtenu un `SqlTriggerContext`, vous pouvez l'utiliser pour déterminer le type d'action ayant provoqué l'activation du déclencheur.</span><span class="sxs-lookup"><span data-stu-id="c322b-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="c322b-129">Ces informations sont disponibles par l'intermédiaire de la propriété `TriggerAction` de la classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="c322b-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="c322b-130">Pour les déclencheurs DML, la propriété `TriggerAction` peut prendre l'une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c322b-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="c322b-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="c322b-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="c322b-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="c322b-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="c322b-133">TriggerAction.Delete (0x3)</span><span class="sxs-lookup"><span data-stu-id="c322b-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="c322b-134">Pour les déclencheurs DDL, la liste de valeurs TriggerAction possibles est considérablement plus longue.</span><span class="sxs-lookup"><span data-stu-id="c322b-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="c322b-135">Pour plus d'informations, consultez la rubrique relative à l'énumération TriggerAction dans le Kit de développement logiciel (SDK) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c322b-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="c322b-136">Utilisation des tables inserted et Deleted</span><span class="sxs-lookup"><span data-stu-id="c322b-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="c322b-137">Deux tables spéciales sont utilisées dans les instructions de déclencheur DML : la table **inserted** et la table **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="c322b-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c322b-138">crée et gère automatiquement ces tables.</span><span class="sxs-lookup"><span data-stu-id="c322b-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="c322b-139">Vous pouvez utiliser ces tables temporaires pour tester les effets de certaines modifications de données et définir des conditions pour les actions de déclencheur DML. Toutefois, vous ne pouvez pas modifier directement les données dans les tables.</span><span class="sxs-lookup"><span data-stu-id="c322b-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="c322b-140">Les déclencheurs CLR peuvent accéder aux tables **inserted** et **Deleted** via le fournisseur in-process du CLR.</span><span class="sxs-lookup"><span data-stu-id="c322b-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="c322b-141">Pour cela, un objet `SqlCommand` est obtenu de l'objet SqlContext.</span><span class="sxs-lookup"><span data-stu-id="c322b-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="c322b-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="c322b-142">For example:</span></span>  
  
 <span data-ttu-id="c322b-143">C#</span><span class="sxs-lookup"><span data-stu-id="c322b-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="c322b-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c322b-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="c322b-145">Détermination des colonnes mises à jour</span><span class="sxs-lookup"><span data-stu-id="c322b-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="c322b-146">Vous pouvez déterminer le nombre de colonnes modifiées par une opération UPDATE en utilisant la propriété `ColumnCount` de l'objet `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="c322b-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="c322b-147">Vous pouvez utiliser la méthode `IsUpdatedColumn`, qui prend l'ordinal de colonne comme paramètre d'entrée, pour déterminer si la colonne a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="c322b-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="c322b-148">Une valeur `True` indique que la colonne a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="c322b-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="c322b-149">Par exemple, cet extrait de code (provenant du déclencheur EmailAudit traité plus loin dans cette rubrique) répertorie toutes les colonnes mises à jour :</span><span class="sxs-lookup"><span data-stu-id="c322b-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="c322b-150">C#</span><span class="sxs-lookup"><span data-stu-id="c322b-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="c322b-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c322b-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="c322b-152">Accès à EventData pour les déclencheurs DDL CLR</span><span class="sxs-lookup"><span data-stu-id="c322b-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="c322b-153">Comme les autres déclencheurs, les déclencheurs DDL activent des procédures stockées en réponse à un événement.</span><span class="sxs-lookup"><span data-stu-id="c322b-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="c322b-154">Toutefois, à la différence des déclencheurs DML, ils ne sont pas activés en réponse à des instructions UPDATE, INSERT ou DELETE sur une table ou une vue.</span><span class="sxs-lookup"><span data-stu-id="c322b-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="c322b-155">Au lieu de cela, ils sont activés en réponse à diverses instructions DDL, qui sont essentiellement des instructions qui commencent par CREATE, ALTER et DROP.</span><span class="sxs-lookup"><span data-stu-id="c322b-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="c322b-156">Les déclencheurs DDL peuvent être utilisés dans des tâches d'administration telles que l'audit et l'analyse des opérations de base de données et des modifications de schéma.</span><span class="sxs-lookup"><span data-stu-id="c322b-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="c322b-157">Les informations sur un événement qui activent un déclencheur DDL sont disponibles dans la propriété `EventData` de la classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="c322b-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="c322b-158">Cette propriété contient une valeur `xml`.</span><span class="sxs-lookup"><span data-stu-id="c322b-158">This property contains an `xml` value.</span></span> <span data-ttu-id="c322b-159">Le schéma xml comprend des informations sur :</span><span class="sxs-lookup"><span data-stu-id="c322b-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="c322b-160">l'heure de l'événement ;</span><span class="sxs-lookup"><span data-stu-id="c322b-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="c322b-161">l'ID du processus système (SPID) de la connexion au cours de laquelle le déclencheur s'est exécuté ;</span><span class="sxs-lookup"><span data-stu-id="c322b-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="c322b-162">le type d'événement qui a lancé le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="c322b-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="c322b-163">Ensuite, selon le type d'événement, le schéma inclut des informations supplémentaires, telles que la base de données dans laquelle s'est produit l'événement, l'objet sur lequel il s'est produit et la commande [!INCLUDE[tsql](../../includes/tsql-md.md)] de l'événement.</span><span class="sxs-lookup"><span data-stu-id="c322b-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="c322b-164">Dans l'exemple suivant, le déclencheur DDL suivant retourne la propriété `EventData` brute.</span><span class="sxs-lookup"><span data-stu-id="c322b-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c322b-165">L'envoi de résultats et de messages par le biais de l'objet `SqlPipe` est montré ici à titre indicatif uniquement. Cette opération est généralement déconseillée pour le code de production lors de la programmation de déclencheurs CLR.</span><span class="sxs-lookup"><span data-stu-id="c322b-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="c322b-166">Les données supplémentaires retournées peuvent être inattendues et générer des erreurs d'application.</span><span class="sxs-lookup"><span data-stu-id="c322b-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="c322b-167">C#</span><span class="sxs-lookup"><span data-stu-id="c322b-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="c322b-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c322b-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="c322b-169">L'exemple de sortie suivant est la valeur de la propriété `EventData` après l'activation d'un déclencheur DDL par un événement `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="c322b-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="c322b-170">En plus des informations accessibles par le biais de la classe `SqlTriggerContext`, les requêtes peuvent toujours faire référence à `COLUMNS_UPDATED` et aux tables inserted/deleted dans le texte d'une commande exécutée in-process.</span><span class="sxs-lookup"><span data-stu-id="c322b-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="c322b-171">Exemple de déclencheur CLR</span><span class="sxs-lookup"><span data-stu-id="c322b-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="c322b-172">Dans cet exemple, imaginez le scénario suivant : vous laissez l'utilisateur entrer l'ID de son choix, mais vous souhaitez connaître les utilisateurs qui ont spécifiquement entré une adresse de messagerie en tant qu'ID.</span><span class="sxs-lookup"><span data-stu-id="c322b-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="c322b-173">Le déclencheur suivant détecterait cette information et l'enregistrerait dans une table d'audit.</span><span class="sxs-lookup"><span data-stu-id="c322b-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c322b-174">L'envoi de résultats et ds messages par le biais de l'objet `SqlPipe` est montré ici à titre indicatif uniquement. Cette opération est généralement déconseillée pour le code de production.</span><span class="sxs-lookup"><span data-stu-id="c322b-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="c322b-175">Certaines données supplémentaires retournées peuvent être inattendues et générer des erreurs d'application.</span><span class="sxs-lookup"><span data-stu-id="c322b-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="c322b-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c322b-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="c322b-177">Supposons que deux tables existent avec les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c322b-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="c322b-178">L' [!INCLUDE[tsql](../../includes/tsql-md.md)] instruction qui crée le déclencheur dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est la suivante et suppose que l’assembly **SQLCLRTest** est déjà inscrit dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de données active.</span><span class="sxs-lookup"><span data-stu-id="c322b-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="c322b-179">Validation et annulation de transactions non valides</span><span class="sxs-lookup"><span data-stu-id="c322b-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="c322b-180">Il est courant d'utiliser des déclencheurs pour valider et annuler des transactions INSERT, UPDATE ou DELETE non valides, ou pour empêcher les modifications à votre schéma de base de données.</span><span class="sxs-lookup"><span data-stu-id="c322b-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="c322b-181">Pour ce faire, vous pouvez incorporer une logique de validation dans votre déclencheur, puis restaurer la transaction actuelle si l'action ne répond pas aux critères de validation.</span><span class="sxs-lookup"><span data-stu-id="c322b-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="c322b-182">Lorsque la méthode `Transaction.Rollback` ou une commande SqlCommand avec le texte de commande « TRANSACTION ROLLBACK » est appelée dans un déclencheur, elle lève une exception avec un message d'erreur ambigu et doit être encapsulée dans un bloc try/catch.</span><span class="sxs-lookup"><span data-stu-id="c322b-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="c322b-183">Le message d'erreur qui s'affiche est semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="c322b-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="c322b-184">Cette exception est attendue et le bloc try/catch est nécessaire pour que l'exécution du code continue.</span><span class="sxs-lookup"><span data-stu-id="c322b-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="c322b-185">Lorsque l'exécution du code du déclencheur se termine, une autre exception est levée.</span><span class="sxs-lookup"><span data-stu-id="c322b-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="c322b-186">Cette exception est également attendue, et un bloc try/catch autour de l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] qui effectue l'action qui active le déclencheur est nécessaire pour que l'exécution puisse continuer.</span><span class="sxs-lookup"><span data-stu-id="c322b-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="c322b-187">Malgré les deux exceptions levées, la transaction est restaurée et les modifications ne sont pas validées dans la table.</span><span class="sxs-lookup"><span data-stu-id="c322b-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="c322b-188">Une différence majeure entre les déclencheurs CLR et les déclencheurs [!INCLUDE[tsql](../../includes/tsql-md.md)] vient du fait que les déclencheurs [!INCLUDE[tsql](../../includes/tsql-md.md)] peuvent continuer à effectuer des tâches une fois la transaction restaurée.</span><span class="sxs-lookup"><span data-stu-id="c322b-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c322b-189">Exemple</span><span class="sxs-lookup"><span data-stu-id="c322b-189">Example</span></span>  
 <span data-ttu-id="c322b-190">Le déclencheur suivant effectue une validation simple d'instructions INSERT sur une table.</span><span class="sxs-lookup"><span data-stu-id="c322b-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="c322b-191">Si la valeur entière insérée est égale à un, la transaction est restaurée et la valeur n'est pas insérée dans la table.</span><span class="sxs-lookup"><span data-stu-id="c322b-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="c322b-192">Toutes les autres valeurs entières sont insérées dans la table.</span><span class="sxs-lookup"><span data-stu-id="c322b-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="c322b-193">Notez le bloc try/catch autour de la méthode `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="c322b-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="c322b-194">Le script [!INCLUDE[tsql](../../includes/tsql-md.md)] crée une table, un assembly et une procédure stockée managée de test.</span><span class="sxs-lookup"><span data-stu-id="c322b-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="c322b-195">Notez que les deux instructions INSERT sont encapsulées dans un bloc try/catch pour que l'exception levée au terme de l'exécution du déclencheur soit interceptée.</span><span class="sxs-lookup"><span data-stu-id="c322b-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="c322b-196">C#</span><span class="sxs-lookup"><span data-stu-id="c322b-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="c322b-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c322b-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="c322b-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c322b-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c322b-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c322b-199">See Also</span></span>  
 <span data-ttu-id="c322b-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c322b-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c322b-201">[Déclencheurs DML](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="c322b-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="c322b-202">[Déclencheurs DDL](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="c322b-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="c322b-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c322b-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="c322b-204">[Génération d’objets de base de données avec Common Language Runtime &#40;l’intégration du CLR&#41;](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="c322b-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="c322b-205">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c322b-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
