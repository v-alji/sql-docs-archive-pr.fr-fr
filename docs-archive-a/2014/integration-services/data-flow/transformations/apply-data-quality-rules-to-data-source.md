---
title: Appliquer des règles de qualité des données à la source de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695876"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="22de4-102">Appliquer des règles de qualité des données à la source de données</span><span class="sxs-lookup"><span data-stu-id="22de4-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="22de4-103">Vous pouvez utiliser Data Quality (DQS) Services pour corriger les données dans le flux de données du package en connectant la transformation de nettoyage DQS à la source de données.</span><span class="sxs-lookup"><span data-stu-id="22de4-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="22de4-104">Pour plus d’informations sur DQS, consultez [Concepts Data Quality Services](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="22de4-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="22de4-105">Pour plus d’informations sur la transformation, consultez [Transformation de nettoyage DQS](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="22de4-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="22de4-106">Lorsque vous traitez des données avec la transformation de nettoyage DQS, un projet de qualité des données est créé sur le serveur de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="22de4-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="22de4-107">Vous utilisez le client de qualité des données pour gérer le projet.</span><span class="sxs-lookup"><span data-stu-id="22de4-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="22de4-108">Pour plus d’informations, consultez [Gérer &#40;ouvrir, déverrouiller, renommer et supprimer&#41; un projet de qualité des données](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="22de4-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="22de4-109">Pour corriger les données dans le flux de données</span><span class="sxs-lookup"><span data-stu-id="22de4-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="22de4-110">Créer un package.</span><span class="sxs-lookup"><span data-stu-id="22de4-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="22de4-111">Ajoutez et configurez la transformation de nettoyage DQS.</span><span class="sxs-lookup"><span data-stu-id="22de4-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="22de4-112">Pour plus d’informations, consultez [Éditeur de transformation de nettoyage DQS (boîte de dialogue)](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="22de4-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="22de4-113">Connectez la transformation de nettoyage DQS à une source de données.</span><span class="sxs-lookup"><span data-stu-id="22de4-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
