---
title: Guide pratique pour utiliser des services CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604087"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="697a0-102">Procédure : utiliser des services de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="697a0-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="697a0-103">Cette procédure décrit comment utiliser la console de configuration du service de capture de données modifiées pour préparer une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en vue de l'utilisation des services de capture de données modifiées Oracle et de la création d'un service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="697a0-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="697a0-104">Pour utiliser des services de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="697a0-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="697a0-105">Dans le menu **Démarrer** , sélectionnez **Configuration du service de capture de données modifiées pour Oracle**.</span><span class="sxs-lookup"><span data-stu-id="697a0-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="697a0-106">Dans le volet gauche, sélectionnez **Services de capture de données modifiées locaux** (au niveau de la racine).</span><span class="sxs-lookup"><span data-stu-id="697a0-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="697a0-107">Vous effectuez l'une des deux tâches suivantes ou les deux :</span><span class="sxs-lookup"><span data-stu-id="697a0-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="697a0-108">**Préparer SQL Server**</span><span class="sxs-lookup"><span data-stu-id="697a0-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="697a0-109">Sélectionnez cette option dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="697a0-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="697a0-110">Vous pouvez également cliquer avec le bouton droit sur **Services de capture de données modifiées locaux** et sélectionner **Préparer SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="697a0-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="697a0-111">La boîte de dialogue Préparation d'une l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la capture de données modifiées Oracle s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="697a0-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="697a0-112">Pour préparer l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les services de capture de données modifiées Oracle, la connexion doit avoir une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le rôle serveur fixe `dbcreator` .</span><span class="sxs-lookup"><span data-stu-id="697a0-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="697a0-113">Cette connexion est utilisée pour créer la base de données MSXDBCDC requise pour ajouter des services de capture de données modifiées Oracle et, ultérieurement, des instances Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="697a0-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="697a0-114">Pour plus d'informations sur l'utilisation de cette boîte de dialogue, consultez [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="697a0-115">Pour plus d’informations sur l’activation d’une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la capture de données modifiées, consultez [Procédure : préparer SQL Server pour la capture de données modifiées](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="697a0-116">**Créer un service de capture de données modifiées**</span><span class="sxs-lookup"><span data-stu-id="697a0-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="697a0-117">Cliquez sur **Nouveau service** dans le volet **Actions** à droite de la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="697a0-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="697a0-118">Vous pouvez également cliquer avec le bouton droit sur **Services de capture de données modifiées locaux** et sélectionner **Nouveau service**.</span><span class="sxs-lookup"><span data-stu-id="697a0-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="697a0-119">La boîte de dialogue Nouveau service de capture de données modifiées Oracle s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="697a0-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="697a0-120">Pour plus d'informations sur l'utilisation de cette boîte de dialogue, consultez [Créer et modifier un service de capture de données modifiées Oracle](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="697a0-121">Pour plus d'informations sur la façon de créer ou modifier un service de capture de données modifiées, consultez [Procédure : créer et modifier un service de capture de données modifiées](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="697a0-122">La connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée par le service de capture de données modifiées Oracle doit être membre du rôle serveur fixe `public` ; aucun autre privilège n'est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="697a0-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="697a0-123">Toutefois, pour créer le service de capture de données modifiées Oracle, la connexion doit avoir l’autorisation d’écriture dans la base de données MSXDBCDC, par exemple le rôle de base de données **db_owner** doit être assigné à la connexion.</span><span class="sxs-lookup"><span data-stu-id="697a0-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="697a0-124">Lorsqu'une connexion sans autorisation d'écriture sur la base de données MSXDBDCDC tente de créer une instance Oracle CDC un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="697a0-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="697a0-125">Cliquez sur **OK** dans cette boîte de dialogue pour afficher la boîte de dialogue Connexion à SQL Server.</span><span class="sxs-lookup"><span data-stu-id="697a0-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="697a0-126">Pour plus d’informations sur la façon d’entrer des informations d’identification pour une connexion ayant l’autorisation d’écriture dans la base de données MSXDBCDC, tel le rôle de base de données **db_owner** , consultez [Créer et modifier un service de capture de données modifiées Oracle](create-and-edit-an-oracle-cdc-service.md) et [Connexion à SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="697a0-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697a0-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="697a0-127">See Also</span></span>  
 [<span data-ttu-id="697a0-128">Utiliser les services CDC</span><span class="sxs-lookup"><span data-stu-id="697a0-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
