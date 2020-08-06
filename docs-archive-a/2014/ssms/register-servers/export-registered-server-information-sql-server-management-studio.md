---
title: Exporter des informations de serveur inscrit
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.exportregisteredservers.f1
helpviewer_keywords:
- Registered Servers [SQL Server], exporting
- exporting registered server information
- transferring registered server information
ms.assetid: b65e168f-b6bf-489c-b8ad-3b8644acf0b6
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 03092de2d722e8f8b807dbb3d23c4b4e2b91f6f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705843"
---
# <a name="export-registered-server-information-sql-server-management-studio"></a><span data-ttu-id="5b975-102">Exporter les informations des serveurs inscrits (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5b975-102">Export Registered Server Information (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5b975-103">Cette rubrique explique comment enregistrer et exporter les informations des serveurs inscrits dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]et les distribuer à d'autres employés ou serveurs.</span><span class="sxs-lookup"><span data-stu-id="5b975-103">This topic describes how to save and export registered server information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]and distribute it to other employees or servers.</span></span> <span data-ttu-id="5b975-104">Vous pouvez utiliser cette fonction d'exportation pour présenter une interface utilisateur cohérente sur plusieurs ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="5b975-104">You can use this export feature to present a consistent user interface on multiple computers.</span></span>  
  
 <span data-ttu-id="5b975-105">Si vous exportez puis importez les fichiers de serveurs inscrits, vous pouvez configurer facilement plusieurs ordinateurs en leur affectant les mêmes serveurs dans Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5b975-105">Exporting and then importing Registered Server files lets you easily configure several computers with the same servers in Registered Servers.</span></span> <span data-ttu-id="5b975-106">Ceci peut être utile si vous gérez un grand nombre de serveurs à partir d'ordinateurs situés à différents endroits ou si vous voulez configurer des paramètres de connexion de base pour un utilisateur moins expérimenté.</span><span class="sxs-lookup"><span data-stu-id="5b975-106">This is useful when managing a large number of servers from computers in several locations, or when you want to configure a less experienced user with basic connection settings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b975-107">Les inscriptions de serveurs qui utilisent l’authentification SQL Server stockent les mots de passe par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5b975-107">Server registrations that use SQL Server Authentication store passwords on a per-user basis.</span></span> <span data-ttu-id="5b975-108">Après avoir exporté et importé les inscriptions de serveurs, les utilisateurs doivent entrer le mot de passe pour chaque serveur la première fois qu'ils se connectent et stocker leurs mots de passe dans les listes de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5b975-108">After exporting and importing the server registrations, users must enter the password for each server the first time they connect, storing the passwords in their lists of registered servers.</span></span> <span data-ttu-id="5b975-109">Par contre, ce n'est pas nécessaire pour les serveurs inscrits à l'aide de l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="5b975-109">This is not necessary for servers registered using Windows Authentication.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-export-registered-server-information"></a><span data-ttu-id="5b975-110">Pour exporter les informations des serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="5b975-110">To export registered server information</span></span>  
  
1.  <span data-ttu-id="5b975-111">Dans Serveurs inscrits, cliquez avec le bouton droit de la souris sur un groupe de serveurs, puis cliquez sur **Exporter**.</span><span class="sxs-lookup"><span data-stu-id="5b975-111">In Registered Servers, right-click a server group, and then click **Export**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5b975-112">Vous pouvez exporter un serveur individuel, toute l'arborescence des serveurs inscrits ou un sous-ensemble de l'arborescence des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5b975-112">You can export an individual server, all of the registered server tree, or a subset of the registered server tree.</span></span>  
  
2.  <span data-ttu-id="5b975-113">Dans la boîte de dialogue **Exporter les serveurs inscrits** , effectuez les sélections suivantes.</span><span class="sxs-lookup"><span data-stu-id="5b975-113">In the **Export Registered Servers** dialog box, make the following selections.</span></span>  
  
     <span data-ttu-id="5b975-114">**Groupe de serveurs**</span><span class="sxs-lookup"><span data-stu-id="5b975-114">**Server group**</span></span>  
     <span data-ttu-id="5b975-115">Spécifiez le groupe de serveurs à exporter.</span><span class="sxs-lookup"><span data-stu-id="5b975-115">Specify the server group which will be exported.</span></span> <span data-ttu-id="5b975-116">Vous pouvez exporter dans le fichier d'exportation tous les serveurs inscrits, les serveurs inscrits d'un groupe de serveurs donné ou un seul serveur inscrit.</span><span class="sxs-lookup"><span data-stu-id="5b975-116">Export all registered servers, registered servers in a particular server group, or a single registered server to the export file.</span></span> <span data-ttu-id="5b975-117">La fonctionnalité d'exportation est récursive : par exemple, si le groupe de serveurs A contient le groupe de serveurs B et que le groupe de serveurs B contient les groupes de serveurs C et D, en exportant le groupe de serveurs A vous exportez tous les enregistrements des groupes de serveurs A, B, C et D.</span><span class="sxs-lookup"><span data-stu-id="5b975-117">The export functionality is recursive; for example, if server group A contains server group B, and server group B contains server groups C and D, exporting server group A exports all entries in A, B, C, and D.</span></span>  
  
     <span data-ttu-id="5b975-118">Le groupe de serveurs affiche uniquement les groupes de serveurs de l'arborescence actuelle de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5b975-118">The server group displays only the server groups of the current registered server tree.</span></span>  
  
     <span data-ttu-id="5b975-119">**Fichier d'exportation**</span><span class="sxs-lookup"><span data-stu-id="5b975-119">**Export file**</span></span>  
     <span data-ttu-id="5b975-120">Tapez le nom du fichier d’exportation dans la zone de texte ou utilisez le bouton Parcourir ( **...** ) pour rechercher un fichier d’exportation sur l’ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="5b975-120">Type the name of the export file in the text box or use the Browse button (**...**) to locate an export file on the client computer.</span></span> <span data-ttu-id="5b975-121">Si vous sélectionnez un fichier existant, les informations de serveur inscrit sont ajoutées au fichier.</span><span class="sxs-lookup"><span data-stu-id="5b975-121">If you select an existing file, the registered server information is appended to the file.</span></span> <span data-ttu-id="5b975-122">Utilisez l'extension .regsrvr.</span><span class="sxs-lookup"><span data-stu-id="5b975-122">Use the .regsrvr extension.</span></span> <span data-ttu-id="5b975-123">Pour rendre les informations de serveurs inscrits accessibles à d'autres utilisateurs ou un autre ordinateur, vous pouvez enregistrer le fichier sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="5b975-123">If you want your registered server information to be available to other users or another computer, you can save the file on the network.</span></span> <span data-ttu-id="5b975-124">Les autres utilisateurs peuvent accéder au fichier et importer l'ensemble ou une partie des informations de serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="5b975-124">Other users can access the file and import part or all of the registered server information.</span></span> <span data-ttu-id="5b975-125">Si vous sélectionnez un fichier d'exportation existant, le contenu du fichier est remplacé par les informations d'inscription des serveurs.</span><span class="sxs-lookup"><span data-stu-id="5b975-125">If you select an existing file as your export file, the contents of the file are overwritten with the server registration information.</span></span>  
  
     <span data-ttu-id="5b975-126">**Ne pas inclure les noms d'utilisateur ni les mots de passe dans le fichier d'exportation**</span><span class="sxs-lookup"><span data-stu-id="5b975-126">**Do not include user names and passwords in the export file**</span></span>  
     <span data-ttu-id="5b975-127">Exclut les noms d'utilisateur lors de l'exportation du fichier.</span><span class="sxs-lookup"><span data-stu-id="5b975-127">Exclude user names when exporting the file.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5b975-128">Bien que les fichiers d'exportation soient chiffrés, si les noms d'utilisateur et les mots de passe d'authentification SQL Server sont inclus dans le fichier, l'accès à ce fichier doit être soigneusement contrôlé.</span><span class="sxs-lookup"><span data-stu-id="5b975-128">Although the export files are encrypted, if user names and SQL Server Authentication passwords are included in the file, access to the file should be carefully controlled.</span></span> <span data-ttu-id="5b975-129">Les noms d'utilisateur et les mots de passe sont par conséquent exclus par défaut du fichier d'exportation.</span><span class="sxs-lookup"><span data-stu-id="5b975-129">User names and passwords are therefore excluded from the export file by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b975-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b975-130">See Also</span></span>  
 <span data-ttu-id="5b975-131">[Importez les informations de serveur inscrit &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [créer un serveur inscrit &#40;SQL Server Management Studio](create-a-new-registered-server-sql-server-management-studio.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="5b975-131">[Import Registered Server Information &#40;SQL Server Management Studio&#41;](import-registered-server-information-sql-server-management-studio.md) [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md)</span></span>  
  
  
