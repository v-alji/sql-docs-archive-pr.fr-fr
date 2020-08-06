---
title: Créer des informations d’identification - Authentification Azure Storage
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707624"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="3d79c-102">Créer des informations d’identification - Authentification Azure Storage</span><span class="sxs-lookup"><span data-stu-id="3d79c-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="3d79c-103">Utilisez la boîte de dialogue **Sauvegarde sur un périphérique URL - Créer des informations d’identification** pour créer des informations d’identification SQL.</span><span class="sxs-lookup"><span data-stu-id="3d79c-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="3d79c-104">Lorsque vous utilisez cette boîte de dialogue pour créer des informations d’identification, vous devez ajouter un certificat de gestion Azure au magasin de certificats local, ou un profil de publication téléchargé sur votre ordinateur, pour valider l’abonnement et les informations d’identification du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="3d79c-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="3d79c-105">**Informations d'identification SQL**</span><span class="sxs-lookup"><span data-stu-id="3d79c-105">**SQL Credential**</span></span>  
 <span data-ttu-id="3d79c-106">Spécifiez le nom des informations d'identification SQL que vous souhaitez créer.</span><span class="sxs-lookup"><span data-stu-id="3d79c-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="3d79c-107">Informations d’identification Azure</span><span class="sxs-lookup"><span data-stu-id="3d79c-107">Azure Credentials</span></span>  
 <span data-ttu-id="3d79c-108">**Certificat de gestion**</span><span class="sxs-lookup"><span data-stu-id="3d79c-108">**Management Certificate**</span></span>  
 <span data-ttu-id="3d79c-109">Utilisez cette option pour spécifier un certificat dans le magasin de certificats local qui correspond au certificat de gestion Azure.</span><span class="sxs-lookup"><span data-stu-id="3d79c-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="3d79c-110">Pour plus d’informations sur le certificat de gestion Azure, consultez [Créer et télécharger un certificat de gestion pour Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span><span class="sxs-lookup"><span data-stu-id="3d79c-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="3d79c-111">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="3d79c-111">**Subscription**</span></span>  
 <span data-ttu-id="3d79c-112">Sélectionnez, entrez ou collez votre ID d’abonnement Azure qui correspond au certificat de gestion dans le magasin de certificats local.</span><span class="sxs-lookup"><span data-stu-id="3d79c-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="3d79c-113">**Profil de publication**</span><span class="sxs-lookup"><span data-stu-id="3d79c-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="3d79c-114">Utilisez cette option si vous avez un profil de publication téléchargé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3d79c-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="3d79c-115">Si vous utilisez cette option, l'ID d'abonnement et le certificat sont remplis automatiquement.</span><span class="sxs-lookup"><span data-stu-id="3d79c-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3d79c-116">SQL Server prend actuellement en charge la version 2.0 du profil de publication.</span><span class="sxs-lookup"><span data-stu-id="3d79c-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="3d79c-117">Pour télécharger la version prise en charge du profil de publication, consultez [Télécharger le profil de publication 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="3d79c-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="3d79c-118">Compte de stockage</span><span class="sxs-lookup"><span data-stu-id="3d79c-118">Storage Account</span></span>  
 <span data-ttu-id="3d79c-119">Sélectionnez le compte de stockage que vous souhaitez utiliser pour stocker les fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="3d79c-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
