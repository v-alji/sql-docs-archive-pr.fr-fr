---
title: Boîte de dialogue Détails de la conversion de colonne (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611899"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="c60b0-102">Boîte de dialogue Détails de la conversion de colonne (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c60b0-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="c60b0-103">Utilisez la boîte de dialogue détails de la **conversion de colonne** pour consulter des informations détaillées sur la conversion d’une colonne.</span><span class="sxs-lookup"><span data-stu-id="c60b0-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="c60b0-104">Ces informations de conversion incluent notamment le type de données de la colonne au niveau de la source et de la destination, ainsi que la conversion à laquelle l'Assistant procèdera.</span><span class="sxs-lookup"><span data-stu-id="c60b0-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="c60b0-105">Cette page répertorie également les fichiers de mappage de type de données que l'Assistant utilise pour déterminer les conversions de type de données requises.</span><span class="sxs-lookup"><span data-stu-id="c60b0-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="c60b0-106">installe ces fichiers de mappage de type de données au cours de l'installation.</span><span class="sxs-lookup"><span data-stu-id="c60b0-106">installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="c60b0-107">**Pour ouvrir la boîte de dialogue Détails de la conversion de colonne**</span><span class="sxs-lookup"><span data-stu-id="c60b0-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="c60b0-108">Sur la page **vérifier les problèmes de type de données** de l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistant importation et exportation, dans la liste **table** , sélectionnez une table.</span><span class="sxs-lookup"><span data-stu-id="c60b0-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="c60b0-109">Dans la liste **mappage de type de données** , double-cliquez sur la ligne qui contient la colonne pour laquelle vous souhaitez afficher les détails de la conversion.</span><span class="sxs-lookup"><span data-stu-id="c60b0-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="c60b0-110">Pour en savoir plus sur l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistant importation et exportation, consultez [SQL Server Assistant importation et exportation](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c60b0-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="c60b0-111">Pour en savoir plus sur les options de démarrage de l’Assistant et sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c60b0-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="c60b0-112">La fonction de l'Assistant Importation et Exportation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="c60b0-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="c60b0-113">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="c60b0-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="c60b0-114">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="c60b0-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="c60b0-115">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="c60b0-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
