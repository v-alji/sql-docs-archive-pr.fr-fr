---
title: Service de capture de données modifiées pour Oracle par Attunity | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 22ec8a5c-9550-4d38-8a4a-485ec3e53ea8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68e68e9edd91bd1d0c718b32e29c3b29f74778c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610816"
---
# <a name="change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="447d8-102">Service de capture de données modifiées pour Oracle par Attunity</span><span class="sxs-lookup"><span data-stu-id="447d8-102">Change Data Capture Service for Oracle by Attunity</span></span>
  <span data-ttu-id="447d8-103">Le service de capture de données modifiées pour Oracle est un service Windows qui analyse les journaux des transactions Oracle et capture les modifications des tables d'intérêt dans des tables de modifications [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="447d8-103">The CDC Service for Oracle is a Windows service that scans Oracle transaction logs and captures changes to Oracle tables of interest into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] change tables.</span></span> <span data-ttu-id="447d8-104">Les tables de modifications SQL dans lesquelles les modifications capturées à partir d'Oracle sont stockées sont du même type que les tables de modifications utilisées dans les fonctionnalités de capture de données modifiées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] natif.</span><span class="sxs-lookup"><span data-stu-id="447d8-104">The SQL change tables where the changes captured from Oracle are stored are the same type of change tables used in the native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Change Data Capture feature.</span></span> <span data-ttu-id="447d8-105">Cela rend la consommation de ces modifications aussi simple que la consommation des modifications apportées aux bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="447d8-105">This makes consuming these changes as easy as consuming changes made to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="447d8-106">Installation</span><span class="sxs-lookup"><span data-stu-id="447d8-106">Installation</span></span>  
 <span data-ttu-id="447d8-107">Le service de capture de données modifiées pour Oracle peut être installé sur un ordinateur Windows pris en charge doté d’un accès à la base de données Oracle source qui est capturée et à l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible où la base de données CDC cible réside.</span><span class="sxs-lookup"><span data-stu-id="447d8-107">The CDC Service for Oracle can be installed on any supported Windows computer with access to the source Oracle database(s) being captured and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the target CDC database resides.</span></span> <span data-ttu-id="447d8-108">Le service de capture de données modifiées n'a pas besoin d'une installation locale de la base de données Oracle ou de la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , uniquement de leurs clients pris en charge.</span><span class="sxs-lookup"><span data-stu-id="447d8-108">The CDC Service does not need a local installation of the Oracle database or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, only their supported clients.</span></span> <span data-ttu-id="447d8-109">Pour plus d'informations sur l'emplacement d'installation des composants de base de données requis, consultez **Composants requis pour la base de données** dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="447d8-109">For information about where to install the required database components, see **Database Prerequisites** in this topic.</span></span>  
  
 <span data-ttu-id="447d8-110">L'installation du service de capture de données modifiées [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour Oracle place l'interface de configuration du service et le programme de service dans l'emplacement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="447d8-110">The installation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC Service for Oracle places the service configuration UI and the service program in the selected location.</span></span> <span data-ttu-id="447d8-111">Le service de capture de données modifiées pour Oracle est configuré séparément à l'aide de la console de configuration du service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="447d8-111">The CDC Service for Oracle is configured separately using the Oracle CDC Service Configuration Console.</span></span> <span data-ttu-id="447d8-112">Pour plus d'informations sur la configuration du service de capture de données modifiées Oracle, consultez [Aide sur le service de capture de données modifiées pour Oracle par Attunity via la touche F1](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="447d8-112">For more information on configuring the Oracle CDC Service, see [Change Data Capture Service for Oracle by Attunity F1 Help](change-data-capture-service-for-oracle-by-attunity-f1-help.md).</span></span>  
  
 <span data-ttu-id="447d8-113">Pour installer le service de capture de données modifiées pour Oracle, exécutez manuellement **AttunityOracleCdcService.msi** à partir du support d’installation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="447d8-113">To install the CDC Service for Oracle, manually run **AttunityOracleCdcService.msi** from the SQL Server installation media.</span></span> <span data-ttu-id="447d8-114">Les packages d’installation pour x86 et x64 se trouvent dans \*\*.\Tools\AttunityCDCOracle \\ \*\* sur le support d’installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="447d8-114">Installation packages for x86 and x64 are located in **.\Tools\AttunityCDCOracle\\** on the SQL Server installation media.</span></span>  
  
 <span data-ttu-id="447d8-115">Le service de capture de données modifiées pour Oracle peut être installé sur un ordinateur Windows pris en charge lorsque [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client est installé ; il n'a pas besoin d'être installé sur le même ordinateur où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible est installé.</span><span class="sxs-lookup"><span data-stu-id="447d8-115">The CDC Service for Oracle can be installed on any supported Windows computer where the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client is installed; it does not need to be installed on the same computer where the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
## <a name="supported-windows-environments"></a><span data-ttu-id="447d8-116">Environnements Windows pris en charge</span><span class="sxs-lookup"><span data-stu-id="447d8-116">Supported Windows Environments</span></span>  
 <span data-ttu-id="447d8-117">Le service de capture de données modifiées pour Oracle par Attunity s'exécute dans les environnements Windows suivants :</span><span class="sxs-lookup"><span data-stu-id="447d8-117">The Change Data Capture Service for Oracle by Attunity can run in the following Windows environments:</span></span>  
  
-   <span data-ttu-id="447d8-118">Windows 8</span><span class="sxs-lookup"><span data-stu-id="447d8-118">Windows 8</span></span>  
  
-   <span data-ttu-id="447d8-119">Windows 7 32 bits (x86) et 64 bits (x64)</span><span class="sxs-lookup"><span data-stu-id="447d8-119">Windows 7 32-bit (x86) and 64-bit (x64)</span></span>  
  
-   <span data-ttu-id="447d8-120">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="447d8-120">Windows Server 2012</span></span>  
  
-   <span data-ttu-id="447d8-121">Windows Server 2008 R2 avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="447d8-121">Windows Server 2008 R2 with Service Pack 1</span></span>  
  
-   <span data-ttu-id="447d8-122">Windows Server 2008 32 bits (x86) et 64 bits (x64) avec Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="447d8-122">Windows Server 2008 32-bit (x86) and 64-bit (x64) with Service Pack 2</span></span>  
  
## <a name="database-prerequisites"></a><span data-ttu-id="447d8-123">Composants requis pour la base de données</span><span class="sxs-lookup"><span data-stu-id="447d8-123">Database Prerequisites</span></span>  
 <span data-ttu-id="447d8-124">Pour utiliser le service de capture de données modifiées pour Oracle, vous devez installer le logiciel [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle.</span><span class="sxs-lookup"><span data-stu-id="447d8-124">To work with the CDC Service for Oracle you must install the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Native Client Oracle software.</span></span> <span data-ttu-id="447d8-125">Il s'agit d'un composant requis qui doit être obtenu auprès d'Oracle et installé avant d'installer le service de capture de données modifiées Oracle.</span><span class="sxs-lookup"><span data-stu-id="447d8-125">This is a prerequisite that should be obtained from Oracle and installed before installing the Oracle CDC Service.</span></span> <span data-ttu-id="447d8-126">En outre, vous devez installer le client SQL Server ODBC à l'aide du programme d'installation de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="447d8-126">Additionally, you need to install the SQL Server ODBC Client using SQL Server Setup.</span></span>  
  
 <span data-ttu-id="447d8-127">Le service de capture de données modifiées pour Oracle prend en charge les versions suivantes :</span><span class="sxs-lookup"><span data-stu-id="447d8-127">The CDC Service for Oracle supports the following versions:</span></span>  
  
### <a name="source-oracle-database"></a><span data-ttu-id="447d8-128">Base de données Oracle source</span><span class="sxs-lookup"><span data-stu-id="447d8-128">Source Oracle Database</span></span>  
  
-   <span data-ttu-id="447d8-129">Base de données Oracle 11x (toute version)</span><span class="sxs-lookup"><span data-stu-id="447d8-129">Oracle Database 11x, any version</span></span>  
  
-   <span data-ttu-id="447d8-130">Base de données Oracle 10x (toute version)</span><span class="sxs-lookup"><span data-stu-id="447d8-130">Oracle Database 10x, any version</span></span>  
  
### <a name="target-sql-server-database"></a><span data-ttu-id="447d8-131">Base de données SQL Server cible</span><span class="sxs-lookup"><span data-stu-id="447d8-131">Target SQL Server Database</span></span>  
 <span data-ttu-id="447d8-132">Pour obtenir une liste des fonctionnalités prises en charge par les éditions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consultez [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="447d8-132">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="running-the-installation-program"></a><span data-ttu-id="447d8-133">Exécution du programme d'installation</span><span class="sxs-lookup"><span data-stu-id="447d8-133">Running the Installation Program</span></span>  
 <span data-ttu-id="447d8-134">Pour installer le service de capture de données modifiées pour Oracle, ouvrez l'Assistant Installation de la plateforme Windows que vous utilisez (32/64 bit) et suivez les instructions à l'écran.</span><span class="sxs-lookup"><span data-stu-id="447d8-134">To install the CDC Service for Oracle, open the installation wizard for the Windows platform you are using (32/64-bit) and follow the directions on the screen.</span></span>  
  
## <a name="uninstalling-change-data-capture-service-for-oracle-by-attunity"></a><span data-ttu-id="447d8-135">Désinstallation du service de capture de données modifiées pour Oracle par Attunity</span><span class="sxs-lookup"><span data-stu-id="447d8-135">Uninstalling Change Data Capture Service for Oracle by Attunity</span></span>  
 <span data-ttu-id="447d8-136">Vous désinstallez le service de capture de données modifiées pour Oracle à l'aide du composant Programmes et fonctionnalités du Panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="447d8-136">You uninstall the CDC Service for Oracle using Control Panel, Programs and Features.</span></span>  
  
 <span data-ttu-id="447d8-137">La désinstallation du service de capture de données modifiées ne supprime pas les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] créées.</span><span class="sxs-lookup"><span data-stu-id="447d8-137">Uninstalling the CDC Service does not delete the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases created.</span></span> <span data-ttu-id="447d8-138">Pour la suppression complète de l'outil, vous devez supprimer la base de données MSXDBCDC et les bases de données CDC spécifiques qui ont été créés dans l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="447d8-138">For complete removal of the tool, you must remove the MSXDBCDC database and the specific CDC databases that were created in the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you worked with.</span></span>  
  
 <span data-ttu-id="447d8-139">Si vous désinstallez le logiciel de service de capture de données modifiées d'un ordinateur et l'installez sur un autre ordinateur, vous devez uniquement fournir les définitions suivantes :</span><span class="sxs-lookup"><span data-stu-id="447d8-139">If you uninstall the CDC Service software from one machine and install it on another computer, you only need to provide the following definitions:</span></span>  
  
-   <span data-ttu-id="447d8-140">Compte de service</span><span class="sxs-lookup"><span data-stu-id="447d8-140">Service account</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="447d8-141">Chaîne de connexion et informations d’identification</span><span class="sxs-lookup"><span data-stu-id="447d8-141">connect string and credentials</span></span>  
  
-   <span data-ttu-id="447d8-142">Mot de passe principal</span><span class="sxs-lookup"><span data-stu-id="447d8-142">The master password</span></span>  
  
 <span data-ttu-id="447d8-143">Toutes les autres définitions sont stockées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et sont fournies par l'installation précédente sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="447d8-143">All the other definitions are stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and are available from the previous installation on another computer.</span></span>  
  
## <a name="in-this-documentation"></a><span data-ttu-id="447d8-144">Dans cette documentation</span><span class="sxs-lookup"><span data-stu-id="447d8-144">In This Documentation</span></span>  
  
-   [<span data-ttu-id="447d8-145">Architecture système du service de capture de données modifiées pour Oracle par Attunity</span><span class="sxs-lookup"><span data-stu-id="447d8-145">Change Data Capture Service for Oracle by Attunity System Architecture</span></span>](change-data-capture-service-for-oracle-by-attunity-system-architecture.md)  
  
-   [<span data-ttu-id="447d8-146">Service de capture de données modifiées Oracle</span><span class="sxs-lookup"><span data-stu-id="447d8-146">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
-   [<span data-ttu-id="447d8-147">Aide sur le service de capture de données modifiées pour Oracle par Attunity via la touche F1</span><span class="sxs-lookup"><span data-stu-id="447d8-147">Change Data Capture Service for Oracle by Attunity F1 Help</span></span>](change-data-capture-service-for-oracle-by-attunity-f1-help.md)  
  
-   [<span data-ttu-id="447d8-148">Service de capture de données modifiées pour Oracle par Attunity : rubrique Procédures</span><span class="sxs-lookup"><span data-stu-id="447d8-148">Change Data Capture Service for Oracle by Attunity How to Guide</span></span>](change-data-capture-service-for-oracle-by-attunity-how-to-guide.md)  
  
## <a name="see-also"></a><span data-ttu-id="447d8-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="447d8-149">See Also</span></span>  
 [<span data-ttu-id="447d8-150">Utilisation du service de capture de données modifiées Oracle</span><span class="sxs-lookup"><span data-stu-id="447d8-150">Working with the Oracle CDC Service</span></span>](working-with-the-oracle-cdc-service.md)  
  
  
