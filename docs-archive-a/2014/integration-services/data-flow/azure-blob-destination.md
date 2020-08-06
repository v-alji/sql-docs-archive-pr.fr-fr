---
title: Azure Blob Destination | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706612"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="0a779-102">Destination d’objet blob Azure</span><span class="sxs-lookup"><span data-stu-id="0a779-102">Azure Blob Destination</span></span>
  <span data-ttu-id="0a779-103">Le composant **Destination d’objet blob Azure** permet à un package SSIS d’écrire des données dans un objet blob Azure.</span><span class="sxs-lookup"><span data-stu-id="0a779-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="0a779-104">Les formats de fichier pris en charge sont CSV et AVRO.</span><span class="sxs-lookup"><span data-stu-id="0a779-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="0a779-105">Ddrag-déposez la **destination d’objet BLOB Azure** dans le concepteur de workflow et double-cliquez dessus pour voir l’éditeur).</span><span class="sxs-lookup"><span data-stu-id="0a779-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="0a779-106">Dans le champ **Gestionnaire de connexions du Stockage Azure**, spécifiez un gestionnaire de connexions du Stockage Azure existant ou créez-en un qui fera référence à un compte de Stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="0a779-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="0a779-107">Dans le champ **Nom du conteneur d’objets blob** , spécifiez le nom du conteneur d’objets blob qui contient les fichiers sources.</span><span class="sxs-lookup"><span data-stu-id="0a779-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="0a779-108">Dans le champ **Nom de l’objet blob** , indiquez le chemin d’accès à l’objet blob.</span><span class="sxs-lookup"><span data-stu-id="0a779-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="0a779-109">Dans le champ **Format de fichier d’objet blob** , spécifiez le format d’objet blob à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0a779-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="0a779-110">Si le format de fichier est CSV, vous devez renseigner le champ **Caractère séparateur de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="0a779-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="0a779-111">Sélectionnez également les **noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="0a779-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="0a779-112">Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.</span><span class="sxs-lookup"><span data-stu-id="0a779-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
