---
title: Gestionnaire de connexions Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPHDICM.F1
- SQL11.DTS.DESIGNER.AFPHDICM.F1
ms.assetid: 850a978d-5dba-45b6-a10e-306aafbc353d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaf2f57fec50a58ad1b7e7578407fb6cf3fa0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696011"
---
# <a name="azure-hdinsight-connection-manager"></a><span data-ttu-id="4747f-102">Gestionnaire de connexions Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4747f-102">Azure HDInsight Connection Manager</span></span>
<span data-ttu-id="4747f-103">Le **gestionnaire de connexions Azure HDInsight** permet à un package SSIS de se connecter à un cluster Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4747f-103">The **Azure HDInsight Connection Manager** enables an SSIS package to connect to an Azure HDInsight cluster.</span></span>

<span data-ttu-id="4747f-104">Pour créer et configurer un **gestionnaire de connexions Azure HDInsight**, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4747f-104">To create and configure an **Azure HDInsight Connection Manager**, follow the steps below:</span></span>

1. <span data-ttu-id="4747f-105">Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS**, sélectionnez **AzureHDInsight**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4747f-105">In the **Add SSIS Connection Manager** dialog box, select **AzureHDInsight**, and click **Add**.</span></span>
2. <span data-ttu-id="4747f-106">Dans l’**Éditeur du gestionnaire de connexions Azure HDInsight**, spécifiez le **nom DNS du cluster** (sans le préfixe de protocole), le **nom d’utilisateur** et le **mot de passe** du cluster HDInsight auquel se connecter.</span><span class="sxs-lookup"><span data-stu-id="4747f-106">In the **Azure HDInsight Connection Manager Editor** dialog box, specify the **Cluster DNS name** (without the protocol prefix), **Username**, and **Password** for the HDInsight cluster to connect to.</span></span>
3. <span data-ttu-id="4747f-107">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4747f-107">Click **OK** to close the dialog box.</span></span>
4. <span data-ttu-id="4747f-108">Les propriétés du gestionnaire de connexions que vous avez créées apparaissent dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="4747f-108">You can see the properties of the connection manager you created in the **Properties** window.</span></span>
