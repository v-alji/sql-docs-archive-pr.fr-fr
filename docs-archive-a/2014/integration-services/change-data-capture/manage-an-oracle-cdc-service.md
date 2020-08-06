---
title: Gérer un service Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695952"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="ae59f-102">Gérer un Service de capture de données modifiées Oracle</span><span class="sxs-lookup"><span data-stu-id="ae59f-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="ae59f-103">Vous pouvez utiliser la console de configuration du service de capture de données modifiées pour gérer un service de capture de données modifiées spécifique.</span><span class="sxs-lookup"><span data-stu-id="ae59f-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="ae59f-104">**Pour sélectionner le service de capture de données modifiées à utiliser**</span><span class="sxs-lookup"><span data-stu-id="ae59f-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="ae59f-105">Dans le volet gauche de la console de configuration du service de capture de données modifiées, développez **Services de capture de données modifiées locaux**.</span><span class="sxs-lookup"><span data-stu-id="ae59f-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="ae59f-106">Sélectionnez le service de capture de données modifiées à utiliser.</span><span class="sxs-lookup"><span data-stu-id="ae59f-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="ae59f-107">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées que vous souhaitez utiliser et sélectionner l'action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ae59f-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="ae59f-108">Consultez [Opérations possibles avec un service de capture de données modifiées](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="ae59f-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="ae59f-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="ae59f-109">**OR**</span></span>  
  
1.  <span data-ttu-id="ae59f-110">Sélectionnez **Services de capture de données modifiées locaux** dans le volet gauche de la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="ae59f-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="ae59f-111">Dans la section centrale de la console de configuration du service de capture de données modifiées, sélectionnez le service que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="ae59f-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="ae59f-112">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées que vous souhaitez utiliser et sélectionner l'action souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ae59f-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="ae59f-113">Consultez [Opérations possibles avec un service de capture de données modifiées](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="ae59f-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="ae59f-114">Que pouvez-vous faire avec un Service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="ae59f-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="ae59f-115">Vous pouvez effectuer les actions suivantes lorsque vous utilisez un service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="ae59f-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="ae59f-116">Supprimer le service</span><span class="sxs-lookup"><span data-stu-id="ae59f-116">Delete the service</span></span>  
 <span data-ttu-id="ae59f-117">Dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées, cliquez sur **Supprimer** pour supprimer le service.</span><span class="sxs-lookup"><span data-stu-id="ae59f-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="ae59f-118">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées à supprimer et sélectionner **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ae59f-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="ae59f-119">**Remarque**: si le service est en cours d'exécution lors de sa suppression, il est arrêté avant d'être supprimé.</span><span class="sxs-lookup"><span data-stu-id="ae59f-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="ae59f-120">Pour supprimer la définition de service Windows de capture de données modifiées Oracle, le programme doit disposer d'un accès de mise à jour à la base de données MSXDBCDC dans l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associée.</span><span class="sxs-lookup"><span data-stu-id="ae59f-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="ae59f-121">Lorsque vous cliquez sur OK pour supprimer le service, le programme tente de supprimer l'inscription du service de capture de données modifiées Oracle dans la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ae59f-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="ae59f-122">Si le programme ne peut pas supprimer l'inscription du service de capture de données modifiées Oracle, car il ne dispose pas des autorisations appropriées, il invite l'utilisateur à entrer une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec des autorisations de mise à jour de la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ae59f-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="ae59f-123">Pour plus d'informations sur les données que vous devez taper dans la boîte de dialogue Connexion à SQL Server, consultez [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="ae59f-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="ae59f-124">Modifier les propriétés de service de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="ae59f-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="ae59f-125">Dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ae59f-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="ae59f-126">Vous pouvez également cliquer avec le bouton droit sur le service de capture de données modifiées où vous souhaitez modifier les propriétés et sélectionner **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ae59f-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae59f-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae59f-127">See Also</span></span>  
 [<span data-ttu-id="ae59f-128">Guide pratique pour gérer un service CDC local</span><span class="sxs-lookup"><span data-stu-id="ae59f-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
