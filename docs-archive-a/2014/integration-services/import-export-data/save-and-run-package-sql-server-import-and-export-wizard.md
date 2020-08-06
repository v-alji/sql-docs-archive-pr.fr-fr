---
title: Enregistrer et exécuter le package (Assistant importation et exportation SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611878"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="09ae8-102">Enregistrer et exécuter le package (Assistant Importation et Exportation SQL Server)</span><span class="sxs-lookup"><span data-stu-id="09ae8-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="09ae8-103">Utilisez la boîte de dialogue **enregistrer et exécuter le package** pour exécuter le package immédiatement, l’enregistrer pour l’exécuter ultérieurement, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="09ae8-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-104"> Si vous arrêtez un package avant la fin de son exécution, il n'est alors pas enregistré même si vous avez coché la case **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="09ae8-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="09ae8-105">Pour en savoir plus sur cet Assistant, consultez [Assistant Importation et Exportation SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="09ae8-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="09ae8-106">Pour en savoir plus sur les options de démarrage de l’Assistant, ainsi que sur les autorisations requises pour exécuter correctement l’Assistant, consultez [exécuter l’Assistant importation et exportation SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="09ae8-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="09ae8-107">La fonction de l'Assistant Importation et Exportation SQL Server est de copier des données d'une source vers une destination.</span><span class="sxs-lookup"><span data-stu-id="09ae8-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="09ae8-108">L'Assistant peut également créer une base de données de destination et des tables de destination à votre intention.</span><span class="sxs-lookup"><span data-stu-id="09ae8-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="09ae8-109">Toutefois, si vous devez copier plusieurs tables ou bases de données, ou autres types d'objets de bases de données, vous devez plutôt utiliser l'Assistant Copie de base de données.</span><span class="sxs-lookup"><span data-stu-id="09ae8-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="09ae8-110">Pour plus d'informations, consultez [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="09ae8-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="09ae8-111">Options</span><span class="sxs-lookup"><span data-stu-id="09ae8-111">Options</span></span>  
 <span data-ttu-id="09ae8-112">**Exécuter immédiatement**</span><span class="sxs-lookup"><span data-stu-id="09ae8-112">**Execute immediately**</span></span>  
 <span data-ttu-id="09ae8-113">Choisissez cette option pour lancer l'exécution du package immédiatement.</span><span class="sxs-lookup"><span data-stu-id="09ae8-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="09ae8-114">**Enregistrer le package SSIS**</span><span class="sxs-lookup"><span data-stu-id="09ae8-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="09ae8-115">Permet d'enregistrer le package pour une exécution ultérieure, avec la possibilité l'exécuter immédiatement.</span><span class="sxs-lookup"><span data-stu-id="09ae8-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-116">Dans [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], l'option permettant d'enregistrer le package créé par l'Assistant n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="09ae8-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="09ae8-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="09ae8-117">**SQL Server**</span></span>  
 <span data-ttu-id="09ae8-118">Sélectionnez cette option pour enregistrer le package dans la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` base de données.</span><span class="sxs-lookup"><span data-stu-id="09ae8-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-119">Cette option est disponible uniquement si vous avez sélectionné l’option **enregistrer le package SSIS** .</span><span class="sxs-lookup"><span data-stu-id="09ae8-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="09ae8-120">**Système de fichiers**</span><span class="sxs-lookup"><span data-stu-id="09ae8-120">**File system**</span></span>  
 <span data-ttu-id="09ae8-121">Permet d'enregistrer le package en tant que fichier portant l'extension .dtsx.</span><span class="sxs-lookup"><span data-stu-id="09ae8-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-122">Cette option est disponible uniquement si vous avez sélectionné l’option **enregistrer le package SSIS** .</span><span class="sxs-lookup"><span data-stu-id="09ae8-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="09ae8-123">**Niveau de protection du package**</span><span class="sxs-lookup"><span data-stu-id="09ae8-123">**Package protection level**</span></span>  
 <span data-ttu-id="09ae8-124">Sélectionnez un niveau de protection dans la liste.</span><span class="sxs-lookup"><span data-stu-id="09ae8-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="09ae8-125">Le niveau de protection détermine la méthode de protection (par mot de passe ou par clé utilisateur) et l'étendue de la protection du package.</span><span class="sxs-lookup"><span data-stu-id="09ae8-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="09ae8-126">La protection peut inclure toutes les données ou uniquement les données sensibles.</span><span class="sxs-lookup"><span data-stu-id="09ae8-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="09ae8-127">Pour comprendre les exigences et les options de sécurité des packages, consultez [Access Control pour obtenir des données sensibles dans packages](../security/access-control-for-sensitive-data-in-packages.md) et [vue d’ensemble de la sécurité &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="09ae8-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-128">Cette option est disponible uniquement si vous avez sélectionné l’option **enregistrer le package SSIS** .</span><span class="sxs-lookup"><span data-stu-id="09ae8-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="09ae8-129">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="09ae8-129">**Password**</span></span>  
 <span data-ttu-id="09ae8-130">Tapez un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="09ae8-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-131">Cette option est disponible uniquement si vous avez défini l’option **niveau de protection du package** pour **chiffrer les données sensibles avec un mot de passe** ou **chiffrer toutes les données avec le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="09ae8-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="09ae8-132">**Retapez le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="09ae8-132">**Retype password**</span></span>  
 <span data-ttu-id="09ae8-133">Entrez à nouveau le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="09ae8-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="09ae8-134">Cette option est disponible uniquement si vous avez défini l’option **niveau de protection du package** pour **chiffrer les données sensibles avec un mot de passe** ou **chiffrer toutes les données avec le mot de passe**.</span><span class="sxs-lookup"><span data-stu-id="09ae8-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ae8-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09ae8-135">See Also</span></span>  
 <span data-ttu-id="09ae8-136">[Exécution de projets et de packages](../packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="09ae8-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="09ae8-137">Enregistrer des packages</span><span class="sxs-lookup"><span data-stu-id="09ae8-137">Save Packages</span></span>](../save-packages.md)  
  
  
