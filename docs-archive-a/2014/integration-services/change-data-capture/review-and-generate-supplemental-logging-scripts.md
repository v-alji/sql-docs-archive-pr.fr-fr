---
title: Examiner et générer des scripts de journalisation supplémentaires | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603586"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="e0ed3-102">Examiner et générer des scripts de journalisation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e0ed3-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="e0ed3-103">L’onglet **Scripts** permet d’exécuter ou de réexécuter un script sur la base de données source Oracle qui configure une journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="e0ed3-104">Avant d'exécuter les scripts, sélectionnez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e0ed3-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="e0ed3-105">**Inclure les modifications de cette session**</span><span class="sxs-lookup"><span data-stu-id="e0ed3-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="e0ed3-106">Sélectionnez cette option pour exécuter le script sur toute nouvelle table qui a été ajoutée à l'instance de capture de données modifiées ou sur des tables qui ont été modifiées à l'aide de l'éditeur de propriétés.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0ed3-107">Si aucune modification n'a été apportée aux tables de l'instance de capture de données modifiées, la zone de script de journalisation supplémentaire Oracle est vide.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="e0ed3-108">**Inclure toutes les tables/instances de capture**</span><span class="sxs-lookup"><span data-stu-id="e0ed3-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="e0ed3-109">Sélectionnez cette option pour exécuter le script sur toutes les tables et instances de capture dans l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="e0ed3-110">Après avoir sélectionné une de ces options, exécutez le script de journalisation supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="e0ed3-111">Pour exécuter les scripts de journalisation supplémentaire</span><span class="sxs-lookup"><span data-stu-id="e0ed3-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="e0ed3-112">Cliquez sur **Exécuter le script** pour exécuter le script de journalisation supplémentaire sur les tables définies pour l'instance de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="e0ed3-113">Ce script demande à la base de données Oracle d'écrire toutes les colonnes d'intérêt dans ses journaux des transactions lors de la journalisation des opérations de mise à jour (UPDATE) dans les tables capturées.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="e0ed3-114">Ce script est normalement examiné et exécuté par un administrateur système Oracle.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="e0ed3-115">Lorsque vous exécutez des scripts de journalisation supplémentaires, la boîte de dialogue des informations d'identification Oracle pour l'exécution de script s'ouvre et vous permet de spécifier un nom d'utilisateur et un mot de passe Oracle valides.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="e0ed3-116">Pour plus d'informations sur la façon de fournir les informations d'identification Oracle appropriées, consultez [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="e0ed3-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="e0ed3-117">Vous pouvez également exécuter les scripts manuellement à l'aide de SQL\*PLUS, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="e0ed3-118">Pour exécuter les script manuellement</span><span class="sxs-lookup"><span data-stu-id="e0ed3-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="e0ed3-119">Cliquez sur **Copier** pour coller le script dans le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="e0ed3-120">Ouvrez SQL\*PLUS et accédez au répertoire contenant votre base de données source Oracle.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="e0ed3-121">Collez le script dans SQL\*Plus pour l’exécuter.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="e0ed3-122">Pour enregistrer le script de journalisation supplémentaire dans un fichier texte</span><span class="sxs-lookup"><span data-stu-id="e0ed3-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="e0ed3-123">Cliquez sur **Enregistrer sous** et accédez à l'emplacement où vous souhaitez enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="e0ed3-124">Donnez un nom au fichier, puis cliquez sur **Enregistrer** pour enregistrer le fichier.</span><span class="sxs-lookup"><span data-stu-id="e0ed3-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ed3-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0ed3-125">See Also</span></span>  
 <span data-ttu-id="e0ed3-126">[Procédure : modifier les propriétés d'une instance de capture de données modifiées](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e0ed3-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="e0ed3-127">Informations d’identification Oracle pour l’exécution d’un script</span><span class="sxs-lookup"><span data-stu-id="e0ed3-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
