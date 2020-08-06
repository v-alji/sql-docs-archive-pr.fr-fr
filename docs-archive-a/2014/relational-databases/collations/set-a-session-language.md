---
title: Définir une langue de session | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614656"
---
# <a name="set-a-session-language"></a><span data-ttu-id="87a44-102">Définir une langue de session</span><span class="sxs-lookup"><span data-stu-id="87a44-102">Set a Session Language</span></span>
  <span data-ttu-id="87a44-103">La langue de la session permet de définir le mode d'affichage des éléments suivants sur le serveur, en fonction des préférences linguistiques et culturelles :</span><span class="sxs-lookup"><span data-stu-id="87a44-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="87a44-104">Langue utilisée pour les messages d'erreur et autres messages système.</span><span class="sxs-lookup"><span data-stu-id="87a44-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="87a44-105">gère plusieurs copies de tous les messages d'erreur et système dans toutes les langues dans lesquelles [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est disponible.</span><span class="sxs-lookup"><span data-stu-id="87a44-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="87a44-106">Ces messages peuvent être affichés à l'aide de la vue catalogue [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) .</span><span class="sxs-lookup"><span data-stu-id="87a44-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="87a44-107">Lorsque vous installez une version localisée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ces messages système sont traduits pour la version linguistique installée.</span><span class="sxs-lookup"><span data-stu-id="87a44-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="87a44-108">Par défaut, vous disposez également de l'ensemble des messages en anglais.</span><span class="sxs-lookup"><span data-stu-id="87a44-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="87a44-109">De plus, vous pouvez ajouter des messages définis par l’utilisateur dans une langue spécifique à l’aide de [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87a44-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="87a44-110">Format des données de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="87a44-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="87a44-111">Noms des jours et des mois, y compris les abréviations.</span><span class="sxs-lookup"><span data-stu-id="87a44-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="87a44-112">Premier jour de la semaine.</span><span class="sxs-lookup"><span data-stu-id="87a44-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="87a44-113">Données de devise.</span><span class="sxs-lookup"><span data-stu-id="87a44-113">Currency data.</span></span>  
  
 <span data-ttu-id="87a44-114">33 langues sont disponibles dans le cadre des paramètres de session.</span><span class="sxs-lookup"><span data-stu-id="87a44-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="87a44-115">Pour obtenir la liste des langues, consultez [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87a44-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="87a44-116">Définition de la langue de session à partir du serveur</span><span class="sxs-lookup"><span data-stu-id="87a44-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="87a44-117">Pour définir la langue de la session à partir du serveur, utilisez [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="87a44-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="87a44-118">Définition de la langue de session à partir du client</span><span class="sxs-lookup"><span data-stu-id="87a44-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="87a44-119">La langue de la session peut être définie côté client via OLE DB, ODBC ou ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="87a44-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="87a44-120">Pour OLE DB, utilisez la propriété SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="87a44-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="87a44-121">Pour plus d’informations, consultez [Propriétés d’initialisation et d’autorisation](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="87a44-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="87a44-122">Pour ODBC, utilisez le mot clé Language.</span><span class="sxs-lookup"><span data-stu-id="87a44-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="87a44-123">Pour plus d’informations, consultez [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="87a44-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="87a44-124">Pour ADO.NET, utilisez le paramètre **Current Language** de l'objet **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="87a44-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="87a44-125">Pour plus d'informations, consultez la documentation du Kit de développement logiciel (SDK) de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="87a44-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
