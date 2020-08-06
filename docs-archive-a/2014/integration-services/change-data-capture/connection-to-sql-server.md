---
title: Connexion à SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5bb582f9-68d3-4c1e-ab02-6fc16807f1a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6639118b3bd531e5cece8899eb0d68e00e566186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602267"
---
# <a name="connection-to-sql-server"></a><span data-ttu-id="67443-102">Connexion à SQL Server</span><span class="sxs-lookup"><span data-stu-id="67443-102">Connection to SQL Server</span></span>
  <span data-ttu-id="67443-103">Quand une connexion sans rôle de base de données qui inclut l’autorisation d’accès en écriture (par exemple le rôle **db_owner** ) à la base de données MSXDBCDC tente de créer une instance Oracle CDC, la boîte de dialogue Connexion à SQL Server s’affiche.</span><span class="sxs-lookup"><span data-stu-id="67443-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to create an Oracle CDC instanced, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="67443-104">Dans cette boîte de dialogue, vous devez entrer les informations d’identification pour une connexion qui dispose d’une autorisation d’accès en écriture à la base de données MSXDBCDC (tel est notamment le cas du rôle de base de données **db_owner** ) pour créer l’instance Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="67443-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to create the new Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="67443-105">Dans la boîte de dialogue Connexion à SQL Server, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="67443-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="67443-106">Nom du serveur</span><span class="sxs-lookup"><span data-stu-id="67443-106">Server Name</span></span>  
 <span data-ttu-id="67443-107">Tapez le nom du serveur où se trouve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67443-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="67443-108">Authentication</span><span class="sxs-lookup"><span data-stu-id="67443-108">Authentication</span></span>  
 <span data-ttu-id="67443-109">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="67443-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="67443-110">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="67443-110">Windows Authentication</span></span>  
  
-   <span data-ttu-id="67443-111">**Authentification SQL Server**: Si vous sélectionnez cette option, vous devez taper **l’identifiant** et le **mot de passe** de l’utilisateur dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="67443-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
### <a name="options"></a><span data-ttu-id="67443-112">Options</span><span class="sxs-lookup"><span data-stu-id="67443-112">Options</span></span>  
 <span data-ttu-id="67443-113">Cliquez sur la flèche pour afficher les options disponibles à configurer.</span><span class="sxs-lookup"><span data-stu-id="67443-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="67443-114">Vous pouvez choisir de conserver ces options avec leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="67443-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="67443-115">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="67443-115">The available options are:</span></span>  
  
-   <span data-ttu-id="67443-116">**Délai de connexion**: Tapez le délai (en secondes) pendant lequel le programme attend une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant de générer une erreur de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="67443-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="67443-117">La valeur par défaut est **15**.</span><span class="sxs-lookup"><span data-stu-id="67443-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="67443-118">**Délai d’exécution**: Tapez le délai (en secondes) pendant lequel le programme attend la fin d’exécution d’une commande SQL avant de générer une erreur de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="67443-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="67443-119">La valeur par défaut est **30**.</span><span class="sxs-lookup"><span data-stu-id="67443-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="67443-120">**Chiffrer la connexion**: Sélectionnez **Chiffrer la connexion** pour garantir que la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] établie est chiffrée afin d’assurer la protection des données.</span><span class="sxs-lookup"><span data-stu-id="67443-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="67443-121">**Avancé**: Cliquez sur **Avancé** et tapez toutes les propriétés de connexion supplémentaires dans la boîte de dialogue Propriétés avancées de connexion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="67443-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67443-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67443-122">See Also</span></span>  
 [<span data-ttu-id="67443-123">Autorisations de connexion SQL Server nécessaires pour le service CDC</span><span class="sxs-lookup"><span data-stu-id="67443-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
