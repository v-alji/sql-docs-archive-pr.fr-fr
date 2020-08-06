---
title: Importer des informations de serveur inscrit
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.importregisteredservers.f1
helpviewer_keywords:
- transferring registered server information
- Registered Servers [SQL Server], importing
- importing registered server information
ms.assetid: cc497a14-1360-4887-b70c-002f042823b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f2eddb3b83f73253e977316767f2b930bc8ab9ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705844"
---
# <a name="import-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="dd09c-102">Importer des informations de serveur inscrit (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="dd09c-102">Import Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="dd09c-103">Cette rubrique explique comment importer les informations du serveur inscrit enregistrées dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd09c-103">This topic describes how to import saved registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dd09c-104">L'exportation puis l'importation de fichiers de serveurs inscrits vous permet de configurer aisément plusieurs ordinateurs avec les mêmes serveurs dans Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="dd09c-104">Exporting and then importing registered server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="dd09c-105">Cela est utile lors de la gestion d'un grand nombre de serveurs à partir d'ordinateurs situés à des emplacements différents ou lorsque vous voulez configurer des paramètres de connexion de base pour un utilisateur peu expérimenté.</span><span class="sxs-lookup"><span data-stu-id="dd09c-105">This is useful when managing a large number of servers from computers in several locations, or when you want to configure basic connection settings for a less-experienced user.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd09c-106">Vous ne pouvez pas importer d'informations sur les serveurs inscrits dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à partir des versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd09c-106">You cannot import registered server information into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] from earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-import-registered-server-information"></a><span data-ttu-id="dd09c-107">Pour importer des informations de serveur inscrit</span><span class="sxs-lookup"><span data-stu-id="dd09c-107">To import registered server information</span></span>  
  
1.  <span data-ttu-id="dd09c-108">Dans Serveurs inscrits, cliquez sur le type de serveur dans la barre d'outils Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="dd09c-108">In Registered Servers, click the server type on the Registered Servers toolbar.</span></span> <span data-ttu-id="dd09c-109">Le type de serveur doit être identique au type de fichier d'exportation du serveur inscrit.</span><span class="sxs-lookup"><span data-stu-id="dd09c-109">The server type must be the same as the registered server export file type.</span></span> <span data-ttu-id="dd09c-110">Si, par exemple, vous avez exporté des informations de serveur inscrit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez cliquer sur **SQL Server** dans la barre d'outils Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="dd09c-110">For example, if you have exported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registered server information, you must click **SQL Server** on the Registered Servers toolbar.</span></span>  
  
2.  <span data-ttu-id="dd09c-111">Cliquez avec le bouton droit sur un groupe de serveurs, puis sélectionnez **Importer**.</span><span class="sxs-lookup"><span data-stu-id="dd09c-111">Right-click a server group, and select **Import**.</span></span>  
  
3.  <span data-ttu-id="dd09c-112">Dans la boîte de dialogue **Importer des serveurs inscrits** , sélectionnez le fichier de serveurs inscrits à importer, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd09c-112">In the **Import Registered Servers** dialog box, select the registered servers file to import, and then click **OK**.</span></span>  
  
     <span data-ttu-id="dd09c-113">**Fichier d'importation**</span><span class="sxs-lookup"><span data-stu-id="dd09c-113">**Import file**</span></span>  
     <span data-ttu-id="dd09c-114">Tapez le nom du fichier d’importation dans la zone de texte ou cliquez sur le bouton Parcourir ( **...** ) pour rechercher le fichier d’importation sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="dd09c-114">Type the name of the import file in the text box, or click the Browse button (**...**) to locate the import file on the client computer.</span></span> <span data-ttu-id="dd09c-115">Si vous sélectionnez un fichier existant, les informations de serveur inscrit sont ajoutées au fichier.</span><span class="sxs-lookup"><span data-stu-id="dd09c-115">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="dd09c-116">Le fichier d'importation peut être uniquement un fichier de serveur inscrit précédemment exporté.</span><span class="sxs-lookup"><span data-stu-id="dd09c-116">The import file can only be a previously exported registered server file.</span></span> <span data-ttu-id="dd09c-117">Les fichiers de serveur inscrit ont l'extension .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="dd09c-117">Registered server files have a .regsrvr extension.</span></span>  
  
     <span data-ttu-id="dd09c-118">**Sélectionnez le groupe de serveurs vers lequel importer**</span><span class="sxs-lookup"><span data-stu-id="dd09c-118">**Select the server group to import to**</span></span>  
     <span data-ttu-id="dd09c-119">Sélectionnez le nœud racine ou un groupe de serveurs particulier vers lequel seront importées les entrées de serveur inscrit dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="dd09c-119">Select the root node or a particular server group to which the registered server entries in the file will be imported.</span></span> <span data-ttu-id="dd09c-120">Vous pouvez importer dans le fichier d'exportation tous les serveurs inscrits, les serveurs inscrits d'un groupe de serveurs particulier ou un serveur inscrit individuel.</span><span class="sxs-lookup"><span data-stu-id="dd09c-120">You can import all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="dd09c-121">La fonctionnalité d'importation est récursive ; par exemple, si le groupe de serveurs A contient le groupe de serveurs B, et que le groupe de serveurs B contient les groupes de serveurs C et D, l'importation du groupe de serveur A entraîne l'exportation de toutes les entrées de A, B, C et D.</span><span class="sxs-lookup"><span data-stu-id="dd09c-121">The import functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, importing server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="dd09c-122">Le groupe de serveurs affiche uniquement les groupes de serveurs de l'arborescence actuelle de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="dd09c-122">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="dd09c-123">Si vous choisissez d'importer un serveur ou un groupe de serveurs existant, un message confirme que vous voulez remplacer le serveur ou le groupe de serveurs existant.</span><span class="sxs-lookup"><span data-stu-id="dd09c-123">If you select to import an existing server group or server, a message confirms that you want to overwrite the existing server or server group.</span></span>  
  
 <span data-ttu-id="dd09c-124">Les inscriptions de serveurs qui utilisent l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stockent les mots de passe par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="dd09c-124">Server registrations that use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="dd09c-125">Après l'importation des inscriptions de serveurs, les utilisateurs doivent entrer le mot de passe pour chaque serveur la première fois qu'ils se connectent et stocker les mots de passe dans leurs listes de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="dd09c-125">After importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="dd09c-126">Cela n'est pas nécessaire pour les serveurs inscrits via l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="dd09c-126">This is not necessary for servers registered through Windows Authentication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd09c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd09c-127">See Also</span></span>  
 <span data-ttu-id="dd09c-128">[Modifier l’inscription d’un serveur &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Exporter les informations du serveur inscrit &#40;SQL Server Management Studio](export-registered-server-information-sql-server-management-studio.md)&#41; </span><span class="sxs-lookup"><span data-stu-id="dd09c-128">[Change a Server's Registration &#40;SQL Server Management Studio&#41;](change-a-server-s-registration-sql-server-management-studio.md) [Export Registered Server Information &#40;SQL Server Management Studio&#41;](export-registered-server-information-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="dd09c-129">Créer un nouveau serveur inscrit &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="dd09c-129">Create a New Registered Server &#40;SQL Server Management Studio&#41;</span></span>](create-a-new-registered-server-sql-server-management-studio.md)  
  
  
