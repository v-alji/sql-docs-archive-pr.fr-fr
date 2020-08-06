---
title: Source des objets blob Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobsrc.f1
- sql11.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a14c7022437c8a23f898a0f29c211bd9ae82aa0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613580"
---
# <a name="azure-blob-source"></a><span data-ttu-id="09135-102">Azure Blob Source</span><span class="sxs-lookup"><span data-stu-id="09135-102">Azure Blob Source</span></span>
 <span data-ttu-id="09135-103">Le composant **Azure Blob Source** permet à un package SSIS de lire les données provenant d’un blob Azure.</span><span class="sxs-lookup"><span data-stu-id="09135-103">The **Azure Blob Source** component enables an SSIS package to read data from an Azure blob.</span></span> <span data-ttu-id="09135-104">Les formats de fichier pris en charge sont CSV et AVRO.</span><span class="sxs-lookup"><span data-stu-id="09135-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="09135-105">Pour afficher l’éditeur d’Azure Bloc Source, faites glisser **Azure Blob Source** sur le concepteur de flux de données et double-cliquez dessus pour ouvrir l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="09135-105">To see the editor for the Azure Blob Source, drag and drop **Azure Blob Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
1.  <span data-ttu-id="09135-106">Dans le champ **Gestionnaire de connexions du Stockage Azure**, spécifiez un gestionnaire de connexions du Stockage Azure existant ou créez-en un qui fera référence à un compte de Stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="09135-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="09135-107">Dans le champ **Nom du conteneur d’objets blob** , spécifiez le nom du conteneur d’objets blob qui contient les fichiers sources.</span><span class="sxs-lookup"><span data-stu-id="09135-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="09135-108">Dans le champ **Nom de l’objet blob** , indiquez le chemin d’accès à l’objet blob.</span><span class="sxs-lookup"><span data-stu-id="09135-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="09135-109">Dans le champ **Format de fichier d’objet blob** , spécifiez le format d’objet blob à utiliser.</span><span class="sxs-lookup"><span data-stu-id="09135-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="09135-110">Si le format de fichier est CSV, vous devez renseigner le champ **Caractère séparateur de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="09135-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="09135-111">Sélectionnez également l’option **Noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonne.</span><span class="sxs-lookup"><span data-stu-id="09135-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="09135-112">Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.</span><span class="sxs-lookup"><span data-stu-id="09135-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
