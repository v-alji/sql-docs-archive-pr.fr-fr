---
title: Enregistrer le package SSIS (Assistant Importation et Exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611874"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="05780-102">Enregistrer le package SSIS (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="05780-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="05780-103">Utilisez la page **enregistrer le package SSIS** pour nommer, décrire et enregistrer un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Package Integration Services ( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) dans la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` base de données ou dans un fichier portant l’extension. dtsx.</span><span class="sxs-lookup"><span data-stu-id="05780-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05780-104">Dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], l'option permettant d'enregistrer le package créé par l'Assistant n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="05780-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="05780-105">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="05780-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="05780-106">Pour en savoir plus sur les options de démarrage de l’Assistant et sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="05780-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="05780-107">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="05780-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="05780-108">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="05780-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="05780-109">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="05780-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="05780-110">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="05780-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="05780-111">Options statiques</span><span class="sxs-lookup"><span data-stu-id="05780-111">Static Options</span></span>  
 <span data-ttu-id="05780-112">**Nom**</span><span class="sxs-lookup"><span data-stu-id="05780-112">**Name**</span></span>  
 <span data-ttu-id="05780-113">Permet de spécifier un nom unique pour le package.</span><span class="sxs-lookup"><span data-stu-id="05780-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="05780-114">**Description**</span><span class="sxs-lookup"><span data-stu-id="05780-114">**Description**</span></span>  
 <span data-ttu-id="05780-115">Permet de décrire le package.</span><span class="sxs-lookup"><span data-stu-id="05780-115">Provide a description for the package.</span></span> <span data-ttu-id="05780-116">En règle générale, décrivez le package par rapport à sa fonction pour le rendre descriptif et faciliter sa gestion.</span><span class="sxs-lookup"><span data-stu-id="05780-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="05780-117">**Cible**</span><span class="sxs-lookup"><span data-stu-id="05780-117">**Target**</span></span>  
 <span data-ttu-id="05780-118">Permet d'afficher la cible ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou fichier) définie préalablement pour le fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="05780-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="05780-119">Options dynamiques de la cible</span><span class="sxs-lookup"><span data-stu-id="05780-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="05780-120">Cible = SQL Server</span><span class="sxs-lookup"><span data-stu-id="05780-120">Target = SQL Server</span></span>  
 <span data-ttu-id="05780-121">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="05780-121">**Server name**</span></span>  
 <span data-ttu-id="05780-122">Lorsque vous sélectionnez une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tapez ou sélectionnez le nom du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="05780-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="05780-123">**Utiliser l'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="05780-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="05780-124">Lorsque vous sélectionnez une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], indiquez si la connexion au serveur utilise l'authentification intégrée Windows.</span><span class="sxs-lookup"><span data-stu-id="05780-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="05780-125">Il s'agit de la méthode d'authentification conseillée.</span><span class="sxs-lookup"><span data-stu-id="05780-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="05780-126">**Utiliser l’authentification SQL Server**</span><span class="sxs-lookup"><span data-stu-id="05780-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="05780-127">Lorsque vous sélectionnez une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], indiquez si la connexion au serveur utilise l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="05780-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="05780-128">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="05780-128">**User name**</span></span>  
 <span data-ttu-id="05780-129">Lorsque vous sélectionnez une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et définissez l'authentification SQL Server, tapez le nom d'utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05780-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="05780-130">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="05780-130">**Password**</span></span>  
 <span data-ttu-id="05780-131">Lorsque vous sélectionnez une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et définissez l'authentification SQL Server, tapez le mot de passe [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05780-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="05780-132">Cible = Système de fichiers</span><span class="sxs-lookup"><span data-stu-id="05780-132">Target = File System</span></span>  
 <span data-ttu-id="05780-133">**Nom de fichier**</span><span class="sxs-lookup"><span data-stu-id="05780-133">**File name**</span></span>  
 <span data-ttu-id="05780-134">Lorsque vous avez sélectionné une destination de fichier, tapez le chemin d’accès au fichier de destination ou utilisez le bouton **Parcourir** .</span><span class="sxs-lookup"><span data-stu-id="05780-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="05780-135">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="05780-135">**Browse**</span></span>  
 <span data-ttu-id="05780-136">Lorsque vous avez sélectionné une destination de fichier, accédez au fichier de destination à l’aide de la boîte de dialogue **enregistrer le package** .</span><span class="sxs-lookup"><span data-stu-id="05780-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05780-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05780-137">See Also</span></span>  
 [<span data-ttu-id="05780-138">Enregistrer des packages</span><span class="sxs-lookup"><span data-stu-id="05780-138">Save Packages</span></span>](../save-packages.md)  
  
  
