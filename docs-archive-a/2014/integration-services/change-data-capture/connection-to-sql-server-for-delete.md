---
title: Connexion à SQL Server pour la suppression | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 030b10c2-6b88-4c2c-bf67-22994be25a60
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5f069f7686e8b6fa9176f92c9e2f47be5f2c71a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602266"
---
# <a name="connection-to-sql-server-for-delete"></a><span data-ttu-id="fda09-102">Connexion à SQL Server pour la suppression</span><span class="sxs-lookup"><span data-stu-id="fda09-102">Connection to SQL Server for Delete</span></span>
  <span data-ttu-id="fda09-103">Lorsqu’une connexion sans rôle de base de données qui inclut l’autorisation d’accès en écriture (par exemple le rôle **db_owner** ) à la base de données MSXDBCDC tente de supprimer une instance Oracle CDC, la boîte de dialogue Connexion à SQL Server s’affiche.</span><span class="sxs-lookup"><span data-stu-id="fda09-103">When a login without a database role that includes write permission (for example the **db_owner** role) to the MSXDBCDC database attempts to delete an Oracle CDC instance, the Connect to SQL Server dialog box is displayed.</span></span>  
  
 <span data-ttu-id="fda09-104">Dans cette boîte de dialogue, vous devez entrer les informations d’identification pour une connexion qui a l’autorisation d’accès en écriture à la base de données MSXDBCDC, notamment le rôle de base de données **db_owner** pour supprimer l’instance Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="fda09-104">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role to delete the Oracle CDC instance.</span></span>  
  
 <span data-ttu-id="fda09-105">Dans la boîte de dialogue Connexion à SQL Server, entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="fda09-105">Enter the following information in the Connect to SQL Server dialog box.</span></span>  
  
 <span data-ttu-id="fda09-106">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="fda09-106">**Server Name**</span></span>  
 <span data-ttu-id="fda09-107">Tapez le nom du serveur où se trouve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fda09-107">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="fda09-108">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="fda09-108">**Authentication**</span></span>  
 <span data-ttu-id="fda09-109">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="fda09-109">Select one of the following:</span></span>  
  
-   <span data-ttu-id="fda09-110">**Authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="fda09-110">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="fda09-111">**Authentification SQL Server**: Si vous sélectionnez cette option, vous devez taper **l’identifiant** et le **mot de passe** de l’utilisateur dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="fda09-111">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="fda09-112">**Options**</span><span class="sxs-lookup"><span data-stu-id="fda09-112">**Options**</span></span>  
 <span data-ttu-id="fda09-113">Cliquez sur la flèche pour afficher les options disponibles à configurer.</span><span class="sxs-lookup"><span data-stu-id="fda09-113">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="fda09-114">Vous pouvez choisir de conserver ces options avec leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="fda09-114">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="fda09-115">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="fda09-115">The available options are:</span></span>  
  
-   <span data-ttu-id="fda09-116">**Délai de connexion**: Tapez le délai (en secondes) pendant lequel le programme attend une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant de générer une erreur de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="fda09-116">**Connection Timeout**: Type the time (in seconds) the program waits for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection to be established before producing a timeout error.</span></span> <span data-ttu-id="fda09-117">La valeur par défaut est **15**.</span><span class="sxs-lookup"><span data-stu-id="fda09-117">The default value is **15**.</span></span>  
  
-   <span data-ttu-id="fda09-118">**Délai d’exécution**: Tapez le délai (en secondes) pendant lequel le programme attend la fin d’exécution d’une commande SQL avant de générer une erreur de délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="fda09-118">**Execution Timeout**: Type the time (in seconds) that the program waits for SQL command execution to finish before producing a timeout error.</span></span> <span data-ttu-id="fda09-119">La valeur par défaut est **30**.</span><span class="sxs-lookup"><span data-stu-id="fda09-119">The default value is **30**.</span></span>  
  
-   <span data-ttu-id="fda09-120">**Chiffrer la connexion**: Sélectionnez **Chiffrer la connexion** pour garantir que la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] établie est chiffrée afin d’assurer la protection des données.</span><span class="sxs-lookup"><span data-stu-id="fda09-120">**Encrypt Connection**: Select **Encrypt Connection** to ensure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection that being established is encrypted to guarantee privacy.</span></span>  
  
-   <span data-ttu-id="fda09-121">**Avancé**: Cliquez sur **Avancé** et tapez toutes les propriétés de connexion supplémentaires dans la boîte de dialogue Propriétés avancées de connexion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="fda09-121">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda09-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fda09-122">See Also</span></span>  
 [<span data-ttu-id="fda09-123">Autorisations de connexion SQL Server nécessaires pour le service CDC</span><span class="sxs-lookup"><span data-stu-id="fda09-123">SQL Server Connection Required Permissions for the CDC Service</span></span>](sql-server-connection-required-permissions-for-the-cdc-service.md)  
  
  
