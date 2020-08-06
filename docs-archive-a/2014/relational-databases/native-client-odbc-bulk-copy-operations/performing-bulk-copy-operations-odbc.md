---
title: Exécution d’opérations de copie en bloc (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708287"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="5ac81-102">Exécution d'opérations de copie en bloc (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5ac81-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="5ac81-103">Par défaut, ODBC ne prend pas directement en charge les opérations de copie en bloc [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac81-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="5ac81-104">En cas de connexion à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 ou ultérieure, le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client prend en charge les fonctions de la bibliothèque de bases de données qui effectuent les opérations de copie en bloc [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac81-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="5ac81-105">Cette extension spécifique au pilote fournit un chemin d'accès de mise à niveau simple pour les applications de bibliothèque de bases de données existantes qui utilisent les fonctions de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac81-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="5ac81-106">La copie en bloc spécialisée est prise en charge dans les fichiers suivants :</span><span class="sxs-lookup"><span data-stu-id="5ac81-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="5ac81-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="5ac81-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="5ac81-108">Inclut les prototypes de fonction et les définitions de constante pour les fonctions de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac81-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="5ac81-109">sqlncli.h doit être inclus dans l'application ODBC exécutant les opérations de copie en bloc et se trouver dans le chemin d'accès Include de l'application lorsqu'il est compilé.</span><span class="sxs-lookup"><span data-stu-id="5ac81-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="5ac81-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="5ac81-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="5ac81-111">Doit être dans le chemin d'accès de la bibliothèque de l'éditeur de liens et spécifié comme fichier à lier.</span><span class="sxs-lookup"><span data-stu-id="5ac81-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="5ac81-112">sqlncli11.lib est distribué avec le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5ac81-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="5ac81-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="5ac81-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="5ac81-114">Doit être présent lors de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="5ac81-114">Must be present at execution time.</span></span> <span data-ttu-id="5ac81-115">sqlncli11.dll est distribué avec le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5ac81-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac81-116">La fonction ODBC **SQLBulkOperations** n’a aucune relation avec les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctions de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac81-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="5ac81-117">Les applications doivent utiliser les fonctions de copie en bloc spécifiques à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour effectuer les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="5ac81-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="5ac81-118">Enregistrement minimal des copies en bloc dans le journal</span><span class="sxs-lookup"><span data-stu-id="5ac81-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="5ac81-119">Avec le mode de récupération complète, toutes les opérations d'insertion de lignes effectuées par le chargement en masse sont intégralement enregistrées dans le journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="5ac81-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="5ac81-120">Pour les chargements de données volumineux, le journal des transactions peut se remplir rapidement.</span><span class="sxs-lookup"><span data-stu-id="5ac81-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="5ac81-121">Sous certaines conditions, l'enregistrement minimal est possible.</span><span class="sxs-lookup"><span data-stu-id="5ac81-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="5ac81-122">L'enregistrement minimal réduit le risque qu'une opération de chargement en masse ne remplisse l'espace du journal et se révèle plus efficace que l'enregistrement complet.</span><span class="sxs-lookup"><span data-stu-id="5ac81-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="5ac81-123">Pour plus d’informations sur l’utilisation de la journalisation minimale, consultez [Configuration requise pour la journalisation minimale dans l’importation en bloc](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="5ac81-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ac81-124">Notes</span><span class="sxs-lookup"><span data-stu-id="5ac81-124">Remarks</span></span>  
 <span data-ttu-id="5ac81-125">Lors de l'utilisation de bcp.exe dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, il se peut que vous rencontriez des erreurs là où il n'en existait pas avant [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac81-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="5ac81-126">La raison en est que dans les versions ultérieures, bcp.exe n'effectue plus la conversion implicite des types de données.</span><span class="sxs-lookup"><span data-stu-id="5ac81-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="5ac81-127">Avant [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe convertissait les données numériques en type de données money, si la table cible avait un tel type.</span><span class="sxs-lookup"><span data-stu-id="5ac81-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="5ac81-128">Toutefois, dans ce cas, bcp.exe tronquait simplement les champs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="5ac81-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="5ac81-129">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], quand les types de données ne correspondent pas entre le fichier et la table cible, bcp.exe déclenche une erreur s'il existe des données qui devraient être tronquées pour contenir dans la table cible.</span><span class="sxs-lookup"><span data-stu-id="5ac81-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="5ac81-130">Pour résoudre cette erreur, corrigez les données de sorte qu'elles correspondent au type de données cible.</span><span class="sxs-lookup"><span data-stu-id="5ac81-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="5ac81-131">Le cas échéant, utilisez bcp.exe à partir d'une version antérieure à [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ac81-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ac81-132">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5ac81-132">In This Section</span></span>  
  
-   [<span data-ttu-id="5ac81-133">Utilisation de fichiers de données et de format</span><span class="sxs-lookup"><span data-stu-id="5ac81-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="5ac81-134">Copie en bloc à partir de variables de programme</span><span class="sxs-lookup"><span data-stu-id="5ac81-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="5ac81-135">Gestion des tailles de lot de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="5ac81-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="5ac81-136">Copier en bloc des données texte et image</span><span class="sxs-lookup"><span data-stu-id="5ac81-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="5ac81-137">Conversion à partir de la bibliothèque de bases de données vers une copie en bloc ODBC</span><span class="sxs-lookup"><span data-stu-id="5ac81-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="5ac81-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ac81-138">See Also</span></span>  
 <span data-ttu-id="5ac81-139">[SQL Server Native Client &#40;&#41;ODBC](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="5ac81-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="5ac81-140">Importation et exportation en bloc de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac81-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
