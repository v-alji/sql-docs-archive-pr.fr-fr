---
title: Accéder à la console CDC Designer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- accMsDes
ms.assetid: b168c64e-c1b5-42d4-a92a-84de1dd0324e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4f6e4df0a514cb29e36bcd1270b2537dc3ba68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708560"
---
# <a name="access-the-cdc-designer-console"></a><span data-ttu-id="62b82-102">Accéder à la console du concepteur CDC</span><span class="sxs-lookup"><span data-stu-id="62b82-102">Access the CDC Designer Console</span></span>
  <span data-ttu-id="62b82-103">Vous pouvez accéder à la console du concepteur CDC à partir de l'ordinateur sur lequel vous avez installé la console.</span><span class="sxs-lookup"><span data-stu-id="62b82-103">You can access the CDC Designer Console from the computer where you installed the console.</span></span> <span data-ttu-id="62b82-104">Pour plus d'informations sur l'installation, consultez Installation.</span><span class="sxs-lookup"><span data-stu-id="62b82-104">For more information about installation, see Installation.</span></span>  
  
 <span data-ttu-id="62b82-105">Lorsque vous ouvrez la console du concepteur CDC, la boîte de dialogue Connexion à SQL Server s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="62b82-105">When you open the CDC Designer Console, the Connect to SQL Server dialog box opens.</span></span>  
  
 <span data-ttu-id="62b82-106">La connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui accède au concepteur CDC doit avoir les autorisations UPDATE sur la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="62b82-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that accesses the CDC Designer must have UPDATE permissions on the MSXDBCDC database.</span></span> <span data-ttu-id="62b82-107">En outre, la connexion doit également disposer du rôle serveur fixe `dbcreator` pour créer des instances Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="62b82-107">In addition, the login must also have the `dbcreator` fixed-server role to create new Oracle CDC Instances.</span></span> <span data-ttu-id="62b82-108">Il est recommandé que la connexion ait également un accès SELECT aux bases de données CDC qui sont utilisées, sinon l'utilisateur ne peut pas afficher l'état de ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="62b82-108">It is recommended that the login also have SELECT access to the CDC databases being used or the user will not be able to view the state of those databases.</span></span>  
  
 <span data-ttu-id="62b82-109">Dans la boîte de dialogue Connexion à SQL Server, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="62b82-109">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="62b82-110">Nom du serveur</span><span class="sxs-lookup"><span data-stu-id="62b82-110">Server Name</span></span>  
 <span data-ttu-id="62b82-111">Tapez le nom du serveur où se trouve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62b82-111">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="62b82-112">Authentification</span><span class="sxs-lookup"><span data-stu-id="62b82-112">Authentication</span></span>  
 <span data-ttu-id="62b82-113">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="62b82-113">Select one of the following:</span></span>  
  
-   <span data-ttu-id="62b82-114">**Authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="62b82-114">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="62b82-115">**Authentification SQL Server** : si vous sélectionnez cette option, vous devez taper **l’Identifiant** et le **Mot de passe** de l’utilisateur dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="62b82-115">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="62b82-116">La connexion doit avoir un rôle de base de données qui permet l'accès à la base de données MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="62b82-116">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="62b82-117">Il est recommandé que la connexion ait également accès à toutes les bases de données supplémentaires qui sont utilisées, sinon l'utilisateur ne pourra pas afficher les données de ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="62b82-117">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
### <a name="options"></a><span data-ttu-id="62b82-118">Options</span><span class="sxs-lookup"><span data-stu-id="62b82-118">Options</span></span>  
 <span data-ttu-id="62b82-119">Cliquez sur la flèche pour afficher les options disponibles à configurer.</span><span class="sxs-lookup"><span data-stu-id="62b82-119">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="62b82-120">Vous pouvez choisir de conserver ces options avec leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="62b82-120">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="62b82-121">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="62b82-121">The available options are:</span></span>  
  
 <span data-ttu-id="62b82-122">**Délai de connexion**</span><span class="sxs-lookup"><span data-stu-id="62b82-122">**Connection Timeout**</span></span>  
 <span data-ttu-id="62b82-123">Tapez le délai (en secondes) pendant lequel le service de capture de données modifiées pour Oracle attend une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant expiration. La valeur par défaut est **15**.</span><span class="sxs-lookup"><span data-stu-id="62b82-123">Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
 <span data-ttu-id="62b82-124">**Délai d'exécution**</span><span class="sxs-lookup"><span data-stu-id="62b82-124">**Execution Timeout**</span></span>  
 <span data-ttu-id="62b82-125">Tapez le délai (en secondes) pendant lequel le service Windows de capture de données modifiées Oracle attend l'exécution d'une commande avant expiration. La valeur par défaut est **30**.</span><span class="sxs-lookup"><span data-stu-id="62b82-125">Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
 <span data-ttu-id="62b82-126">**Chiffrer la connexion**</span><span class="sxs-lookup"><span data-stu-id="62b82-126">**Encrypt Connection**</span></span>  
 <span data-ttu-id="62b82-127">Sélectionnez **Chiffrer la connexion** pour utiliser une connexion chiffrée dans la communication entre Oracle CDC Service et l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible.
**Avancé** : Cliquez sur **Avancé** et tapez toutes les propriétés de connexion supplémentaires dans la boîte de dialogue Propriétés avancées de connexion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="62b82-127">Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="62b82-128">**Avancée**</span><span class="sxs-lookup"><span data-stu-id="62b82-128">**Advanced**</span></span>  
 <span data-ttu-id="62b82-129">Cliquez sur **Avancé** et tapez toutes les propriétés de connexion supplémentaires dans la boîte de dialogue Propriétés avancées de connexion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="62b82-129">Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
 <span data-ttu-id="62b82-130">Pour plus d’informations sur la boîte de dialogue Propriétés avancées de connexion, consultez [Propriétés avancées de connexion](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="62b82-130">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b82-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="62b82-131">See Also</span></span>  
 [<span data-ttu-id="62b82-132">Autorisations de connexion SQL Server nécessaires pour le concepteur CDC</span><span class="sxs-lookup"><span data-stu-id="62b82-132">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
