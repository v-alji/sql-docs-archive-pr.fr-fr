---
title: Se connecter au stockage Azure (restauration) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614668"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="d3ce3-102">Connectez-vous au Stockage Azure (Restaurer)</span><span class="sxs-lookup"><span data-stu-id="d3ce3-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="d3ce3-103">La boîte de dialogue vous permet de spécifier les informations de connexion au compte de stockage Azure pour récupérer les fichiers qui y sont stockés.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="d3ce3-104">Après avoir spécifié les informations requises, cliquez sur **Connexion** pour établir la connexion au stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="d3ce3-105">Compte Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="d3ce3-105">Azure Storage Account</span></span>  
 <span data-ttu-id="d3ce3-106">**Compte de stockage**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-106">**Storage account**</span></span>  
 <span data-ttu-id="d3ce3-107">Sélectionnez, entrez ou collez le nom du compte de stockage Azure que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="d3ce3-108">La liste déroulante répertorie les comptes utilisés précédemment.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="d3ce3-109">**Clé de compte**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-109">**Account key**</span></span>  
 <span data-ttu-id="d3ce3-110">Spécifiez la clé d’accès du compte de stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="d3ce3-111">Case à cocher**Utiliser des points de terminaisons sécurisés (HTTPS)**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="d3ce3-112">Sélectionnez cette option pour établir une connexion sécurisée au stockage Azure (recommandé).</span><span class="sxs-lookup"><span data-stu-id="d3ce3-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="d3ce3-113">Case à cocher**Enregistrer la clé de compte**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-113">**Save account key** check box</span></span>  
 <span data-ttu-id="d3ce3-114">Cochez cette case si vous souhaitez que SQL Server se souvienne de la clé d'accès de ce compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="d3ce3-115">Informations d'identification SQL</span><span class="sxs-lookup"><span data-stu-id="d3ce3-115">SQL Credential</span></span>  
 <span data-ttu-id="d3ce3-116">**Sélectionner des informations d'identification existantes**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="d3ce3-117">Sélectionnez des informations d'identification SQL existantes correspondant au compte de stockage et à la clé d'accès.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="d3ce3-118">**Créer de nouvelles informations d'identification**</span><span class="sxs-lookup"><span data-stu-id="d3ce3-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="d3ce3-119">Sélectionnez cette option pour créer de nouvelles informations d'identification en utilisant les informations du compte de stockage et de la clé d'accès.</span><span class="sxs-lookup"><span data-stu-id="d3ce3-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="d3ce3-120">Spécifiez le nom des nouvelles informations d'identification dans le champ **Nom d'identification** .</span><span class="sxs-lookup"><span data-stu-id="d3ce3-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
