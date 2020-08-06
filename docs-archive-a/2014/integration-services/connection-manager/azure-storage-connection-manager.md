---
title: Gestionnaire de connexions du Stockage Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpstorageconn.f1
- sql11.dts.designer.afpstorageconn.f1
ms.assetid: 68bd1d04-d20f-4357-a34e-7c9c76457062
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47580d8d1d961df9fbcbed0bd7164f1c54792b86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605678"
---
# <a name="azure-storage-connection-manager"></a><span data-ttu-id="4f1d0-102">Gestionnaire de connexions Azure Storage</span><span class="sxs-lookup"><span data-stu-id="4f1d0-102">Azure Storage Connection Manager</span></span>
  <span data-ttu-id="4f1d0-103">Le Gestionnaire de connexions du Stockage Azure permet à un package SSIS (SQL Server Integration Services) de se connecter à un compte de Stockage Azure en utilisant les valeurs que vous spécifiez pour les propriétés Nom du compte de stockage et Clé de compte.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-103">The Azure Storage connection manager enables an SSIS package to connect to an Azure Storage account by using the values you specify for the properties: Storage Account Name and Account Key.</span></span>  
  
1.  <span data-ttu-id="4f1d0-104">Dans la boîte de dialogue **Ajout d’un gestionnaire de connexions SSIS** , sélectionnez **AzureStorage**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-104">In the **Add SSIS Connection Manager** dialog box, select **AzureStorage**, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="4f1d0-105">Dans la boîte de dialogue Éditeur du gestionnaire de connexions du Stockage Azure, choisissez **Utiliser un compte Azure** pour vous connecter à un service de gestion de données Azure par Internet, ou choisissez **Utiliser le compte de développeur local** pour vous connecter au service local hébergé par l’émulateur de Stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-105">In the Azure Storage Connection Manager Editor dialog box, choose **Use Azure account** to connect to an Azure Storage Service via internet or choose **Use local developer account** to connect to the local service hosted by the Azure Storage Emulator.</span></span>  
  
3.  <span data-ttu-id="4f1d0-106">Si vous avez sélectionné l’option **Utiliser un compte Azure** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4f1d0-106">If you selected **Use Azure account** option, do the following:</span></span>  
  
    1.  <span data-ttu-id="4f1d0-107">Renseignez les champs **Nom du compte de stockage** et **Clé de compte**.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-107">Specify values for the **Storage account name** and **Account key** field.</span></span> <span data-ttu-id="4f1d0-108">Ces valeurs seront stockées en tant que données sensibles dans le package SSIS.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-108">These values will be stored as sensitive data in SSIS package.</span></span>  
  
    2.  <span data-ttu-id="4f1d0-109">Sélectionnez **Utiliser HTTPS** si vous souhaitez utiliser HTTPS plutôt que HTTP pour vous connecter au service de gestion de données Azure.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-109">Select **Use HTTPS** if you want to use HTTPS instead of HTTP to connect to the Azure Storage Service.</span></span>  
  
4.  <span data-ttu-id="4f1d0-110">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="4f1d0-110">Click **OK** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="4f1d0-111">Les propriétés du gestionnaire de connexions que vous avez créées apparaissent dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="4f1d0-111">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
