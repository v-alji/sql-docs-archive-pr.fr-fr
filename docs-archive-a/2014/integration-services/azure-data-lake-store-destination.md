---
title: Destination Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707728"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="724ff-102">Destination Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="724ff-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="724ff-103">Le composant **Destination Azure Data Lake Store** permet à un package SSIS d’écrire des données dans Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="724ff-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="724ff-104">Les formats de fichier pris en charge sont les formats texte, Avro et ORC.</span><span class="sxs-lookup"><span data-stu-id="724ff-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="724ff-105">Configurer la destination Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="724ff-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="724ff-106">Faites glisser le composant **Destination Azure Data Lake Store** vers le concepteur de flux de données et double-cliquez dessus pour visualiser l’éditeur.</span><span class="sxs-lookup"><span data-stu-id="724ff-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="724ff-107">Dans le champ **Gestionnaire de connexions Azure Data Lake Store** , spécifiez un gestionnaire de connexions Azure Data Lake Store existant ou créez-en un qui fait référence à un service Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="724ff-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="724ff-108">Dans le champ **Chemin du fichier** , spécifiez le nom du fichier où vous souhaitez écrire des données.</span><span class="sxs-lookup"><span data-stu-id="724ff-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="724ff-109">Si ce fichier existe déjà, son contenu est remplacé.</span><span class="sxs-lookup"><span data-stu-id="724ff-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="724ff-110">Dans le champ **Format de fichier** , spécifiez le format de fichier à utiliser.</span><span class="sxs-lookup"><span data-stu-id="724ff-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="724ff-111">Si le format de fichier est le format texte, vous devez renseigner le champ **Délimiteur de colonne** .</span><span class="sxs-lookup"><span data-stu-id="724ff-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="724ff-112">Sélectionnez également les **noms de colonne dans la première ligne de données** si la première ligne du fichier contient des noms de colonnes.</span><span class="sxs-lookup"><span data-stu-id="724ff-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="724ff-113">Si le format de fichier est ORC, vous devez installer l’environnement JRE de la plateforme correspondante.</span><span class="sxs-lookup"><span data-stu-id="724ff-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="724ff-114">Après avoir spécifié les informations de connexion, basculez vers la page **Colonnes** pour mapper les colonnes sources sur les colonnes de destination du flux de données SSIS.</span><span class="sxs-lookup"><span data-stu-id="724ff-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
