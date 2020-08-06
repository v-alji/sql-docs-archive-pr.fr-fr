---
title: Création d’applications avec SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611032"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="5a25f-102">Génération d'applications avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="5a25f-103">Lors du développement d'une application qui utilise la bibliothèque [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, plusieurs facteurs entrent en jeu.</span><span class="sxs-lookup"><span data-stu-id="5a25f-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="5a25f-104">Les rubriques de cette section décrivent ces facteurs, notamment la mise à niveau de MDAC vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client et l'utilisation des fichiers de bibliothèque et d'en-tête [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ; par ailleurs, elles fournissent une vue d'ensemble des différentes chaînes de connexion qui peuvent être utilisées avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a25f-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5a25f-105">In This Section</span></span>  
 [<span data-ttu-id="5a25f-106">Installation de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-107">Décrit l'installation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, les emplacements auxquels les différents composants sont installés et la désinstallation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="5a25f-108">Composants de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-109">Discute des composants de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, y compris les fichiers de bibliothèque, de ressources, d'aide et d'en-tête.</span><span class="sxs-lookup"><span data-stu-id="5a25f-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="5a25f-110">Utilisation de mots clés de chaîne de connexion avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-111">Discute des différents types de chaînes de connexion qui peuvent être utilisés lors de la connexion à une base de données par le biais de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="5a25f-112">Utilisation des fichiers bibliothèques et de l'en-tête SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="5a25f-113">Discute de la façon d'utiliser les fichiers de bibliothèque et d'en-tête [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client dans une application.</span><span class="sxs-lookup"><span data-stu-id="5a25f-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="5a25f-114">Mise à jour d'une application vers SQL Server Native Client à partir de MDAC</span><span class="sxs-lookup"><span data-stu-id="5a25f-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="5a25f-115">Discute des différences entre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client et MDAC, et des facteurs à prendre en compte lors d'une mise à niveau de MDAC vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="5a25f-116">Mise à jour d’une application à partir de SQL Server Native Client 2005</span><span class="sxs-lookup"><span data-stu-id="5a25f-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="5a25f-117">Discute des facteurs à prendre en compte lors d'une mise à niveau de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client vers [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client dans [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a25f-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="5a25f-118">Utilisation d'ADO avec SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-119">Discute de la façon dont ADO peut utiliser [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client pour accéder aux fonctionnalités [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et les utiliser.</span><span class="sxs-lookup"><span data-stu-id="5a25f-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="5a25f-120">Stratégies de prise en charge pour SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-121">Discute des façons dont différents composants d'accès aux données peuvent être utilisés avec différentes version de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="5a25f-122">Connexion à une base de données Azure SQL à l’aide de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5a25f-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="5a25f-123">Explique comment se connecter à une [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] à l'aide de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="5a25f-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a25f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a25f-124">See Also</span></span>  
 <span data-ttu-id="5a25f-125">[Programmation SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="5a25f-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="5a25f-126">[Rubriques de procédures relatives à ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="5a25f-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="5a25f-127">Rubriques de procédures liées à OLE DB</span><span class="sxs-lookup"><span data-stu-id="5a25f-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
