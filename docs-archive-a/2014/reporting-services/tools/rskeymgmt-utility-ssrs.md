---
title: Utilitaire rskeymgmt (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], encryption
- joining report server instances [SQL Server]
- report server scale-out deployments [Reporting Services]
- cryptography [Reporting Services]
- multiple report server instances
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], scale-out deployments
- encryption [Reporting Services]
- rskeymgmt utility
- scale-out deployments [Reporting Services]
ms.assetid: 53f1318d-bd2d-4c08-b19f-c8b698b5b3d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae4bdd6656cf5b29f8fd40fcf730f49a6de8f32e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704820"
---
# <a name="rskeymgmt-utility-ssrs"></a><span data-ttu-id="d824c-102">Utilitaire rskeymgmt (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d824c-102">rskeymgmt Utility (SSRS)</span></span>
  <span data-ttu-id="d824c-103">Extrait, restaure, crée et supprime la clé symétrique utilisée pour protéger les données sensibles de serveur de rapports contre un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="d824c-103">Extracts, restores, creates, and deletes the symmetric key used to protect sensitive report server data against unauthorized access.</span></span> <span data-ttu-id="d824c-104">Cet utilitaire sert également à joindre des instances de serveur de rapports dans un déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-104">This utility is also used to join report server instances in a scale-out deployment.</span></span> <span data-ttu-id="d824c-105">Un *déploiement évolutif de serveurs de rapports* correspond à plusieurs instances de serveur de rapports qui partagent une base de données de serveur de rapports unique.</span><span class="sxs-lookup"><span data-stu-id="d824c-105">A *report server scale-out deployment* refers to multiple report server instances that share a single report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d824c-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d824c-106">Syntax</span></span>  
  
```  
  
      rskeymgmt {-?}  
{-eextract}  
{-aapply}  
{-ddeleteall}  
{-srecreatekey}  
{-rremoveinstancekey}  
{-jjoinfarm}  
{-iinstance}  
{-ffile}  
{-pencryptionpassword}  
{-mremotecomputer}  
{-ninstancenameofremotecomputer}  
{-uadministratoruseraccount}  
{-vadministratorpassword}  
{-ttrace}  
```  
  
## <a name="arguments"></a><span data-ttu-id="d824c-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="d824c-107">Arguments</span></span>  
 <span data-ttu-id="d824c-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="d824c-108">**-?**</span></span>  
 <span data-ttu-id="d824c-109">Affiche la syntaxe des arguments de **rskeymgmt** .</span><span class="sxs-lookup"><span data-stu-id="d824c-109">Displays the syntax of **rskeymgmt** arguments.</span></span>  
  
 <span data-ttu-id="d824c-110">**-e**</span><span class="sxs-lookup"><span data-stu-id="d824c-110">**-e**</span></span>  
 <span data-ttu-id="d824c-111">Extrait la clé symétrique utilisée pour chiffrer et déchiffrer des données pour l'instance du serveur de rapports afin que vous puissiez les copier dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="d824c-111">Extracts the symmetric key used to encrypt and decrypt data for the report server instance so that you can copy it to a file.</span></span>  
  
 <span data-ttu-id="d824c-112">Cet argument ne prend pas de valeur.</span><span class="sxs-lookup"><span data-stu-id="d824c-112">This argument does not take a value.</span></span> <span data-ttu-id="d824c-113">Cependant, vous devez inclure des arguments supplémentaires sur la ligne de commande pour effectuer l'extraction.</span><span class="sxs-lookup"><span data-stu-id="d824c-113">However, you must include additional arguments on the command line to complete the extraction.</span></span> <span data-ttu-id="d824c-114">Les arguments que vous devez spécifier incluent notamment `-f` et`-p`.</span><span class="sxs-lookup"><span data-stu-id="d824c-114">The arguments that you must specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="d824c-115">**-a**</span><span class="sxs-lookup"><span data-stu-id="d824c-115">**-a**</span></span>  
 <span data-ttu-id="d824c-116">Remplace une clé symétrique existante par une copie que vous pouvez fournir dans un fichier de sauvegarde protégé par mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d824c-116">Replaces an existing symmetric key with a copy that you provide in a password protected backup file.</span></span> <span data-ttu-id="d824c-117">Toutes les instances de la clé symétrique sont mises à jour.</span><span class="sxs-lookup"><span data-stu-id="d824c-117">All instances of the symmetric key are updated.</span></span>  
  
 <span data-ttu-id="d824c-118">Cet argument ne prend pas de valeur.</span><span class="sxs-lookup"><span data-stu-id="d824c-118">This argument does not take a value.</span></span> <span data-ttu-id="d824c-119">Cependant, vous devez inclure des arguments supplémentaires sur la ligne de commande pour sélectionner le fichier contenant la clé à appliquer.</span><span class="sxs-lookup"><span data-stu-id="d824c-119">However, you must include additional arguments on the command line to select the file that contains the key to be applied.</span></span> <span data-ttu-id="d824c-120">Les arguments que vous pouvez spécifier incluent `-f` et`-p`.</span><span class="sxs-lookup"><span data-stu-id="d824c-120">The arguments that you can specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="d824c-121">**-d**</span><span class="sxs-lookup"><span data-stu-id="d824c-121">**-d**</span></span>  
 <span data-ttu-id="d824c-122">Supprime toutes les instances de clé symétrique et toutes les données chiffrées dans une base de données de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-122">Deletes all symmetric key instances and all encrypted data in a report server database.</span></span> <span data-ttu-id="d824c-123">Cet argument ne prend pas de valeur.</span><span class="sxs-lookup"><span data-stu-id="d824c-123">This argument does not take a value.</span></span>  
  
 `-s`  
 <span data-ttu-id="d824c-124">Génère une nouvelle clé symétrique et rechiffre l'ensemble du contenu chiffré à l'aide de la nouvelle clé.</span><span class="sxs-lookup"><span data-stu-id="d824c-124">Generates a new symmetric key and re-encrypts all encrypted content using the new key.</span></span> <span data-ttu-id="d824c-125">Toutes les instances de la clé symétrique sont régénérées.</span><span class="sxs-lookup"><span data-stu-id="d824c-125">All instances of the symmetric key are regenerated.</span></span>  
  
 `-j`  
 <span data-ttu-id="d824c-126">Configure une instance de serveur de rapports distante de manière à partager la base de données de serveur de rapports qui est utilisée par l'instance de serveur de rapports locale.</span><span class="sxs-lookup"><span data-stu-id="d824c-126">Configures a remote report server instance to share the report server database that is used by the local report server instance.</span></span>  
  
 <span data-ttu-id="d824c-127">**-r**  *installationID*</span><span class="sxs-lookup"><span data-stu-id="d824c-127">**-r**  *installationID*</span></span>  
 <span data-ttu-id="d824c-128">Supprime les informations de clé symétrique pour une instance de serveur de rapports spécifique, supprimant de ce fait le serveur de rapports d'un déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-128">Removes the symmetric key information for a specific report server instance, thereby removing the report server from a scale-out deployment.</span></span> <span data-ttu-id="d824c-129">*installationID* est une valeur GUID se trouvant dans le fichier RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="d824c-129">The *installationID* is a GUID value that can be found in the RSReportserver.config file.</span></span>  
  
 <span data-ttu-id="d824c-130">`-f`  *txt*</span><span class="sxs-lookup"><span data-stu-id="d824c-130">`-f`  *file*</span></span>  
 <span data-ttu-id="d824c-131">Définit un chemin d'accès complet au fichier qui stocke une copie de sauvegarde des clés symétriques.</span><span class="sxs-lookup"><span data-stu-id="d824c-131">Specifies a fully qualified path to the file that stores a backup copy of the symmetric keys.</span></span>  
  
 <span data-ttu-id="d824c-132">Pour **rskeymgmt -e**, la clé symétrique est écrite dans le fichier que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="d824c-132">For **rskeymgmt -e**, the symmetric key is written to the file you specify.</span></span>  
  
 <span data-ttu-id="d824c-133">Pour **rskeymgmt -a**, la valeur de clé symétrique stockée dans le fichier est appliquée à l’instance du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-133">For **rskeymgmt -a**, the symmetric key value stored in the file is applied to the report server instance.</span></span>  
  
 <span data-ttu-id="d824c-134">`-p`  *mot de passe*</span><span class="sxs-lookup"><span data-stu-id="d824c-134">`-p`  *password*</span></span>  
 <span data-ttu-id="d824c-135">(Requis pour `-f`) Spécifie le mot de passe utilisé pour sauvegarder ou appliquer une clé symétrique.</span><span class="sxs-lookup"><span data-stu-id="d824c-135">(Required for `-f`) Specifies the password used to back up or apply a symmetric key.</span></span> <span data-ttu-id="d824c-136">Cette valeur ne peut pas être vide.</span><span class="sxs-lookup"><span data-stu-id="d824c-136">This value cannot be empty.</span></span>  
  
 `-i`  
 <span data-ttu-id="d824c-137">Spécifie une instance de serveur de rapports locale.</span><span class="sxs-lookup"><span data-stu-id="d824c-137">Specifies a local report server instance.</span></span> <span data-ttu-id="d824c-138">Cet argument est facultatif si vous avez installé le serveur de rapports sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut (la valeur par défaut de `-i` est MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d824c-138">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-i` is MSSQLSERVER).</span></span> <span data-ttu-id="d824c-139">Si vous avez installé le serveur de rapports en tant qu'instance nommée, `-i` est requis.</span><span class="sxs-lookup"><span data-stu-id="d824c-139">If you installed the report server as a named instance, `-i` is required.</span></span>  
  
 `-m`  
 <span data-ttu-id="d824c-140">Spécifie le nom de l'ordinateur distant qui héberge l'instance de serveur de rapports que vous joignez au déploiement évolutif de serveurs de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-140">Specifies the name of the remote computer that hosts the report server instance you are joining to the report server scale-out deployment.</span></span> <span data-ttu-id="d824c-141">Utilisez le nom de l'ordinateur qui l'identifie sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="d824c-141">Use the name of the computer that identifies it on your network.</span></span>  
  
 `-n`  
 <span data-ttu-id="d824c-142">Spécifie le nom de l'instance de serveur de rapports sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="d824c-142">Specifies the name of the report server instance on a remote computer.</span></span> <span data-ttu-id="d824c-143">Cet argument est facultatif si vous avez installé le serveur de rapports sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par défaut (la valeur par défaut de `-n` est MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d824c-143">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-n` is MSSQLSERVER).</span></span> <span data-ttu-id="d824c-144">Si vous avez installé le serveur de rapports en tant qu'instance nommée, `-n` est requis.</span><span class="sxs-lookup"><span data-stu-id="d824c-144">If you installed the report server as a named instance, `-n` is required.</span></span>  
  
 <span data-ttu-id="d824c-145">`-u`  *UserAccount*</span><span class="sxs-lookup"><span data-stu-id="d824c-145">`-u`  *useraccount*</span></span>  
 <span data-ttu-id="d824c-146">Spécifie le compte d'administrateur sur l'ordinateur distant que vous joignez au déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-146">Specifies the administrator account on the remote computer that you are joining to the scale-out deployment.</span></span> <span data-ttu-id="d824c-147">Si un compte n'est pas spécifié, les informations d'identification de l'utilisateur actuel sont employées.</span><span class="sxs-lookup"><span data-stu-id="d824c-147">If an account is not specified, the credentials of the current user are used.</span></span>  
  
 <span data-ttu-id="d824c-148">`-v`  *mot de passe*</span><span class="sxs-lookup"><span data-stu-id="d824c-148">`-v`  *password*</span></span>  
 <span data-ttu-id="d824c-149">(Requis pour `-u`) Spécifie le mot de passe d'un compte d'administrateur sur l'ordinateur distant que vous souhaitez joindre au déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-149">(Required for `-u`) Specifies the password of an administrator account on the remote computer that you want to join to the scale-out deployment.</span></span>  
  
 <span data-ttu-id="d824c-150">**-t**  *trace*</span><span class="sxs-lookup"><span data-stu-id="d824c-150">**-t**  *trace*</span></span>  
 <span data-ttu-id="d824c-151">Envoie des messages d'erreur au journal de suivi.</span><span class="sxs-lookup"><span data-stu-id="d824c-151">Outputs error messages to the trace log.</span></span> <span data-ttu-id="d824c-152">Cet argument ne prend pas de valeur.</span><span class="sxs-lookup"><span data-stu-id="d824c-152">This argument does not take a value.</span></span> <span data-ttu-id="d824c-153">Pour plus d’informations, consultez [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="d824c-153">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="d824c-154">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d824c-154">Permissions</span></span>  
 <span data-ttu-id="d824c-155">Vous devez être un administrateur local pour pouvoir exécuter cet outil et vous devez l'exécuter localement sur l'ordinateur qui héberge le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-155">You must be a local administrator to run the tool, and you must run it locally on the computer that hosts the report server.</span></span> <span data-ttu-id="d824c-156">L'utilitaire rskeymgmt fonctionne avec l'instance locale de Windows Report Server (l'utilitaire ne peut pas se connecter à des instances distantes du service Windows Report Server, il ne peut donc pas être utilisé pour gérer les clés de chiffrement d'une instance distante de serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="d824c-156">The rskeymgmt utility works with the local Report Server Windows instance (the utility cannot connect to remote instances of the Report Server Windows service so it cannot be used to manage the encryption keys of a remote report server instance).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d824c-157">Si vous utilisez les arguments `-u` et `-v`, prenez soin de spécifier un compte doté des autorisations d'administrateur sur l'ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="d824c-157">If you are using the `-u` and `-v` arguments, be sure to specify an account that has administrator permissions on the remote computer.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d824c-158">Exemples</span><span class="sxs-lookup"><span data-stu-id="d824c-158">Examples</span></span>  
 <span data-ttu-id="d824c-159">Les exemples suivants illustrent diverses manières d’utiliser **rskeymgmt**.</span><span class="sxs-lookup"><span data-stu-id="d824c-159">The following examples illustrate ways of using **rskeymgmt**.</span></span> <span data-ttu-id="d824c-160">Les exemples suivants illustrent l'extraction, la restauration et la suppression de clés de chiffrement, ainsi que la configuration d'un déploiement évolutif de serveurs de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-160">The following examples show how to extract, restore, and delete encryption keys, and how to configure a report server scale-out deployment.</span></span>  
  
#### <a name="extracting-encryption-keys"></a><span data-ttu-id="d824c-161">Extraction de clés de chiffrement</span><span class="sxs-lookup"><span data-stu-id="d824c-161">Extracting Encryption Keys</span></span>  
 <span data-ttu-id="d824c-162">Cet exemple illustre la création d'une copie de sauvegarde de la clé de chiffrement et son enregistrement sur une disquette dans un fichier protégé par mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d824c-162">This example shows how to create a backup copy of the encryption key and save it to a password-protected file on a floppy disk.</span></span> <span data-ttu-id="d824c-163">Si le serveur de rapports est installé en tant qu'instance nommée, ajoutez l'argument `-i`.</span><span class="sxs-lookup"><span data-stu-id="d824c-163">If the report server is installed as a named instance, add the `-i` argument.</span></span>  
  
```  
rskeymgmt -e -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="restoring-encryption-keys"></a><span data-ttu-id="d824c-164">Restauration de clés de chiffrement</span><span class="sxs-lookup"><span data-stu-id="d824c-164">Restoring Encryption Keys</span></span>  
 <span data-ttu-id="d824c-165">Cet exemple illustre le remplacement de la clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="d824c-165">This example shows how to replace the encryption key.</span></span> <span data-ttu-id="d824c-166">Vous devez spécifier l'emplacement de la copie de sauvegarde de la clé et le mot de passe qui déverrouille le fichier.</span><span class="sxs-lookup"><span data-stu-id="d824c-166">You must specify the location of the backup copy of the key and the password that unlocks the file.</span></span>  
  
```  
rskeymgmt -a -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="deleting-encryption-keys-and-encrypted-content"></a><span data-ttu-id="d824c-167">Suppression de clés de chiffrement et contenu chiffré</span><span class="sxs-lookup"><span data-stu-id="d824c-167">Deleting Encryption Keys and Encrypted Content</span></span>  
 <span data-ttu-id="d824c-168">Cet exemple illustre la suppression de toutes les clés de chiffrement stockées dans un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-168">This example shows how to delete all encryption keys stored in a report server.</span></span> <span data-ttu-id="d824c-169">Si votre installation est un déploiement évolutif de serveur de rapports, les clés de chiffrement de toutes les instances de serveur de rapports qui sont incluses dans le déploiement sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="d824c-169">If your installation is a report server scale-out deployment, the encryption keys for all report server instances that are included in the deployment will be deleted.</span></span> <span data-ttu-id="d824c-170">La suppression d'une clé de chiffrement supprime également toutes les valeurs chiffrées existantes dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-170">Deleting an encryption key also deletes any existing encrypted values in the report server database.</span></span> <span data-ttu-id="d824c-171">Pour plus d’informations sur le contenu chiffré, consultez [Stocker des données chiffrées du serveur de rapports &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span><span class="sxs-lookup"><span data-stu-id="d824c-171">For more information about encrypted content, see [Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span></span>  
  
```  
rskeymgmt -d  
```  
  
#### <a name="joining-a-remote-report-server-named-instance-to-a-scale-out-deployment"></a><span data-ttu-id="d824c-172">Jointure d'une instance nommée de serveur de rapports distante à un déploiement évolutif</span><span class="sxs-lookup"><span data-stu-id="d824c-172">Joining a Remote Report Server Named Instance to a Scale-out Deployment</span></span>  
 <span data-ttu-id="d824c-173">Cet exemple illustre l'ajout d'une instance de serveur de rapports qui est installée sur un ordinateur distant dans un déploiement évolutif de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-173">This example shows how to add a report server instance that is installed on a remote computer to a report server scale-out deployment.</span></span> <span data-ttu-id="d824c-174">Vous devez exécuter la commande sur l'un des ordinateurs déjà configurés pour utiliser la base de données partagée.</span><span class="sxs-lookup"><span data-stu-id="d824c-174">You must run the command on one of the computers that is already configured to use the shared database.</span></span> <span data-ttu-id="d824c-175">Les arguments de la commande spécifient l'instance du serveur de rapports distante que vous souhaitez joindre au déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-175">The command arguments specify the remote report server instance you want to join to the scale-out deployment.</span></span>  
  
```  
rskeymgmt -j -m <remotecomputer> -n <namedreportserverinstance> -u <administratoraccount> -v <administratorpassword>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="d824c-176">Un déploiement évolutif de serveur de rapports se réfère à un modèle de déploiement où plusieurs instances de serveur de rapports partagent la même base de données de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-176">A report server scale-out deployment refers to a deployment model where multiple report server instances share the same report server database.</span></span> <span data-ttu-id="d824c-177">Une base de données de serveur de rapports peut être utilisée par n'importe quelle instance de serveur de rapports qui stocke ses clés symétriques dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d824c-177">A report server database can be used by any report server instance that stores its symmetric keys in the database.</span></span> <span data-ttu-id="d824c-178">Par exemple, si une base de données de serveurs de rapport contient des informations clés pour trois instances de serveur de rapports, les trois instances sont considérées comme étant membres du même déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-178">For example, if a report server database contains key information for three report server instances, all three instances are considered to members of the same scale-out deployment.</span></span>  
  
#### <a name="joining-report-server-instances-on-the-same-computer"></a><span data-ttu-id="d824c-179">Jonction d'instances de serveur de rapports sur un même ordinateur</span><span class="sxs-lookup"><span data-stu-id="d824c-179">Joining Report Server Instances on the Same Computer</span></span>  
 <span data-ttu-id="d824c-180">Vous pouvez créer un déploiement évolutif à partir de plusieurs instances de serveur de rapports installées sur un même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d824c-180">You can create a scale-out deployment from multiple report server instances that are installed on the same computer.</span></span> <span data-ttu-id="d824c-181">Ne définissez pas les arguments `-u` et `-v` si vous joignez des instances de serveur de rapports installées localement.</span><span class="sxs-lookup"><span data-stu-id="d824c-181">Do not set the `-u` and `-v` arguments if you are joining report server instances that are installed locally.</span></span> <span data-ttu-id="d824c-182">Utilisez les arguments `-u` et `-v` uniquement lorsque vous joignez une instance d'un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="d824c-182">The `-u` and `-v` arguments are used only when you are joining an instance from a remote computer.</span></span> <span data-ttu-id="d824c-183">Si vous spécifiez ces arguments, l'erreur suivante s'affiche : « Les références utilisateur ne peuvent pas être utilisées pour des connexions locales ».</span><span class="sxs-lookup"><span data-stu-id="d824c-183">If you specify the arguments, you will get the following error: "User credentials cannot be used for local connections."</span></span>  
  
 <span data-ttu-id="d824c-184">L'exemple suivant illustre la syntaxe de création d'un déploiement évolutif à l'aide de plusieurs instances locales.</span><span class="sxs-lookup"><span data-stu-id="d824c-184">The following example illustrates the syntax for creating a scale-out deployment using multiple local instances.</span></span> <span data-ttu-id="d824c-185">Dans cet exemple, <`initializedinstance`> est le nom d’une instance qui est déjà initialisée pour utiliser la base de données du serveur de rapports, et <`newinstance`> est le nom de l’instance que vous souhaitez ajouter au déploiement :</span><span class="sxs-lookup"><span data-stu-id="d824c-185">In this example, <`initializedinstance`> is the name of an instance that is already initialized to use the report server database, and <`newinstance`> is the name of the instance that you want to add to the deployment:</span></span>  
  
```  
rskeymgmt -j -i <initializedinstance> -m <computer name> -n <newinstance>  
```  
  
#### <a name="removing-encryption-keys-for-a-single-report-server-in-a-scale-out-deployment"></a><span data-ttu-id="d824c-186">Suppression de clés de chiffrement pour un serveur de rapports unique dans un déploiement évolutif</span><span class="sxs-lookup"><span data-stu-id="d824c-186">Removing Encryption Keys for a Single Report Server in a Scale-out Deployment</span></span>  
 <span data-ttu-id="d824c-187">Cet exemple illustre la suppression des clés de chiffrement d'un serveur de rapports unique dans un déploiement évolutif de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-187">This example shows how to remove the encryption keys for a single report server in a report server scale-out deployment.</span></span> <span data-ttu-id="d824c-188">Les clés sont supprimées de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d824c-188">The keys are removed from the report server database.</span></span> <span data-ttu-id="d824c-189">Une fois que les clés de cette instance de serveur de rapports sont retirées, cette instance de serveur de rapports ne peut plus accéder aux données chiffrées dans la base de données, ce qui la retire en fait du déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-189">Once the keys for that report server instance are removed, that report server instance can no longer access encrypted data in the database, effectively removing it from the scale-out deployment.</span></span>  
  
 <span data-ttu-id="d824c-190">La suppression d'une instance de serveur de rapports d'un déploiement avec montée en puissance parallèle requiert la spécification d'un ID d'installation.</span><span class="sxs-lookup"><span data-stu-id="d824c-190">Removing a report server instance from a scale-out deployment requires you to specify an installation ID.</span></span> <span data-ttu-id="d824c-191">L'ID d'installation est un GUID stocké dans le fichier RSReportserver.config de l'instance de serveur de rapports pour laquelle vous souhaitez supprimer des clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="d824c-191">The installation ID is a GUID stored in the RSReportserver.config file of the report server instance for which you want to remove encryption keys.</span></span> <span data-ttu-id="d824c-192">Vous devez exécuter la commande suivante sur l'ordinateur à retirer du déploiement évolutif.</span><span class="sxs-lookup"><span data-stu-id="d824c-192">You must run the following command on the computer that you want to remove from the scale-out deployment.</span></span> <span data-ttu-id="d824c-193">Si le serveur de rapports est installé en tant qu'instance nommée, ajoutez l'argument `-i` pour spécifier l'instance.</span><span class="sxs-lookup"><span data-stu-id="d824c-193">If the report server is installed as a named instance, use the `-i` argument to specify the instance.</span></span> <span data-ttu-id="d824c-194">Pour plus d'informations, consultez [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="d824c-194">For more information, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>  
  
```  
rskeymgmt -r <installationID>  
```  
  
## <a name="file-location"></a><span data-ttu-id="d824c-195">Emplacement du fichier</span><span class="sxs-lookup"><span data-stu-id="d824c-195">File Location</span></span>  
 <span data-ttu-id="d824c-196">Rskeymgmt.exe se trouve à l’emplacement \*\* \<*drive*> suivant : \Program Files\Microsoft SQL Server\110\Tools\Binn\*\* ou à l’emplacement \*\* \<*drive*> suivant : \Program Files (x86) \Microsoft SQL Server\110\Tools\Binn\*\*.</span><span class="sxs-lookup"><span data-stu-id="d824c-196">Rskeymgmt.exe is located at **\<*drive*>:\Program Files\Microsoft SQL Server\110\Tools\Binn** or at **\<*drive*>:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="d824c-197">Vous pouvez exécuter l'utilitaire à partir de n'importe quel dossier de votre système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d824c-197">You can run the utility from any folder on your file system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d824c-198">Notes</span><span class="sxs-lookup"><span data-stu-id="d824c-198">Remarks</span></span>  
 <span data-ttu-id="d824c-199">Un serveur de rapports chiffre les informations d'identification et les informations de connexion stockées.</span><span class="sxs-lookup"><span data-stu-id="d824c-199">A report server encrypts stored credentials and connection information.</span></span> <span data-ttu-id="d824c-200">Une clé publique et une clé symétrique sont utilisées pour chiffrer les données.</span><span class="sxs-lookup"><span data-stu-id="d824c-200">A public key and a symmetric key are used to encrypt data.</span></span> <span data-ttu-id="d824c-201">La base de données d'un serveur de rapports doit posséder les clés valides pour que le serveur de rapports puisse s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="d824c-201">A report server database must have valid keys in order for the report server to run.</span></span> <span data-ttu-id="d824c-202">Vous pouvez utiliser **rskeymgmt** pour sauvegarder, supprimer ou restaurer des clés.</span><span class="sxs-lookup"><span data-stu-id="d824c-202">You can use **rskeymgmt** to back up, delete, or restore the keys.</span></span> <span data-ttu-id="d824c-203">Si les clés ne peuvent pas être restaurées, cet outil permet de supprimer un contenu chiffré qui ne peut plus être utilisé.</span><span class="sxs-lookup"><span data-stu-id="d824c-203">If the keys cannot be restored, this tool provides a way to delete encrypted content that can no longer be used.</span></span>  
  
 <span data-ttu-id="d824c-204">L’utilitaire **rskeymgmt** sert à gérer l’ensemble des clés qui est défini durant l’installation ou l’initialisation.</span><span class="sxs-lookup"><span data-stu-id="d824c-204">The **rskeymgmt** utility is used to manage the key set that is defined during Setup or during initialization.</span></span> <span data-ttu-id="d824c-205">Il se connecte au service Windows Report Server par l'intermédiaire d'un point de terminaison de RPC (Remote Procedure Call).</span><span class="sxs-lookup"><span data-stu-id="d824c-205">It connects to the local Report Server Windows service through a Remote Procedure Call (RPC) endpoint.</span></span> <span data-ttu-id="d824c-206">Le service Windows Report Server doit être en cours d'exécution pour permettre le fonctionnement de cet utilitaire.</span><span class="sxs-lookup"><span data-stu-id="d824c-206">The Report Server Windows service must be running in order for this utility to work.</span></span>  
  
 <span data-ttu-id="d824c-207">Pour plus d’informations sur les clés de chiffrement, consultez [Configurer et gérer des clés de chiffrement &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) et [Initialiser un serveur de rapports &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="d824c-207">For more information about the encryption keys, see [Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) and [Initialize a Report Server &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d824c-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d824c-208">See Also</span></span>  
 <span data-ttu-id="d824c-209">[Configurer un déploiement avec montée en puissance parallèle de serveurs de rapports en mode natif &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="d824c-209">[Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span></span>  
 <span data-ttu-id="d824c-210">[Serveur de rapports Reporting Services &#40;mode natif&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="d824c-210">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="d824c-211">[Utilitaires de ligne de commande du serveur de rapports &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="d824c-211">[Report Server Command Prompt Utilities &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span></span>  
 [<span data-ttu-id="d824c-212">Configurer et gérer des clés de chiffrement &#40;Gestionnaire de configuration de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d824c-212">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  
