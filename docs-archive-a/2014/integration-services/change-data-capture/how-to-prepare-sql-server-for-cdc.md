---
title: Guide pratique pour préparer SQL Server pour CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a327fa18-58f4-4e69-bb87-44faf47e20ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fbd285faaa55a28ad82beb673fa783570809bd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694667"
---
# <a name="how-to-prepare-sql-server-for-cdc"></a><span data-ttu-id="abd3f-102">Procédure : préparer SQL Server pour la capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="abd3f-102">How to Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="abd3f-103">Le service de capture de données modifiées Oracle requiert que toutes les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cibles contiennent la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="abd3f-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="abd3f-104">Vous créez cette base de données à l'aide de l'action Préparer SQL Server dans la console de configuration du service de capture de données modifiées. Cette tâche n'est effectuée qu'une seule fois pour chaque instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible.</span><span class="sxs-lookup"><span data-stu-id="abd3f-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="abd3f-105">La section suivante décrit comment préparer une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la capture de données modifiées Oracle à l'aide de la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="abd3f-105">The following describes how to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database for Oracle Change Data Capture using the CDC Service Configuration Console.</span></span> <span data-ttu-id="abd3f-106">Ce processus crée la base de données MSXDBCDC et définit les tables requises, les procédures stockées et autres artefacts nécessaires.</span><span class="sxs-lookup"><span data-stu-id="abd3f-106">This process creates the MSXDBCDC database and defines the required tables, stored procedures, and other required artifacts.</span></span>  
  
 <span data-ttu-id="abd3f-107">La préparation de SQL Server pour la capture de données modifiées Oracle est effectuée par l'administrateur de service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="abd3f-107">Preparing the SQL Server for Oracle CDC is done by the Oracle CDC Service Administrator.</span></span> <span data-ttu-id="abd3f-108">Pour plus d’informations sur le rôle d’administrateur de service de capture de données modifiées, consultez [rôles d’utilisateur pour change Data Capture service pour Oracle par Attunity](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="abd3f-108">For more information about the CDC Service Administrator role, see [User Roles for Change Data Capture Service for Oracle by Attunity](user-roles.md).</span></span>  
  
### <a name="to-enable-sql-server-for-cdc"></a><span data-ttu-id="abd3f-109">Pour activer SQL Server pour la capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="abd3f-109">To enable SQL Server for CDC</span></span>  
  
1.  <span data-ttu-id="abd3f-110">Dans le menu **Démarrer** , sélectionnez **Configuration du service de capture de données modifiées pour Oracle**.</span><span class="sxs-lookup"><span data-stu-id="abd3f-110">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="abd3f-111">Dans le volet gauche, sélectionnez **Service sde capture de données modifiées locaux** , puis dans le volet **Actions** , cliquez sur **Préparer SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="abd3f-111">From the left pane, select **Local CDC Services** then from the **Actions** pane, click **Prepare SQL Server**.</span></span>  
  
     <span data-ttu-id="abd3f-112">Vous pouvez également cliquer avec le bouton droit sur **Services de capture de données modifiées locaux** et sélectionner **Préparer SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="abd3f-112">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
3.  <span data-ttu-id="abd3f-113">Entrez les informations nécessaires dans la boîte de dialogue Préparation d'une instance SQL Server pour la capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="abd3f-113">Enter the required information in the Preparing SQL Server Instance for Oracle CDC dialog box.</span></span> <span data-ttu-id="abd3f-114">Pour plus d'informations sur la façon d'entrer les informations nécessaires dans cette boîte de dialogue, consultez [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="abd3f-114">For information on how to enter the required information into this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span>  
  
     <span data-ttu-id="abd3f-115">Pour préparer l'instance SQL Server pour la capture de données modifiées Oracle, la connexion doit avoir l'autorisation d'écriture dans la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="abd3f-115">To Prepare the SQL Server instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="abd3f-116">Entrez les informations d'identification pour une connexion qui a l'autorisation d'écriture dans la base de données MSXDBCDC, telle qu'un membre du rôle `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="abd3f-116">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
 <span data-ttu-id="abd3f-117">**Remarque**: Vous pouvez cliquer sur **Afficher le script** pour afficher une version en lecture seule du script d’installation.</span><span class="sxs-lookup"><span data-stu-id="abd3f-117">**Note**: You can click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="abd3f-118">Un administrateur système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut copier ce script dans la console de gestion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en vue de le modifier et de l'exécuter, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="abd3f-118">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Console to edit and execute it, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abd3f-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abd3f-119">See Also</span></span>  
 [<span data-ttu-id="abd3f-120">Préparer SQL Server pour CDC</span><span class="sxs-lookup"><span data-stu-id="abd3f-120">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
