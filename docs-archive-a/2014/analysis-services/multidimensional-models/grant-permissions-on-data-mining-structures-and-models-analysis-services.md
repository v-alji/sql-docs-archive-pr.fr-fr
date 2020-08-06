---
title: Accorder des autorisations sur les modèles et les structures d’exploration de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.miningmodels.f1
helpviewer_keywords:
- data mining [Analysis Services], security
- permissions [Analysis Services], mining models
- mining models [Analysis Services], security
- mining structures [Analysis Services], security
- permissions [Analysis Services], mining structures
- user access rights [Analysis Services], mining structures
- user access rights [Analysis Services], mining models
ms.assetid: a0008004-e2b7-47db-acad-5fe7e12b130f
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0db849551bdb38615f280b123c98f0e9d3053d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703340"
---
# <a name="grant-permissions-on-data-mining-structures-and-models-analysis-services"></a><span data-ttu-id="5e3ea-102">Octroyer des autorisations sur des modèles et des structures d'exploration de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5e3ea-102">Grant permissions on data mining structures and models (Analysis Services)</span></span>
  <span data-ttu-id="5e3ea-103">Par défaut, seul un administrateur de serveur Analysis Services est autorisé à afficher des structures ou des modèles d'exploration de données dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-103">By default, only an Analysis Services server administrator has permissions to view data mining structures or mining models in the database.</span></span> <span data-ttu-id="5e3ea-104">Suivez les instructions ci-dessous pour accorder des autorisations à des utilisateurs non-administrateurs.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-104">Follow the instructions below to grant permissions to non-administrator users.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-structure"></a><span data-ttu-id="5e3ea-105">Définir des autorisations d'accès à une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e3ea-105">Set permissions to access a mining structure</span></span>  
  
1.  <span data-ttu-id="5e3ea-106">Dans SSMS, connectez-vous à Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-106">In SSMS, connect to Analysis Services.</span></span> <span data-ttu-id="5e3ea-107">Si vous avez besoin d’aide pour ces étapes, consultez [Connexion à partir d’applications clientes &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e3ea-107">See [Connect from client applications &#40;Analysis Services&#41;](../instances/connect-from-client-applications-analysis-services.md) if you need help with the steps.</span></span>  
  
2.  <span data-ttu-id="5e3ea-108">Ouvrez le dossier **Bases de données** et sélectionnez une base de données dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-108">Open the **Databases** folder, and select a database in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="5e3ea-109">Cliquez avec le bouton droit sur le dossier **Rôles** et choisissez **Nouveau rôle**.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-109">Right-click **Roles** and choose **New Role**.</span></span>  
  
4.  <span data-ttu-id="5e3ea-110">Dans la page Général, entrez un nom et éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-110">In the General page, enter a name, and optionally, a description.</span></span> <span data-ttu-id="5e3ea-111">La page contient également plusieurs autorisations de base de données, telles que Contrôle total, Traiter la base de données et Lire la définition.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-111">The page also contains several database permissions, such as Full Control, Process Database, and Read Definition.</span></span> <span data-ttu-id="5e3ea-112">Aucune de ces autorisations n'est nécessaire pour l'accès à l'exploration des données.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-112">None of these permissions are needed for data mining access.</span></span> <span data-ttu-id="5e3ea-113">Pour plus d’informations sur les autorisations de base de données, consultez [Octroyer des autorisations de base de données &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5e3ea-113">See [Grant database permissions &#40;Analysis Services&#41;](grant-database-permissions-analysis-services.md) for more information about database permissions.</span></span>  
  
5.  <span data-ttu-id="5e3ea-114">Dans le volet **Structure d’exploration de données** , sélectionnez **Lecture** ou **Lecture/Écriture**  pour chaque structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-114">In the **Mining Structure** pane, select **Read** or **Read/Write**  for each data mining structure.</span></span>  
  
6.  <span data-ttu-id="5e3ea-115">Dans le volet **Appartenance** , entrez les comptes d'utilisateurs et de groupes Windows qui se connectent à Analysis Services à l'aide de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-115">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
7.  <span data-ttu-id="5e3ea-116">Cliquez sur **OK** pour terminer la création du rôle.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-116">Click **OK** to finish creating the role.</span></span>  
  
## <a name="set-permissions-to-access-a-mining-model"></a><span data-ttu-id="5e3ea-117">Définir des autorisations d'accès à un modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="5e3ea-117">Set permissions to access a mining model</span></span>  
 <span data-ttu-id="5e3ea-118">Pour un modèle d’exploration de données, un rôle peut avoir des autorisations **Lecture** ou **Lecture/Écriture** , ainsi que des autorisations **Extraction** et **Lire la définition** qui autorisent l’affichage et le parcours des données sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-118">For a data mining model, a role can have either **Read** or **Read/Write** permissions, as well as **Drillthrough** and **Read Definition** permissions that allow viewing and browsing the underlying data.</span></span>  
  
 <span data-ttu-id="5e3ea-119">**Remarque** Si vous activez l'extraction à la fois sur la structure d'exploration de données et le modèle d'exploration de données, tout utilisateur membre d'un rôle qui a des autorisations d'extraction sur le modèle d'exploration de données et la structure d'exploration de données peut également afficher les colonnes de la structure d'exploration de données, même si ces colonnes ne sont pas incluses dans le modèle d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-119">**Note** If you enable drillthrough on both the mining structure and the mining model, any user who is a member of a role that has drillthrough permissions on the mining model and the mining structure can also view columns in the mining structure, even if those columns are not included in the mining model.</span></span> <span data-ttu-id="5e3ea-120">Par conséquent, vous devez installer la vue de source de données pour masquer des informations personnelles afin de protéger les informations sensibles, et autoriser uniquement l'accès d'extraction sur la structure d'exploration de données lorsque nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-120">Therefore, to protect sensitive information, you should set up the data source view to mask personal information, and allow drillthrough access on the mining structure only when necessary.</span></span>  
  
 <span data-ttu-id="5e3ea-121">Pour accorder des autorisations de lecture ou de lecture/écriture à un rôle de base de données, un utilisateur doit être membre du rôle de serveur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou d'un rôle de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ayant les autorisations Contrôle total (Administrateur).</span><span class="sxs-lookup"><span data-stu-id="5e3ea-121">To grant read or read/write permissions to a database role, a user must be a member of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server role or a member of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database role that has Full Control (Administrator) permissions.</span></span>  
  
1.  <span data-ttu-id="5e3ea-122">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , connectez-vous à l’instance de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , développez **rôles** pour la base de données appropriée dans l’Explorateur d’objets, puis cliquez sur un rôle de base de données (ou créez un rôle de base de données).</span><span class="sxs-lookup"><span data-stu-id="5e3ea-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object Explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="5e3ea-123">Dans le volet **Structure d’exploration de données** , recherchez le modèle d’exploration de données dans la liste **Modèles d’exploration de données** , puis sélectionnez **Lecture**, **Lecture/Écriture**, **Extraire**ou **Parcourir** .</span><span class="sxs-lookup"><span data-stu-id="5e3ea-123">In the **Mining Structure** pane, locate the mining model in the **Mining Models** list, and then select **Read**, **Read/Write**, **Drill Through**, or **Browse** for that mining model.</span></span>  
  
3.  <span data-ttu-id="5e3ea-124">Dans le volet **Appartenance** , entrez les comptes d'utilisateurs et de groupes Windows qui se connectent à Analysis Services à l'aide de ce rôle.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-124">In the **Membership** pane, enter the Windows user and group accounts that connect to Analysis Services using this role.</span></span>  
  
4.  <span data-ttu-id="5e3ea-125">Cliquez sur **OK** pour terminer la création du rôle.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-125">Click **OK** to finish creating the role.</span></span>  
  
 <span data-ttu-id="5e3ea-126">Pour utiliser une source de données dans une requête d’extraction qui utilise la clause DMX (Data Mining Extensions) OPENQUERY, le rôle de base de données doit également disposer d’une autorisation de lecture/écriture sur l’objet de source de données approprié.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-126">To use a data source in a drillthrough query that uses the Data Mining Extensions (DMX) OPENQUERY clause, the database role also needs read/write permission on the appropriate data source object.</span></span> <span data-ttu-id="5e3ea-127">Pour plus d’informations, consultez [Octroyer des autorisations sur un objet de source de données &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) et [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span><span class="sxs-lookup"><span data-stu-id="5e3ea-127">For more information, see [Grant permissions on a data source object &#40;Analysis Services&#41;](grant-permissions-on-a-data-source-object-analysis-services.md) and [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e3ea-128">Par défaut, la soumission de requêtes DMX à l’aide d’OPENROWSET est désactivée.</span><span class="sxs-lookup"><span data-stu-id="5e3ea-128">By default, the submission of DMX queries by using OPENROWSET is disabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3ea-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e3ea-129">See Also</span></span>  
 <span data-ttu-id="5e3ea-130">[Accorder des autorisations d’administrateur de serveur &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="5e3ea-130">[Grant Server Administrator Permissions &#40;Analysis Services&#41;](../instances/grant-server-admin-rights-to-an-analysis-services-instance.md) </span></span>  
 <span data-ttu-id="5e3ea-131">[Octroi d’autorisations de cube ou de modèle &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="5e3ea-131">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 <span data-ttu-id="5e3ea-132">[Accorder un accès personnalisé à des données de dimension &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="5e3ea-132">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 [<span data-ttu-id="5e3ea-133">Octroyer un accès personnalisé à des données de cellule &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5e3ea-133">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  
