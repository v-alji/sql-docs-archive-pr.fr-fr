---
title: Hive Azure HDInsight, tâche | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afphivetask.f1
- sql11.dts.designer.afphivetask.f1
ms.assetid: e1896c73-128a-4128-9814-3e01f7dfe19b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5905dee4a7a195a16d217b28b59cc10bb74dd9a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613086"
---
# <a name="azure-hdinsight-hive-task"></a><span data-ttu-id="c730f-102">Tâche Hive Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="c730f-102">Azure HDInsight Hive Task</span></span>
<span data-ttu-id="c730f-103">Utilisez la **tâche Hive Azure HDInsight** pour exécuter un script Hive sur un cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="c730f-103">Use the **Azure HDInsight Hive Task** to run Hive script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="c730f-104">Pour ajouter une **tâche Hive Azure HDInsight**, faites-la glisser sur le concepteur SSIS, double-cliquez dessus ou cliquez dessus avec le bouton droit, puis cliquez sur **Modifier** pour afficher la boîte de dialogue **Éditeur de tâches Hive Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="c730f-104">To add an **Azure HDInsight Hive Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Hive Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c730f-105">La liste suivante décrit les champs de cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="c730f-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="c730f-106">Dans le champ **HDInsightConnection**, sélectionnez un gestionnaire de connexions Azure HDInsight existant ou créez-en un qui fait référence au cluster Azure HDInsight utilisé pour exécuter le script.</span><span class="sxs-lookup"><span data-stu-id="c730f-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="c730f-107">Dans le champ **AzureStorageConnection**, sélectionnez un gestionnaire de connexions Stockage Azure existant ou créez-en un qui fait référence au compte Stockage Azure associé au cluster.</span><span class="sxs-lookup"><span data-stu-id="c730f-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="c730f-108">Celui-ci est nécessaire uniquement si vous souhaitez télécharger les journaux de sortie d’exécution de script et les journaux d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="c730f-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="c730f-109">Dans le champ **BlobContainer**, spécifiez le nom du conteneur de stockage associé au cluster.</span><span class="sxs-lookup"><span data-stu-id="c730f-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="c730f-110">Celui-ci est nécessaire uniquement si vous souhaitez télécharger les journaux de sortie d’exécution de script et les journaux d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="c730f-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="c730f-111">Dans le champ **LocalLogFolder**, spécifiez le dossier dans lequel seront téléchargés les journaux de sortie d’exécution de script et les journaux d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="c730f-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="c730f-112">Celui-ci est nécessaire uniquement si vous souhaitez télécharger les journaux de sortie d’exécution de script et les journaux d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="c730f-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="c730f-113">Deux méthodes permettent de spécifier le script Hive à exécuter :</span><span class="sxs-lookup"><span data-stu-id="c730f-113">There are two ways to specify the Hive script to execute:</span></span>
  
    1.  <span data-ttu-id="c730f-114">**Script en ligne** : renseignez le champ **Script** en tapant en ligne le script à exécuter dans la boîte de dialogue **Entrer le script**.</span><span class="sxs-lookup"><span data-stu-id="c730f-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="c730f-115">**Fichier de script** : téléchargez le fichier de script dans Stockage Blob Azure et renseignez le champ **BlobName**.</span><span class="sxs-lookup"><span data-stu-id="c730f-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="c730f-116">Si l’objet blob ne se trouve pas dans le compte ou le conteneur de stockage par défaut associé au cluster HDInsight, vous devez renseigner les champs **ExternalStorageAccountName** et **ExternalBlobContainer**.</span><span class="sxs-lookup"><span data-stu-id="c730f-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="c730f-117">Dans le cas d’un objet blob externe, assurez-vous qu’il est configuré comme étant accessible au public.</span><span class="sxs-lookup"><span data-stu-id="c730f-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="c730f-118">Si les deux sont spécifiés, le fichier de script est utilisé et le script en ligne est ignoré.</span><span class="sxs-lookup"><span data-stu-id="c730f-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
