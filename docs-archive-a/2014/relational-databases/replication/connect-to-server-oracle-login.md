---
title: Se connecter au serveur (Oracle), Connexion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600822"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="20a72-102">Se connecter au serveur (Oracle), Connexion</span><span class="sxs-lookup"><span data-stu-id="20a72-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="20a72-103">Utilisez l’onglet **Connexion** de la boîte de dialogue **Se connecter au serveur** pour définir le compte sous lequel les connexions sont effectuées du serveur de distribution [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vers le serveur de publication Oracle.</span><span class="sxs-lookup"><span data-stu-id="20a72-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="20a72-104">Vous devez utiliser le compte défini pour le schéma utilisateur d'administration de réplication au cours de la configuration du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="20a72-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="20a72-105">Pour plus d’informations, consultez [Configurer un serveur de publication Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="20a72-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="20a72-106">Options</span><span class="sxs-lookup"><span data-stu-id="20a72-106">Options</span></span>  
 <span data-ttu-id="20a72-107">**Instance de serveur**</span><span class="sxs-lookup"><span data-stu-id="20a72-107">**Server instance**</span></span>  
 <span data-ttu-id="20a72-108">Nom TNS (Transparent Network Substrate) du serveur de publication Oracle, défini au cours de la configuration du logiciel client Oracle installé sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="20a72-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="20a72-109">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="20a72-109">**Authentication**</span></span>  
 <span data-ttu-id="20a72-110">Sélectionnez **Authentification standard Oracle** (recommandé) ou **Authentification Windows**.</span><span class="sxs-lookup"><span data-stu-id="20a72-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="20a72-111">Si vous sélectionnez **Authentification Windows**:</span><span class="sxs-lookup"><span data-stu-id="20a72-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="20a72-112">Le serveur Oracle doit être configuré pour permettre les connexions en utilisant les informations d'identification Windows.</span><span class="sxs-lookup"><span data-stu-id="20a72-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="20a72-113">Pour plus d'informations, consultez votre documentation Oracle.</span><span class="sxs-lookup"><span data-stu-id="20a72-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="20a72-114">Vous devez être connecté avec le compte [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows que vous avez défini pour le schéma utilisateur d'administration de réplication.</span><span class="sxs-lookup"><span data-stu-id="20a72-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="20a72-115">**Connexion** et **Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="20a72-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="20a72-116">Si vous avez sélectionné **Authentification standard Oracle** pour l'option d' **authentification** , définissez la connexion et le mot de passe à utiliser qui doivent être identiques à ceux du schéma utilisateur d'administration de réplication.</span><span class="sxs-lookup"><span data-stu-id="20a72-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a72-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20a72-117">See Also</span></span>  
 [<span data-ttu-id="20a72-118">Glossaire des termes de la publication Oracle</span><span class="sxs-lookup"><span data-stu-id="20a72-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
