---
title: Conseiller de compilation native | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
f1_keywords:
- sql12.swb.nativecompilationwizard.f1
- swb.nativecompilationwizard.f1
ms.assetid: d3898a47-2985-4a08-bc70-fd8331a01b7b
author: rothja
ms.author: jroth
ms.openlocfilehash: b2182d89489af5da8bc3b85b89484fbbf72e4dfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709424"
---
# <a name="native-compilation-advisor"></a><span data-ttu-id="253cf-102">Conseiller de compilation native</span><span class="sxs-lookup"><span data-stu-id="253cf-102">Native Compilation Advisor</span></span>
  <span data-ttu-id="253cf-103">L'outil de génération de rapports sur les performances des transactions (voir [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) vous indique quelles procédures stockées interprétées dans votre base de données tireront parti de l'utilisation de la compilation native.</span><span class="sxs-lookup"><span data-stu-id="253cf-103">Transaction performance reports tool (see [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md)) informs you about which interpreted stored procedures in your database will benefit if ported to use native compilation.</span></span> <span data-ttu-id="253cf-104">Après avoir identifié une procédure stockée que vous souhaitez déplacer pour utiliser la compilation native, vous pouvez utiliser le conseiller de compilation native pour vous aider à migrer la procédure stockée interprétée vers la compilation native.</span><span class="sxs-lookup"><span data-stu-id="253cf-104">After you identify a stored procedure that you would like to port to use native compilation, you can use the native compilation advisor to help you migrate the interpreted stored procedure to native compilation.</span></span> <span data-ttu-id="253cf-105">Pour plus d'informations sur les procédures stockées compilées en mode natif, consultez [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="253cf-105">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="253cf-106">Pour démarrer, connectez-vous à l'instance qui contient la procédure stockée interprétée.</span><span class="sxs-lookup"><span data-stu-id="253cf-106">To begin, connect to the instance that contains the interpreted stored procedure.</span></span> <span data-ttu-id="253cf-107">Vous pouvez vous connecter à l'instance [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]ou [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="253cf-107">You can connect to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance.</span></span> <span data-ttu-id="253cf-108">Toutefois, si vous souhaitez effectuer une opération de migration avec le conseiller, vous devez vous connecter à une instance [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] sur laquelle la fonctionnalité OLTP en mémoire est activée.</span><span class="sxs-lookup"><span data-stu-id="253cf-108">However, if you wish to perform a migration operation with the advisor, you must connect to a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] instance on which In-Memory OLTP functionality is enabled.</span></span> <span data-ttu-id="253cf-109">Pour plus d'informations sur les spécifications applicables à la fonctionnalité OLTP en mémoire, consultez [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="253cf-109">For more information about In-Memory OLTP requirements, see [Requirements for Using Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="253cf-110">Pour plus d’informations sur les méthodologies de migration, consultez [OLTP en mémoire - Modèles de charge de travail courants et considérations relatives à la migration](https://msdn.microsoft.com/library/dn673538.aspx).</span><span class="sxs-lookup"><span data-stu-id="253cf-110">For information about migration methodologies, see [In-Memory OLTP - Common Workload Patterns and Migration Considerations](https://msdn.microsoft.com/library/dn673538.aspx).</span></span>  
  
## <a name="walkthrough-using-the-native-compilation-advisor"></a><span data-ttu-id="253cf-111">Procédure pas à pas d'utilisation du Conseiller de compilation native</span><span class="sxs-lookup"><span data-stu-id="253cf-111">Walkthrough Using the Native Compilation Advisor</span></span>  
 <span data-ttu-id="253cf-112">Dans l' **Explorateur d'objets**, cliquez avec le bouton droit sur la procédure stockée à convertir, puis sélectionnez **Conseiller de compilation native**.</span><span class="sxs-lookup"><span data-stu-id="253cf-112">In **Object Explorer**, right click the stored procedure you want to convert, and select **Native Compilation Advisor**.</span></span> <span data-ttu-id="253cf-113">Ce faisant, vous affichez la page d'accueil du **Conseiller compilation native de procédure stockée**.</span><span class="sxs-lookup"><span data-stu-id="253cf-113">This will display the welcome page for the **Stored Procedure Native Compilation Advisor**.</span></span> <span data-ttu-id="253cf-114">Cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="253cf-114">Click **Next** to continue.</span></span>  
  
### <a name="stored-procedure-validation"></a><span data-ttu-id="253cf-115">Validation de la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="253cf-115">Stored Procedure Validation</span></span>  
 <span data-ttu-id="253cf-116">Cette page signale si la procédure stockée utilise des éléments qui ne sont pas compatibles avec la compilation native.</span><span class="sxs-lookup"><span data-stu-id="253cf-116">This page will report if the stored procedure uses any constructs that are not compatible with native compilation.</span></span> <span data-ttu-id="253cf-117">Vous pouvez cliquer sur **Suivant** pour afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="253cf-117">You can click **Next** to see details.</span></span> <span data-ttu-id="253cf-118">Si certains éléments ne sont pas compatibles avec la compilation native, vous pouvez cliquer sur **Suivant** pour afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="253cf-118">If there are constructs that are not compatible with native compilation, you can click **Next** to see details.</span></span>  
  
### <a name="stored-procedure-validation-result"></a><span data-ttu-id="253cf-119">Résultats de la validation de la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="253cf-119">Stored Procedure Validation Result</span></span>  
 <span data-ttu-id="253cf-120">Si certains éléments ne sont pas compatibles avec la compilation native, la page **Résultat de la validation de la procédure stockée** affiche les détails.</span><span class="sxs-lookup"><span data-stu-id="253cf-120">If there are constructs that are not compatible with native compilation, the **Stored Procedure Validation Result** page will display details.</span></span> <span data-ttu-id="253cf-121">Vous pouvez générer un rapport (cliquez sur **Générer le rapport**), quitter le **Conseiller de compilation native**et mettre à jour votre code afin qu’il soit compatible avec la compilation native.</span><span class="sxs-lookup"><span data-stu-id="253cf-121">You can generate a report (click **Generate Report**), exit the **Native Compilation Advisor**, and update your code so that it is compatible with native compilation.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="253cf-122">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="253cf-122">Code Sample</span></span>  
 <span data-ttu-id="253cf-123">L'exemple suivant illustre une procédure stockée interprétée et la procédure stockée équivalente pour la compilation native.</span><span class="sxs-lookup"><span data-stu-id="253cf-123">The following sample shows an interpreted stored procedure and the equivalent stored procedure for native compilation.</span></span> <span data-ttu-id="253cf-124">L'exemple suppose la présence d'un répertoire appelé c:\data.</span><span class="sxs-lookup"><span data-stu-id="253cf-124">The sample assumes a directory called c:\data.</span></span>  
  
```sql  
CREATE DATABASE Demo  
ON  
PRIMARY(NAME = [Demo_data],  
FILENAME = 'C:\DATA\Demo_data.mdf', size=500MB)  
, FILEGROUP [Demo_fg] CONTAINS MEMORY_OPTIMIZED_DATA(  
NAME = [Demo_dir],  
FILENAME = 'C:\DATA\Demo_dir')  
LOG ON (name = [Demo_log], Filename='C:\DATA\Demo_log.ldf', size=500MB)  
COLLATE Latin1_General_100_BIN2;  
GO  
USE Demo;  
GO  
  
CREATE TABLE [dbo].[SalesOrders]  
(  
     [order_id] [int] NOT NULL,  
     [order_date] [datetime] NOT NULL,  
     [order_status] [tinyint] NOT NULL  
  
CONSTRAINT [PK_SalesOrders] PRIMARY KEY NONCLUSTERED HASH   
(  
     [order_id]  
)WITH ( BUCKET_COUNT = 2097152)  
)WITH ( MEMORY_OPTIMIZED = ON )  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrder] @id INT, @date DATETIME2, @status TINYINT  
AS   
BEGIN   
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
  
go  
  
CREATE PROCEDURE [dbo].[InsertOrderXTP] @id INT, @date DATETIME2, @status TINYINT  
  WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS   
BEGIN ATOMIC WITH   
(    TRANSACTION ISOLATION LEVEL = SNAPSHOT,  
     LANGUAGE = N'us_english')  
  
  INSERT dbo.SalesOrders VALUES (@id, @date, @status)  
  
END  
go  
  
select * from SalesOrders  
go  
exec dbo.InsertOrder @id= 10, @date = '1956-01-01 12:00:00', @status = 1 ;  
exec dbo.InsertOrderXTP @id= 11, @date = '1956-01-01 12:01:00', @status = 2 ;  
select * from SalesOrders  
```  
  
## <a name="see-also"></a><span data-ttu-id="253cf-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="253cf-125">See Also</span></span>  
 [<span data-ttu-id="253cf-126">Migration vers OLTP en mémoire</span><span class="sxs-lookup"><span data-stu-id="253cf-126">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
