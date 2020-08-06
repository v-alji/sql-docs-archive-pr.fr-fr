---
title: Serveur de publication Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600800"
---
# <a name="oracle-publisher"></a><span data-ttu-id="a79a1-102">Serveur de publication Oracle</span><span class="sxs-lookup"><span data-stu-id="a79a1-102">Oracle Publisher</span></span>
  <span data-ttu-id="a79a1-103">Depuis [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vous permet de publier des données à partir d’une base de données Oracle à l’aide de la réplication transactionnelle et d’instantané.</span><span class="sxs-lookup"><span data-stu-id="a79a1-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="a79a1-104">Pour plus d’informations, consultez [Présentation de la publication Oracle](non-sql/oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a79a1-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="a79a1-105">Le serveur de publication Oracle doit utiliser un serveur de distribution distant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; cet Assistant doit être exécuté sur ce serveur après l'installation et le test du logiciel réseau Oracle nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a79a1-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="a79a1-106">Pour plus d’informations, consultez [Configurer un serveur de publication Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="a79a1-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a79a1-107">Si un autre administrateur a configuré la base de données Oracle en tant que serveur de publication, après avoir cliqué sur **Suivant** , le système vous demande d'entrer le mot de passe de la connexion de réplication utilisée en vue de vous connecter à la base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="a79a1-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a79a1-108">crée ensuite un mappage entre votre nom d'accès et la connexion de serveur liée à la base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="a79a1-108">will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="a79a1-109">Vous ne devez pas entrer un mot de passe pour les connexions ultérieures à la base de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="a79a1-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a79a1-110">Options</span><span class="sxs-lookup"><span data-stu-id="a79a1-110">Options</span></span>  
 <span data-ttu-id="a79a1-111">**Serveurs de publication Oracle**</span><span class="sxs-lookup"><span data-stu-id="a79a1-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="a79a1-112">Sélectionnez un serveur de publication Oracle dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a79a1-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="a79a1-113">Cette liste contient les serveurs de publication Oracle, qui ont été configurés au préalable pour utiliser le serveur, sur lequel s'exécute l'Assistant en tant que serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="a79a1-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="a79a1-114">Si la liste est vide ou si le serveur de publication Oracle souhaité n'y figure pas, cliquez sur **Ajouter un serveur de publication Oracle**.</span><span class="sxs-lookup"><span data-stu-id="a79a1-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="a79a1-115">**Ajouter un serveur de publication Oracle**</span><span class="sxs-lookup"><span data-stu-id="a79a1-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="a79a1-116">Cliquez sur ce bouton pour ouvrir la boîte de dialogue **Propriétés du serveur de distribution** .</span><span class="sxs-lookup"><span data-stu-id="a79a1-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="a79a1-117">Dans cette la boîte de dialogue, cliquez sur **Ajouter**, puis sur **Ajouter un serveur de publication Oracle**.</span><span class="sxs-lookup"><span data-stu-id="a79a1-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="a79a1-118">Dans la boîte de dialogue **Se connecter au serveur** , spécifiez le nom du serveur Oracle ainsi que le nom de connexion et le mot de passe destinés au schéma de l'administrateur de réplication.</span><span class="sxs-lookup"><span data-stu-id="a79a1-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="a79a1-119">Pour plus d’informations, consultez [Se connecter au serveur &#40;Oracle&#41;, Connexion](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="a79a1-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a79a1-120">Si le serveur, sur lequel s'exécute l'Assistant, n'a pas été configuré en tant que serveur de distribution, le système vous demande alors de le faire.</span><span class="sxs-lookup"><span data-stu-id="a79a1-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79a1-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a79a1-121">See Also</span></span>  
 [<span data-ttu-id="a79a1-122">Créer une publication à partir d’une base de données Oracle</span><span class="sxs-lookup"><span data-stu-id="a79a1-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
