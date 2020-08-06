---
title: Procédure stockée de validation (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8fa6b01d950c87768d10b0252c1ccbab2b932fe1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605515"
---
# <a name="validation-stored-procedure-master-data-services"></a><span data-ttu-id="c6f86-102">Procédure stockée de validation (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c6f86-102">Validation Stored Procedure (Master Data Services)</span></span>
  <span data-ttu-id="c6f86-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validez une version pour appliquer des règles d’entreprise à tous les membres dans la version de modèle.</span><span class="sxs-lookup"><span data-stu-id="c6f86-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="c6f86-104">Cette rubrique explique comment utiliser la procédure stockée **mdm.udpValidateModel** pour valider des données.</span><span class="sxs-lookup"><span data-stu-id="c6f86-104">This topic explains how to use the **mdm.udpValidateModel** stored procedure to validate data.</span></span> <span data-ttu-id="c6f86-105">Si vous êtes administrateur dans l’application web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , vous pouvez à la place effectuer la validation dans l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6f86-105">If you are an administrator in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, you can do validation in the UI instead.</span></span> <span data-ttu-id="c6f86-106">Pour plus d’informations, consultez [Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c6f86-106">For more information, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6f86-107">Si vous appelez la validation avant la fin de l'exécution du processus de site, les membres qui n'ont pas terminé la mise en lots ne sont pas validés.</span><span class="sxs-lookup"><span data-stu-id="c6f86-107">If you invoke validation before the staging process is complete, members that have not finished staging will not be validated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6f86-108">Exemple</span><span class="sxs-lookup"><span data-stu-id="c6f86-108">Example</span></span>  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f86-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="c6f86-109">Parameters</span></span>  
 <span data-ttu-id="c6f86-110">Cette procédure présente les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="c6f86-110">The parameters of this procedure are as follows:</span></span>  
  
|<span data-ttu-id="c6f86-111">Paramètre</span><span class="sxs-lookup"><span data-stu-id="c6f86-111">Parameter</span></span>|<span data-ttu-id="c6f86-112">Description</span><span class="sxs-lookup"><span data-stu-id="c6f86-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6f86-113">UserID</span><span class="sxs-lookup"><span data-stu-id="c6f86-113">UserID</span></span>|<span data-ttu-id="c6f86-114">Identificateur utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c6f86-114">The user ID.</span></span>|  
|<span data-ttu-id="c6f86-115">Model_ID</span><span class="sxs-lookup"><span data-stu-id="c6f86-115">Model_ID</span></span>|<span data-ttu-id="c6f86-116">ID de modèle.</span><span class="sxs-lookup"><span data-stu-id="c6f86-116">The model ID.</span></span>|  
|<span data-ttu-id="c6f86-117">Version_ID</span><span class="sxs-lookup"><span data-stu-id="c6f86-117">Version_ID</span></span>|<span data-ttu-id="c6f86-118">ID de version.</span><span class="sxs-lookup"><span data-stu-id="c6f86-118">The version ID.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6f86-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6f86-119">See Also</span></span>  
 <span data-ttu-id="c6f86-120">[&#40;d’importation de données Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c6f86-120">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="c6f86-121">Valider une version par rapport aux règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c6f86-121">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](validate-a-version-against-business-rules-master-data-services.md)  
  
  
