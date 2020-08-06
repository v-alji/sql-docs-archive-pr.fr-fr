---
title: Restaurer la clé principale du service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710527"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="aba4d-102">Restaurer la clé principale du service</span><span class="sxs-lookup"><span data-stu-id="aba4d-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="aba4d-103">Cette rubrique explique comment restaurer la clé principale de service dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aba4d-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aba4d-104">Il est peu probable que vous ayez jamais à restaurer cette clé.</span><span class="sxs-lookup"><span data-stu-id="aba4d-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="aba4d-105">Si vous deviez le faire, observez la plus grande prudence.</span><span class="sxs-lookup"><span data-stu-id="aba4d-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="aba4d-106">Pour plus d’informations, consultez [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="aba4d-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="aba4d-107">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="aba4d-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aba4d-108">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="aba4d-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aba4d-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="aba4d-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aba4d-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aba4d-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="aba4d-111">Pour restaurer la clé principale de service à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aba4d-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aba4d-112">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="aba4d-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aba4d-113">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="aba4d-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="aba4d-114">Lorsque la clé principale de service est restaurée, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] déchiffre toutes les clés et les secrets qui ont été chiffrés au moyen de la clé principale de service en cours, puis les chiffre au moyen de la clé principale de service chargée à partir du fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="aba4d-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="aba4d-115">Si l'un des déchiffrements échoue, la restauration échoue.</span><span class="sxs-lookup"><span data-stu-id="aba4d-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="aba4d-116">Vous pouvez utiliser l'option FORCE pour ignorer les erreurs, mais cette option entraîne la perte de toutes les données ne pouvant pas être déchiffrées.</span><span class="sxs-lookup"><span data-stu-id="aba4d-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="aba4d-117">La régénération de la hiérarchie de chiffrement est une opération qui consomme beaucoup de ressources.</span><span class="sxs-lookup"><span data-stu-id="aba4d-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="aba4d-118">Par conséquent, vous devez planifier cette opération au cours d'une période de faible demande.</span><span class="sxs-lookup"><span data-stu-id="aba4d-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="aba4d-119">La clé principale de service représente la racine de la hiérarchie de chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aba4d-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="aba4d-120">La clé principale de service sécurise de manière directe ou indirecte toutes les autres clés de l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="aba4d-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="aba4d-121">Si une clé dépendante ne peut pas être déchiffrée au cours d'une restauration forcée, les données sécurisées par cette clé sont perdues.</span><span class="sxs-lookup"><span data-stu-id="aba4d-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aba4d-122">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aba4d-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aba4d-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="aba4d-123">Permissions</span></span>  
 <span data-ttu-id="aba4d-124">Requiert l'autorisation CONTROL SERVER sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="aba4d-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aba4d-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aba4d-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="aba4d-126">Pour restaurer la clé principale du service</span><span class="sxs-lookup"><span data-stu-id="aba4d-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="aba4d-127">Récupérez une copie de la clé principale du service sauvegardée, à partir d'un support de sauvegarde physique ou d'un répertoire sur le système de fichiers local.</span><span class="sxs-lookup"><span data-stu-id="aba4d-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="aba4d-128">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aba4d-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="aba4d-129">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="aba4d-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="aba4d-130">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="aba4d-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="aba4d-131">Le chemin d'accès à la clé et le mot de passe de la clé (s'il existe) seront différents de ce qui est indiqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="aba4d-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="aba4d-132">Assurez-vous que les deux sont spécifiques à votre installation de serveur et de clé.</span><span class="sxs-lookup"><span data-stu-id="aba4d-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  
