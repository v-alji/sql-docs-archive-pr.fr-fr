---
title: Exécution de l’opération (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611889"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="2f42d-102">Exécution de l'opération (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2f42d-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="2f42d-103">Utilisez la page opération en cours d' **exécution** pour afficher la progression et les résultats de l’opération d’importation/exportation, et pour interrompre l’opération si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2f42d-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="2f42d-104">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2f42d-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="2f42d-105">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2f42d-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2f42d-106">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="2f42d-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="2f42d-107">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="2f42d-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="2f42d-108">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="2f42d-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="2f42d-109">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2f42d-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f42d-110">Options</span><span class="sxs-lookup"><span data-stu-id="2f42d-110">Options</span></span>  
 <span data-ttu-id="2f42d-111">**Action**</span><span class="sxs-lookup"><span data-stu-id="2f42d-111">**Action**</span></span>  
 <span data-ttu-id="2f42d-112">Affiche chaque action faisant partie de l'opération.</span><span class="sxs-lookup"><span data-stu-id="2f42d-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="2f42d-113">**État**</span><span class="sxs-lookup"><span data-stu-id="2f42d-113">**Status**</span></span>  
 <span data-ttu-id="2f42d-114">Indique la réussite ou l'échec de chaque action.</span><span class="sxs-lookup"><span data-stu-id="2f42d-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="2f42d-115">**Message**</span><span class="sxs-lookup"><span data-stu-id="2f42d-115">**Message**</span></span>  
 <span data-ttu-id="2f42d-116">Affiche les messages d'information et les messages d'erreur que l'action peut générer.</span><span class="sxs-lookup"><span data-stu-id="2f42d-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="2f42d-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="2f42d-117">**Filter**</span></span>  
 <span data-ttu-id="2f42d-118">Indiquez si vous voulez afficher uniquement les erreurs, les avertissements ou les actions qui aboutissent.</span><span class="sxs-lookup"><span data-stu-id="2f42d-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="2f42d-119">Vous pouvez revenir à l’affichage par défaut en choisissant **afficher toutes les actions**.</span><span class="sxs-lookup"><span data-stu-id="2f42d-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="2f42d-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="2f42d-120">**Stop**</span></span>  
 <span data-ttu-id="2f42d-121">Interrompez l’opération, si nécessaire, en utilisant le bouton **arrêter** .</span><span class="sxs-lookup"><span data-stu-id="2f42d-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="2f42d-122">**Report**</span><span class="sxs-lookup"><span data-stu-id="2f42d-122">**Report**</span></span>  
 <span data-ttu-id="2f42d-123">Affichez un rapport de résultats, enregistrez-le dans un fichier, copiez-le vers le Presse-papiers, ou envoyez-le par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="2f42d-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
