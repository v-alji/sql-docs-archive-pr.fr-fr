---
title: Procédure stockée de mise en lots (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 6a613106-9f87-4caf-a23a-a726fc6561c5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9259352350a099db5d9b18411ad4da06dfb19819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614700"
---
# <a name="staging-stored-procedure-master-data-services"></a><span data-ttu-id="a6d0e-102">Procédure stockée de mise en lots (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a6d0e-102">Staging Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="a6d0e-103">Lors de l’initialisation du processus de site à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], vous devez utiliser l’une des trois procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-103">When initiating the staging process from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you use one of three stored procedures.</span></span>  
  
-   <span data-ttu-id="a6d0e-104">stg.udp_name_Leaf</span><span class="sxs-lookup"><span data-stu-id="a6d0e-104">stg.udp_name_Leaf</span></span>  
  
-   <span data-ttu-id="a6d0e-105">stg.udp_name_Consolidated</span><span class="sxs-lookup"><span data-stu-id="a6d0e-105">stg.udp_name_Consolidated</span></span>  
  
-   <span data-ttu-id="a6d0e-106">stg.udp_name_Relationship</span><span class="sxs-lookup"><span data-stu-id="a6d0e-106">stg.udp_name_Relationship</span></span>  
  
 <span data-ttu-id="a6d0e-107">Où nom indique le nom de la table de mise en lots spécifié lors de la création de l'entité.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-107">Where name is the name of the staging table that was specified when the entity was created.</span></span>  
  
## <a name="staging-process-stored-procedure-parameters"></a><span data-ttu-id="a6d0e-108">Paramètres de procédure stockée du processus de site</span><span class="sxs-lookup"><span data-stu-id="a6d0e-108">Staging Process Stored Procedure Parameters</span></span>  
 <span data-ttu-id="a6d0e-109">Le tableau suivant répertorie les paramètres de ces procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-109">The following table lists the parameters of these stored procedures.</span></span>  
  
|<span data-ttu-id="a6d0e-110">Paramètre</span><span class="sxs-lookup"><span data-stu-id="a6d0e-110">Parameter</span></span>|<span data-ttu-id="a6d0e-111">Description</span><span class="sxs-lookup"><span data-stu-id="a6d0e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6d0e-112">**VersionName**</span><span class="sxs-lookup"><span data-stu-id="a6d0e-112">**VersionName**</span></span><br /><br /> <span data-ttu-id="a6d0e-113">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a6d0e-113">Required</span></span>|<span data-ttu-id="a6d0e-114">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-114">The name of the version.</span></span> <span data-ttu-id="a6d0e-115">Peut ou non respecter la casse, en fonction de votre paramètre de classement [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6d0e-115">This may or may not be case-sensitive, depending on your [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] collation setting.</span></span>|  
|<span data-ttu-id="a6d0e-116">**LogFlag**</span><span class="sxs-lookup"><span data-stu-id="a6d0e-116">**LogFlag**</span></span><br /><br /> <span data-ttu-id="a6d0e-117">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="a6d0e-117">Required</span></span>|<span data-ttu-id="a6d0e-118">Détermine si les transactions sont inscrites dans un journal au cours du processus de site.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-118">Determines whether transactions are logged during the staging process.</span></span> <span data-ttu-id="a6d0e-119">Les valeurs possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6d0e-119">Possible values are:</span></span><br /><br /> <span data-ttu-id="a6d0e-120">**0**: ne pas enregistrer les transactions.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-120">**0**: Do not log transactions.</span></span><br /><span data-ttu-id="a6d0e-121">**1**: enregistrer les transactions.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-121">**1**: Log transactions.</span></span><br /><br /> <br /><br /> <span data-ttu-id="a6d0e-122">Pour plus d’informations sur les transactions, consultez [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6d0e-122">For more information about transactions, see [Transactions &#40;Master Data Services&#41;](transactions-master-data-services.md).</span></span>|  
|<span data-ttu-id="a6d0e-123">**BatchTag**</span><span class="sxs-lookup"><span data-stu-id="a6d0e-123">**BatchTag**</span></span><br /><br /> <span data-ttu-id="a6d0e-124">Requis, sauf par le service Web</span><span class="sxs-lookup"><span data-stu-id="a6d0e-124">Required, except by web service</span></span>|<span data-ttu-id="a6d0e-125">La valeur de **BatchTag** spécifiée dans la table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-125">The **BatchTag** value as specified in the staging table.</span></span>|  
|<span data-ttu-id="a6d0e-126">**Batch_ID**</span><span class="sxs-lookup"><span data-stu-id="a6d0e-126">**Batch_ID**</span></span><br /><br /> <span data-ttu-id="a6d0e-127">Requis par le service Web uniquement</span><span class="sxs-lookup"><span data-stu-id="a6d0e-127">Required by web service only</span></span>|<span data-ttu-id="a6d0e-128">La valeur de **Batch_ID** spécifiée dans la table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-128">The **Batch_ID** value as specified in the staging table.</span></span>|  
  
### <a name="staging-process-stored-procedure-example"></a><span data-ttu-id="a6d0e-129">Exemple de procédure stockée du processus de site</span><span class="sxs-lookup"><span data-stu-id="a6d0e-129">Staging Process Stored Procedure Example</span></span>  
 <span data-ttu-id="a6d0e-130">L'exemple suivant montre comment démarrer le processus de site à l'aide de la procédure stockée de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="a6d0e-130">The following example shows how to start the staging process by using the staging stored procedure.</span></span>  
  
```  
USE [DATABASE_NAME]  
GO  
  
EXEC[stg].[udp_name_Leaf]  
      @VersionName = N'VERSION_1',  
@LogFlag = 1,  
@BatchTag = N'batch1'  
  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6d0e-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6d0e-131">See Also</span></span>  
 <span data-ttu-id="a6d0e-132">[&#40;de la procédure stockée de validation Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a6d0e-132">[Validation Stored Procedure &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="a6d0e-133">[Charger ou mettre à jour des membres dans Master Data Services à l’aide du processus de site](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a6d0e-133">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 [<span data-ttu-id="a6d0e-134">Affichez les erreurs qui se produisent pendant le processus de site &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a6d0e-134">View Errors that Occur During the Staging Process &#40;Master Data Services&#41;</span></span>](view-errors-that-occur-during-staging-master-data-services.md)  
  
  
