---
title: Leçon 2. Créer une stratégie sur un conteneur et générer une clé de signature d’accès partagé (SAP) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41674d9d-8132-4bff-be4d-85a861419f3d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab209f08d53b25a4791ef675e6fb6b78cab115f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707528"
---
# <a name="lesson-2-create-a-policy-on-container-and-generate-a-shared-access-signature-sas-key"></a><span data-ttu-id="b60f5-103">Leçon 2.</span><span class="sxs-lookup"><span data-stu-id="b60f5-103">Lesson 2.</span></span> <span data-ttu-id="b60f5-104">Créer une stratégie sur le conteneur et générer une clé de signature d'accès partagé</span><span class="sxs-lookup"><span data-stu-id="b60f5-104">Create a policy on container and generate a Shared Access Signature (SAS) key</span></span>
  <span data-ttu-id="b60f5-105">Dans cette leçon, vous allez apprendre comment créer une stratégie sur le conteneur d'objets blob et générer une clé SAS.</span><span class="sxs-lookup"><span data-stu-id="b60f5-105">In this lesson, you will learn how to create a policy on the Blob container and also generate a SAS key.</span></span>  
  
 <span data-ttu-id="b60f5-106">Une stratégie d'accès stockée fournit un niveau de contrôle supplémentaire sur des signatures d'accès partagé côté serveur.</span><span class="sxs-lookup"><span data-stu-id="b60f5-106">A stored access policy provides an additional level of control over shared access signatures on the server side.</span></span> <span data-ttu-id="b60f5-107">Une signature d'accès partagé est un URI qui octroie des droits d'accès restreints aux conteneurs, aux objets blob, aux files d'attente et aux tables.</span><span class="sxs-lookup"><span data-stu-id="b60f5-107">A shared access signature is a URI that grants restricted access rights to containers, blobs, queues, and tables.</span></span> <span data-ttu-id="b60f5-108">Si vous utilisez cette nouvelle amélioration, vous devez créer une stratégie sur un conteneur avec des droits en lecture, en écriture et en création de liste.</span><span class="sxs-lookup"><span data-stu-id="b60f5-108">When using this new enhancement, you need to create a policy on a container with read, write, and list rights.</span></span>  
  
 <span data-ttu-id="b60f5-109">Créez une stratégie et une signature d'accès partagé en utilisant une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b60f5-109">You can create a policy and a shared access signature by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="b60f5-110">Opérations de l’API REST Azure : [créer un conteneur](https://msdn.microsoft.com/library/azure/dd179468.aspx), définir une liste de contrôle d' [accès de conteneur](https://msdn.microsoft.com/library/azure/dd179391.aspx)et récupérer un [ACL de conteneur](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span><span class="sxs-lookup"><span data-stu-id="b60f5-110">Azure REST API operations: [Create Container](https://msdn.microsoft.com/library/azure/dd179468.aspx), [Set Container ACL](https://msdn.microsoft.com/library/azure/dd179391.aspx), and [Get Container ACL](https://msdn.microsoft.com/library/azure/dd179469.aspx).</span></span>  
  
-   <span data-ttu-id="b60f5-111">[Méthode CloudBlobContainer. GetSharedAccessSignature](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) dans le kit de développement logiciel (SDK) Azure.</span><span class="sxs-lookup"><span data-stu-id="b60f5-111">[CloudBlobContainer.GetSharedAccessSignature Method](https://docs.microsoft.com/dotnet/api/microsoft.azure.storage.blob.cloudblobcontainer.getsharedaccesssignature) in the Azure SDK.</span></span>  
  
    ```  
  
       string signature = blob.GetSharedAccessSignature(new SharedAccessPolicy()   
        {   
            // Specify the expiration time for the signature.   
            SharedAccessExpiryTime = DateTime.Now.Years(1),   
            // Specify the permissions granted by the signature.    
            Permissions = SharedAccessPermissions.Write | SharedAccessPermissions.Read   
        });  
  
    ```  
  
-   <span data-ttu-id="b60f5-112">Un outil de l’Explorateur Azure tiers, tel que [Explorateur stockage Azure](https://azurestorageexplorer.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="b60f5-112">A third-party Azure explorer tool, such as [Azure Storage Explorer](https://azurestorageexplorer.codeplex.com/).</span></span>  
  
 <span data-ttu-id="b60f5-113">**Leçon suivante :**</span><span class="sxs-lookup"><span data-stu-id="b60f5-113">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="b60f5-114">Leçon 3 : Créer des informations d'identification SQL Server</span><span class="sxs-lookup"><span data-stu-id="b60f5-114">Lesson 3: Create a SQL Server Credential</span></span>](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)  
  
