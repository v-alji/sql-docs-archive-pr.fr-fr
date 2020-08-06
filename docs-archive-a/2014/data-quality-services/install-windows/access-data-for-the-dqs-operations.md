---
title: Accéder aux données pour les opérations DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 88dfb9ea-6321-4eaf-b9e4-45d36ef048f6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 515b087a8d16e44314d1a21d3dfbd6f13c767f5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701988"
---
# <a name="access-data-for-the-dqs-operations"></a><span data-ttu-id="58e79-102">Accéder aux données pour les opérations DQS</span><span class="sxs-lookup"><span data-stu-id="58e79-102">Access Data for the DQS Operations</span></span>
  <span data-ttu-id="58e79-103">Pour utiliser vos données sources pour les opérations [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS), et exporter vos données traitées, vous pouvez effectuer l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="58e79-103">To use your source data for [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS) operations, and export your processed data, you can do either of the following:</span></span>  
  
-   <span data-ttu-id="58e79-104">Copiez vos données sources dans une table/vue dans la base de données DQS_STAGING_DATA, puis utilisez-les pour les opérations DQS.</span><span class="sxs-lookup"><span data-stu-id="58e79-104">Copy your source data to a table/view in the DQS_STAGING_DATA database, and then use it for DQS operations.</span></span> <span data-ttu-id="58e79-105">Vous pouvez également exporter les données traitées dans une nouvelle table de la base de données DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="58e79-105">You can also export the processed data to a new table in the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="58e79-106">Pour cela, votre compte d'utilisateur Windows doit être accordé l'accès en lecture/écriture à la base de données de DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="58e79-106">To do so, your Windows user account must be granted read/write access to the DQS_STAGING_DATA database.</span></span>  
  
-   <span data-ttu-id="58e79-107">Utilisez votre propre base de données comme données sources pour les opérations DQS, et destination pour exporter les données traitées.</span><span class="sxs-lookup"><span data-stu-id="58e79-107">Use your own database as the source data for the DQS operations, and destination for exporting the processed data.</span></span> <span data-ttu-id="58e79-108">Pour cela, vérifiez que votre base de données est dans la même instance SQL Server que les bases de données Data Quality Server.</span><span class="sxs-lookup"><span data-stu-id="58e79-108">To do so, ensure that your database is in the same SQL Server instance as the Data Quality Server databases.</span></span> <span data-ttu-id="58e79-109">Sinon, la base de données ne sera pas disponible dans Data Quality Client pour les opérations DQS.</span><span class="sxs-lookup"><span data-stu-id="58e79-109">Otherwise, the database will not be available in the Data Quality Client for DQS operations.</span></span> <span data-ttu-id="58e79-110">De plus, votre compte d'utilisateur Windows doit avoir accès à la base de données DQS_STAGING_DATA pour exporter les résultats correspondants, car ceux-ci sont exportés en deux phases : en premier lieu, les résultats de correspondance sont exportés vers des tables temporaires dans la base de données DQS_STAGING_DATA, puis déplacés vers la table de votre base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="58e79-110">Also, your Windows user account must be granted access on the DQS_STAGING_DATA database for exporting the matching results because matching results are exported in two phases: first, the matching results are exported to the temporary tables in the DQS_STAGING_DATA database, and then moved to the table in your destination database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58e79-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="58e79-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="58e79-112">Vous devez avoir terminé l'installation du [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] en exécutant le fichier DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="58e79-112">You must have completed the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="58e79-113">Pour plus d’informations, consultez [Exécuter DQSInstaller.exe pour terminer l’installation du serveur DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="58e79-113">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
-   <span data-ttu-id="58e79-114">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe approprié (tel que le securityadmin, le serveradmin, ou le sysadmin) dans l'instance du moteur de base de données à accorder/modifier l'accès à la connexion SQL sur les bases de données.</span><span class="sxs-lookup"><span data-stu-id="58e79-114">Your Windows user account must be a member of the appropriate fixed server role (such as securityadmin, serveradmin, or sysadmin) in the database engine instance to grant/modify access to SQL login on databases.</span></span>  
  
### <a name="to-grant-readwrite-access-to-a-user-on-the-dqs_staging_data-database"></a><span data-ttu-id="58e79-115">Pour accorder l'accès en lecture/écriture à un utilisateur sur la base de données DQS_STAGING_DATA</span><span class="sxs-lookup"><span data-stu-id="58e79-115">To grant read/write access to a User on the DQS_STAGING_DATA Database</span></span>  
  
1.  <span data-ttu-id="58e79-116">Démarrez Microsoft SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="58e79-116">Start Microsoft SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="58e79-117">Dans Microsoft SQL Server Management Studio, développez votre instance SQL Server, puis développez **Sécurité**et ensuite **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="58e79-117">In Microsoft SQL Server Management Studio, expand your SQL Server instance, and expand **Security**, and then expand **Logins**.</span></span>  
  
3.  <span data-ttu-id="58e79-118">Cliquez avec le bouton droit sur une connexion SQL, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="58e79-118">Right-click a SQL login, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="58e79-119">Dans la boîte de dialogue **Propriétés de la connexion** , cliquez sur la page de **Mappage de l'utilisateur** dans le volet gauche.</span><span class="sxs-lookup"><span data-stu-id="58e79-119">In the **Login Properties** dialog box, click the **User Mapping** page in the left pane.</span></span>  
  
5.  <span data-ttu-id="58e79-120">Dans le volet droit, cochez la case sous la colonne **Mappage** de la base de données **DQS_STAGING_DATA** , puis sélectionnez les rôles suivants dans le volet **Appartenance au rôle de base de données : DQS_STAGING_DATA** :</span><span class="sxs-lookup"><span data-stu-id="58e79-120">In the right pane, select the check box under the **Map** column for the **DQS_STAGING_DATA** database, and then select the following roles in the **Database role membership for: DQS_STAGING_DATA** pane:</span></span>  
  
    -   <span data-ttu-id="58e79-121">**db_datareader**: lire des données depuis des tables/vues.</span><span class="sxs-lookup"><span data-stu-id="58e79-121">**db_datareader**: Read data from tables/views.</span></span>  
  
    -   <span data-ttu-id="58e79-122">**db_datawriter**: ajouter, supprimer ou modifier des données dans des tables.</span><span class="sxs-lookup"><span data-stu-id="58e79-122">**db_datawriter**: Add, delete, or change data in tables.</span></span>  
  
    -   <span data-ttu-id="58e79-123">**db_ddladmin**: créer, modifier ou supprimer des tables/vues.</span><span class="sxs-lookup"><span data-stu-id="58e79-123">**db_ddladmin**: Create, modify, or delete tables/views.</span></span>  
  
6.  <span data-ttu-id="58e79-124">Dans la boîte de dialogue **Propriétés de la connexion** , cliquez sur **OK** pour appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="58e79-124">In the **Login Properties** dialog box, click **OK** to apply the changes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="58e79-125">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="58e79-125">Next Steps</span></span>  
 <span data-ttu-id="58e79-126">Essayez effectuer des opérations DQS qui accèdent à la base de données en tant que source de données pour l'opération DQS, puis exportez les données traitées vers la base de données.</span><span class="sxs-lookup"><span data-stu-id="58e79-126">Try performing DQS operations that accesses the database as data source for DQS operation, and then exports the processed data to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e79-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58e79-127">See Also</span></span>  
 [<span data-ttu-id="58e79-128">Installer Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="58e79-128">Install Data Quality Services</span></span>](install-data-quality-services.md)  
  
  
