---
title: Générer et exécuter le script de journalisation supplémentaire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695988"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="c55d6-102">Générer et exécuter le script de journalisation supplémentaire</span><span class="sxs-lookup"><span data-stu-id="c55d6-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="c55d6-103">Utilisez la page Configurer des tables pour la capture des modifications pour exécuter un script sur la base de données source Oracle qui configure une journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c55d6-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="c55d6-104">**Pour exécuter les scripts de journalisation supplémentaire**</span><span class="sxs-lookup"><span data-stu-id="c55d6-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="c55d6-105">Cliquez sur **Exécuter le script** pour exécuter le script de journalisation supplémentaire sur les tables définies pour l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="c55d6-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="c55d6-106">Ce script demande à la base de données Oracle d'écrire toutes les colonnes d'intérêt dans ses journaux des transactions lors de la journalisation des opérations de mise à jour (UPDATE) dans les tables capturées.</span><span class="sxs-lookup"><span data-stu-id="c55d6-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="c55d6-107">Ce script est normalement examiné et exécuté par un administrateur système Oracle.</span><span class="sxs-lookup"><span data-stu-id="c55d6-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="c55d6-108">Vous pouvez également exécuter des scripts manuellement à l'aide de SQL\*Plus.</span><span class="sxs-lookup"><span data-stu-id="c55d6-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="c55d6-109">**Pour exécuter les script manuellement**</span><span class="sxs-lookup"><span data-stu-id="c55d6-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="c55d6-110">Cliquez sur **Copier** pour coller le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="c55d6-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="c55d6-111">Ouvrez SQL\*PLUS et accédez au répertoire contenant votre base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="c55d6-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="c55d6-112">Collez le script dans SQL\*Plus pour l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="c55d6-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="c55d6-113">Pour enregistrer le script de journalisation supplémentaire dans un fichier texte, cliquez sur **Enregistrer sous** et accédez à l'emplacement où vous souhaitez enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="c55d6-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="c55d6-114">Donnez un nom au fichier, puis cliquez sur **Enregistrer** pour enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="c55d6-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="c55d6-115">Cliquez sur **Suivant** pour [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span><span class="sxs-lookup"><span data-stu-id="c55d6-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55d6-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c55d6-116">See Also</span></span>  
 <span data-ttu-id="c55d6-117">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c55d6-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="c55d6-118">Examiner et générer des scripts de journalisation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c55d6-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
