---
title: Gestion de clés extensible à l’aide d’Azure Key Vault (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710532"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="1f33d-102">Gestion de clés extensible à l'aide d'Azure Key Vault (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1f33d-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="1f33d-103">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] connecteur pour [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault permet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] au chiffrement de tirer parti du service Azure Key Vault en tant que fournisseur de [gestion de clés Extensible &#40;fournisseur de&#41;EKM](extensible-key-management-ekm.md) pour protéger ses clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="1f33d-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="1f33d-104">Contenu de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="1f33d-104">Included in this topic:</span></span>

-   [<span data-ttu-id="1f33d-105">Utilisations de la gestion de clés extensible</span><span class="sxs-lookup"><span data-stu-id="1f33d-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="1f33d-106">Étape 1 : Configuration du coffre de clés pour une utilisation par SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f33d-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="1f33d-107">Étape 2 : Installation du connecteur SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f33d-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="1f33d-108">Étape 3 : Configurer SQL Server pour utiliser un fournisseur EKM pour le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="1f33d-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="1f33d-109">Exemple A : chiffrement transparent des données à l'aide d'une clé asymétrique dans le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="1f33d-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="1f33d-110">Exemple B : chiffrement des sauvegardes à l'aide d'une clé asymétrique dans le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="1f33d-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="1f33d-111">Exemple C : chiffrement au niveau colonne à l'aide d'une clé asymétrique dans le coffre de clés</span><span class="sxs-lookup"><span data-stu-id="1f33d-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="1f33d-112">Utilisations de EKM</span><span class="sxs-lookup"><span data-stu-id="1f33d-112">Uses of EKM</span></span>
 <span data-ttu-id="1f33d-113">Une organisation peut utiliser le chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour protéger les données sensibles.</span><span class="sxs-lookup"><span data-stu-id="1f33d-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="1f33d-114">le chiffrement comprend [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), le [chiffrement au niveau des colonnes](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE) et le [chiffrement](../../backup-restore/backup-encryption.md)de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="1f33d-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="1f33d-115">Dans tous ces cas, les données sont chiffrées à l'aide d'une clé de chiffrement de données symétrique.</span><span class="sxs-lookup"><span data-stu-id="1f33d-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="1f33d-116">La clé de chiffrement de données symétrique est ensuite protégée en la chiffrant avec une hiérarchie de clés stockées dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f33d-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1f33d-117">Par ailleurs, l'architecture du fournisseur EKM permet à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de protéger les clés de chiffrement de données à l'aide d'une clé asymétrique stockée en dehors de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans un fournisseur de services de chiffrement externe.</span><span class="sxs-lookup"><span data-stu-id="1f33d-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="1f33d-118">L'utilisation de l'architecture du fournisseur EKM ajoute une couche supplémentaire de sécurité et permet aux organisations de séparer la gestion des clés de celle des données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="1f33d-119">Le connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour Azure Key Vault permet à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] d'utiliser le service de coffre de clés extensible à hautes performances et haute disponibilité comme un fournisseur EKM pour la protection des clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="1f33d-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="1f33d-120">Vous pouvez utiliser le service de coffre de clés avec les installations [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur Machines virtuelles [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure et pour les serveurs locaux.</span><span class="sxs-lookup"><span data-stu-id="1f33d-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="1f33d-121">Le service de coffre de clés offre également la possibilité d'utiliser des modules de sécurité matériels étroitement contrôlés et surveillés pour augmenter le niveau de protection des clés de chiffrement asymétriques.</span><span class="sxs-lookup"><span data-stu-id="1f33d-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="1f33d-122">Pour plus d’informations sur le coffre de clés, consultez [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="1f33d-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="1f33d-123">L'illustration suivante résume le flux du processus de la gestion de clés extensible à l'aide du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="1f33d-124">Les numéros d'étapes de processus dans l'image ne sont pas censés correspondre aux numéros d'étapes d'installation qui suivent l'image.</span><span class="sxs-lookup"><span data-stu-id="1f33d-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="1f33d-125">![Gestion de clés extensible SQL Server avec Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "Gestion de clés extensible (EKM) SQL Server avec Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="1f33d-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="1f33d-126">Étape 1 : configurer le Key Vault pour une utilisation par SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f33d-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="1f33d-127">Les étapes suivantes vous permettent de configurer un coffre de clés en vue de l'utiliser avec le [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] pour la protection de clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="1f33d-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="1f33d-128">Un coffre est peut-être déjà en cours d'utilisation pour l'organisation.</span><span class="sxs-lookup"><span data-stu-id="1f33d-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="1f33d-129">Si aucun coffre n'existe, l'administrateur Azure dans votre organisation chargé de gérer les clés de chiffrement peut créer un coffre, générer une clé asymétrique dans le coffre, puis autoriser [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à utiliser la clé.</span><span class="sxs-lookup"><span data-stu-id="1f33d-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="1f33d-130">Pour vous familiariser avec le service de coffre de clés, consultez la page [Prise en main du coffre de clés Azure](https://go.microsoft.com/fwlink/?LinkId=521402)et les informations de référence sur les [applets de commande du coffre de clés Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f33d-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="1f33d-131">Si vous avez plusieurs abonnements Azure, vous devez utiliser l'abonnement qui comprend [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f33d-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="1f33d-132">**Créer un coffre :** Créez un coffre en suivant les instructions de la section **Créer un coffre de clés** de la page [Prise en main du coffre de clés Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="1f33d-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="1f33d-133">Notez le nom du coffre.</span><span class="sxs-lookup"><span data-stu-id="1f33d-133">Record the name of the vault.</span></span> <span data-ttu-id="1f33d-134">Cette rubrique utilise **ContosoKeyVault** comme nom de coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="1f33d-135">**Générer une clé asymétrique dans le coffre :** la clé asymétrique dans le coffre de clés permet de protéger les clés de chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f33d-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="1f33d-136">Seule la partie publique de la clé asymétrique quitte le coffre, la partie privée n'étant jamais exportée par celui-ci.</span><span class="sxs-lookup"><span data-stu-id="1f33d-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="1f33d-137">Toutes les opérations de chiffrement à l'aide de la clé asymétrique sont déléguées au coffre de clés Azure et sont protégées par la sécurité du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="1f33d-138">Il existe plusieurs méthodes pour générer une clé asymétrique et la stocker dans le coffre.</span><span class="sxs-lookup"><span data-stu-id="1f33d-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="1f33d-139">Vous pouvez générer une clé en externe et l'importer dans le coffre en tant que fichier .pfx.</span><span class="sxs-lookup"><span data-stu-id="1f33d-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="1f33d-140">Vous pouvez aussi créer la clé directement dans le coffre à l'aide des API du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="1f33d-141">Le connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nécessite que les clés asymétriques soient des clés RSA 2 048 bits, et le nom des clés peut uniquement contenir les caractères « a-z », « A-Z », « 0-9 » et « - ».</span><span class="sxs-lookup"><span data-stu-id="1f33d-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="1f33d-142">Dans ce document, le nom de la clé asymétrique est appelé **ContosoMasterKey**.</span><span class="sxs-lookup"><span data-stu-id="1f33d-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="1f33d-143">Remplacez-le par le nom unique que vous utilisez pour la clé.</span><span class="sxs-lookup"><span data-stu-id="1f33d-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1f33d-144">L'importation de la clé asymétrique est fortement recommandée dans les scénarios de production, car elle permet à l'administrateur de déposer la clé dans un système de dépôt de clés (Key escrow).</span><span class="sxs-lookup"><span data-stu-id="1f33d-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="1f33d-145">Si la clé asymétrique est créée dans le coffre, elle ne peut pas être déposée, car la clé privée ne peut jamais sortir du coffre.</span><span class="sxs-lookup"><span data-stu-id="1f33d-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="1f33d-146">Les clés utilisées pour protéger les données critiques doivent être déposées.</span><span class="sxs-lookup"><span data-stu-id="1f33d-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="1f33d-147">La perte d'une clé asymétrique rend une partie des données définitivement irrécupérable.</span><span class="sxs-lookup"><span data-stu-id="1f33d-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1f33d-148">Le coffre de clés prend en charge plusieurs versions de la même clé nommée.</span><span class="sxs-lookup"><span data-stu-id="1f33d-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="1f33d-149">Les clés à utiliser par le connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne doivent pas être gérées sous forme de versions, ni être restaurées.</span><span class="sxs-lookup"><span data-stu-id="1f33d-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="1f33d-150">Si l'administrateur veut modifier la clé utilisée pour le chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , une nouvelle clé avec un autre nom doit être créée dans le coffre et utilisée pour chiffrer la clé de chiffrement des données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="1f33d-151">Pour plus d'informations sur la façon d'importer une clé dans le coffre de clés ou de créer une clé dans le coffre de clés (non recommandé pour un environnement de production), voir la section **Ajouter une clé ou une clé secrète dans le coffre de clés** de la page [Prise en main d’Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="1f33d-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="1f33d-152">**Obtenir les principaux du service Azure Active Directory à utiliser pour SQL Server :** quand l'organisation s'inscrit à un service cloud Microsoft, elle obtient un répertoire Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f33d-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="1f33d-153">Créez dans le répertoire Azure Active Directory des **principaux de service** qui permettront à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de s'authentifier auprès d'Azure Active Directory au moment d'accéder au coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="1f33d-154">Un **principal de service** permet à un administrateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] d'accéder au coffre pendant la configuration de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour utiliser le chiffrement.</span><span class="sxs-lookup"><span data-stu-id="1f33d-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="1f33d-155">Un autre **principal de service** permet au [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] d'accéder au coffre afin de désencapsuler les clés utilisées dans le chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f33d-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="1f33d-156">Pour plus d'informations sur la façon d'inscrire une application et de générer un principal du service, consultez la section **Inscrire une application auprès d'Azure Active Directory** dans [Prise en main d'Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="1f33d-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="1f33d-157">Le processus d'inscription retourne un **ID d'application** (également appelé **ID CLIENT**) et une **clé d'authentification** (également appelée **clé secrète**) pour chaque **principal du service**Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f33d-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="1f33d-158">Lorsqu’il est utilisé dans l' `CREATE CREDENTIAL` instruction, le trait d’Union doit être supprimé de l' **ID client**.</span><span class="sxs-lookup"><span data-stu-id="1f33d-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="1f33d-159">Enregistrez ces éléments en vue de les utiliser dans les scripts ci-après :</span><span class="sxs-lookup"><span data-stu-id="1f33d-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="1f33d-160">**Principal de service** pour une connexion **sysadmin** : **CLIENTID_sysadmin_login** et **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="1f33d-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="1f33d-161">**Principal de service** pour le [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** et **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="1f33d-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="1f33d-162">**Accordez des autorisations pour que les principaux du service accèdent au Key Vault :** Les deux principaux **CLIENTID_sysadmin_login** et **CLIENTID_DBEngineService** requièrent les autorisations d' **extraction**, de **liste**, d' **wrapKey**et de **unwrapKey** dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="1f33d-163">Si vous prévoyez de créer des clés via [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , vous devez également accorder l'autorisation **create** dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1f33d-164"> Les utilisateurs doivent avoir au moins les opérations **wrapKey** et **unwrapKey** pour le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="1f33d-165">Pour plus d'informations sur l'octroi d'autorisations dans le coffre, voir la section **Autoriser l'application à utiliser la clé ou la clé secrète** de la page [Prise en main du coffre de clés Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="1f33d-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="1f33d-166">Liens vers la documentation du coffre de clés Azure</span><span class="sxs-lookup"><span data-stu-id="1f33d-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="1f33d-167">Qu’est-ce qu’Azure Key Vault ?</span><span class="sxs-lookup"><span data-stu-id="1f33d-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="1f33d-168">Prise en main d'Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="1f33d-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="1f33d-169">Informations de référence sur les [applets de commande Azure Key Vault](https://docs.microsoft.com/powershell/module/azurerm.keyvault) de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f33d-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="1f33d-170">Étape 2 : installer le connecteur SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f33d-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="1f33d-171">Le connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est téléchargé et installé par l'administrateur de l'ordinateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f33d-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="1f33d-172">Le connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] peut être téléchargé à partir du [Centre de téléchargement Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span><span class="sxs-lookup"><span data-stu-id="1f33d-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="1f33d-173">Recherchez le **connecteur SQL Server pour le coffre de clés Microsoft Azure**, passez en revue les détails, la configuration système requise et les instructions d'installation, téléchargez le connecteur et démarrez l'installation à l'aide de l'option **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1f33d-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="1f33d-174">Passez en revue la licence et acceptez-la, puis continuez.</span><span class="sxs-lookup"><span data-stu-id="1f33d-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="1f33d-175">Par défaut, le connecteur est installé à l’emplacement **C:\Program Files\SQL Server Connector pour Microsoft Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="1f33d-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="1f33d-176">Cet emplacement peut être changé lors de l'installation.</span><span class="sxs-lookup"><span data-stu-id="1f33d-176">This location can be changed during setup.</span></span> <span data-ttu-id="1f33d-177">(S'il est changé, adaptez les scripts ci-dessous).</span><span class="sxs-lookup"><span data-stu-id="1f33d-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="1f33d-178">À la fin de l'installation, les éléments suivants sont installés sur l'ordinateur :</span><span class="sxs-lookup"><span data-stu-id="1f33d-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="1f33d-179">**Microsoft.AzureKeyVaultService.EKM.dll**: Il s'agit de la bibliothèque de liens dynamiques du fournisseur EKM de chiffrement qui doit être enregistrée avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'instruction CREATE CRYPTOGRAPHIC PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="1f33d-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="1f33d-180">**Connecteur SQL Server pour le coffre de clés Azure**: Il s'agit d'un service Windows qui permet au fournisseur EKM de chiffrement de communiquer avec le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="1f33d-181">L'installation du connecteur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vous permet également de télécharger éventuellement des exemples de scripts pour le chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f33d-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="1f33d-182">Étape 3 : configurer SQL Server pour utiliser un fournisseur EKM pour le Key Vault</span><span class="sxs-lookup"><span data-stu-id="1f33d-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1f33d-183">Autorisations</span><span class="sxs-lookup"><span data-stu-id="1f33d-183">Permissions</span></span>
 <span data-ttu-id="1f33d-184">L'exécution de l'ensemble de ce processus nécessite l'autorisation CONTROL SERVER ou l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1f33d-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="1f33d-185">Des actions spécifiques nécessitent les autorisations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f33d-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="1f33d-186">Pour créer un fournisseur de chiffrement, l'autorisation CONTROL SERVER ou l'appartenance au rôle de serveur fixe **sysadmin** est requise.</span><span class="sxs-lookup"><span data-stu-id="1f33d-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="1f33d-187">Pour modifier une option de configuration et exécuter l'instruction RECONFIGURE, vous devez disposer de l'autorisation de niveau serveur ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="1f33d-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1f33d-188">L'autorisation ALTER SETTINGS est implicitement détenue par les rôles serveur fixes **sysadmin** et **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1f33d-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="1f33d-189">La création des informations d'identification nécessite l'autorisation ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="1f33d-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="1f33d-190">L'ajout d'informations d'identification à une connexion nécessite l'autorisation ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="1f33d-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="1f33d-191">La création d'une clé asymétrique nécessite l'autorisation CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="1f33d-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="1f33d-192">Pour configurer SQL Server pour utiliser un fournisseur de services de chiffrement</span><span class="sxs-lookup"><span data-stu-id="1f33d-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="1f33d-193">Configurez le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] pour utiliser la gestion de clés extensible et inscrivez (créez) le fournisseur de chiffrement avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f33d-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="1f33d-194">Définissez des informations d'identification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour une connexion d'administrateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour utiliser le coffre de clés, de façon à pouvoir configurer et gérer des scénarios de chiffrement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1f33d-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1f33d-195">L’argument **Identity** de `CREATE CREDENTIAL` requiert le nom du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="1f33d-196">L’argument **secret** de `CREATE CREDENTIAL` exige que *\<Client ID>* (sans trait d’Union) et *\<Secret>* soit passé ensemble sans espace entre eux.</span><span class="sxs-lookup"><span data-stu-id="1f33d-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="1f33d-197">Dans l’exemple suivant, l' **ID client** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) est supprimé des traits d’Union et entré en tant que chaîne `EF5C8E094D2A4A769998D93440D8115D` et le **secret** est représenté par la chaîne *SECRET_sysadmin_login*.</span><span class="sxs-lookup"><span data-stu-id="1f33d-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="1f33d-198">Pour obtenir un exemple d’utilisation de variables pour les `CREATE CREDENTIAL` arguments et la suppression par programmation des tirets de l’ID client, consultez [Create Credential &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f33d-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="1f33d-199">Si vous avez importé une clé asymétrique comme décrit précédemment dans l'étape 1 de la section 3, ouvrez la clé en fournissant son nom dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="1f33d-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="1f33d-200">Bien que cela ne soit pas recommandé pour la production (la clé ne pouvant pas être exportée), il est possible de créer une clé asymétrique directement dans le coffre à partir de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f33d-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1f33d-201">Si vous n'avez pas déjà importé de clé, créez une clé asymétrique dans le coffre de clés à des fins de test en utilisant le script suivant.</span><span class="sxs-lookup"><span data-stu-id="1f33d-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="1f33d-202">Exécutez le script à l'aide d'une connexion configurée avec les informations d'identification **sysadmin_ekm_cred** .</span><span class="sxs-lookup"><span data-stu-id="1f33d-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="1f33d-203">Les utilisateurs reçoivent l'erreur **Impossible d’exporter la clé publique du fournisseur. Code d’erreur du fourniseur : 2053.**</span><span class="sxs-lookup"><span data-stu-id="1f33d-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="1f33d-204">doit vérifier ses autorisations **get**, **list**, **wrapKey**et **unwrapKey** dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="1f33d-205">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f33d-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="1f33d-206">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="1f33d-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="1f33d-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="1f33d-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="1f33d-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="1f33d-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="1f33d-212">Exemples</span><span class="sxs-lookup"><span data-stu-id="1f33d-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="1f33d-213">Exemple A : Transparent Data Encryption à l’aide d’une clé asymétrique du Key Vault</span><span class="sxs-lookup"><span data-stu-id="1f33d-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="1f33d-214">Après avoir effectué les étapes ci-dessus, créez des informations d'identification et une connexion, puis créez une clé de chiffrement de base de données protégée par la clé asymétrique dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="1f33d-215">Utilisez la clé de chiffrement de base de données pour chiffrer une base de données avec le chiffrement transparent des données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="1f33d-216">Chiffrer une base de données nécessite l'autorisation CONTROL sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="1f33d-217">Pour activer le chiffrement transparent des données à l'aide de la gestion de clés extensible et du coffre de clés</span><span class="sxs-lookup"><span data-stu-id="1f33d-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="1f33d-218">Créez des informations d'identification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] qui permettront d'accéder à la gestion de clés extensible du coffre de clés au moment du chargement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1f33d-219">L’argument **Identity** de `CREATE CREDENTIAL` requiert le nom du coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="1f33d-220">L’argument **secret** de `CREATE CREDENTIAL` exige que *\<Client ID>* (sans trait d’Union) et *\<Secret>* soit passé ensemble sans espace entre eux.</span><span class="sxs-lookup"><span data-stu-id="1f33d-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="1f33d-221">Dans l'exemple suivant, l' **ID client** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) est débarrassé des tirets et entré comme chaîne `EF5C8E094D2A4A769998D93440D8115D` , tandis que la **clé secrète** est représentée par la chaîne *SECRET_DBEngine*.</span><span class="sxs-lookup"><span data-stu-id="1f33d-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="1f33d-222">Créez une connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilisable par le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] pour le chiffrement transparent des données et ajoutez-y les informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="1f33d-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="1f33d-223">Cet exemple utilise la clé asymétrique CONTOSO_KEY stockée dans le coffre de clés, qui a été importée ou créée précédemment pour la base de données MASTER, comme décrit à l' [étape 3 de la section 3](#Step3) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1f33d-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="1f33d-224">Créez la clé de chiffrement de base de données (DEK) qui sera utilisée pour le chiffrement transparent des données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="1f33d-225">La clé de chiffrement de base de données peut être créée à l'aide de n'importe quelle longueur de clé ou algorithme pris en charge par SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f33d-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="1f33d-226">La clé DEK est protégée par la clé asymétrique dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="1f33d-227">Cet exemple utilise la clé asymétrique CONTOSO_KEY stockée dans le coffre de clés, qui a été importée ou créée précédemment, comme décrit à l' [étape 3 de la section 3](#Step3) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1f33d-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="1f33d-228">Pour plus d’informations, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1f33d-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="1f33d-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="1f33d-230">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1f33d-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="1f33d-231">Exemple B : chiffrement des sauvegardes à l’aide d’une clé asymétrique à partir du Key Vault</span><span class="sxs-lookup"><span data-stu-id="1f33d-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="1f33d-232">Les sauvegardes chiffrées sont prises en charge à partir de [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f33d-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="1f33d-233">L'exemple suivant crée et restaure une sauvegarde chiffrée avec une clé de chiffrement de données protégée par la clé asymétrique dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="1f33d-234">Exemple de code de restauration.</span><span class="sxs-lookup"><span data-stu-id="1f33d-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="1f33d-235">Pour plus d’informations sur les options de sauvegarde, consultez [backup &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1f33d-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="1f33d-236">Exemple C : chiffrement au niveau des colonnes à l’aide d’une clé asymétrique à partir du Key Vault</span><span class="sxs-lookup"><span data-stu-id="1f33d-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="1f33d-237">L'exemple suivant crée une clé symétrique protégée par la clé asymétrique dans le coffre de clés.</span><span class="sxs-lookup"><span data-stu-id="1f33d-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="1f33d-238">La clé symétrique est ensuite utilisée pour chiffrer les données de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1f33d-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="1f33d-239">Cet exemple utilise la clé asymétrique CONTOSO_KEY stockée dans le coffre de clés, qui a été importée ou créée précédemment, comme décrit à l' [étape 3 de la section 3](#Step3) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1f33d-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="1f33d-240">Pour utiliser cette clé asymétrique dans la base de données `ContosoDatabase` , vous devez réexécuter l'instruction CREATE ASYMMETRIC KEY pour fournir à la base de données `ContosoDatabase` une référence à la clé.</span><span class="sxs-lookup"><span data-stu-id="1f33d-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="1f33d-241">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f33d-241">See Also</span></span>
 <span data-ttu-id="1f33d-242">[Créer un fournisseur de services de chiffrement &#40;Transact-sql&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [créer des informations d’identification &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [créer une clé asymétrique &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [créer une clé symétrique &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [gestion de clés extensible &#40;EKM&#41;](extensible-key-management-ekm.md) [activer TDE à l’aide de EKM](enable-tde-on-sql-server-using-ekm.md) [Backup](../../backup-restore/backup-encryption.md) Encryption [créer une sauvegarde chiffrée](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="1f33d-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
