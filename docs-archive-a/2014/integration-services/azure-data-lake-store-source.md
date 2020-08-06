---
title: Source Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611247"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="4d239-102">Source Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="4d239-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="4d239-103">Le composant **Source Azure Data Lake Store** permet à un package SSIS de lire des données dans Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="4d239-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="4d239-104">Les formats de fichier pris en charge sont le format texte et Avro.</span><span class="sxs-lookup"><span data-stu-id="4d239-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="4d239-105">Configurer la source Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="4d239-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="4d239-106">Pour afficher l’éditeur de la source Azure Data Lake Store, faites glisser **Source Azure Data Lake Store** sur le concepteur de flux de données et double-cliquez dessus pour ouvrir l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="4d239-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="4d239-107">Dans le champ **Gestionnaire de connexions Azure Data Lake Store** , spécifiez un gestionnaire de connexions Azure Data Lake Store existant ou créez-en un qui fait référence à un service Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="4d239-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="4d239-108">Dans le champ **Chemin d’accès au fichier** , spécifiez le chemin du fichier source dans Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="4d239-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="4d239-109">Dans le champ **Format de fichier** , spécifiez le format du fichier source.</span><span class="sxs-lookup"><span data-stu-id="4d239-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="4d239-110">Si le format de fichier est le format texte, vous devez renseigner le champ **Délimiteur de colonne** .</span><span class="sxs-lookup"><span data-stu-id="4d239-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="4d239-111">Sélectionnez également l’option **Noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonne.</span><span class="sxs-lookup"><span data-stu-id="4d239-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="4d239-112">Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.</span><span class="sxs-lookup"><span data-stu-id="4d239-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
