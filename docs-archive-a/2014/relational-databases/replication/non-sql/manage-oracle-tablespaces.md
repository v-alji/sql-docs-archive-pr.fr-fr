---
title: Gérer des espaces disque logiques Oracle
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Oracle publishing [SQL Server replication], managing tablespaces
- tablespaces [SQL Server replication]
ms.assetid: b8ea6c3b-01d6-4efc-bbfb-03b264530bbd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3624aed38a7a5bf75e0c0807aa8d3657156264f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702756"
---
# <a name="manage-oracle-tablespaces"></a><span data-ttu-id="da3d9-102">Gérer des espaces disque logiques Oracle</span><span class="sxs-lookup"><span data-stu-id="da3d9-102">Manage Oracle Tablespaces</span></span>
  <span data-ttu-id="da3d9-103">Un espace disque logique est une unité de stockage de base de données qui est à peu près équivalent à un groupe de fichiers dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da3d9-103">A tablespace is a unit of database storage that is roughly equivalent to a file group in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da3d9-104">Les espaces disque logiques permettent le stockage et la gestion d'objets de base de données au sein de groupes individuels.</span><span class="sxs-lookup"><span data-stu-id="da3d9-104">Tablespaces allow storage and management of database objects within individual groups.</span></span> <span data-ttu-id="da3d9-105">Pour plus d'informations, consultez votre documentation Oracle.</span><span class="sxs-lookup"><span data-stu-id="da3d9-105">For more information, see the Oracle documentation.</span></span>  
  
 <span data-ttu-id="da3d9-106">Quand vous configurez une table comme composant d'une publication Oracle, vous pouvez spécifier en option un espace disque logique Oracle existant à utiliser lors du stockage d'informations de journalisation de la réplication.</span><span class="sxs-lookup"><span data-stu-id="da3d9-106">When you configure a table as part of an Oracle publication, you can optionally specify an existing Oracle tablespace to be used when storing replication logging information.</span></span> <span data-ttu-id="da3d9-107">S'il n'est pas spécifié, l'espace disque logique pour les objets de réplication est l'espace disque logique associé au schéma utilisateur d'administration de réplication qui a été configuré lors de la configuration du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="da3d9-107">If unspecified, the tablespace for the replication objects is the default tablespace associated with the replication administrative user schema that was configured when configuring the Publisher.</span></span>  
  
 <span data-ttu-id="da3d9-108">**Pour spécifier un espace disque logique pour une table de journalisation d'articles**:</span><span class="sxs-lookup"><span data-stu-id="da3d9-108">**To specify a tablespace for an article logging table**:</span></span>  
  
-   <span data-ttu-id="da3d9-109">Spécifiez un espace disque logique dans la boîte de dialogue **Propriétés de l'article** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-109">Specify a tablespace in the **Article Properties** dialog box.</span></span> <span data-ttu-id="da3d9-110">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Afficher et modifier les propriétés d’un serveur de publication](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="da3d9-110">For more information about accessing this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="da3d9-111">Utilisez [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="da3d9-111">Use [sp_changearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql).</span></span> <span data-ttu-id="da3d9-112">Pour utiliser **sp_changearticle**, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="da3d9-112">To use **sp_changearticle**, specify the following:</span></span>  
  
    -   <span data-ttu-id="da3d9-113">Nom du serveur de publication Oracle pour le paramètre **@publisher** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-113">The name of the Oracle Publisher for the parameter **@publisher**.</span></span>  
  
    -   <span data-ttu-id="da3d9-114">Nom de la publication Oracle pour le paramètre **@publication** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-114">The name of the Oracle publication for the parameter **@publication**.</span></span>  
  
    -   <span data-ttu-id="da3d9-115">Nom de l’article pour le paramètre **@article** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-115">The name of the article for the parameter **@article**.</span></span>  
  
    -   <span data-ttu-id="da3d9-116">Valeur de « tablespace » pour le paramètre **@property** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-116">A value of 'tablespace' for the parameter **@property**.</span></span>  
  
    -   <span data-ttu-id="da3d9-117">Nom de l’espace disque logique pour le paramètre **@value** .</span><span class="sxs-lookup"><span data-stu-id="da3d9-117">The name of the tablespace for the parameter **@value**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da3d9-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da3d9-118">See Also</span></span>  
 <span data-ttu-id="da3d9-119">[Configurer un serveur de publication Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="da3d9-119">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="da3d9-120">Objects Created on the Oracle Publisher</span><span class="sxs-lookup"><span data-stu-id="da3d9-120">Objects Created on the Oracle Publisher</span></span>](objects-created-on-the-oracle-publisher.md)  
  
  
