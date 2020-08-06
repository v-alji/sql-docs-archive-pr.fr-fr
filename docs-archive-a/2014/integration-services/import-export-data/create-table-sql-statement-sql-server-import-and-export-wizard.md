---
title: Instruction SQL de création de table (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611893"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="65bba-102">Instruction SQL de création de table (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="65bba-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="65bba-103">Utilisez la boîte de dialogue **instruction SQL de création de table** pour afficher l’instruction qui a été générée automatiquement ou pour la modifier dans vos besoins.</span><span class="sxs-lookup"><span data-stu-id="65bba-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="65bba-104">Si vous modifiez cette instruction, il est possible que vous deviez également apporter des modifications associées au mappage de colonnes. Vous devrez alors gérer manuellement l'instruction SQL modifiée.</span><span class="sxs-lookup"><span data-stu-id="65bba-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="65bba-105">génère une instruction CREATE TABLE par défaut basée sur la source de données connectée.</span><span class="sxs-lookup"><span data-stu-id="65bba-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="65bba-106">Cette instruction CREATE TABLE par défaut n'inclut pas l'attribut FILESTREAM, même si la table source inclut une colonne dans laquelle l'attribut FILESTREAM est déclaré.</span><span class="sxs-lookup"><span data-stu-id="65bba-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="65bba-107">Pour exécuter un composant [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] avec l'attribut FILESTREAM, implémentez d'abord le stockage FILESTREAM sur la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="65bba-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="65bba-108">Ajoutez ensuite l’attribut FILESTREAM à l’instruction CREATE TABLE dans la boîte de dialogue **Créer une table** .</span><span class="sxs-lookup"><span data-stu-id="65bba-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="65bba-109">Pour plus d’informations, consultez [Données blob &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="65bba-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="65bba-110">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="65bba-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="65bba-111">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="65bba-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="65bba-112">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="65bba-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="65bba-113">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="65bba-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="65bba-114">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="65bba-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="65bba-115">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="65bba-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="65bba-116">Options</span><span class="sxs-lookup"><span data-stu-id="65bba-116">Options</span></span>  
 <span data-ttu-id="65bba-117">**Instruction SQL**</span><span class="sxs-lookup"><span data-stu-id="65bba-117">**SQL statement**</span></span>  
 <span data-ttu-id="65bba-118">Affiche l'instruction SQL générée automatiquement et permet sa modification.</span><span class="sxs-lookup"><span data-stu-id="65bba-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65bba-119">Si vous souhaitez inclure un retour chariot dans l'instruction SQL, appuyez sur CTRL+ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="65bba-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="65bba-120">Si vous appuyez seulement sur ENTRÉE, la boîte de dialogue se referme.</span><span class="sxs-lookup"><span data-stu-id="65bba-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="65bba-121">**Générer automatiquement**</span><span class="sxs-lookup"><span data-stu-id="65bba-121">**Autogenerate**</span></span>  
 <span data-ttu-id="65bba-122">Restaurez l’instruction SQL par défaut, si vous l’avez modifiée, en cliquant sur **Créer automatiquement**.</span><span class="sxs-lookup"><span data-stu-id="65bba-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
