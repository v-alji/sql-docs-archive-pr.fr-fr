---
title: Gestionnaire de connexions Azure Resource Manager | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPARMCM.F1
- SQL11.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: a2380258-0418-4a8c-a731-5071a44ddf1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1dce4def11f14072295dbf3cde9d5ab77304fe74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610831"
---
# <a name="azure-resource-manager-connection-manager"></a><span data-ttu-id="5448b-102">Gestionnaire de connexions Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="5448b-102">Azure Resource Manager Connection Manager</span></span>
<span data-ttu-id="5448b-103">Le **gestionnaire de connexions Azure Resource Manager** permet à un package SSIS de gérer les ressources Azure à l’aide d’un [principal du service](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="5448b-103">The **Azure Resource Manager Connection Manager** enables an SSIS package to manage Azure resources using a [service principal](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>

<span data-ttu-id="5448b-104">Pour créer et configurer un **gestionnaire de connexions Azure Resource Manager**, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="5448b-104">To create and configure an **Azure Resource Manager Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="5448b-105">Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS**, sélectionnez **AzureResourceManager**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5448b-105">In the **Add SSIS Connection Manager** dialog box, select **AzureResourceManager**, and click **Add**.</span></span>
2. <span data-ttu-id="5448b-106">Dans l’**Éditeur du gestionnaire de connexions Azure Resource Manager**, spécifiez l’**ID d’application**, la **clé de l’application** et l’**ID de locataire** du principal du service.</span><span class="sxs-lookup"><span data-stu-id="5448b-106">In the **Azure Resource Manager Connection Manager Editor** dialog box, specify the **Application ID**, **Application Key**, and **Tenant ID** for the service principal.</span></span> <span data-ttu-id="5448b-107">Pour plus d’informations sur ces propriétés, consultez [cet](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) article.</span><span class="sxs-lookup"><span data-stu-id="5448b-107">For details about these properties, please refer to [this](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) article.</span></span>
3. <span data-ttu-id="5448b-108">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5448b-108">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="5448b-109">Les propriétés du gestionnaire de connexions que vous avez créées apparaissent dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="5448b-109">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
