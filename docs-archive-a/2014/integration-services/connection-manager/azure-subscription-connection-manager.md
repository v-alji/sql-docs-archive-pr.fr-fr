---
title: Gestionnaire de connexions d’abonnement Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpsubscrconn.f1
- sql11.dts.designer.afpsubscrconn.f1
ms.assetid: e1225327-c308-4c50-8f44-c411f52ef378
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bff1286525983b32c2191f1f8864a0f2bef0e6b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605673"
---
# <a name="azure-subscription-connection-manager"></a><span data-ttu-id="01493-102">Gestionnaire de connexions d’abonnement Azure</span><span class="sxs-lookup"><span data-stu-id="01493-102">Azure Subscription Connection Manager</span></span>
  <span data-ttu-id="01493-103">Le gestionnaire de connexions Azure HDInsight permet à un package SSIS de se connecter à un abonnement Azure en utilisant les valeurs spécifiées pour les propriétés : ID d’abonnement Azure et certificat de gestion.</span><span class="sxs-lookup"><span data-stu-id="01493-103">The Azure HDInsight connection manager enables an SSIS package to connect to an Azure subscription by using the values you specify for the properties: Azure Subscription ID and Management Certificate.</span></span>

1.  <span data-ttu-id="01493-104">Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS** ci-dessus, sélectionnez **Abonnement Azure**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="01493-104">In the **Add SSIS Connection Manager** dialog box shown above, you select **Azure Subscription**, and click **Add**.</span></span>  <span data-ttu-id="01493-105">Vous devez voir s’afficher la boîte de dialogue **Éditeur du gestionnaire de connexions d’abonnement Azure** .</span><span class="sxs-lookup"><span data-stu-id="01493-105">You should see the following **Azure Subscription Connection Manager Editor** dialog box.</span></span>

     <span data-ttu-id="01493-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span><span class="sxs-lookup"><span data-stu-id="01493-106">![SSIS-AzureSubscriptionManager](../media/ssis-azuresubscriptionmanager.png "SSIS-AzureSubscriptionManager")</span></span>

2.  <span data-ttu-id="01493-107">Entrez votre ID d’abonnement Azure, qui identifie de façon unique un abonnement Azure, pour l’ **ID d’abonnement Azure**.</span><span class="sxs-lookup"><span data-stu-id="01493-107">Enter your Azure subscription ID, which uniquely identifies an Azure subscription, for the **Azure subscription ID**.</span></span>  <span data-ttu-id="01493-108">Cette valeur est indiquée sur le [portail de gestion Azure](https://manage.windowsazure.com) , à la page **Paramètres** :</span><span class="sxs-lookup"><span data-stu-id="01493-108">The value can be found on the [Azure Management Portal](https://manage.windowsazure.com) under **Settings** page:</span></span>

     <span data-ttu-id="01493-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span><span class="sxs-lookup"><span data-stu-id="01493-109">![SSIS-AzureSettings-SubscriptionID](../media/ssis-azuresettings-subscriptionid.png "SSIS-AzureSettings-SubscriptionID")</span></span>

3.  <span data-ttu-id="01493-110">Choisissez **Emplacement du magasin de certificats de gestion** et **Nom du magasin de certificats de gestion** dans les listes déroulantes.</span><span class="sxs-lookup"><span data-stu-id="01493-110">Choose **Management certificate store location** and **Management certificate store name** from the drop-down lists.</span></span>

4.  <span data-ttu-id="01493-111">Entrez l’**empreinte numérique du certificat de gestion** ou cliquez sur **Parcourir...** pour choisir un certificat dans le magasin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="01493-111">Enter **Management certificate thumbprint** or click the **Browse...** to choose a certificate from the selected store.</span></span> <span data-ttu-id="01493-112">Le certificat doit être téléchargé en tant que certificat de gestion pour l’abonnement.</span><span class="sxs-lookup"><span data-stu-id="01493-112">The certificate must be uploaded as a management certificate for the subscription.</span></span> <span data-ttu-id="01493-113">Pour ce faire, cliquez sur **Télécharger** dans la page suivante du portail Azure (voir cet [article MSDN](https://msdn.microsoft.com/library/azure/gg551722.aspx) pour plus de détails).</span><span class="sxs-lookup"><span data-stu-id="01493-113">To do so, click **Upload** on the following page of the Azure Portal (see this [MSDN post](https://msdn.microsoft.com/library/azure/gg551722.aspx) for more detail).</span></span>

     <span data-ttu-id="01493-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span><span class="sxs-lookup"><span data-stu-id="01493-114">![SSIS-AzureSettings-ManagementCertificate](../media/ssis-azuresettings-managementcertificate.png "SSIS-AzureSettings-ManagementCertificate")</span></span>

5.  <span data-ttu-id="01493-115">Cliquez sur **tester la connexion** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="01493-115">Click **Test Connection** to test the connection.</span></span>

6.  <span data-ttu-id="01493-116">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="01493-116">Click **OK** to close the dialog box.</span></span>


