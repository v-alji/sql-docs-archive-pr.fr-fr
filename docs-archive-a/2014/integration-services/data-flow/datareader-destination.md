---
title: Destination DataReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.datareaderdest.f1
helpviewer_keywords:
- DataReader destination
- destinations [Integration Services], DataReader
ms.assetid: 56fcc4bf-c901-42c3-a71d-110039293431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 40cfe5d99c33eb19d415f204173005a64bde7855
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709823"
---
# <a name="datareader-destination"></a><span data-ttu-id="87e79-102">destination DataReader</span><span class="sxs-lookup"><span data-stu-id="87e79-102">DataReader Destination</span></span>
  <span data-ttu-id="87e79-103">La destination DataReader expose les données d'un flux à l'aide de l'interface ADO.NET `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="87e79-103">The DataReader destination exposes the data in a data flow by using the ADO.NET `DataReader` interface.</span></span> <span data-ttu-id="87e79-104">Les données peuvent ensuite être utilisées par d'autres applications.</span><span class="sxs-lookup"><span data-stu-id="87e79-104">The data can then be consumed by other applications.</span></span> <span data-ttu-id="87e79-105">Vous pouvez par exemple configurer la source de données d’un rapport [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de sorte qu’elle utilise le résultat d’exécution d’un package [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87e79-105">For example, you can configure the data source of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report to use the result of running a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="87e79-106">Pour ce faire, vous devez créer un flux qui implémente la destination DataReader.</span><span class="sxs-lookup"><span data-stu-id="87e79-106">To do this, you create a data flow that implements the DataReader destination.</span></span>  
  
 <span data-ttu-id="87e79-107">Pour plus d’informations sur l’accès aux valeurs de la destination DataReader et sur leur lecture par programmation, consultez [Chargement de la sortie d’un package local](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span><span class="sxs-lookup"><span data-stu-id="87e79-107">For information about accessing and reading values in the DataReader destination programmatically, see [Loading the Output of a Local Package](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md).</span></span>  
  
## <a name="configuration-of-the-datareader-destination"></a><span data-ttu-id="87e79-108">Configuration de la destination DataReader</span><span class="sxs-lookup"><span data-stu-id="87e79-108">Configuration of the DataReader Destination</span></span>  
 <span data-ttu-id="87e79-109">Vous pouvez spécifier une valeur de délai d'attente de la destination DataReader et indiquer si la destination doit échouer en cas de dépassement de délai.</span><span class="sxs-lookup"><span data-stu-id="87e79-109">You can specify a time-out value for the DataReader destination and indicate whether the destination should fail if a time-out occurs.</span></span> <span data-ttu-id="87e79-110">Un délai d'attente est dépassé si l'application ne demande aucune donnée dans le délai spécifié.</span><span class="sxs-lookup"><span data-stu-id="87e79-110">A time-out occurs if the application does not ask for data within the specified time.</span></span>  
  
 <span data-ttu-id="87e79-111">La destination DataReader possède une entrée.</span><span class="sxs-lookup"><span data-stu-id="87e79-111">The DataReader destination has one input.</span></span> <span data-ttu-id="87e79-112">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="87e79-112">It does not support an error output.</span></span>  
  
 <span data-ttu-id="87e79-113">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="87e79-113">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="87e79-114">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="87e79-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="87e79-115">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="87e79-115">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="87e79-116">Propriétés personnalisées de la destination DataReader</span><span class="sxs-lookup"><span data-stu-id="87e79-116">DataReader Destination Custom Properties</span></span>](datareader-destination-custom-properties.md)  
  
 <span data-ttu-id="87e79-117">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="87e79-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
